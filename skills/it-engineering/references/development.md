# Software Development

## Writing code
- Clarify inputs, outputs, constraints, and the target language/framework/version before writing anything non-trivial.
- Follow the existing project's conventions (style, structure, libraries) over personal preference.
- Handle errors explicitly; validate input at boundaries; no silent `except: pass`.
- Prefer simple, readable solutions; avoid premature abstraction.
- Include how to run it and, for non-trivial logic, tests.
- Never hard-code secrets; use env vars or a secret manager.

## Debugging method
1. Reproduce reliably (minimal input, exact steps, environment versions)
2. Read the full error and stack trace; find the first frame in the user's code
3. Form a hypothesis; add targeted logging or use a debugger; bisect (`git bisect`) for regressions
4. Fix the root cause, not the symptom; add a regression test
5. Check for the same bug pattern elsewhere

## Code review checklist
- **Correctness**: edge cases (empty, null, large, unicode, time zones, concurrency), off-by-one, error paths
- **Security**: injection (SQL, shell, XSS), authz checks on every endpoint, secrets in code, unsafe deserialization, SSRF, path traversal, dependency vulnerabilities
- **Performance**: N+1 queries, unbounded loops/memory, missing indexes, blocking I/O in async code
- **Reliability**: timeouts and retries with backoff on network calls, idempotency, resource cleanup
- **Maintainability**: naming, function size, duplication, tests, docs for non-obvious decisions
Report findings ranked by severity with file:line and a concrete fix.

## Shell scripting
```bash
#!/usr/bin/env bash
set -euo pipefail
IFS=$'\n\t'
```
Quote variables (`"$var"`), check required tools (`command -v jq >/dev/null || { echo "jq required"; exit 1; }`), support `--dry-run` for destructive scripts, log what is being done, and make scripts idempotent. Validate with `shellcheck`.

## Git
- Small, focused commits with meaningful messages; branch per feature/fix
- Never force-push shared branches; never commit secrets (if leaked: rotate the secret, then clean history)

## CI/CD
- Pipeline: lint → test → build → security scan → deploy to staging → smoke tests → production (with approval for critical systems)
- Reproducible builds (lockfiles, pinned base images), artefacts built once and promoted
- Fast rollback path (previous artefact / blue-green / canary)
- Secrets from the CI secret store; least-privilege deploy credentials

## Databases
- Use migrations under version control; backward-compatible changes for zero-downtime deploys (expand → migrate → contract)
- `EXPLAIN ANALYZE` slow queries; index for WHERE/JOIN/ORDER BY patterns; avoid `SELECT *` in hot paths
- Run destructive queries inside a transaction and check affected row count first; back up before bulk changes
