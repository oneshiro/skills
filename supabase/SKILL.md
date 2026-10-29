---
name: supabase
description: >-
  Build, configure, or debug Supabase backends and client apps. Use for Auth,
  Postgres/database, Realtime, Storage, Edge Functions, REST/API, local CLI
  development, self-hosting, deployment, AI features, RLS, and framework
  quickstarts. Prefer this skill whenever Supabase APIs, CLI, or project layout
  are involved.
---

# Supabase

Confirm the project's Supabase client version, whether work is cloud-hosted or
local (`supabase start`), and which products are in use (Auth, DB, Realtime,
Storage, Functions) before changing code or config.

Official docs: https://supabase.com/docs

## Workflow

1. Read existing env (`NEXT_PUBLIC_SUPABASE_URL`, service/anon keys) and client
   setup; never invent or expose secrets.
2. Prefer official JS/TS clients and framework helpers already used in the repo.
3. For schema/RLS changes, keep migrations reproducible via CLI when the project
   already uses them.
4. Test Auth and RLS with the roles the app actually uses (anon vs authenticated).

## Quick decisions

| Topic | Prefer |
| --- | --- |
| New project / quickstart | Framework guide under Getting Started |
| Login / sessions | Auth guides + existing client helpers |
| Tables / RLS / SQL | Database guides + migrations |
| Live updates | Realtime channels matching existing patterns |
| Files | Storage buckets + policies |
| Serverless logic | Edge Functions |

## References

Read only the matching file; search inside it.

- [references/getting-started.md](references/getting-started.md)
- [references/auth.md](references/auth.md)
- [references/database.md](references/database.md)
- [references/realtime-storage-functions.md](references/realtime-storage-functions.md)
- [references/local-dev-self-hosting.md](references/local-dev-self-hosting.md)
- [references/ai-platform.md](references/ai-platform.md)
- [references/blog-examples-misc.md](references/blog-examples-misc.md)

```bash
rg -n -i -C 3 'rls|policy|auth\.|signIn' references/auth.md references/database.md
rg -n -i -C 3 'supabase start|cli' references/local-dev-self-hosting.md
```

Snippets keep upstream `Source:` links. Reconcile with the installed Supabase
version and current docs before applying.
