# Prisma — Guides

Sourced snippets (77 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Start local server with npm start

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/deployment/docker.mdx

Starts the application server locally to test against the migrated database.

```npm
npm start
```

```text
Server is running on http://localhost:3000
```


--------------------------------

### Agent prompt for TanStack Start app setup and deployment

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/frameworks/tanstack-start.mdx

Copy this prompt to an AI coding agent to scaffold a TanStack Start app with Prisma ORM, initialize and seed PostgreSQL, test locally, and deploy to Prisma Compute.

```text
Create a new TanStack Start app with Prisma ORM, seed it, and deploy it to Prisma Compute.

1. Scaffold: `npm create prisma@latest -- my-app --template tanstack-start --provider postgres --yes`. Then run `npx prisma@latest init` in `my-app` so the Prisma agent skills are installed and stay current, and use them. Get a database connection string: use the one I give you, or create a Prisma Postgres database with `npx create-db@latest` and show me the claim URL it prints. Export it as `DATABASE_URL` in the shell; the generated scripts read the environment variable, not `.env`.
2. In `my-app`, run `npm run db:init` with `DATABASE_URL` exported. Sample users are seeded automatically on the app's first query; there is no separate seed script.
3. Start `npm run dev` in the background, wait until it reports ready, verify http://localhost:3000 renders the three seeded users, then stop the dev server.
4. Deploy: check `npx prisma auth whoami`; if I am not signed in, stop and ask me to run `npx prisma auth login`. Then run `npm run build` followed by `npx prisma deploy module.ts` and verify the live URL renders the seeded users. The deployed app provisions and seeds its own Prisma Postgres database; do not pass the local DATABASE_URL. If the deploy fails with `HostedStateBootstrapError`, a project with the module's name exists in my workspace but its hosted state cannot be verified; re-run the deploy with `--name <a unique name>`.
```


--------------------------------

### Install Prisma ORM and initialize project

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/upgrade-prisma-orm/v1.mdx

Initialize a new Node.js project, install the Prisma CLI and client packages, and initialize Prisma configuration.

```npm
# Initialize a new project
npm init -y
npm install prisma@prev @prisma/client@7

# Initialize Prisma
npx prisma init
```


--------------------------------

### Start the HTTP server

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/runtimes/deno.mdx

Starts the generated HTTP server using Deno tasks.

```bash
deno task dev
```


--------------------------------

### Initialize the database with the starter contract

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/runtimes/deno.mdx

Applies the starter contract and signs the database.

```bash
deno task db:init
```


--------------------------------

### Serve the production build with pnpm start

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/deployment/pnpm-workspaces.mdx

Starts the production server after building. The application renders data using the production database connection.

```bash
pnpm start
```


--------------------------------

### Start development server

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/deployment/bun-workspaces.mdx

Starts the Next.js development server using Bun filtering from the workspace root directory.

```bash
bun run dev
```

```text
$ bun run --filter web dev
web dev: ▲ Next.js 16.3.4 (Turbopack)
web dev: - Local:         http://localhost:3000
web dev: - Network:       http://192.168.1.16:3000
web dev: - Environments: .env
web dev: ✓ Ready in 4.0s
```


--------------------------------

### Initialize project and install Express

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/deployment/docker.mdx

Creates a new project directory, initializes a Node.js project, and installs Express to generate package-lock.json.

```npm
mkdir docker-test
cd docker-test
npm init -y
npm install express
```


--------------------------------

### Clone and install the Plasmic Prisma starter

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/plasmic.mdx

Clone the starter repository containing the Plasmic data queries and Prisma schema, and install dependencies.

```bash
git clone https://github.com/plasmicapp/plasmic-prisma-starter.git
cd plasmic-prisma-starter
pnpm install
```


--------------------------------

### Verify application endpoints with curl

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/upgrade-prisma-orm/postgresql.mdx

Performs a POST and GET request against the users route to ensure the Prisma ORM 7 setup is working properly before making configuration changes.

```bash
curl -X POST localhost:3000/users -H 'content-type: application/json' \
  -d '{"email":"alice@prisma.io","name":"Alice"}'
curl localhost:3000/users
```


--------------------------------

### Navigate into the project directory

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/runtimes/bun.mdx

Switch into the newly scaffolded project directory.

```bash
cd my-bun-app
```


--------------------------------

### Install tracing dependencies

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/datadog.mdx

Installs @prisma/instrumentation and the official dd-trace library for Datadog tracing.

```npm
npm install @prisma/instrumentation \
  dd-trace
```


--------------------------------

### Create a platform project

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/github-actions.mdx

Creates a dedicated platform project for preview databases and links the directory by generating .prisma/local.json.

```npm
npx prisma project create prisma-gha-preview
```


--------------------------------

### Install PostgreSQL adapter and type definitions

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/datadog.mdx

Installs the PostgreSQL database driver adapter and corresponding type definitions.

```npm
npm i @prisma/adapter-pg pg
```

```npm
npm i -D @types/pg
```


--------------------------------

### Install Prisma Client and PostgreSQL adapter packages

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/authentication/clerk/astro.mdx

Installs runtime dependencies including Prisma Client, the PostgreSQL driver adapter, dotenv, and pg.

```bash
npm install @prisma/client@7 @prisma/adapter-pg dotenv pg
```


--------------------------------

### Start Next.js development server

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/plasmic.mdx

Start the development server so Plasmic Studio can connect and load registered data queries.

```bash
pnpm dev
```


--------------------------------

### Start development server

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/deployment/pnpm-workspaces.mdx

Runs the Next.js development server from the workspace root.

```bash
pnpm dev
```

```text
$ next dev
▲ Next.js 16.3.6 (Turbopack)
- Local:         http://localhost:3000
- Environments: .env
✓ Ready in 479ms
```


--------------------------------

### Install and link workspace dependencies

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/deployment/bun-workspaces.mdx

Runs `bun install` from the monorepo root to link `packages/database` into `apps/web/node_modules/database` as a symlink.

```bash
cd ../..
bun install
```

```text
bun install v1.3.3 (274e01c7)
Saved lockfile

Checked 478 installs across 616 packages (no changes) [440.00ms]
```


--------------------------------

### Install Auth.js dependencies

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/authentication/authjs/nextjs.mdx

Installs the Auth.js Prisma adapter and NextAuth beta package for Next.js authentication.

```npm
npm install @auth/prisma-adapter next-auth@beta
```


--------------------------------

### Install TypeScript development dependency

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/datadog.mdx

Installs TypeScript as a development dependency.

```npm
npm install -D typescript
```


--------------------------------

### Install dotenv

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/datadog.mdx

Installs the dotenv package required for loading environment variables in prisma.config.ts.

```npm
npm install dotenv
```


--------------------------------

### Install Prisma and tsx

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/datadog.mdx

Installs Prisma and the tsx TypeScript runner as development dependencies.

```npm
npm install -D prisma@prev tsx
```


--------------------------------

### Install Better Auth core package

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/authentication/better-auth/nextjs.mdx

Install the core `better-auth` dependency in your project.

```npm
npm install better-auth
```


--------------------------------

### Start server and query users endpoint

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/runtimes/bun.mdx

Starts the HTTP server using Bun and verifies the /users endpoint using curl.

```bash
bun src/server.ts
```

```bash
curl http://localhost:3000/users
```

```json
[{ "id": 1, "email": "ada+1784893846026@prisma.io", "name": "Ada Lovelace" }]
```


--------------------------------

### Quick start scaffold with create-prisma

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/frameworks/tanstack-start.mdx

Scaffolds a TanStack Start project with Prisma ORM configured for PostgreSQL without immediate deployment.

```npm
npm create prisma@latest -- my-app --template tanstack-start --provider postgres --no-deploy
```


--------------------------------

### Install workspace dependencies

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/deployment/pnpm-workspaces.mdx

Runs `pnpm install` from the root directory to link the shared `database` package into the Next.js app.

```bash
cd ..
pnpm install
```

```text
Scope: all 3 workspace projects
Progress: resolved 700, reused 700, downloaded 0, added 700, done
Done in 1.9s using pnpm v12.7.0
```


--------------------------------

### Install Prisma ORM 8 and PostgreSQL packages

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/upgrade-prisma-orm/postgresql.mdx

Installs the Prisma ORM 8 CLI as a dev dependency to resolve `prisma/config` subpath imports such as `definePrismaConfig`, and installs `@prisma/orm-postgres` for PostgreSQL application code.

```npm
npm install --save-dev prisma@latest
npm install @prisma/orm-postgres
```


--------------------------------

### Configure DATABASE_URL in .env

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/datadog.mdx

Example connection string placeholder generated in the root .env file.

```text
# Placeholder url you have to replace
DATABASE_URL="postgresql://janedoe:mypassword@localhost:5432/mydb?schema=sample"
```


--------------------------------

### Install project dependencies

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/frameworks/solid-start.mdx

Installs npm packages and creates package-lock.json to configure npm as the package manager.

```npm
npm install
```


--------------------------------

### Install Prisma CLI development dependency

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/postgres/netlify.mdx

Installs the preview version of the Prisma CLI as a development dependency.

```npm
npm install prisma@prev --save-dev
```


--------------------------------

### Navigate to the scaffolded project directory

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/runtimes/deno.mdx

Change into the newly created project folder containing `deno.json` and generated Prisma artifacts.

```bash
cd my-deno-app
```


--------------------------------

### Configure environment variables and Auth.js secret

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/plasmic.mdx

Copy the example environment file, generate an Auth.js secret, and update the database and auth configuration in .env.

```bash
cp .env.example .env
pnpm dlx auth secret
```

```text
DATABASE_URL="postgres://USER:PASSWORD@HOST:5432/postgres?sslmode=require"
AUTH_SECRET="YOUR_GENERATED_SECRET"
```


--------------------------------

### Start development server with npm run dev

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/database/multiple-databases.mdx

Runs the local development server using Next.js Turbopack.

```npm
npm run dev
```

```text
▲ Next.js 16.3.4 (Turbopack)
- Local:         http://localhost:3000
- Environments: .env
✓ Ready in 894ms
```


--------------------------------

### Request starter users from the HTTP server

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/runtimes/deno.mdx

Sends a GET request to the local server, which seeds initial data idempotently on the first query and returns the user list.

```bash
curl http://localhost:3000
```

```json
{
  "users": [
    { "id": "1", "email": "alice@prisma.io", "username": "alice", "name": "Alice", "createdAt": "2026-07-24T10:55:54.156Z" },
    { "id": "2", "email": "bob@prisma.io", "username": "bob", "name": "Bob", "createdAt": "2026-07-24T10:55:54.192Z" },
    { "id": "3", "email": "carol@prisma.io", "username": "carol", "name": "Carol", "createdAt": "2026-07-24T10:55:54.228Z" }
  ]
}
```


--------------------------------

### Provision a Prisma Postgres database using prisma init

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/plasmic.mdx

Create and provision a new Prisma Postgres database. Signs in to the Prisma Console and returns a PostgreSQL connection string.

```bash
pnpm exec prisma init --db
```


--------------------------------

### Build image and start services with Docker Compose

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/deployment/docker.mdx

Builds the application Docker image and starts the containers in detached mode. Displays the Docker Compose build and startup status output.

```bash
docker compose up --build -d
```

```text
[+] up 4/4
 ✔ Image docker-test-server       Built                                     1.4s
 ✔ Network docker-test_default    Created                                   0.0s
 ✔ Container postgres_db          Healthy                                   5.7s
 ✔ Container docker-test-server-1 Started                                   5.7s
```


--------------------------------

### Launch Prisma Studio locally with a direct connection string

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/postgres/viewing-data.mdx

Starts a local Prisma Studio server at http://localhost:5555 connected directly to your Prisma Postgres database.

```npm
npx prisma@prev studio --url="postgres://USER:PASSWORD@db.prisma.io:5432/postgres?sslmode=require"
```


--------------------------------

### Initialize Prisma scaffolding with prisma init

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/authentication/clerk/astro.mdx

Creates the prisma directory, schema.prisma, prisma.config.ts, and a .env file containing a local DATABASE_URL.

```bash
npx prisma init
```


--------------------------------

### Install PostgreSQL adapter and pg driver

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/postgres/netlify.mdx

Installs the PostgreSQL driver adapter (@prisma/adapter-pg) and pg library used by Prisma Client to connect over TCP.

```npm
npm install @prisma/adapter-pg pg
```


--------------------------------

### Install Prisma development dependencies

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/authentication/clerk/astro.mdx

Installs the Prisma CLI, tsx, and PostgreSQL type definitions as development dependencies.

```bash
npm install prisma@prev tsx @types/pg --save-dev
```


--------------------------------

### Start SolidStart development server

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/frameworks/solid-start.mdx

Runs the local Vite development server to serve the SolidStart application and API endpoints.

```npm
npm run dev
```

```text
  VITE v8.3.1  ready in 5509 ms

  ➜  Local:   http://localhost:3000/
  ➜  Network: use --host to expose
```


--------------------------------

### Install and run prisma1-upgrade CLI

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/upgrade-prisma-orm/v1.mdx

Installs the Prisma 1 Upgrade CLI globally and runs the upgrade helper to convert datamodels and identify migration issues.

```npm
# Install the upgrade CLI
npm install -g prisma1-upgrade

# Run the upgrade helper
prisma1-upgrade
```


--------------------------------

### Install and sync Prisma ORM agent skills

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/frameworks/solid-start.mdx

Runs npx prisma@latest init to install agent skills matching your packages and adds the skills synchronization hook to package.json, followed by the expected CLI output.

```npm
npx prisma@latest init
```

```text
✔ Added "postinstall": "prisma skills sync || exit 0" to package.json.
⚠ prisma.config.ts already exists; left untouched.
✔ Synced 3 skills.

project:  ~/my-solid-prisma-app
check:    enabled

Skill                          Package               Version      Installed into
prisma-8                       @prisma/orm-postgres  8.0.0-rc.17  .claude/skills, .cursor/skills, .agents/skills, .devin/skills
prisma-composer-core-concepts  @prisma/composer      0.25.0       .claude/skills, .cursor/skills, .agents/skills, .devin/skills
prisma-platform-core-concepts  prisma                8.0.0-rc.21  .claude/skills, .cursor/skills, .agents/skills, .devin/skills

⚠ [INIT.CONFIG_KEPT] prisma.config.ts already exists, so init left it alone instead of writing the skills section.
→ Add skills: { agents: ["claude", "cursor", "agents", "devin"] } to the object passed to definePrismaConfig in prisma.config.ts.
```


--------------------------------

### Create project directory and initialize Prisma ORM

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/database/data-migration.mdx

Creates a new directory and initializes Prisma ORM targeting PostgreSQL using PSL authoring mode.

```bash
mkdir expand-contract && cd expand-contract
```

```npm
npm init -y
npx prisma@latest orm init --yes --target postgres --authoring psl
```


--------------------------------

### Start development server using npm run dev

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/frameworks/react-router-7.mdx

Start the React Router development server. Running the dev server generates route type definitions such as `./+types/home`.

```npm
npm run dev
```

```text
  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
```


--------------------------------

### Start PostgreSQL container with docker compose up

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/deployment/docker.mdx

Starts the standalone PostgreSQL container in detached mode using docker-compose.postgres.yml.

```bash
docker compose -f docker-compose.postgres.yml up -d
```

```text
 Container docker-test-postgres-1  Started
```


--------------------------------

### Scaffold and navigate into the project directory

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/frameworks/tanstack-start.mdx

Generates the TanStack Start app with Prisma ORM dependencies and contract types, then changes directory into the project folder.

```npm
npm create prisma@latest -- my-app --template tanstack-start --provider postgres --no-deploy
cd my-app
```


--------------------------------

### Initialize a new Node.js project

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/datadog.mdx

Creates a dedicated project directory and generates a default package.json file for Datadog and Prisma tracing.

```npm
mkdir prisma-datadog-tracing
cd prisma-datadog-tracing
npm init -y
```


--------------------------------

### Install Prisma dependencies for MySQL

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/embed-studio.mdx

Installs Prisma CLI, TypeScript runner, Prisma Client, and MySQL adapter dependencies.

```npm
npm install prisma@prev tsx @types/mysql2 --save-dev
npm install @prisma/client@7 @prisma/adapter-mysql dotenv mysql2
```


--------------------------------

### Install Prisma dependencies for SQLite

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/embed-studio.mdx

Installs Prisma CLI, TypeScript runner, Prisma Client, and SQLite driver dependencies.

```npm
npm install prisma@prev tsx --save-dev
npm install @prisma/client@7 @prisma/adapter-sqlite dotenv better-sqlite3
```


--------------------------------

### Install AI SDK dependencies with npm

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/ai-sdk.mdx

Installs the AI SDK core package, React hooks, and OpenAI provider.

```npm
npm install ai @ai-sdk/react @ai-sdk/openai
```


--------------------------------

### Initialize Prisma ORM with custom output

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/datadog.mdx

Initializes Prisma scaffolding and configures the client output path to '../src/generated/prisma'.

```npm
npx prisma init --output ../src/generated/prisma
```


--------------------------------

### Initialize Prisma and create Prisma Postgres database

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/authentication/better-auth/nextjs.mdx

Initializes Prisma scaffolding with a customized output path for the generated client, then creates a Prisma Postgres database instance.

```npm
npx prisma init --output ../src/generated/prisma
```

```npm
npx create-db
```


--------------------------------

### Initialize database with pnpm prisma db init

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/deployment/pnpm-workspaces.mdx

Applies the contract to the database and signs it. If the command fails with 'Connection terminated unexpectedly', wait a few seconds for the database to finish starting and rerun.

```bash
pnpm prisma db init
```

```text
✔ Initialising database across spaces
│  contract:  src/prisma/contract.json
│  database:  postgres://****@localhost:5432/mydb
✔ Applied 5 operation(s) across 1 contract space
App space
├─ Create table "Post"
├─ Create table "User"
├─ Add unique constraint on "User" (email)
├─ Create index "Post_authorId_idx_e47547ed" on "Post"
├─ Add foreign key "Post_authorId_fkey" on "Post"
└─ marker 91e7f9f035806fa2789a4d726ef7724cad434fd6b00014d47ebf12d6e6bb784e
✔ Advanced ref "db" → 91e7f9f035806fa2789a4d726ef7724cad434fd6b00014d47ebf12d6e6bb784e
```


--------------------------------

### Create and verify a minimal Prisma ORM app on Deno via coding agent

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/runtimes/deno.mdx

Agent prompt with sequential instructions to scaffold a minimal PostgreSQL Prisma ORM application on Deno, initialize the database, and verify the app locally.

```text
Create and verify a minimal Prisma ORM app on Deno.

1. Run `deno run -A --minimum-dependency-age=0 npm:create-prisma@latest my-deno-app --template minimal --provider postgres --package-manager deno --no-deploy --yes`.
2. Enter `my-deno-app`. Run `deno run -A npm:create-db@latest --env .env --ttl 24h` and show me the claim URL so I can keep the temporary database.
3. Run `deno task db:init`, then start `deno task dev` in the background.
4. Request `http://localhost:3000` and verify that it returns Alice, Bob, and Carol. The first request seeds these users automatically; do not add or run a separate seed command.
5. Do not deploy to Prisma Compute because it does not support Deno.

Use the generated tasks instead of invoking a Prisma CLI package directly.
```


--------------------------------

### Build and run the production server

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/frameworks/react-router-7.mdx

Bundles the server with `react-router build` and runs it with `react-router-serve` on port 3000.

```npm
npm run build
npm run start
```

```text
[react-router-serve] http://localhost:3000 (http://192.168.1.16:3000)
GET /posts 200 - - 7.514 ms
```


--------------------------------

### Set up GitHub Actions preview databases agent prompt

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/github-actions.mdx

Copy this prompt to delegate the configuration of per-pull-request Prisma Postgres preview databases to a coding agent.

```text
Set up per-pull-request Prisma Postgres databases for this project with GitHub Actions and Prisma ORM.

1. Add Prisma ORM to the project with `npx prisma@latest orm init --yes --target postgres --authoring psl` (run it after a lockfile exists), then run `npx prisma@latest init` so the Prisma agent skills are installed and stay current, and use them. Define User and Post models in `src/prisma/contract.prisma`, run `npx prisma contract emit`, then `npx prisma migration plan --name init` and `npx prisma db migrate` against the DATABASE_URL I give you (or one from `npx create-db@latest`).
2. Write `src/prisma/seed.ts` that creates two users with posts through `db.orm.public.User.create` and `db.orm.public.Post.create`, skips when users already exist (use `.aggregate((a) => ({ total: a.count() }))`, not `.count()`), and ends with `await db.close()`. Add a `seed` script and verify `npm run seed` works twice.
3. Check `npx prisma auth whoami`; if I am not signed in, stop and ask me to run `npx prisma auth login`. Create a dedicated platform project with `npx prisma project create <name>` and show me the project id.
4. Write `.github/workflows/prisma-postgres-preview.yml` following https://www.prisma.io/docs/guides/integrations/github-actions.md: a provision job that finds or creates a database named after the pull request with `npx prisma postgres list|create --project "$PRISMA_PROJECT_ID" --json`, reads `.envelope.result.connectionString` with jq, runs `db migrate --db`, `db verify --db`, and `npm run seed`, then comments on the pull request; and a cleanup job that deletes the database with `postgres delete <id> --confirm <id>` when the pull request closes. Always pass `--project`; the CLI does not read PRISMA_PROJECT_ID from the environment for these commands.
5. Tell me which GitHub secrets to add: PRISMA_SERVICE_TOKEN, PRISMA_WORKSPACE_ID, PRISMA_PROJECT_ID.
```


--------------------------------

### Install Clerk Astro SDK and Node adapter

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/authentication/clerk/astro.mdx

Install the necessary Clerk and Node adapter packages for Astro via npm.

```npm
npm install @clerk/astro @astrojs/node
```


--------------------------------

### Launch Prisma Studio with pnpm dlx

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/deployment/pnpm-workspaces.mdx

Connects Prisma Studio to a Prisma 8 database using the --url flag. Run this command from the workspace root where no prisma.config.ts is present.

```bash
pnpm dlx prisma@prev studio --url "postgres://user:password@localhost:5432/mydb"
```

```text
Prisma Studio is running at: http://localhost:51212
```


--------------------------------

### Delegate Bun app creation and deployment to an AI agent

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/runtimes/bun.mdx

Provide this prompt to a coding agent to scaffold a Bun app with Prisma ORM, initialize database contracts, set up a Bun.serve HTTP server, and deploy the application to Prisma Compute.

```text
Create a new Bun app with Prisma ORM, run a first typed query, and deploy it to Prisma Compute.

1. Scaffold: `bun create prisma@latest my-bun-app --template minimal --provider postgres --package-manager bun --yes`. Then run `bunx prisma@latest init` in `my-bun-app` so the Prisma agent skills are installed and stay current, and use them. Get a database connection string: use the one I give you, or create a Prisma Postgres database with `bunx create-db` and show me the claim URL it prints. Export it as `DATABASE_URL` in the shell; the generated scripts read the environment variable, not `.env`.
2. In `my-bun-app`, run `bun run contract:emit`, then `bun run db:init`, with `DATABASE_URL` exported.
3. Replace `src/index.ts` with a script that creates a user and reads all users back via `db.orm.public.User`, following https://www.prisma.io/docs/guides/runtimes/bun.md, and verify `bun src/index.ts` prints the created user (`bun run dev` is `tsx watch`, which does not exit).
4. Add `src/server.ts` with a `Bun.serve` server exposing GET /users, and verify `curl http://localhost:3000/users` returns the users.
5. Deploy: check `bunx prisma@latest auth whoami`; if I am not signed in, stop and ask me to run `bunx prisma@latest auth login`. Then point the build at the server by setting `entry` in `tsdown.config.ts` to `{ server: "src/server.ts" }`, run `bun run build`, then `bunx prisma@latest deploy module.ts`, and verify the live URL's /users endpoint returns `[]`. The deployed app provisions its own fresh Prisma Postgres database, so the local users are not there; do not pass the local DATABASE_URL. If the deploy fails with `HostedStateBootstrapError`, a project with the module's name exists in my workspace but its hosted state cannot be verified; re-run the deploy with `--name <a unique name>`.

Use the installed Prisma ORM skills.
```


--------------------------------

### Open Prisma Studio with Prisma Postgres Database URL

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/postgres/vercel.mdx

Starts the local Prisma Studio interface against your Prisma Postgres instance using the database connection string from the Storage tab.

```npm
npx prisma@prev studio --url="$DATABASE_URL"
```


--------------------------------

### Create the monorepo directory

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/deployment/bun-workspaces.mdx

Initializes and navigates into a new directory for the monorepo.

```bash
mkdir my-monorepo
cd my-monorepo
```


--------------------------------

### Install Prisma and PostgreSQL driver dependencies

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/authentication/better-auth/nextjs.mdx

Installs the required Prisma CLI, client, TypeScript execution tooling, and PostgreSQL adapter packages.

```npm
npm install prisma@prev tsx @types/pg --save-dev
```

```npm
npm install @prisma/client@7 @prisma/adapter-pg dotenv pg
```


--------------------------------

### Delegate Astro with Prisma setup and deployment to an agent

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/frameworks/astro.mdx

Copy and provide this prompt to a coding agent to scaffold an Astro project, configure Prisma ORM, and deploy to Prisma Compute.

```text
Create a new Astro app with Prisma ORM, seed it, and deploy it to Prisma Compute.

1. Scaffold: `npm create prisma@latest -- my-astro-app --template astro --provider postgres --yes`. Then run `npx prisma@latest init` in `my-astro-app` so the Prisma agent skills are installed and stay current, and use them. Get a database connection string: use the one I give you, or create a Prisma Postgres database with `npx create-db@latest` and show me the claim URL it prints. Export it as `DATABASE_URL` in the shell; the generated scripts read the environment variable, not `.env`.
2. In `my-astro-app`, run `npm run db:init` with `DATABASE_URL` exported. Sample users are seeded automatically on the app's first query; there is no separate seed script.
3. Start `npm run dev` in the background, wait until it reports ready, verify http://localhost:4321 lists the seeded users and `curl http://localhost:4321/api/users` returns them as JSON, then stop the dev server.
4. Confirm `astro.config.mjs` still sets `output: "server"` and `adapter: node({ mode: "standalone" })` (the template sets both).
5. Deploy: check `npx prisma auth whoami`; if I am not signed in, stop and ask me to run `npx prisma auth login`. Then run `npm run build` followed by `npx prisma deploy module.ts` and verify the live URL's /api/users endpoint with curl. The deployed app provisions and seeds its own Prisma Postgres database; do not pass the local DATABASE_URL. If the deploy fails with `HostedStateBootstrapError`, a project with the module's name exists in my workspace but its hosted state cannot be verified; re-run the deploy with `--name <a unique name>`.

Use the installed Prisma ORM skills.
```


--------------------------------

### Delegate SvelteKit App Setup to an AI Coding Agent

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/frameworks/sveltekit.mdx

Copy and pass this prompt to a coding agent to scaffold a SvelteKit app with Prisma ORM, initialize the database, and verify the dev server.

```text
Create a new SvelteKit app with Prisma ORM, seed it, and verify the page renders.

1. Scaffold: `npm create prisma@latest -- my-app --template svelte --provider postgres --yes`. Then run `npx prisma@latest init` in `my-app` so the Prisma agent skills are installed and stay current, and use them. Get a database connection string: use the one I give you, or create a Prisma Postgres database with `npx create-db@latest` and show me the claim URL it prints. Export it as `DATABASE_URL` in the shell; the generated scripts read the environment variable, not `.env`.
2. In `my-app`, run `npm run db:init` with `DATABASE_URL` exported. Sample users are seeded automatically on the app's first query; there is no separate seed script.
3. Do not deploy to Prisma Compute; it does not support SvelteKit yet. Start `npm run dev` in the background, wait until it reports ready, verify http://localhost:5173 lists the three seeded users, then stop the dev server, following https://www.prisma.io/docs/guides/frameworks/sveltekit.md.

Use the installed Prisma ORM skills.
```


--------------------------------

### Inspect sample GET /users response

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/switch-to-prisma-orm/from-mongoose.mdx

Shows the initial JSON output returned by the Mongoose GET /users route for comparison after migration.

```json
[{"profile":{"bio":"Writes about databases"},"_id":"6aa2cd2ed97f8d7357dc9bd1","email":"alice@prisma.io","name":"Alice","__v":0},{"_id":"6aa2cd2ed97f8d7357dc9bd2","email":"bob@prisma.io","name":"Bob","__v":0}]
```


--------------------------------

### Set up Prisma ORM 7 baseline configuration and routes

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/upgrade-prisma-orm/postgresql.mdx

Baseline setup showing package.json dependencies, schema definition, configuration, database adapter client initialization, and Hono route implementation for Prisma ORM 7.

```json
{
  "scripts": {
    "prisma:generate": "prisma generate",
    "db:migrate": "prisma migrate dev"
  },
  "dependencies": {
    "@prisma/adapter-pg": "^7.10.0",
    "@prisma/client": "^7.10.0"
  },
  "devDependencies": {
    "prisma": "^7.10.0"
  }
}
```

```prisma
generator client {
  provider = "prisma-client"
  output   = "../generated/prisma"
}

datasource db {
  provider = "postgresql"
}

model User {
  id    Int     @id @default(autoincrement())
  email String  @unique
  name  String?
  posts Post[]
}

model Post {
  id        Int     @id @default(autoincrement())
  title     String
  published Boolean @default(false)
  authorId  Int
  author    User    @relation(fields: [authorId], references: [id], onDelete: Cascade)

  @@index([authorId])
}
```

```typescript
import "dotenv/config";
import { defineConfig } from "prisma/config";

export default defineConfig({
  schema: "prisma/schema.prisma",
  migrations: {
    path: "prisma/migrations",
  },
  datasource: {
    url: process.env["DATABASE_URL"],
  },
});
```

```typescript
import "dotenv/config";
import { PrismaPg } from "@prisma/adapter-pg";
import { PrismaClient } from "../generated/prisma/client";

const adapter = new PrismaPg({ connectionString: process.env.DATABASE_URL! });

export const prisma = new PrismaClient({ adapter });
```

```typescript
import { Hono } from "hono";
import { prisma } from "../db";

export const users = new Hono();

users.get("/", async (c) => {
  const result = await prisma.user.findMany({
    include: { posts: true },
    orderBy: { id: "asc" },
  });
  return c.json(result);
});

users.post("/", async (c) => {
  const body = await c.req.json<{ email: string; name?: string }>();
  const user = await prisma.user.create({ data: body });
  return c.json(user, 201);
});
```


--------------------------------

### Check types and start development server

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/ai-sdk.mdx

Runs TypeScript type checking without emitting output, then starts the Next.js local development server.

```npm
npx tsc --noEmit
npm run dev
```

```text
▲ Next.js 16.1.6 (Turbopack)
- Local:         http://localhost:3000
- Environments: .env

✓ Ready in 5.5s
```


--------------------------------

### Initialize tables and contract markers in both databases

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/database/multiple-databases.mdx

Create schema tables across both databases and sign each database with its corresponding contract marker hash.

```npm
npm run db:init
```

```text
│  contract:  prisma/users/contract.json
│  database:  postgres://****@localhost:5432/users

✔ Applied 2 operation(s) across 1 contract space

App space
├─ Create table "User"
├─ Add unique constraint on "User" (email)
└─ marker f340195186d0acf8e9914097e58af0375650e7251358382aa9ad3ed5b724daf7

│  contract:  prisma/posts/contract.json
│  database:  postgres://****@localhost:5432/posts

✔ Applied 1 operation(s) across 1 contract space

App space
├─ Create table "Post"
└─ marker a0c012793cc392569087d82d7ea41686c8e60586b63c7a131391b99717157804
```


--------------------------------

### Run initial Prisma migration

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/postgres/netlify.mdx

Executes the first database migration named init to map the User model to the database.

```npm
npx prisma migrate dev --name init
```


--------------------------------

### Uninstall Mongoose and install direct MongoDB driver

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/switch-to-prisma-orm/from-mongoose.mdx

Run this when no module imports Mongoose. It removes Mongoose while installing mongodb directly as required by Prisma ORM.

```npm
npm uninstall mongoose
npm install mongodb
```


--------------------------------

### Create the GitHub Actions workflow file

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/github-actions.mdx

Creates the `.github/workflows` directory and touches the `prisma-postgres-preview.yml` file.

```bash
mkdir -p .github/workflows
touch .github/workflows/prisma-postgres-preview.yml
```


--------------------------------

### Set up project as an ES module

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/github-actions.mdx

Initializes a new directory as an npm ES module package and generates a package-lock.json.

```npm
mkdir prisma-gha-demo && cd prisma-gha-demo
npm init -y
npm pkg set type=module
npm install
```


--------------------------------

### Build and deploy to Prisma Compute

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/runtimes/bun.mdx

Builds the server bundle and deploys the application along with its provisioned Prisma Postgres database.

```bash
bun run build
bunx prisma@latest deploy module.ts
```

```text
my-bun-app
├─ database   postgres-database db_abc123
└─ app        compute-service cps_abc123
              https://xyz.ewr.prisma.build
```


--------------------------------

### Create lib directory and prisma.ts file

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/authentication/clerk/astro.mdx

Creates the destination directory and source file for the shared Prisma Client instance.

```bash
mkdir src/lib
touch src/lib/prisma.ts
```


--------------------------------

### Apply migrations and seed the preview database

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/integrations/github-actions.mdx

Runs database migration, verification, and seeding against the preview database using the retrieved connection string.

```bash
export PREVIEW_URL="<the connectionString from above>"
npx prisma db migrate --db "$PREVIEW_URL"
npx prisma db verify --db "$PREVIEW_URL"
DATABASE_URL="$PREVIEW_URL" npm run seed
```

```text
✔ Applied 1 migration(s) (6 operation(s)) across 1 contract space(s)
✔ Database marker and schema match contract
Seeded alice@prisma.io with 2 posts
Seeded bob@prisma.io with 1 posts
```


--------------------------------

### Add a guide to category meta.json

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/guides/making-guides.mdx

Updates category navigation to include a newly added guide. The page entry must match the .mdx filename without its extension.

```json
{
  "title": "Frameworks",
  "defaultOpen": true,
  "pages": [
    "nextjs",
    "astro",
    "nuxt",
    "your-new-guide" // [!code ++]
  ]
}
```
