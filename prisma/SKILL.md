---
name: prisma
description: >-
  Model schemas, migrate databases, query data, or deploy with Prisma ORM,
  Prisma CLI, Prisma Postgres, Studio, Accelerate, and related guides
  (auth/framework integrations, runtimes, upgrades). Use for schema.prisma,
  Prisma Client, migrate/deploy, and Prisma Postgres. Prefer this skill whenever
  Prisma APIs or project files are involved.
---

# Prisma

Confirm the Prisma package major version, datasource provider, and whether the
project uses Migrate, `db push`, or an external migration tool before editing
`schema.prisma` or generating the client.

Official docs: https://www.prisma.io/docs

## Workflow

1. Read `schema.prisma`, existing migrations, and env (`DATABASE_URL`).
2. Prefer Migrate for shared/production schemas; avoid destructive resets unless
   explicitly requested and safe.
3. Regenerate the client after schema changes (`prisma generate`).
4. Keep connection strings and secrets out of committed files and agent output.

## Quick decisions

| Topic | Prefer |
| --- | --- |
| Schema / Client / Migrate | ORM / CLI / Studio |
| Prisma Postgres ops | Postgres |
| Framework or auth recipes | Guides |
| AI tooling / MCP prompts | AI |
| Narrative tutorials | Blog (verify against current ORM version) |

## References

- [references/guides.md](references/guides.md)
- [references/orm-cli-studio.md](references/orm-cli-studio.md)
- [references/postgres.md](references/postgres.md)
- [references/ai.md](references/ai.md)
- [references/blog.md](references/blog.md)
- [references/other.md](references/other.md)

```bash
rg -n -i -C 3 'model |migrate|PrismaClient' references/orm-cli-studio.md references/guides.md
rg -n -i -C 3 'accelerate|connection' references/postgres.md references/other.md
```

Snippets keep upstream `Source:` links. Reconcile with the installed Prisma
version before applying — blog posts may be outdated.
