---
name: bootstrap-5-3
description: Build, modify, debug, and customize Bootstrap 5.3 interfaces in HTML, CSS, Sass, JavaScript, and common build tools. Use when a task involves Bootstrap 5.3 components, grid/layout, utilities, responsive behavior, accessibility markup, theming, Sass customization, JavaScript plugins, or Bootstrap installation with npm, Vite, Webpack, Parcel, Bun, Composer, NuGet, RubyGems, or Yarn.
---

# Bootstrap 5.3

Use Bootstrap 5.3 conventions and the bundled reference before writing or changing code.

## Workflow

1. Inspect the project's existing Bootstrap version, build tool, and local conventions.
2. Prefer Bootstrap classes and documented data attributes over custom CSS or handwritten JavaScript where they cover the requirement.
3. Preserve semantic HTML, keyboard operation, focus management, labels, and ARIA relationships. Include Bootstrap JavaScript when using interactive components.
4. For Sass changes, override variables before importing the relevant Bootstrap Sass files; use the Utilities API for generated utilities.
5. Test responsive breakpoints and interactive behavior after implementation.

## Reference

Read `references/bootstrap_5_3.md` only for the relevant topic. It contains 672 sourced Bootstrap 5.3 snippets and may contain escaped headings (`\###`) and HTML entities.

Search it with `rg` before reading a section:

```powershell
rg -n -i -C 3 'carousel|toast|modal' references/bootstrap_5_3.md
rg -n -i -C 3 'sass|variables|utilities api|theme' references/bootstrap_5_3.md
rg -n -i -C 3 'vite|webpack|parcel|npm|bun' references/bootstrap_5_3.md
rg -n -i -C 3 'navbar|grid|forms|accessibility' references/bootstrap_5_3.md
```

Normalize copied snippets as needed: remove the leading backslash before Markdown headings and decode entities such as `&#x20;` into spaces. Keep the Bootstrap API, class names, and attribute relationships intact.
