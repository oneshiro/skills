---
name: yii
description: >
  Yii 1.1 guide examples and patterns for myASM (PHP 7.0 / Yii 1.1.19).
  Use when writing or reviewing controllers, models, AR/DAO/Query Builder,
  forms, URL rules, auth, caching, migrations, Gii, console commands,
  widgets, i18n, or security code in this Yii 1.x codebase.
  Not for Yii 2/3.
---

# Yii 1.1 (myASM)

Project stack: **PHP 7.0.32**, **Yii 1.1.19**, Bootstrap 4.6.

Use this skill only for **Yii 1.x**. Do not apply Yii 2/3 APIs (`yii\`, ActiveQuery namespaces, etc.).

## How to use

1. Match the task to a topic below.
2. Open [`references/guide-examples.md`](references/guide-examples.md) and search the matching section title or source file name.
3. Prefer patterns already used in `protected/` over inventing new ones.
4. Keep PHP 7.0-compatible syntax (no typed properties, no nullsafe `?->`, no union types).

## Topic map → search keys in `guide-examples.md`

| Task | Search / source keys |
|---|---|
| App / entry / module / component | `basics.application`, `basics.entry`, `basics.module`, `basics.component` |
| Controller / action / filter | `basics.controller`, Filter class, Login and logout |
| View / layout / widget / theme | `basics.view`, Layout view, CTabView, CLinkPager, `topics.theming` |
| ActiveRecord / relations | `database.ar`, `database.arr`, HAS_MANY, HAS_ONE, through |
| DAO / CDbCommand | `database.dao`, bindParam, beginTransaction |
| Query Builder | `database.query-builder`, select/where/join/order/limit |
| Migration / schema | `database.migration`, createTable, addColumn, addForeignKey |
| Forms / models / validation | `form.model`, `form.view`, `form.action`, `form.builder`, Massive Assignment, Validator |
| URL / path format / rules | `topics.url`, URL rule |
| Auth / RBAC | `topics.auth`, authManager, default roles |
| Cache | `caching.overview`, `caching.data`, `caching.fragment`, `caching.page` |
| Console / yiic | `topics.console`, CConsoleCommand, migrate |
| Gii | `topics.gii`, Install Gii |
| i18n | `topics.i18n`, Choice format, plural |
| Security | `topics.security`, SQL injection, bindParam |
| Logging / errors / performance | `topics.logging`, `topics.error`, `topics.performance` |
| Tests / fixtures | `test.overview`, `test.unit`, `test.fixture`, `test.functional` |
| Extensions | `extension.use`, `extension.create`, `extension.integration` |

## myASM conventions

- Controllers live under `protected/controllers/`; models under `protected/models/` (forms) and `protected/models/table/` (AR tables).
- Messages: `protected/messages/{en,th}/`.
- Config: `protected/config/` (`main.php`, `accessRules.php`, `menu.php`).
- Prefer existing Yii helpers (`CHtml`, `CActiveForm`, `Tb*` if already used) over new UI libs.

## Out of scope

- Yii 2 / Yii 3 / Yii rewrite guides
- Changing PHP or framework major version
- Copying entire guide sections into replies — cite the pattern and adapt to local files
