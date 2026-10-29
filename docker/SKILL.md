---
name: docker
description: >-
  Install, configure, build, run, or troubleshoot Docker Engine, Docker Desktop,
  images, containers, BuildKit, Compose (engine docs), Scout, extensions, and
  Docker AI/sandbox features. Use for Dockerfiles, docker CLI, Desktop install,
  and Engine API reference snippets. Prefer this skill over generic Linux
  container advice when Docker-specific docs apply.
---

# Docker

Identify whether the environment is Docker Desktop, Engine-only, or CI builders
before changing install steps or daemon config. Prefer the project's existing
Dockerfile / Compose / Buildx setup.

Official docs: https://docs.docker.com/

## Workflow

1. Confirm OS, Docker version (`docker version`), and whether Buildx/Compose are
   available.
2. Keep multi-stage builds and base images consistent with the repo unless asked
   to change them.
3. Prefer non-root users and minimal images for production Dockerfiles.
4. Do not expose daemon sockets or bake secrets into image layers.

## Quick decisions

| Topic | Prefer |
| --- | --- |
| First concepts / tutorials | Get Started |
| Daemon / install / Linux Engine | Engine manuals |
| Windows/Mac Desktop | Desktop manuals |
| Dockerfile / BuildKit | Build (+ Compose when multi-service) |
| HTTP Engine API | API reference |
| Language sample apps | Guides |

## References

- [references/get-started.md](references/get-started.md)
- [references/engine.md](references/engine.md)
- [references/desktop.md](references/desktop.md)
- [references/build-compose.md](references/build-compose.md)
- [references/ai-extensions.md](references/ai-extensions.md)
- [references/guides.md](references/guides.md)
- [references/api-reference.md](references/api-reference.md)

```bash
rg -n -i -C 3 'Dockerfile|FROM |BUILDKIT' references/build-compose.md references/get-started.md
rg -n -i -C 3 'install|desktop' references/desktop.md references/engine.md
```

Snippets keep upstream `Source:` links. Reconcile with the installed Docker
version before applying.
