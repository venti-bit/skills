# System Administration

## Linux essentials
- Services: `systemctl status|start|stop|restart|enable svc`, logs via `journalctl -u svc -f`
- Users & permissions: least privilege, `sudo` via groups, no shared accounts; `chmod`/`chown` precisely, never `chmod 777`
- Packages: keep updated (`apt`/`dnf`), enable unattended security updates where appropriate
- Logs: configure `logrotate`; ship logs centrally for multi-host setups
- Scheduling: systemd timers or cron (absolute paths, redirect output, lock to avoid overlap with `flock`)

## Security hardening baseline
- SSH: key-only auth, `PermitRootLogin no`, fail2ban or equivalent, non-default exposure behind VPN/bastion if possible
- Firewall: default deny inbound (ufw/firewalld/nftables/security groups), open only needed ports
- TLS everywhere; auto-renew certificates (certbot/ACME) and monitor expiry
- Secrets in a vault/secret manager or env injected at runtime, never in git
- Backups: 3-2-1 rule (3 copies, 2 media, 1 offsite), encrypted, and **regularly test restores**
- Monitoring: CPU, RAM, disk (space + inodes), service health, cert expiry, backup success; alerts with actionable thresholds
- Patch cadence and inventory of what runs where

## Docker
```bash
docker ps -a ; docker logs --tail 200 -f <c> ; docker inspect <c>
docker stats                     # live resource usage
docker system df                 # disk usage by images/containers/volumes
docker image prune -a            # confirm with user — removes unused images
```
Best practices: small base images, non-root user, pinned versions, healthchecks, resource limits, one process per container, config via env, persistent data in volumes.

## Kubernetes
```bash
kubectl get pods -A -o wide
kubectl describe pod <p> -n <ns>        # events: scheduling, probes, OOMKilled
kubectl logs <p> -n <ns> --previous     # logs of crashed container
kubectl get events -n <ns> --sort-by=.lastTimestamp
kubectl top pods -n <ns>
kubectl rollout undo deploy/<d> -n <ns> # rollback (confirm first)
```
Always set requests/limits, readiness/liveness probes, PodDisruptionBudgets for critical apps; use namespaces and RBAC.

## Networking basics
- Subnetting, NAT, VLANs; document IP plan
- DNS: TTLs matter during migrations — lower TTL in advance
- Reverse proxy (nginx/HAProxy/Traefik): test config before reload (`nginx -t && systemctl reload nginx`)

## Windows / Active Directory
- Use Group Policy for configuration at scale; least-privilege admin tiers
- Check replication `repadmin /replsummary`, DC health `dcdiag`
- PowerShell remoting over WinRM with HTTPS; log and audit admin actions
