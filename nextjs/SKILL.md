---
name: nextjs
description: >-
  Build, update, debug, or migrate Next.js apps with the App Router or Pages
  Router. Use when working with create-next-app, routing, layouts, Server and
  Client Components, data fetching, caching, Route Handlers, Server Actions,
  middleware, testing (Jest/Playwright/Cypress/Vitest), upgrading/migrating,
  next.config, Turbopack, deployment, or self-hosting. Prefer this skill over
  generic React guidance whenever Next.js file conventions or APIs are involved.
---

# Next.js

Confirm the project's Next.js major version, whether it uses the **App Router**
(`app/`) or **Pages Router** (`pages/`), and how dependencies are installed
before changing code. Keep the project's package manager and existing
conventions unless the user asks to switch.

Official docs: https://nextjs.org/docs

## Workflow

1. Identify router mode (`app/` vs `pages/`) and Next.js version from
   `package.json` / project layout.
2. Prefer App Router patterns for new work unless the repo is Pages-only or the
   user asks otherwise.
3. Preserve Server/Client Component boundaries; add `"use client"` only where
   browser APIs, state, or event handlers require it.
4. Match data-fetching and caching patterns already used in the repo (fetch
   options, `unstable_cache` / cache components, `getStaticProps`, etc.).
5. Run the project's existing test and lint scripts after meaningful changes.

## create-next-app

Bootstrap with the package manager already used in the environment:

```bash
npx create-next-app@latest
pnpm create next-app
yarn create next-app
bun create next-app
```

Use `--example <name>` when a documented template fits (e.g. testing setups).
Prefer TypeScript, App Router, and the project's CSS choice unless told otherwise.

## Quick decisions

| Topic | Prefer |
| --- | --- |
| New routes (App Router) | `app/**/page.tsx`, nested `layout.tsx` |
| API endpoints (App Router) | Route Handlers in `route.ts` |
| Mutations (App Router) | Server Actions when fitting; otherwise Route Handlers |
| Client interactivity | Small Client Components under a Server parent |
| Images | `next/image` (not legacy `next/legacy/image` unless Pages legacy) |
| Config | `next.config.ts` / `next.config.mjs` — read before changing |
| Diagnostics | `npx next info` |

## References (progressive disclosure)

Read only the file that matches the task. Search inside it; do not load every
reference up front.

- Getting started / install / layouts / CSS / deploy:
  [references/getting-started.md](references/getting-started.md)
- App Router guides (auth, caching, PWA, MDX, env, self-hosting, …):
  [references/app-guides.md](references/app-guides.md)
- Testing (Jest, Playwright, Cypress, Vitest, …):
  [references/testing.md](references/testing.md)
- Upgrading and migrating (incl. cache components):
  [references/upgrading-migrating.md](references/upgrading-migrating.md)
- API reference (components, file conventions, functions, config, CLI, adapters, Turbopack):
  [references/api-reference.md](references/api-reference.md)
- Pages Router (routing, data fetching, upgrades, legacy image):
  [references/pages-router.md](references/pages-router.md)
- Compiler architecture and docs contribution notes:
  [references/architecture-community.md](references/architecture-community.md)

Example searches:

```bash
rg -n -i -C 3 'server action|use server' references/app-guides.md
rg -n -i -C 3 'jest|playwright|cypress|vitest' references/testing.md
rg -n -i -C 3 'getStaticProps|getServerSideProps|pages/' references/pages-router.md
rg -n -i -C 3 'next.config|turbopack|middleware' references/api-reference.md
```

Snippets keep their upstream `Source:` links. Treat them as patterns — reconcile
with the installed Next.js version and current docs before applying.
