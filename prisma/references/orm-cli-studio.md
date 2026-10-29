# Prisma — ORM, CLI & Studio

Sourced snippets (43 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Install and initialize Prisma ORM 8 in a new project

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/orm/coming-from-prisma-orm-7.mdx

Installs the required CLI and PostgreSQL packages and generates starter configuration files, contract schema, client setup, and `.env`.

```npm
npm install --save-dev prisma
npm install @prisma/orm-postgres
npx prisma orm init --write-env
```


--------------------------------

### Run prisma init with options

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/cli/init.mdx

Examples demonstrating prisma init invocations with custom agent skills configurations or skipping the postinstall hook.

```shell
npx prisma@latest init
npx prisma@latest init --skills=claude,cursor
npx prisma@latest init --skills=none
npx prisma@latest init --no-postinstall
```


--------------------------------

### Install @prisma/management-api-sdk

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/rest-api/sdk.mdx

Install the SDK package using npm.

```npm
npm install @prisma/management-api-sdk
```


--------------------------------

### Install Prisma CLI globally

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/studio/getting-started.mdx

Installs the Prisma CLI globally using npm. Ensure Node.js is installed before running this command.

```npm
npm install -g prisma@prev
```


--------------------------------

### Initialize project and install dependencies

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/composer/getting-started.mdx

Initialize an npm project with ES module support and install the required Composer, schema, and development packages. Setting `type=module` is required to avoid `COMPOSE.ENTRY_UNLOADABLE` errors.

```bash
npm init -y
npm pkg set type=module
npm install @prisma/composer @prisma/composer-prisma-cloud arktype
npm install -D typescript @types/bun prisma
```


--------------------------------

### Configure local development in alchemy.run.ts

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/compute/alchemy.mdx

Configures local persistence mode for the database and development command/port settings for the application. Use dev.migrate on Prisma.Postgres if setup is required before start.

```ts
const postgres = yield* Prisma.Postgres("database", {
  project,
  dev: {
    persistenceMode: "stateful",
  },
});

const connection = yield* Prisma.Connection("connection", {
  database: postgres,
});

const app = yield* Prisma.Compute("app", {
  project,
  build: "auto",
  env: {
    DATABASE_URL: connection.databaseUrl,
  },
  dev: {
    command: "bun run dev",
    port: 3000,
  },
});
```


--------------------------------

### Agent prompt for porting an application to Prisma Composer

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/composer/porting-an-app.mdx

Pass this prompt to a coding agent to guide it through installing dependencies, surveying the repository, declaring services in module.ts, and testing locally.

```text
Port this app to Prisma Composer.

1. Install `@prisma/composer` and `@prisma/composer-prisma-cloud`, and install `prisma` as a dev dependency (the deploy config in `prisma.config.ts` imports `prisma/config`), then install the Composer skill with `npx prisma@latest skills sync` (the skill ships inside the package; run `npx prisma@latest skills list` to confirm). Then read https://www.prisma.io/docs/composer/porting-an-app.md and follow it for this repository.
2. Survey the repo before changing anything and report back: every deployable server, its runtime (Node, Bun, or Next.js), its build command and entry file, every `process.env` read, and any database it connects to. Ask me about anything ambiguous.
3. Declare each server as a service with `compute()`, using the `node` or `nextjs` build adapter as appropriate, and compose them in a single `module.ts`.
4. Replace the `process.env` reads: the listen port becomes `service.port()` bound to `0.0.0.0`, config and credentials become fields of the service input schema, and anything another service provides becomes a typed dependency. Replace the URLs services use to reach each other with contracts.
5. If the app talks to Postgres, declare `rawPostgres()` (from `@prisma/composer-prisma-cloud`) as a dependency and build the existing client from the injected `db.url` instead of a connection-string variable.
6. Verify with `npx tsc --noEmit`, then build and run `npx prisma dev module.ts` and confirm every service boots with a local URL. Do not deploy; show me the diff first.
```


--------------------------------

### Connect explicit repository URL with Prisma CLI

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/compute/github.mdx

Specify the full GitHub repository URL to connect a project to a specific repository. If the GitHub App is not installed, the CLI opens a browser window to complete setup.

```npm
npx prisma git connect https://github.com/acme/shop
```


--------------------------------

### Install Prisma CLI

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/composer/porting-an-app.mdx

Install prisma as a dev dependency to resolve imports from prisma/config.

```npm
npm install -D prisma
```


--------------------------------

### Start Prisma Studio via CLI

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/studio/index.mdx

Launch Prisma Studio either from within an existing Prisma project or by supplying a direct database connection URL with the --url flag.

```npm
# With Prisma project
npx prisma studio

# With direct database connection
npx prisma studio --url="postgresql://user:password@localhost:5432/dbname"
```


--------------------------------

### Install Hono dependency

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/compute/image-transformations.mdx

Installs the Hono framework using Bun package manager.

```bash
bun add hono
```


--------------------------------

### Initialize Prisma ORM with target, authoring, and install options

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/cli/orm-init.mdx

Runs `orm init` using specified target databases (such as Postgres or MongoDB), authoring formats, or skipping dependency installation.

```npm
npx prisma@latest orm init --yes --target postgres --authoring psl
npx prisma@latest orm init --yes --target mongodb --authoring typescript --json
npx prisma@latest orm init --skip-install
```


--------------------------------

### Install @prisma/studio-core

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/studio/integrations/embedding.mdx

Installs the core package required to embed Prisma Studio in a web application.

```npm
npm install @prisma/studio-core
```


--------------------------------

### Execute contract infer with common options

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/cli/contract-infer.mdx

Examples demonstrating how to specify the database URL, output file path, or receive machine-readable JSON output.

```bash
npx prisma contract infer --db "$DATABASE_URL"
npx prisma contract infer --db "$DATABASE_URL" --output ./prisma/contract.prisma
npx prisma contract infer --db "$DATABASE_URL" --json
```


--------------------------------

### Install additional database dependencies

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/studio/integrations/embedding.mdx

Installs optional drivers for SQLite or MySQL support. PostgreSQL support is included by default in @prisma/studio-core.

```npm
# For SQLite support
npm install better-sqlite3

# For MySQL support
npm install mysql2
```


--------------------------------

### Install the pgvector extension package via npm

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/orm/extensions/using-extensions.mdx

Install the extension package from npm in your project root.

```npm
npm install @prisma/orm-extension-pgvector
```


--------------------------------

### Start local development server with Alchemy CLI

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/compute/alchemy.mdx

Starts a local Prisma Postgres server, passes the connection string to the application, and executes the configured development command.

```npm
npx alchemy dev
```


--------------------------------

### Initialize database with prisma db init

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/cli/db-init.mdx

Bootstraps a database to match the emitted contract and signs it using additive operations only.

```npm
npx prisma db init --db "$DATABASE_URL"
```


--------------------------------

### Create a Bucket and Key with prisma bucket

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/cli/index.mdx

Create a new storage bucket and mint access credentials. `bucket key create` prints one-time credentials for the specified bucket ID.

```bash
npx prisma bucket create --name my-bucket
npx prisma bucket key create <bucket-id>
```


--------------------------------

### Install Alchemy dependencies and update .gitignore

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/compute/alchemy.mdx

Installs Alchemy and Effect beta packages, then appends the local `.alchemy/` state folder to `.gitignore`.

```npm
npm install alchemy@next effect@beta @effect/platform-bun@beta @effect/platform-node@beta
printf '\n.alchemy/\n' >> .gitignore
```


--------------------------------

### Create a Database and Connection with prisma postgres

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/cli/index.mdx

Provision a database and generate connection URLs. `postgres create` prints a one-time connection URL, while `postgres connection create` generates additional URLs.

```bash
npx prisma postgres create mydb
npx prisma postgres connection create mydb
```


--------------------------------

### Initialize Prisma ORM project

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/orm/fundamentals/relations-and-joins.mdx

Create a new Prisma ORM setup or initialize Prisma ORM in an existing project. Both commands generate `src/prisma/db.ts` to export the client as `db` configured from `.env`.

```bash
npm create prisma@latest -- my-app --no-deploy   # a new project
npx prisma orm init                              # a project you already have
```


--------------------------------

### Configure Studio for PostgreSQL with createPostgresAdapter

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/studio/integrations/embedding.mdx

Initializes createStudioBFFClient and createPostgresAdapter to render the Studio component against a PostgreSQL backend.

```tsx
import { Studio } from "@prisma/studio-core/ui";
import { createPostgresAdapter } from "@prisma/studio-core/data/postgres-core";
import { createStudioBFFClient } from "@prisma/studio-core/data/bff";
import "@prisma/studio-core/ui/index.css";

function App() {
  const adapter = useMemo(() => {
    // 1. Create a client that points to your backend endpoint
    const executor = createStudioBFFClient({
      url: "http://localhost:4242/studio",
    });

    // 2. Create a Postgres adapter with the executor
    const adapter = createPostgresAdapter({ executor });
    return adapter;
  }, []);

  return (
    <Layout>
      <Studio adapter={adapter} />
    </Layout>
  );
}
```


--------------------------------

### Install Prisma Client and Accelerate extension

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/accelerate/getting-started.mdx

Installs the latest Prisma Client and the @prisma/extension-accelerate package. Requires Prisma Client 4.16.1+ and Node.js 18+ for extension version 2.0.0+.

```npm
npm install @prisma/client@latest @prisma/extension-accelerate
```


--------------------------------

### Run migration new with name and from options

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/cli/migration-new.mdx

Scaffold manual migrations using `--name` or specifying a starting contract hash prefix with `--from`.

```npm
npx prisma migration new --name split-name
npx prisma migration new --name custom-fk --from abc123
```


--------------------------------

### List and create Prisma Postgres databases

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/cli/postgres.mdx

Demonstrates basic usage of the Prisma CLI to list existing Prisma Postgres databases and create a new database named mydb.

```npm
npx prisma postgres list
npx prisma postgres create mydb
```


--------------------------------

### Start local development server with Prisma dev

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/composer/getting-started.mdx

Launches the application locally against local stand-ins for Prisma Compute and Prisma Postgres, displaying local URLs for each service.

```npm
npx prisma dev module.ts
```

```text
dev: ready
gateway: http://localhost:3001
quotes: http://localhost:3000
```


--------------------------------

### Preview database initialization with --dry-run

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/cli/db-init.mdx

Shows planned operations without applying changes to the database. Useful before modifying non-disposable databases.

```npm
npx prisma db init --db "$DATABASE_URL" --dry-run
```


--------------------------------

### Run Prisma Composer locally using prisma dev

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/cli/dev.mdx

Starts a local development instance of a Prisma Composer application using an entry module. The optional --fresh flag destroys the stack and wipes dev state before starting.

```npm
npx prisma dev module.ts
npx prisma dev module.ts --fresh
```


--------------------------------

### Start local Prisma Postgres instance with prisma dev

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/local-development/app-development.mdx

Launches a local Prisma Postgres instance from your project directory and outputs a DATABASE_URL to copy into your .env file.

```npm
npx prisma dev
```


--------------------------------

### Run prisma init

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/cli/init.mdx

Prepares the current directory for Prisma development without scaffolding the ORM. Safe to rerun and never prompts.

```shell
npx prisma@latest init
```


--------------------------------

### Connect a GitHub repository with prisma git connect

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/cli/git.mdx

Run this command from a linked project directory to connect a GitHub repository and initiate the GitHub App installation flow. Requires an interactive terminal; using --no-interactive will fail with CLI.INTERACTION_REQUIRED.

```npm
npx prisma git connect
```


--------------------------------

### Check installed @prisma/orm-postgres version

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/orm/contract-authoring/editor-support.mdx

Run this command to check the installed version of the database ORM package when the editor displays false contract errors.

```bash
npm ls @prisma/orm-postgres
```


--------------------------------

### Sync Prisma agent skills

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/composer/index.mdx

Installs and syncs the Composer skill from the installed `@prisma/composer` package before your AI coding agent writes Composer code.

```npm
npx prisma skills sync
```


--------------------------------

### Run Bun-native server entry file

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/local-development/app-development.mdx

Runs a Bun-native server entry file directly to match the Prisma Compute deployment runtime.

```bash
bun run src/index.ts
```


--------------------------------

### Show and retry domain provisioning

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/compute/domains.mdx

Prints the exact state, certificate details, and DNS hints using show, or restarts stuck provisioning with retry. Returns DOMAIN_RETRY_NOT_ELIGIBLE if the domain cannot be retried.

```npm
npx prisma service domain show shop.acme.com --service web
npx prisma service domain retry shop.acme.com --service web
```


--------------------------------

### List, inspect, and open services

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/compute/getting-started.mdx

Lists services, prints service details along with the live version, and opens the service URL.

```npm
npx prisma service list
npx prisma service show <service>
npx prisma service open <service>
```


--------------------------------

### Install prisma-compute agent skill

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/compute/getting-started.mdx

Installs the Prisma Compute skill into the repository for coding agents. Teaches agents workflows for authentication, configuration, deployments, logs, and domains.

```npm
npx skills add prisma/skills --skill prisma-compute
```


--------------------------------

### Run scriptable orm init with --target and --authoring

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/cli/orm-init.mdx

Runs a non-interactive setup suitable for CI, AI coding agents, and automation by specifying flags upfront.

```npm
npx prisma@latest orm init --yes --target postgres --authoring psl
```


--------------------------------

### Initialize Prisma ORM 8 with --from-prisma7-schema

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/cli/orm-init.mdx

Sets up Prisma ORM 8 next to Prisma ORM 7 on PostgreSQL by reading the existing schema file as its contract source.

```npm
npx prisma@latest orm init --from-prisma7-schema prisma/schema.prisma
```


--------------------------------

### Initialize ORM in an Existing Project

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/cli/index.mdx

Initialize ORM configuration, emit contracts, and initialize the database. Use `--advance-ref db` when passing `--db` so that the `db` ref stays current for future migration planning.

```bash
npx prisma@latest orm init --target postgres --authoring psl
npx prisma contract emit
npx prisma db init --db "$DATABASE_URL" --advance-ref db
```


--------------------------------

### Stop, start, and delete versions with `prisma service version`

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/compute/deployments.mdx

Stop a version to take it out of service without deleting its artifact, start it to bring it back, or delete it permanently after confirmation.

```npm
npx prisma service version stop ver_123
npx prisma service version start ver_123
npx prisma service version delete ver_123
```


--------------------------------

### Launch Prisma Studio outside project with database URL

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/studio/prisma-next.mdx

Starts Studio using the Prisma CLI outside the project directory with the database connection URL passed via the --url flag.

```bash
cd .. && npx prisma@prev studio --url "$DATABASE_URL"
```
