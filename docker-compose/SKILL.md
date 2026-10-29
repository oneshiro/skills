---
name: docker-compose
description: >-
  Author or debug Docker Compose files and the compose CLI (up, run, ps, pull,
  push, kill, rm, events, extensions, SDK). Use when editing compose.yaml /
  docker-compose.yml, multi-service stacks, or compose CLI flags. Prefer this
  skill for Compose-specific work; use the docker skill for Engine/Desktop/
  Dockerfile topics.
---

# Docker Compose

Confirm Compose file version/format already used in the repo (`compose.yaml` vs
legacy `docker-compose.yml`) and the installed `docker compose` plugin version
before changing syntax.

Official docs: https://docs.docker.com/compose/

## Workflow

1. Read the existing Compose file and `.env` patterns; preserve service names
   and networks the app already depends on.
2. Prefer `docker compose` (V2 plugin) over legacy `docker-compose` unless the
   project documents otherwise.
3. Keep secrets out of committed Compose overrides; use env files or secret
   stores already adopted by the team.

## Quick decisions

| Topic | Prefer |
| --- | --- |
| CLI flags / subcommands | CLI reference |
| Extensions / SDK | Extensions & SDK |
| Building Compose itself / contrib | Building & contributing |

## References

- [references/cli-reference.md](references/cli-reference.md)
- [references/extensions-sdk.md](references/extensions-sdk.md)
- [references/building-contributing.md](references/building-contributing.md)

```bash
rg -n -i -C 3 'compose up|depends_on|services:' references/cli-reference.md
```

Snippets keep upstream `Source:` links. Reconcile with the installed Compose
version before applying.
