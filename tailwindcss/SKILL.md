---
name: tailwindcss
description: >-
  Style UIs with Tailwind CSS utilities, theme tokens, responsive/dark variants,
  custom styles, Vite/PostCSS/CLI setup, and upgrades (including v3/v4 notes).
  Use when editing className utilities, tailwind.config, @theme, or Tailwind
  build plugins. Prefer this skill over generic CSS advice when Tailwind is in
  the project.
---

# Tailwind CSS

Confirm the major version (v3 vs v4) from `package.json` and config style
(`tailwind.config.*` vs CSS-first `@theme`) before changing setup or class
syntax.

Official docs: https://tailwindcss.com/docs

## Workflow

1. Detect v3 vs v4 and the bundler integration already in use.
2. Prefer utility classes consistent with nearby components; extend theme instead
   of one-off arbitrary values when a token already exists.
3. For upgrades, follow the upgrade guide — do not mix v3 config assumptions
   into a v4 CSS-first project without an explicit migration.

## Quick decisions

| Topic | Prefer |
| --- | --- |
| Install / theme / variants / upgrade | Core |
| Specific utility class APIs | Utilities |
| Historical release notes | Blog (verify against current major) |

## References

- [references/core.md](references/core.md)
- [references/utilities.md](references/utilities.md)
- [references/blog.md](references/blog.md)

```bash
rg -n -i -C 3 '@theme|tailwind.config|upgrade' references/core.md
rg -n -i -C 3 'hover:|sm:|dark:' references/core.md references/utilities.md
```

Snippets keep upstream `Source:` links. Reconcile with the installed Tailwind
major version before applying.
