# Troubleshooting Playbook

## Quick triage (Linux)
```bash
uptime                          # load average vs CPU count
free -h                         # memory and swap
df -h && df -i                  # disk space and inodes
top -o %CPU   # or htop         # hot processes
dmesg -T | tail -50             # kernel errors, OOM killer, disk I/O errors
journalctl -p err -S "1 hour ago" --no-pager | tail -100
systemctl --failed
ss -tulpn                       # listening ports and owners
```

## Windows triage (PowerShell)
```powershell
Get-Counter '\Processor(_Total)\% Processor Time','\Memory\Available MBytes'
Get-PSDrive -PSProvider FileSystem
Get-Process | Sort-Object CPU -Descending | Select-Object -First 10
Get-WinEvent -LogName System -MaxEvents 50 | Where-Object Level -le 3
Get-Service | Where-Object Status -ne 'Running' | Where-Object StartType -eq 'Automatic'
Get-NetTCPConnection -State Listen
```

## By symptom

| Symptom | Check | Typical causes |
|---|---|---|
| Site unreachable | `ping`, `curl -v https://host`, `dig host`, `traceroute`/`mtr` | DNS, firewall/security group, service down, expired domain |
| TLS errors | `openssl s_client -connect host:443 -servername host` ; check expiry and chain | Expired cert, missing intermediate, wrong SNI, clock skew |
| HTTP 502/504 | Proxy (nginx) error log, upstream health, timeouts | App crashed/slow, wrong upstream port, timeouts too low |
| HTTP 500 | App logs / stack trace | Code bug, failed dependency, missing config/env var |
| Slow app | Latency per layer, DB slow query log, `EXPLAIN`, APM | Missing index, N+1 queries, lock contention, GC, saturation |
| Disk full | `du -xh / --max-depth=1 \| sort -h`, `lsof +L1` (deleted but open files) | Logs without rotation, Docker images/volumes, core dumps |
| High memory / OOM | `dmesg \| grep -i oom`, per-process RSS | Leak, too many workers, missing limits |
| High CPU | `top`, `pidstat`, profiler (`perf`, `py-spy`) | Busy loops, regex backtracking, crypto, crawlers/DDoS |
| Can't SSH | Console access, `sshd -t`, `/var/log/auth.log`, fail2ban | Firewall, key/permissions (`~/.ssh` 700, keys 600), disk full |
| Service won't start | `systemctl status svc`, `journalctl -u svc -b` | Bad config (test with `nginx -t` etc.), port in use, permissions |
| Container restarting | `docker logs`, `kubectl describe pod`, `kubectl logs --previous` | CrashLoop on config, OOMKilled, failed probes, missing secrets |
| Intermittent failures | Correlate timestamps across logs, check one node vs all | Single bad node, DNS TTL, connection pool exhaustion, rate limits |

## Reading logs & stack traces
- Find the **first** error in time, not the loudest; later errors are often consequences.
- In a stack trace, the root cause is usually the innermost "Caused by" / last frame in the user's own code.
- Correlate by request ID / trace ID / timestamp across services; mind time zones (UTC vs local).
- Useful filters: `grep -E "ERROR|FATAL|Exception" app.log | sort | uniq -c | sort -rn | head`

## Network checklist
1. Name resolves to the right IP? (`dig +short`, check `/etc/hosts`)
2. Route exists? (`ip route`, `traceroute`)
3. Port open? (`nc -vz host port`, `Test-NetConnection host -Port 443`)
4. Firewall / security groups / NAT allow it?
5. Service listening on the right interface (0.0.0.0 vs 127.0.0.1)?
6. MTU, proxy, or TLS interception in between?
