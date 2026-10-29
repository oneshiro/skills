---
name: reactjs
description: >-
  Build or refactor React UIs with components, hooks, effects, state, Suspense,
  refs, React DOM APIs, React Compiler, RSC notes, and eslint-plugin-react-hooks.
  Use for learn/tutorial patterns and API reference snippets from react.dev.
  Prefer the nextjs skill when Next.js App/Pages Router conventions dominate.
---

# React

Confirm the React major version and whether the app is client-only, SSR, or RSC
before applying patterns. Prefer hooks and component structure already used in
the repo.

Official docs: https://react.dev/

## Workflow

1. Identify React version and renderer (`react-dom` client vs static).
2. Keep Server/Client boundaries intact in RSC or Next.js apps; add client
   hooks only in Client Components.
3. Follow Rules of Hooks; prefer the project's existing state libraries when
   present.
4. Use React Compiler guidance only when the project already enables it or the
   user asks to adopt it.

## Quick decisions

| Topic | Prefer |
| --- | --- |
| Concepts / tutorials / effects | Learn |
| `useState`, `useEffect`, Suspense, … | Reference — react |
| `createRoot`, `hydrateRoot`, DOM utils | Reference — react-dom |
| Compiler / RSC / hooks eslint | Reference — other |

## References

- [references/learn.md](references/learn.md)
- [references/reference-react.md](references/reference-react.md)
- [references/reference-react-dom.md](references/reference-react-dom.md)
- [references/reference-other.md](references/reference-other.md)
- [references/blog-warnings.md](references/blog-warnings.md)

```bash
rg -n -i -C 3 'useEffect|useState|Suspense' references/reference-react.md references/learn.md
rg -n -i -C 3 'createRoot|hydrateRoot' references/reference-react-dom.md
```

Snippets keep upstream `Source:` links. Reconcile with the installed React
version before applying.
