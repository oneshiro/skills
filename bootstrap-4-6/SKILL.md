---
name: bootstrap-4-6
description: Build or update Bootstrap 4.6 pages when a project must remain on the Bootstrap 4 API. Use for Bootstrap 4.3-to-4.6 updates, not Bootstrap 5 migrations.
---

# Bootstrap 4.6

Use the official Bootstrap 4.6 documentation as the source of truth:
https://getbootstrap.com/docs/4.6/

Before changing a project, identify how Bootstrap is installed and keep that delivery method unless the user requests a change. Update all Bootstrap CDN or package references to `4.6.2`, the final 4.6 release.

For CDN markup, load Bootstrap CSS before application styles. Load jQuery before Bootstrap JavaScript; use `bootstrap.bundle.min.js` when Popper is needed. Preserve the documented SRI and `crossorigin` attributes.

Use Bootstrap 4 data attributes such as `data-toggle` and `data-target`; do not introduce Bootstrap 5 `data-bs-*` attributes. Keep v4-compatible classes and jQuery plugin calls unless the request explicitly includes a v5 migration.

Bootstrap 4 is end-of-life. Honor an explicit 4.6 requirement, but flag the maintenance status when choosing a version for a new project.

Read [references/official-docs.md](references/official-docs.md) before writing Bootstrap-specific markup, dependencies, or component JavaScript.
