# Prisma — Other

Sourced snippets (47 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Quick start: install dependencies and run apps

Source: https://github.com/prisma/web/blob/main/apps/docs/README.md

Installs dependencies across all monorepo workspaces and starts development servers via Turbo. Access the docs application at http://localhost:3001.

```bash
# From repo root: install deps for all workspaces
pnpm install

# Run the docs app (and other apps via Turbo)
pnpm dev
```


--------------------------------

### Install and start application with Bun

Source: https://github.com/prisma/web/blob/main/apps/handbook/content/handbook/component-showcase.mdx

Fenced shell commands showing standard package installation and local development server execution.

```bash
bun install
bun run dev
```


--------------------------------

### Install and initialize Prisma in a project

Source: https://github.com/prisma/web/blob/main/apps/eclipse/content/design-system/components/steps.mdx

Installs the Prisma CLI as a development dependency and initializes the Prisma setup.

```bash
npm install prisma --save-dev
npx prisma init
```


--------------------------------

### Install dependencies and start all apps locally

Source: https://github.com/prisma/web/blob/main/README.md

Execute from the repository root to install all workspace dependencies and run all apps via Turbo concurrently.

```bash
pnpm install
pnpm dev
```


--------------------------------

### Run handbook locally

Source: https://github.com/prisma/web/blob/main/apps/handbook/README.md

Installs dependencies and starts the handbook app dev server on http://localhost:3004/handbook. Requires @prisma/eclipse to be built first.

```bash
pnpm install
pnpm --filter handbook dev
```


--------------------------------

### Example prompt to build and deploy a Bun API

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-compute/deploy.mdx

Concrete example prompt instructing an agent to build a Bun API with an in-memory /todos endpoint and deploy to Prisma Compute.

```text
Build a Bun API with a /todos endpoint backed by an in-memory list as a Prisma Composer app and deploy it to Prisma Compute using `npx prisma@latest`.
```


--------------------------------

### Installing Prisma Client with yarn

Source: https://github.com/prisma/web/blob/main/apps/eclipse/content/design-system/components/codeblock.mdx

Installs the Prisma Client package and generates the client using yarn.

```bash
yarn add @prisma/client
yarn prisma generate
```


--------------------------------

### Build and serve the docs application

Source: https://github.com/prisma/web/blob/main/README.md

Build the production output and start the production server specifically for the docs app.

```bash
pnpm --filter docs build
pnpm --filter docs start
```


--------------------------------

### Initialize project with npx prisma init --prompt

Source: https://github.com/prisma/web/blob/main/apps/site/content/changelog/2025-04-10.mdx

Scaffold a Prisma schema from a natural language prompt and deploy it to a fresh Prisma Postgres instance.

```text
npx prisma init --prompt "An encyclopedia for cats"
```


--------------------------------

### Check PostgreSQL CLI Tools Version

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-postgres/import-from-existing-database-postgresql.mdx

Confirm that local installations of pg_dump, pg_restore, and psql report version 17.x before starting the migration.

```bash
pg_dump --version
pg_restore --version
psql --version
```


--------------------------------

### Install @prisma/eclipse

Source: https://github.com/prisma/web/blob/main/apps/eclipse/content/design-system/index.mdx

Install the Eclipse design system package in your project using pnpm.

```bash
pnpm add @prisma/eclipse
```


--------------------------------

### Install @prisma/client-runtime-utils for prisma-client-js

Source: https://github.com/prisma/web/blob/main/apps/site/content/changelog/2025-11-19.mdx

Install `@prisma/client-runtime-utils` when continuing to use `prisma-client-js` alongside the new `output` generator configuration.

```sh
# for prisma-client-js users only
npm install @prisma/client-runtime-utils
```


--------------------------------

### Installing Prisma Client with npm

Source: https://github.com/prisma/web/blob/main/apps/eclipse/content/design-system/components/codeblock.mdx

Installs the Prisma Client package and runs code generation using npm and npx.

```bash
npm install @prisma/client
npx prisma generate
```


--------------------------------

### Installing Prisma Client with pnpm (Python)

Source: https://github.com/prisma/web/blob/main/apps/eclipse/content/design-system/components/codeblock.mdx

Installs the prisma package via pip and generates the client.

```bash
pip install prisma
prisma generate
```


--------------------------------

### Initialize database and start dev server

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-orm/create-prisma.mdx

Initializes the database and launches the development server in the scaffolded app directory. Export the connection string (`DATABASE_URL` for PostgreSQL or `MONGODB_URL` for MongoDB) in the shell before executing.

```bash
cd my-app
npm run db:init
npm run dev
```


--------------------------------

### Minimal setup and integration for @prisma/eclipse

Source: https://github.com/prisma/web/blob/main/packages/eclipse/ARCHITECTURE.md

Follow sequential steps to integrate @prisma/eclipse: install the package, import the global styles into your root component, extend your Tailwind configuration with the Eclipse preset, and import design system components.

```bash
pnpm add @prisma/eclipse
```

```tsx
import "@prisma/eclipse/styles/globals.css";
```

```ts
import eclipseConfig from "@prisma/eclipse/tailwind.config";

export default {
  presets: [eclipseConfig],
  content: ["./src/**/*.{ts,tsx}"],
};
```

```tsx
import { Button } from "@prisma/eclipse";
```


--------------------------------

### Create a vertical steps timeline with Steps and Step

Source: https://github.com/prisma/web/blob/main/apps/eclipse/content/design-system/components/steps.mdx

Use the `variant="vertical"` prop on both `Steps` and `Step` components to render a vertical timeline layout with connector lines. Ideal for sequential instructions, tutorials, and setup guides.

```tsx
import { Steps, Step } from "@prisma/eclipse";

export function VerticalSteps() {
  return (
    <Steps variant="vertical">
      <Step variant="vertical">
        #### Install dependencies
      </Step>
      <Step variant="vertical">
        #### Configure environment
      </Step>
      <Step variant="vertical">
        #### Start the server
      </Step>
    </Steps>
  );
}
```


--------------------------------

### Installing Prisma Client with pnpm (TypeScript/JavaScript)

Source: https://github.com/prisma/web/blob/main/apps/eclipse/content/design-system/components/codeblock.mdx

Installs the Prisma Client package and generates the client using pnpm.

```bash
pnpm add @prisma/client
pnpm prisma generate
```


--------------------------------

### Chart examples directory layout

Source: https://github.com/prisma/web/blob/main/apps/eclipse/src/components/chart-examples/README.md

File structure organization for chart example components and exports.

```text
chart-examples/
├── README.md                    # This file
├── index.ts                     # Barrel export file
└── interactive-examples.tsx     # All chart example components
```


--------------------------------

### Run prisma bootstrap with a starter template

Source: https://github.com/prisma/web/blob/main/apps/site/content/changelog/2026-04-07.mdx

Scaffolds an empty directory with a specified starter template from prisma-examples, such as Next.js.

```text
npx prisma@7.9.1 bootstrap --template nextjs
```


--------------------------------

### Add @prisma/eclipse workspace dependency and install

Source: https://github.com/prisma/web/blob/main/packages/eclipse/GETTING_STARTED.md

Add @prisma/eclipse to package.json dependencies and run pnpm install to install it in your monorepo project.

```json
{
  "dependencies": {
    "@prisma/eclipse": "workspace:*"
  }
}
```

```bash
pnpm install
```


--------------------------------

### Navigate to project directory and install dependencies

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-postgres/quickstart/typeorm.mdx

Changes working directory into the newly created project folder and installs standard project dependencies.

```npm
cd typeorm-quickstart
npm install
```


--------------------------------

### Initialize the database with db:init

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-postgres/quickstart/prisma-orm.mdx

Apply the starter schema to Prisma Postgres and sign the database from the project directory. Sample users seed automatically during the initial query.

```npm
npm run db:init
```


--------------------------------

### Start the app and local database using Composer

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-orm/quickstart/postgresql.mdx

Runs the application with Prisma Composer, which starts a local Prisma Postgres database and applies the starter contract automatically without requiring a connection string.

```npm
npm run dev:composer
```


--------------------------------

### Install @tailwindcss/postcss plugin

Source: https://github.com/prisma/web/blob/main/packages/eclipse/TROUBLESHOOTING.md

Installs the PostCSS plugin package when encountered with a plugin not found error.

```bash
pnpm install @tailwindcss/postcss
```


--------------------------------

### Create and initialize project directory

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-postgres/quickstart/drizzle-orm.mdx

Create a new project directory and initialize it with default npm configuration.

```npm
mkdir drizzle-quickstart
cd drizzle-quickstart
npm init -y
```


--------------------------------

### Install TypeScript as a development dependency

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-postgres/quickstart/kysely.mdx

Installs the TypeScript compiler package required for type safety.

```shell
npm install --save-dev typescript
```


--------------------------------

### Install Prisma ORM and TypeScript dependencies

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-orm/from-scratch.mdx

Installs @prisma/orm-postgres, dotenv, prisma CLI, tsx, and typescript.

```npm
npm install @prisma/orm-postgres dotenv
npm install --save-dev prisma tsx typescript
```


--------------------------------

### Install tsx and typescript

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-orm/add-to-existing-project/postgresql.mdx

Install tsx and typescript as dev dependencies to run scripts within the project.

```npm
npm install --save-dev tsx typescript
```


--------------------------------

### Install dotenv dependency

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-postgres/quickstart/typeorm.mdx

Installs the dotenv package to load database connection credentials from environment variables.

```npm
npm install dotenv
```


--------------------------------

### Install and configure TypeScript

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-postgres/quickstart/drizzle-orm.mdx

Install TypeScript as a development dependency and generate a default tsconfig.json configuration file.

```npm
npm install --save-dev typescript
```

```npm
npx tsc --init
```


--------------------------------

### Create project directory and initialize npm

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-postgres/quickstart/kysely.mdx

Initializes a new project directory and generates a default package.json file.

```shell
mkdir kysely-quickstart
cd kysely-quickstart
npm init -y
```


--------------------------------

### Install @prisma/extension-read-replicas for Prisma 6

Source: https://github.com/prisma/web/blob/main/apps/site/content/changelog/2025-12-03.mdx

Installs version 0.4.1 of the read-replicas extension for projects remaining on Prisma v6.

```npm
npm install @prisma/extension-read-replicas@0.4.1
```


--------------------------------

### Install recharts dependency

Source: https://github.com/prisma/web/blob/main/apps/eclipse/content/design-system/components/chart.mdx

Install the recharts peer dependency required by the Chart component when configuring the project manually.

```bash
npm install recharts
```


--------------------------------

### Restart development server using pnpm

Source: https://github.com/prisma/web/blob/main/packages/eclipse/TROUBLESHOOTING.md

Navigates to the dev app directory and starts the development server to verify styling fixes.

```bash
cd apps/eclipse/dev
pnpm dev
```


--------------------------------

### Create a local project and Prisma Postgres database via CLI

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/full-stack-tutorial.mdx

Logs in and provisions a project and Prisma Postgres instance when running the framework dev server directly.

```npm
npx prisma auth login
npx prisma project create my-app-local
npx prisma postgres create mydb
```


--------------------------------

### Run TypeORM application

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-postgres/quickstart/typeorm.mdx

Starts the application, synchronizing the schema and performing sample user insertion and query operations.

```npm
npm start
```

```bash
Inserting a new user into the database...
Saved a new user with id: 1
Loading users from the database...
Loaded users:  [ User { id: 1, firstName: 'Timber', lastName: 'Saw', age: 25 } ]
```


--------------------------------

### Importing chart examples from the barrel index

Source: https://github.com/prisma/web/blob/main/apps/eclipse/src/components/chart-examples/README.md

Import multiple chart example components using the module index barrel export.

```tsx
import { BasicBarChartExample, LineChartExample } from "@/components/chart-examples";
```


--------------------------------

### Create a new Deno project with create-prisma

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-orm/create-prisma.mdx

Scaffolds a local minimal PostgreSQL application with Deno as the package manager. The `--minimum-dependency-age=0` flag ensures Deno 2.9 resolves the latest published package rather than an older cached version.

```bash
deno run -A --minimum-dependency-age=0 npm:create-prisma@latest my-deno-app --template minimal --provider postgres --package-manager deno --no-deploy
```


--------------------------------

### Install Drizzle ORM and required dependencies

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-postgres/quickstart/drizzle-orm.mdx

Install runtime dependencies (drizzle-orm, pg, dotenv) and development tooling (drizzle-kit, @types/pg, tsx).

```npm
npm install drizzle-orm pg dotenv
```

```npm
npm install --save-dev drizzle-kit @types/pg tsx
```


--------------------------------

### Cross-boundary commit message example

Source: https://github.com/prisma/web/blob/main/CONTRIBUTING.md

Example of a commit message with an empty scope used when changes intentionally span multiple apps or packages.

```text
chore: update shared lint rules and apply fixes
```


--------------------------------

### Single app bug fix commit message example

Source: https://github.com/prisma/web/blob/main/CONTRIBUTING.md

Example of a commit message for a bug fix scoped to a single workspace app.

```text
fix(docs): ensure UTMs are persisted
```


--------------------------------

### Create migration plan with npm run migration:plan

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-orm/quickstart/mongodb.mdx

Generates the initial migration plan from the starter contract to create collections and indexes.

```npm
npm run migration:plan -- --name init
```


--------------------------------

### Single app feature commit message example

Source: https://github.com/prisma/web/blob/main/CONTRIBUTING.md

Example of a properly formatted commit message scoped to a single workspace app for a feature change.

```text
feat(docs): update getting started
```


--------------------------------

### Initialize Prisma ORM for MongoDB with orm init

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-orm/quickstart/existing-app/mongodb.mdx

Runs `prisma orm init` to configure `tsconfig.json` and `package.json`, set target to MongoDB with PSL authoring, write a `.env` file, and install required dependencies.

```npm
npx prisma@latest orm init --yes --target mongodb --authoring psl --write-env
```

```text
│  target:     mongodb
│  authoring:  psl
│  schema:     src/prisma/contract.prisma

written
├─ src/prisma/contract.prisma
├─ prisma.config.ts
├─ src/prisma/db.ts
├─ prisma-8.md
├─ .env.example
├─ .env
├─ tsconfig.json
├─ .gitignore
├─ .gitattributes
└─ package.json
installed
├─ @prisma/orm-mongo
├─ dotenv
├─ prisma@latest (dev)
├─ @types/node (dev)
└─ @prisma/cli-engine@0.6.3 (dev)

✔ Done. Open prisma-8.md to get started.
```


--------------------------------

### Install Kysely and PostgreSQL dependencies

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/(index)/prisma-postgres/quickstart/kysely.mdx

Install runtime dependencies (kysely, pg, and dotenv) along with development dependencies (@types/pg and tsx) for executing TypeScript files.

```npm
npm install kysely pg dotenv
```

```npm
npm install --save-dev @types/pg tsx
```


--------------------------------

### Add aiPrompt to guide MDX frontmatter

Source: https://github.com/prisma/web/blob/main/apps/docs/PROMPT_GUIDE.md

Configure the aiPrompt field in the guide's frontmatter. The value must match the slug of the prompt MDX file.

```yaml
---
title: Remix
description: Learn how to use Prisma ORM in a Remix app
url: /docs/guides/frameworks/remix
metaTitle: ...
metaDescription: ...
aiPrompt: "remix"
---
```
