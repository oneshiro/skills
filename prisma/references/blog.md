# Prisma — Blog

Sourced snippets (162 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Install dependencies and start development server

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/sveltekit-prisma-kvCOEoeQlC/index.mdx

Installs project dependencies and starts the SvelteKit development server at http://localhost:5173/.

```shell
npm install
npm run dev
```


--------------------------------

### Install dependencies and run Next.js development server

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-nextjs-graphql-prisma-oklidw1rhw/index.mdx

Navigates into the project directory, installs npm packages, and starts the local development server at localhost:3000.

```shell
cd awesome-links
npm install
npm run dev
```


--------------------------------

### Configure and initialize Prisma Client with PrismaPg adapter

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/convergence/index.mdx

Demonstrates the multi-step setup to configure schema generator settings, install the adapter dependencies, and instantiate PrismaClient with the PrismaPg driver adapter.

```tsx
// Step 1: Update schema
generator client {
  provider = "prisma-client"
  engineType = "client"
}
```

```tsx
// Step 2: Install adapter
npm install @prisma/adapter-pg pg
```

```tsx
// Step 3: Use it
import { PrismaClient } from '@prisma/client'
import { PrismaPg } from '@prisma/adapter-pg'

const adapter = new PrismaPg(process.env.DATABASE_URL!)
const prisma = new PrismaClient({ adapter })
```


--------------------------------

### Run Prisma Blog locally with pnpm

Source: https://github.com/prisma/web/blob/main/apps/blog/README.md

Install dependencies and start the local development server. The application runs on http://localhost:3002.

```bash
pnpm install
pnpm dev
```


--------------------------------

### Install Prisma Client package

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-nextjs-graphql-prisma-oklidw1rhw/index.mdx

Installs `@prisma/client` manually if it was not automatically installed during migration.

```shell
npm install @prisma/client
```


--------------------------------

### Download starter project and install dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/tutorial-building-a-realtime-graphql-server-with-subscriptions-2758cfc6d427/index.mdx

Downloads the starter project repository archive, extracts it into the subscriptions-starter directory, and installs npm packages.

```sh
curl https://codeload.github.com/nikolasburk/subscriptions/tar.gz/starter | tar -xz subscriptions-starter
cd subscriptions-starter
yarn install # or npm install
```


--------------------------------

### Initialize project and install dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/improving-query-performance-using-indexes-2-MyoiJNMFTsfq/index.mdx

Creates the project directory, initializes an npm package, and installs required Prisma CLI, client, PostgreSQL driver adapter, Faker, dotenv, and TypeScript tooling.

```shell
mkdir prisma-indexes && cd prisma-indexes
npm init -y
npm install prisma@7.9.1 @prisma/client@7.9.1 @prisma/adapter-pg @faker-js/faker dotenv tsx typescript @types/node
```


--------------------------------

### Start local Prisma Postgres server with npx prisma dev

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/improving-query-performance-using-indexes-2-MyoiJNMFTsfq/index.mdx

Starts a local Prisma Postgres server without needing Docker or a standalone database installation.

```shell
npx prisma dev
```


--------------------------------

### Install project dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/metrics-tutorial-prisma-pmoldgq10kz/index.mdx

Installs the required Node.js packages for the tutorial application.

```shell
npm install
```


--------------------------------

### Download the rest-nestjs example repository

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/documenting-apis-mjjpZ7E7NkVP/index.mdx

Downloads and extracts the rest-nestjs example project from the Prisma examples repository into the local directory.

```shell
curl https://codeload.github.com/prisma/prisma-examples/tar.gz/latest | tar -xz --strip=2 prisma-examples-latest/typescript/rest-nestjs
```


--------------------------------

### Initialize project and install dependencies with Bun

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/postgres-bloom-index-the-overlooked-postgres-feature/index.mdx

Initializes a new Bun project and installs the PostgreSQL client `pg`, `create-db` for provisioning temporary databases, and development types.

```bash
bun init -y
bun add pg create-db
bun add -d @types/pg
```


--------------------------------

### Install Prisma CLI and Prisma Client

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/type-safe-js-with-jsdoc-typeSaf3js/index.mdx

Initializes npm and installs prisma as a development dependency alongside @prisma/client.

```shell
npm init -y
npm install -D prisma@7.9.1
npm install @prisma/client@7.9.1
```


--------------------------------

### Create and enter project directory

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/you-dont-need-redis-postgres-already-has-pub-sub/index.mdx

Creates a new folder named postgres-pubsub-demo and navigates into it.

```bash
mkdir postgres-pubsub-demo
cd postgres-pubsub-demo
```


--------------------------------

### Install and configure PostgreSQL driver adapter

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/orm-v6-17-0-new-usage-metrics-and-direct-connections-in-ga-for-prisma-postgres/index.mdx

Install `@prisma/adapter-pg` and instantiate `PrismaClient` using `PrismaPg` with a connection string.

```shell
npm install @prisma/adapter-pg
```

```ts
import { PrismaClient } from './generated/prisma'
import { PrismaPg } from '@prisma/adapter-pg'

const adapter = new PrismaPg({ connectionString: env.DATABASE_URL })
const prisma = new PrismaClient({ adapter })

// ... send queries using `prisma` like before
```


--------------------------------

### Initialize project directory and install dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/testing-series-1-8eRB5p0Y8o/index.mdx

Initializes a new Node.js project and installs Prisma 7, Vitest, TypeScript, and required adapter packages as dependencies.

```sh
mkdir prisma-testing && cd prisma-testing
npm init -y
npm install -D prisma@7.9.1 typescript tsx @types/node vitest vitest-mock-extended
npm install @prisma/client@7.9.1 @prisma/adapter-pg dotenv
```


--------------------------------

### Install @prisma/extension-read-replicas package

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/read-replicas-prisma-client-extension-f66prwk56wow/index.mdx

Install the read replica client extension in your project via npm.

```shell
npm install @prisma/extension-read-replicas
```


--------------------------------

### Run try-prisma with npx

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/try-prisma-announcment-Kv6bwRcdjd/index.mdx

Execute the try-prisma CLI tool without installation to select and initialize a starter project from the prisma-examples repository.

```shell
npx try-prisma
```


--------------------------------

### Start development server with npm run dev

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/introducing-prisma-nuxt/index.mdx

Starts the Nuxt development server, initializing Prisma with SQLite, generating the client, and prompting for migrations and Prisma Studio.

```shell
npm run dev
```


--------------------------------

### Initialize Bun project and install pg dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/you-dont-need-a-job-queue-postgres-already-has-skip-locked/index.mdx

Initializes a new project using Bun and installs pg alongside its TypeScript type definitions.

```bash
bun init -y
bun add pg
bun add -d @types/pg
```


--------------------------------

### Uninstall global Prisma and install prisma1 locally

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-2-beta-b7bcl0gd8d8e/index.mdx

Recommended steps for Prisma 1 users to remove the global CLI installation and install the legacy `prisma1` CLI locally within a project.

```bash
# Remove global installation
npm uninstall -g prisma

# Navigate into Prisma 1 project directory & install locally
cd path/to/prisma-1-project
npm install prisma1 --save-dev

# Invoke `prisma1` by prefixing it with `npx`
npx prisma1
```


--------------------------------

### Install project dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-nextjs-graphql-prisma-4-1k1kc83x3v/index.mdx

Navigates into the cloned application directory and installs required npm dependencies.

```shell
cd awesome-links
npm install
```


--------------------------------

### Create Next.js starter project

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/database-access-on-the-edge-8F0t1s1BqOJE/index.mdx

Initializes a new Next.js application using the prisma-edge-functions starter example repository.

```bash
npx create-next-app --example https://github.com/prisma/prisma-edge-functions/tree/starter prisma-edge-functions
```


--------------------------------

### Initialize Bun project and install pg dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/you-dont-need-elasticsearch-postgres-already-has-full-text-search/index.mdx

Initialize a default Bun project and install the pg package alongside TypeScript type definitions.

```bash
bun init -y
bun add pg
bun add -d @types/pg
```


--------------------------------

### Create and start a GraphQL server with GraphQLServer

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/graphql-server-basics-the-network-layer-51d97d21861/index.mdx

Sets up a minimal GraphQL server using graphql-yoga with type definitions and resolvers. Calling server.start() defaults to listening on port 4000 and exposes GraphQL Playground at http://localhost:4000.

```js
const { GraphQLServer } = require('graphql-yoga')

const typeDefs = `
  type Query {
    hello: String!
  }
`

const resolvers = {
  Query: {
    hello: (root, args, context, info) => 'Hello  World',
  },
}

const server = new GraphQLServer({ typeDefs, resolvers })
server.start() // defaults to port 4000
```


--------------------------------

### Guided error remediation steps for missing migrations

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/stop-your-ai-agent-dropping-your-database/index.mdx

Example Prisma 8 error message directing the user or AI agent to plan and run a missing migration without resetting the database.

```text
fix: Plan the missing migration, then run it:
  1. prisma migration plan --from <hash> --to <hash> --name <slug>
  2. prisma migrate --to <hash>
```


--------------------------------

### Install libSQL database client and Prisma adapter

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-turso-ea-support-rXGd_Tmy3UXX/index.mdx

Install the driver adapter for Prisma Client and the official libSQL client via npm.

```shell
npm install @prisma/adapter-libsql 
npm install @libsql/client
```


--------------------------------

### Test status route with Vitest and app.request

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/backend-prisma-typescript-orm-with-postgresql-rest-api-validation-dcba1ps7kip3/index.mdx

Tests the GET / status endpoint using Hono's app.request helper without starting an HTTP server. Asserts that the response returns HTTP status 200 and { up: true }.

```ts
import { describe, test, expect } from "vitest";
import app from "../src/app";

describe("Status route", () => {
  test("GET / returns 200 and { up: true }", async () => {
    const res = await app.request("/");
    expect(res.status).toBe(200);
    expect(await res.json()).toEqual({ up: true });
  });
});
```


--------------------------------

### Install create-react-native-app CLI

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/tutorial-using-create-react-native-app-with-graphql-apollo-e630aee3ae1e/index.mdx

Installs the create-react-native-app CLI globally on your machine using npm.

```bash
npm install -g create-react-native-app
```


--------------------------------

### Install Vitest and vitest-mock-extended

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/testing-series-2-xPhjjmIEsM/index.mdx

Installs Vitest and vitest-mock-extended as development dependencies for unit testing.

```sh
npm i -D vitest vitest-mock-extended
```


--------------------------------

### Explore starter project directory structure

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/sveltekit-prisma-kvCOEoeQlC/index.mdx

Shows the initial file and directory tree for the starter application before adding Prisma.

```tsx
demo-sveltekit/
├ src/
│ ├ lib/
│ │ ├ components/
│ │ │ ├ Header.svelte
│ │ │ └ Post.svelte
│ │ ├ styles/
│ │ │ └ style.css
│ │ └ data.json
│ ├ routes/
│ │ │ ├ create
│ │ │ │ └ +page.svelte
│ │ │ ├ drafts
│ │ │ │ └ +page.svelte
│ │ │ ├ p
│ │ │ │ └ [id]
│ │ │ │ │ └ +page.svelte
│ │ │ ├ signup
│ │ │ │ └ +page.svelte
│ │ │ ├ +layout.svelte
│ │ │ ├ +page.server.ts
│ │ │ └ +page.svelte
│ ├ app.d.ts
│ └ app.html
├ static/
│ └ favicon.png
├ package-lock.json
├ package.json
├ svelte.config.js
├ tsconfig.json
└ vite.config.js
```


--------------------------------

### Install @prisma/nuxt module

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/introducing-prisma-nuxt/index.mdx

Navigates into the newly created Nuxt project folder and installs the @prisma/nuxt package.

```shell
cd test-nuxt-app
npm install @prisma/nuxt
```


--------------------------------

### Download the starter repository

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/tutorial-render-props-in-react-apollo-2-1-199e9e2bd01e/index.mdx

Downloads and extracts the React Apollo tutorial starter code from GitHub into a new local directory.

```sh
curl https://codeload.github.com/nikolasburk/react-apollo-tutorial/tar.gz/starter | tar -xz react-apollo-tutorial-starter
```


--------------------------------

### Navigate to project directory and install dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/announcing-prisma-2-zq1s745db8i5/index.mdx

Changes working directory into the newly generated project folder and installs Node dependencies.

```shell
cd hello-prisma2
npm install
```


--------------------------------

### Clone the starter repository

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/metrics-tutorial-prisma-pmoldgq10kz/index.mdx

Clones the metrics-begin branch of the metrics tutorial repository.

```shell
git clone -b metrics-begin git@github.com:prisma/metrics-tutorial-prisma.git
```


--------------------------------

### Run Relay Compiler and Start Application

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/getting-started-with-relay-modern-46f8de6bd6ec/index.mdx

Compiles GraphQL queries and fragments with relay-compiler and starts the development server.

```shell
relay-compiler --src ./src --schema ./schema.graphql
yarn start
```


--------------------------------

### Install Prisma CLI using Homebrew

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/using-graphql-nexus-with-a-database-pmyl3660ncst/index.mdx

Tap the repository and install the Prisma CLI using Homebrew on macOS.

```shell
brew tap prisma/prisma
brew install prisma
```


--------------------------------

### Install Neon driver adapter and WebSocket dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/serverless-database-drivers-KML1ehXORxZV/index.mdx

Installs @prisma/adapter-neon, @neondatabase/serverless, and ws to enable WebSocket connections with Neon.

```shell
npm install @prisma/adapter-neon
npm install @neondatabase/serverless
npm install ws
```


--------------------------------

### Install Prisma Client and Prisma CLI dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/full-stack-typesafety-with-angular-nest-nx-and-prisma-CcMK7fbQfTWc/index.mdx

Installs @prisma/client as a runtime dependency and @prisma/cli as a development dependency. On modern versions of Prisma (2.16.0+), install 'prisma' instead of '@prisma/cli'.

```shell
npm install @prisma/client
npm install -D @prisma/cli
```


--------------------------------

### Start Prisma MCP server with CLI command

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/about-mcp-servers-and-how-we-built-one-for-prisma/index.mdx

Starts the local Prisma MCP server packaged directly into the Prisma CLI.

```shell
prisma mcp
```


--------------------------------

### Clone repository and initialize Graphcool project

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/how-to-build-a-real-time-chat-with-graphql-subscriptions-and-apollo-d4004369b0d4/index.mdx

Clones the example repository, navigates into the project directory, and initializes a new Graphcool service using graphcool init with the specified schema.

```shell
git clone [https://github.com/graphcool-examples/react-graphql.git](https://github.com/graphcool-examples/react-graphql.git)
cd react-graphql/subscriptions-with-apollo-worldchat/
graphcool init --schema schema.graphql --name Worldchat
```


--------------------------------

### Install nodemon using yarn

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/introducing-graphql-nexus-code-first-graphql-server-development-ll6s1yy5cxl5/index.mdx

Installs nodemon as a development dependency with Yarn.

```js
yarn add -D nodemon
```


--------------------------------

### Install ts-node-dev using yarn

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/introducing-graphql-nexus-code-first-graphql-server-development-ll6s1yy5cxl5/index.mdx

Installs ts-node-dev as a development dependency with Yarn.

```js
yarn add -D ts-node-dev
```


--------------------------------

### Launch Prisma Studio via CLI

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/backend-prisma-typescript-orm-with-postgresql-data-modeling-tsjs1ps7kip1/index.mdx

Starts Prisma Studio to inspect and edit database records visually.

```sh
npx prisma studio
```


--------------------------------

### Install Prisma Accelerate extension

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/database-access-on-the-edge-8F0t1s1BqOJE/index.mdx

Installs the `@prisma/extension-accelerate` package required to use Prisma Accelerate with Prisma Client.

```bash
npm i @prisma/extension-accelerate
```


--------------------------------

### Create and run a new React app

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/how-to-use-create-react-app-with-graphql-apollo-62e574617cff/index.mdx

Initializes a new React project, navigates into the project directory, and launches the local development server.

```shell
create-react-app react-apollo-instagram-example
cd react-apollo-instagram-example
npm start # open http://localhost:3000
```


--------------------------------

### Install React Router with npm

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/how-to-use-create-react-app-with-graphql-apollo-62e574617cff/index.mdx

Installs React Router to handle page navigation across the application.

```shell
npm install react-router --save
```


--------------------------------

### Configure and start PostgreSQL with Docker Compose

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/nestjs-prisma-rest-api-7D056s1BmOL0/index.mdx

Creates a docker-compose.yml file, defines a PostgreSQL 17 service with persistent storage and port mapping, and starts the container in detached mode. Ensure nothing is already running on port 5432 before starting.

```shell
touch docker-compose.yml
```

```yml
# docker-compose.yml

services:
  postgres:
    image: postgres:17
    restart: always
    environment:
      - POSTGRES_USER=myuser
      - POSTGRES_PASSWORD=mypassword
    volumes:
      - postgres:/var/lib/postgresql/data
    ports:
      - '5432:5432'

volumes:
  postgres:
```

```shell
docker compose up -d
```


--------------------------------

### Start development server

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/database-access-on-the-edge-8F0t1s1BqOJE/index.mdx

Runs the Next.js application locally on `http://localhost:3000` to test the edge functions and database connection.

```bash
npm run dev
```


--------------------------------

### Install and configure PostgreSQL database adapter

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/announcing-prisma-6-18-0/index.mdx

Installs the PostgreSQL adapter package and passes the adapter instance to PrismaClient. This step is not needed when using Prisma Postgres.

```shell
npm install @prisma/adapter-pg
```

```ts
import { PrismaClient } from './generated/prisma'
import { PrismaPg } from '@prisma/adapter-pg'

const adapter = new PrismaPg({ connectionString: env.DATABASE_URL })
const prisma = new PrismaClient({ adapter })
```


--------------------------------

### Initialize a new Prisma project with create-prisma

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/introducing-create-prisma/index.mdx

Runs the interactive create-prisma CLI prompt to choose a framework template and database provider.

```bash
npm create prisma@stable
```


--------------------------------

### Install project dependencies with npm

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/using-graphql-nexus-with-a-database-pmyl3660ncst/index.mdx

Initialize a package.json file and install runtime dependencies alongside TypeScript development tooling.

```shell
npm init -y
npm install --save nexus graphql nexus-prisma prisma-client-lib graphql-yoga
npm install --save-dev typescript ts-node-dev
```


--------------------------------

### Start the Next.js development server

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-nextjs-graphql-prisma-3-clxbrcqppv/index.mdx

Launches the application server locally once database tables have been migrated and seeded.

```shell
npm run dev

```


--------------------------------

### Install the Auth0 Next.js SDK

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-nextjs-graphql-prisma-3-clxbrcqppv/index.mdx

Add Auth0 authentication support to your project by installing the official Next.js SDK package.

```shell
npm install @auth0/nextjs-auth0
```


--------------------------------

### Install randomcolor and TypeScript types

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/testing-series-2-xPhjjmIEsM/index.mdx

Installs the randomcolor package and its TypeScript type definitions.

```sh
npm i randomcolor && npm i -D @types/randomcolor
```


--------------------------------

### Install TypeScript and development dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/e2e-type-safety-graphql-react-2-j9mEyHY0Ej/index.mdx

Installs ts-node-dev, typescript, and @types/node as development dependencies.

```shell
npm i -D ts-node-dev typescript @types/node
```


--------------------------------

### Install nexus and graphql using npm

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/introducing-graphql-nexus-code-first-graphql-server-development-ll6s1yy5cxl5/index.mdx

Installs GraphQL Nexus and its required peer dependency graphql-js using npm.

```shell
npm install --save nexus graphql
```


--------------------------------

### Initialize a new Prisma project with prisma init

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/using-graphql-nexus-with-a-database-pmyl3660ncst/index.mdx

Use the Prisma CLI to initialize a project directory named myblog.

```shell
prisma init myblog
```


--------------------------------

### Install bcrypt and TypeScript type definitions

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/nestjs-prisma-authentication-7D056s1s0k3l/index.mdx

Install bcrypt along with its development type definitions using npm.

```shell
npm install bcrypt
npm install --save-dev @types/bcrypt
```


--------------------------------

### Initialize a new Prisma project

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-studio-3rtf78dg99fe/index.mdx

Initializes Prisma by creating a prisma directory with a schema file and a .env file for database credentials.

```bash
npx prisma@7.9.1 init
```


--------------------------------

### Install create-react-app CLI

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/how-to-use-create-react-app-with-graphql-apollo-62e574617cff/index.mdx

Installs create-react-app globally via npm to bootstrap React applications with preconfigured Webpack and Babel.

```shell
npm install -g create-react-app
```


--------------------------------

### Starter project folder structure

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-nextjs-graphql-prisma-oklidw1rhw/index.mdx

Directory layout of the starter project showing the components, data, and pages structure.

```shell
awesome-links/
┣ components/
┃ ┗ Layout/
┣ data/
┃ ┗ links.ts
┣ pages/
┃ ┣ _app.tsx
┃ ┣ about.tsx
┃ ┗ index.tsx
┣ public/
┣ styles/
┃ ┗ tailwind.css
┣ .env.example
┣ .gitignore
┣ next-env.d.ts
┣ package-lock.json
┣ package.json
┣ postcss.config.js
┣ README.md
┣ tailwind.config.js
┗ tsconfig.json
```


--------------------------------

### Scaffold and run a Hono API with PostgreSQL

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/introducing-create-prisma/index.mdx

Creates a Hono project configured with PostgreSQL and starts the development server.

```bash
npm create prisma@stable -- --name my-api --template hono --provider postgresql
cd my-api
npm run dev
```


--------------------------------

### Create and enter project directory

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/you-dont-need-a-job-queue-postgres-already-has-skip-locked/index.mdx

Creates a new folder for the PostgreSQL job queue demo and changes the working directory into it.

```bash
mkdir postgres-job-queue-demo
cd postgres-job-queue-demo
```


--------------------------------

### Create a Prisma project with CLI flags

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-studio-migrations-view/index.mdx

Scaffolds a minimal PostgreSQL project non-interactively using PSL authoring and default configurations.

```bash
npm create prisma@latest -- my-app --yes --provider postgres --authoring psl --template minimal
```


--------------------------------

### Install relay-compiler and babel-plugin-relay

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/getting-started-with-relay-modern-46f8de6bd6ec/index.mdx

Install relay-compiler and babel-plugin-relay as development dependencies for ahead-of-time Relay optimizations.

```shell
yarn add relay-compiler babel-plugin-relay --dev
```


--------------------------------

### Install nexus and graphql using yarn

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/introducing-graphql-nexus-code-first-graphql-server-development-ll6s1yy5cxl5/index.mdx

Installs GraphQL Nexus along with the graphql peer dependency using Yarn.

```shell
yarn add nexus graphql
```


--------------------------------

### Install Prisma Client and PostgreSQL adapter packages

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/nestjs-prisma-rest-api-7D056s1BmOL0/index.mdx

Installs the Prisma Client runtime and the PostgreSQL driver adapter. The driver adapter automatically includes the pg driver and its types.

```shell
npm install @prisma/client@7.9.1 @prisma/adapter-pg
```


--------------------------------

### Initialize CipherStash Prisma integration

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/search-encrypted-data-with-prisma-8-and-cipherstash/index.mdx

Installs @cipherstash/stack and @cipherstash/stack-prisma packages and authenticates with CipherStash.

```sh
npx stash init --prisma
```


--------------------------------

### Initialize Prisma Client with PrismaLibSQL adapter

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-turso-ea-support-rXGd_Tmy3UXX/index.mdx

Create a libSQL client instance using your Turso credentials and supply the PrismaLibSQL adapter to PrismaClient.

```tsx
import { PrismaClient } from '@prisma/client'

// 1. Import libSQL and the Prisma libSQL driver adapter
import { PrismaLibSQL } from '@prisma/adapter-libsql'
import { createClient } from '@libsql/client'

// 2. Instantiate libSQL
const libsql = createClient({
  // @ts-expect-error
  url: process.env.TURSO_DATABASE_URL,
  authToken: process.env.TURSO_AUTH_TOKEN
})

// 3. Instantiate the libSQL driver adapter
const adapter = new PrismaLibSQL(libsql)
// Pass the adapter option to the Prisma Client instance
const prisma = new PrismaClient({ adapter })
```


--------------------------------

### Clone the starter repository branch with Git

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-nextjs-graphql-prisma-2-fwpc6ds155/index.mdx

Clones the part-2 branch of the awesome-links repository to match the starting point for this section of the tutorial.

```shell
git clone -b part-2 https://github.com/m-abdelwahab/awesome-links.git
```


--------------------------------

### Clone starter repository branch

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-nextjs-graphql-prisma-oklidw1rhw/index.mdx

Clones the repository at the part-1 branch to set up the starter project.

```shell
git clone -b part-1 https://github.com/m-abdelwahab/awesome-links.git
```


--------------------------------

### Clone SvelteKit starter repository

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/sveltekit-prisma-kvCOEoeQlC/index.mdx

Clones the starter SvelteKit blog demo repository and navigates into the project folder.

```shell
git clone https://github.com/sonylomo/demo-sveltekit.git
cd demo-sveltekit
```


--------------------------------

### Install Prisma and dotenv packages

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/serverless-database-drivers-KML1ehXORxZV/index.mdx

Installs the required versions of prisma and @prisma/client (at least 5.4.1) along with dotenv to load environment variables.

```shell
npm install --save-dev prisma@^5.4.1
npm install @prisma/client@^5.4.1
npm install dotenv
```


--------------------------------

### Install the Pothos Prisma plugin

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/e2e-type-safety-graphql-react-3-fbV2ZVIGWg/index.mdx

Install the @pothos/plugin-prisma package via npm to provide Prisma integration and type generation.

```shell
npm i @pothos/plugin-prisma
```


--------------------------------

### Install Prisma 2 CLI globally using npm

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/announcing-prisma-2-zq1s745db8i5/index.mdx

Installs the Prisma 2 CLI globally on the system via npm.

```shell
npm install -g prisma2
```


--------------------------------

### Initialize a new project with prisma2 init

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/announcing-prisma-2-zq1s745db8i5/index.mdx

Runs the interactive project generator to configure database choice, tools (Photon and Lift), and language boilerplate.

```shell
prisma2 init hello-prisma2
```


--------------------------------

### Install Prisma ORM and PostgreSQL dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/backend-prisma-typescript-orm-with-postgresql-data-modeling-tsjs1ps7kip1/index.mdx

Installs the Prisma CLI, Prisma Client, node-postgres driver adapter, and dotenv dependencies.

```sh
npm install prisma@7.9.1 @types/pg --save-dev
npm install @prisma/client@7.9.1 @prisma/adapter-pg pg dotenv
```


--------------------------------

### Install SQLite Driver Adapter

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/try-the-new-rust-free-version-of-prisma-orm-early-access/index.mdx

Install the @prisma/better-sqlite3 package when using SQLite with the new Rust-free architecture.

```shell
npm install @prisma/better-sqlite3
```


--------------------------------

### Install PostgreSQL driver adapter

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-orm-without-rust-latest-performance-benchmarks/index.mdx

Installs the PostgreSQL driver adapter package for use with Prisma ORM.

```shell
npm install @prisma/adapter-pg
```


--------------------------------

### Start a local Prisma Postgres instance with prisma dev

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/from-local-to-production-with-prisma-postgres/index.mdx

Starts an embedded PGlite Postgres instance without requiring Docker or daemons and displays connection strings for .env. Requires Node.js 20.19+, 22.12+, or 24.

```bash
npx prisma@7 dev
```

```text
✔  Your local Prisma Postgres server default is now running

🔌 To connect with Prisma ORM use the following connection strings:

   DATABASE_URL="postgres://postgres:postgres@localhost:51214/template1?sslmode=disable&..."
```


--------------------------------

### Install TailwindCSS dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-remix-prisma-mongodb-1-7d0bftxbmb6r/index.mdx

Installs TailwindCSS, PostCSS, Autoprefixer, and Concurrently as development dependencies for a Remix project.

```shell
npm install -D tailwindcss postcss autoprefixer concurrently
```


--------------------------------

### Create and run React Native project

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/tutorial-using-create-react-native-app-with-graphql-apollo-e630aee3ae1e/index.mdx

Bootstraps a new React Native project, navigates into the project folder, and launches the app on either iOS or Android simulator.

```bash
create-react-native-app react-native-apollo-instagram-example
cd react-native-apollo-instagram-example
npm run ios # or
npm run android
```


--------------------------------

### Install PlanetScale database driver and Prisma adapter

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-orm-support-for-edge-functions-is-now-in-preview/index.mdx

Installs the PlanetScale serverless database driver and the Prisma driver adapter packages required for edge environments.

```bash
npm install @prisma/adapter-planetscale @planetscale/database
```


--------------------------------

### Install Prisma CLI development dependency

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-nextjs-graphql-prisma-oklidw1rhw/index.mdx

Installs the Prisma CLI package as a development dependency in the project.

```shell
npm install --save-dev prisma
```


--------------------------------

### Install @pothos/plugin-relay

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-nextjs-graphql-prisma-2-fwpc6ds155/index.mdx

Installs the Pothos Relay plugin for handling cursor-based pagination, nodes, connections, and utilities.

```sh
npm install @pothos/plugin-relay
```


--------------------------------

### Add development start script to package.json

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/using-graphql-nexus-with-a-database-pmyl3660ncst/index.mdx

Development start script using ts-node-dev to watch files and regenerate SDL and Nexus typings as you code.

```json
"scripts": {
  "start": "ts-node-dev --no-notify --respawn --transpileOnly ./"
},
```


--------------------------------

### Initialize e2e project and install Playwright and Faker

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/testing-series-4-OVXtDis201/index.mdx

Creates a new directory for end-to-end tests, initializes a package.json file, installs Playwright and Faker as developer dependencies, and downloads the required browser binaries.

```shell
mkdir e2e && cd e2e
npm init -y
npm i -D @playwright/test @faker-js/faker
npx playwright install
```


--------------------------------

### Install project dependencies with npm

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/documenting-apis-mjjpZ7E7NkVP/index.mdx

Navigates into the rest-nestjs project directory and installs required npm dependencies.

```shell
cd rest-nestjs
npm install
```


--------------------------------

### Install prisma-ltree package

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-next-ltree-extension/index.mdx

Install the prisma-ltree extension package to add Postgres ltree support to Prisma 8.

```bash
npm install prisma-ltree
```


--------------------------------

### Initialize and push React client repository to GitHub

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/e2e-type-safety-graphql-react-4-JaHA8GbkER/index.mdx

Example showing initialization and pushing of the React client repository using a concrete GitHub SSH repository URL.

```sh
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:sabinadams/e2e-type-safety-client.git
git push -u origin main
```


--------------------------------

### Install React Router Native

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/tutorial-using-create-react-native-app-with-graphql-apollo-e630aee3ae1e/index.mdx

Installs React Router Native for routing and navigation handling within the application.

```bash
npm install react-router-native --save
```


--------------------------------

### Create a React app with create-react-app

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/getting-started-with-relay-modern-46f8de6bd6ec/index.mdx

Installs the create-react-app CLI globally and bootstraps a new React application named instagram.

```shell
# If necessary, install `create-react-app`
npm install -g create-react-app

# Create React app called `instagram` (and navigate into it)
create-react-app instagram
cd instagram
```


--------------------------------

### Scaffold a schema using prisma init --prompt

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-orm-6-6-0-esm-support-d1-migrations-and-prisma-mcp-server/index.mdx

Scaffolds a Prisma schema based on a text description and deploys it to a fresh Prisma Postgres instance.

```bash
npx prisma init --prompt "Simple habit tracker application"
```


--------------------------------

### Install Tachyons CSS framework with npm

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/how-to-use-create-react-app-with-graphql-apollo-62e574617cff/index.mdx

Installs Tachyons for utility-based CSS styling across the React components.

```shell
npm install tachyons --save
```


--------------------------------

### Emit, plan, and apply initial migration

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-studio-migrations-view/index.mdx

Compiles the contract schema, generates the init_users_posts migration plan, and applies it while moving the db ref forward.

```bash
npx prisma@latest contract emit
npx prisma@latest migration plan --name init_users_posts
npx prisma@latest migrate --advance-ref db
```


--------------------------------

### Install react-hook-form and react-hot-toast

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-nextjs-graphql-prisma-3-clxbrcqppv/index.mdx

Installs the packages used for managing form state and displaying notification toasts in the application.

```sh
npm install react-hook-form react-hot-toast
```


--------------------------------

### Download GraphQL schema using get-graphql-schema

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/getting-started-with-relay-modern-46f8de6bd6ec/index.mdx

Installs get-graphql-schema CLI and downloads the GraphQL schema to schema.graphql.

```shell
npm install -g get-graphql-schema
get-graphql-schema __RELAY_API_ENDPOINT__ > ./schema.graphql
```


--------------------------------

### Initialize TypeScript project directory

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/backend-prisma-typescript-orm-with-postgresql-data-modeling-tsjs1ps7kip1/index.mdx

Creates a new project directory and installs base TypeScript development dependencies.

```sh
mkdir grading-app
cd grading-app
npm init -y
npm install typescript tsx @types/node --save-dev
```


--------------------------------

### Initialize npm in project folder

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/e2e-type-safety-graphql-react-2-j9mEyHY0Ej/index.mdx

Navigates into the project folder and generates a default package.json file.

```shell
cd graphql-server
npm init -y
```


--------------------------------

### Add a GET route endpoint in Express

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/graphql-server-basics-the-network-layer-51d97d21861/index.mdx

Registers an additional endpoint to handle GET requests on the /goodbye route.

```javascript
app.get('/goodbye', function(req, res) {
  res.send('<h1>Goodbye</h1>')
})
```


--------------------------------

### Scaffold a new project with prisma init --vibe

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/announcing-prisma-s-mcp-server-vibe-code-with-prisma-postgres/index.mdx

Scaffold a Prisma schema and deploy it to a fresh Prisma Postgres instance using a prompt description.

```shell
npx prisma init --vibe "Cat meme generator"
```


--------------------------------

### Start Development Server with Yarn

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/getting-started-with-relay-modern-46f8de6bd6ec/index.mdx

Runs the development server to load the React application in the browser at http://localhost:3000.

```shell
yarn start
```


--------------------------------

### Install OpenTelemetry Node.js SDK and API packages

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/tracing-tutorial-prisma-pmkddgq1lm2/index.mdx

Install the required OpenTelemetry packages to enable tracing in Node.js applications.

```shell
npm install --save @opentelemetry/api
npm install --save @opentelemetry/sdk-trace-node
```


--------------------------------

### Install @nestjs/config package

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/nestjs-prisma-rest-api-7D056s1BmOL0/index.mdx

Installs the NestJS configuration package required to load environment variables from the `.env` file at runtime.

```shell
npm install @nestjs/config
```


--------------------------------

### Install Passport and JWT dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/nestjs-prisma-authentication-7D056s1s0k3l/index.mdx

Installs the required Passport and JWT libraries along with development TypeScript types for passport-jwt.

```shell
npm install @nestjs/passport passport @nestjs/jwt passport-jwt
npm install --save-dev @types/passport-jwt
```


--------------------------------

### Initialize Bun project with bun init

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/you-dont-need-redis-postgres-already-has-pub-sub/index.mdx

Generates a default Bun project configuration in the current working directory.

```bash
bun init -y
```


--------------------------------

### Navigate to the React client directory

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/e2e-type-safety-graphql-react-4-JaHA8GbkER/index.mdx

Run this command in the terminal to enter the React application's root directory before installing dependencies.

```sh
cd react-client
```


--------------------------------

### Set up and instantiate Prisma Client with MS SQL Server adapter

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/orm-6-10-0-new-features-for-prisma-postgres-remote-mcp-and-more/index.mdx

Re-generate the client, install the @prisma/adapter-mssql package, and instantiate PrismaClient passing the driver adapter configuration.

```bash
npx prisma generate
```

```bash
npm install @prisma/adapter-mssql
```

```typescript
import { PrismaMssql } from '@prisma/adapter-mssql'
import { PrismaClient } from '@prisma/client'

const config = {
  server: 'localhost',
  port: 1433,
  database: 'mydb',
  user: 'sa',
  password: 'mypassword',
  options: {
    encrypt: true, // Use this if you're on Windows Azure
    trustServerCertificate: true, // Use this if you're using self-signed certificates
  },
}

const adapter = new PrismaMssql(config)
const prisma = new PrismaClient({ adapter })
```


--------------------------------

### Install graphql-middleware via NPM or Yarn

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/graphql-middleware-zie3iphithxy/index.mdx

Installs the graphql-middleware package using either NPM or Yarn package manager.

```shell
npm install graphql-middleware --save
# or
yarn add graphql-middleware
```


--------------------------------

### Install react-router package

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/getting-started-with-relay-modern-46f8de6bd6ec/index.mdx

Install react-router version 2.8.1 using Yarn to handle client-side routing in the Relay application.

```shell
yarn add react-router@2.8.1
```


--------------------------------

### Install react-relay

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/getting-started-with-relay-modern-46f8de6bd6ec/index.mdx

Install the core react-relay dependency using yarn to access Relay APIs like QueryRenderer and FragmentContainer.

```shell
yarn add react-relay
```


--------------------------------

### Example image transformation request URLs

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/image-transformations-with-bun-on-prisma-compute/index.mdx

Sample URLs demonstrating query parameters for image dimension resizing, format selection, and fill options.

```text
/images/products/chair.jpg?w=640&q=75
/images/products/chair.jpg?w=1280&format=webp
/images/products/chair.jpg?w=512&h=512&fit=inside
```


--------------------------------

### Install urql dependency with npm

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/e2e-type-safety-graphql-react-4-JaHA8GbkER/index.mdx

Installs the urql GraphQL client library for querying GraphQL APIs in React applications.

```sh
npm i urql
```


--------------------------------

### Install pg and type definitions using bun add

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/you-dont-need-redis-postgres-already-has-pub-sub/index.mdx

Adds the pg PostgreSQL client and its TypeScript type definitions to project dependencies.

```bash
bun add pg
bun add -d @types/pg
```


--------------------------------

### Configuring ApolloProvider and ApolloClient in React

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/enabling-cors-for-express-graphql-apollo-server-1ef999bfb38d/index.mdx

Standard setup for bootstrapping Apollo Client 2.0 in a React application connecting to a local GraphQL endpoint.

```javascript
import React from 'react'
import ReactDOM from 'react-dom'
import './index.css'
import App from './App'
import registerServiceWorker from './registerServiceWorker'
import { ApolloProvider } from 'react-apollo'
import { ApolloClient, HttpLink, InMemoryCache } from 'apollo-client-preset'

const httpLink = new HttpLink({ uri: 'http://localhost:4000/graphql' })

const client = new ApolloClient({
  link: httpLink,
  cache: new InMemoryCache(),
})

ReactDOM.render(
  <ApolloProvider client={client}>
    <App />
  </ApolloProvider>,
  document.getElementById('root'),
)
registerServiceWorker()
```


--------------------------------

### Create a new database with Prisma CLI

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-postgres-the-future-of-serverless-databases/index.mdx

Initialize and set up a new Prisma Postgres database directly from the terminal using the Prisma CLI.

```shell
# Create a new database
npx prisma@7.9.1 init --db
```


--------------------------------

### Initialize a new Nuxt project

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/introducing-prisma-nuxt/index.mdx

Initializes a fresh Nuxt application using the Nuxt CLI.

```shell
npx nuxi@latest init test-nuxt-app
```


--------------------------------

### Install TypeScript 7 with pnpm

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/typescript-7-native-compiler-faster-type-checking/index.mdx

Installs TypeScript 7 as a development dependency to test compiler performance in CI or local environments.

```bash
pnpm add -D typescript@7.0.2
```


--------------------------------

### Create and navigate to project directory

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/type-safe-js-with-jsdoc-typeSaf3js/index.mdx

Sets up a new working directory for the Prisma project.

```shell
mkdir awesome-project # Give your project a memorable name
cd awesome-project
```


--------------------------------

### Install prisma-compute agent skill

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-compute-config-file/index.mdx

Installs the Compute-specific agent skill from prisma/skills into the repository to enable AI agent deploy workflows.

```bash
bunx skills add prisma/skills --skill prisma-compute
```


--------------------------------

### Install nodemon using npm

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/introducing-graphql-nexus-code-first-graphql-server-development-ll6s1yy5cxl5/index.mdx

Installs nodemon as a development dependency for JavaScript projects to reload the server upon file updates.

```js
npm install --save-dev nodemon
```


--------------------------------

### Install ts-node-dev using npm

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/introducing-graphql-nexus-code-first-graphql-server-development-ll6s1yy5cxl5/index.mdx

Installs ts-node-dev as a development dependency for TypeScript projects to enable live reloading and type regeneration.

```js
npm install --save-dev ts-node-dev
```


--------------------------------

### Fetch sample users from /users endpoint

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-orm-8-nestjs/index.mdx

Sends a GET request to the local API endpoint to retrieve initialized sample users as JSON.

```bash
curl http://localhost:3000/users
```


--------------------------------

### Install Hono and testing dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/backend-prisma-typescript-orm-with-postgresql-rest-api-validation-dcba1ps7kip3/index.mdx

Installs Hono, Node.js server adapter, Zod validation packages, dotenv, and Vitest for development.

```sh
npm install hono @hono/node-server zod @hono/zod-validator dotenv
npm install vitest --save-dev
```


--------------------------------

### Install aws-sdk and cuid dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-remix-prisma-mongodb-4-l3mwep4zlim2/index.mdx

Installs the AWS SDK for interacting with S3 services and CUID for generating unique random filenames.

```sh
npm i aws-sdk cuid
```


--------------------------------

### Create the Prometheus configuration directory and file

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/metrics-tutorial-prisma-pmoldgq10kz/index.mdx

Create a `prometheus` folder at the project root and add a new `prometheus.yml` file inside it.

```shell
mkdir prometheus
touch prometheus/prometheus.yml
```


--------------------------------

### Create project directory for Postgres FTS demo

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/you-dont-need-elasticsearch-postgres-already-has-full-text-search/index.mdx

Create and navigate to a new directory named postgres-fts-demo for the demo project.

```bash
mkdir postgres-fts-demo
cd postgres-fts-demo
```


--------------------------------

### Install TailwindCSS, PostCSS, and Autoprefixer via npm

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/e2e-type-safety-graphql-react-1-I2GxIfxkSZ/index.mdx

Installs TailwindCSS, PostCSS, and Autoprefixer as developer dependencies, including the Tailwind CLI.

```sh
npm install -D tailwindcss postcss autoprefixer
```


--------------------------------

### Install NestJS Swagger dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/documenting-apis-mjjpZ7E7NkVP/index.mdx

Installs the required Swagger module and Swagger UI express package for NestJS API documentation.

```shell
npm install @nestjs/swagger swagger-ui-express
```


--------------------------------

### Initialize Prisma with SQLite datasource

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/sveltekit-prisma-kvCOEoeQlC/index.mdx

Initializes Prisma configuration, creating a prisma directory with schema.prisma and a .env file configured for SQLite.

```shell
npx prisma init --datasource-provider sqlite
```


--------------------------------

### Create a GraphQL server with express-graphql

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/graphql-server-basics-the-network-layer-51d97d21861/index.mdx

Sets up and starts a Node.js Express server on port 4000 using express-graphql middleware with GraphiQL enabled.

```javascript
const express = require('express')
const graphqlHTTP = require('express-graphql')
const { GraphQLSchema, GraphQLObjectType, GraphQLString } = require('graphql')

const app = express()

const schema = new GraphQLSchema({
  query: new GraphQLObjectType({
  name: 'Query',
  fields: {
    hello: {
      type: GraphQLString,
      resolve: (root, args, context, info) => {
        return 'Hello World'
      }
    }
  }
})

app.use('/graphql', graphqlHTTP({
  schema,
  graphiql: true // enable GraphiQL
}))

app.listen(4000)
```


--------------------------------

### Initialize Git repository and push to GitHub

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/database-access-on-the-edge-8F0t1s1BqOJE/index.mdx

Initializes the local repository and pushes your project files to GitHub. Replace `<username>` with your actual GitHub username before running the commands.

```bash
git init
git remote add origin https://github.com/<username>/prisma-edge-functions
git add .
git commit -m "initial commit"
git push -u origin main
```


--------------------------------

### Install Prisma 2 CLI globally using Yarn

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/announcing-prisma-2-zq1s745db8i5/index.mdx

Installs the Prisma 2 CLI globally on the system using Yarn.

```shell
yarn global add prisma2
```


--------------------------------

### Initialize Prisma with MySQL datasource provider

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-orm-support-for-edge-functions-is-now-in-preview/index.mdx

Initializes Prisma in the project, creating the prisma/schema.prisma and .env files configured for MySQL.

```bash
npx prisma init --datasource-provider mysql
```


--------------------------------

### Create a basic Express.js web server

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/graphql-server-basics-the-network-layer-51d97d21861/index.mdx

Initializes an Express application listening on port 3000 that responds with HTML to GET requests at the root endpoint.

```javascript
const express = require('express')
const app = express()

// respond with "hello world" when a GET request is received
app.get('/', function(req, res) {
  res.send('<h1>Hello World</h1>')
})
app.listen(3000)
```


--------------------------------

### Configure and instantiate Rust-free Prisma Client with PostgreSQL adapter

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-6-9-0-release/index.mdx

Enable queryCompiler and driverAdapters preview features in schema.prisma, install the adapter package, and instantiate PrismaClient with PrismaPg.

```prisma
generator client {
  provider        = "prisma-client-js"
  previewFeatures = ["queryCompiler", "driverAdapters"]
  output          = "../generated/prisma"
}
```

```shell
npm install @prisma/adapter-pg
```

```ts
import { PrismaClient } from './generated/prisma'
import { PrismaPg } from '@prisma/adapter-pg'

const adapter = new PrismaPg({ connectionString: env.DATABASE_URL })
const prisma = new PrismaClient({ adapter })
```


--------------------------------

### Run initial migration with Prisma Migrate

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-nextjs-graphql-prisma-3-clxbrcqppv/index.mdx

Creates database tables defined in your Prisma schema. Run this command after setting the database connection string in `.env`.

```shell
npx prisma migrate dev --name init

```


--------------------------------

### Install @nestjs/swagger dependency

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/nestjs-prisma-rest-api-7D056s1BmOL0/index.mdx

Installs the dedicated Swagger module for NestJS to document APIs with OpenAPI. In @nestjs/swagger v11, swagger-ui-express is included by default.

```shell
npm install @nestjs/swagger
```


--------------------------------

### Install aws-sdk package with npm

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-nextjs-graphql-prisma-4-1k1kc83x3v/index.mdx

Installs the AWS SDK library required to generate presigned upload URLs and interact with S3 services.

```shell
npm install aws-sdk
```


--------------------------------

### Configure and start @prisma/streams-server entrypoint

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/building-open-chat/index.mdx

Sets configuration defaults and bootstrap flags for @prisma/streams-server. Automatically checks for an existing local SQLite WAL and adds the R2 bootstrap argument on fresh instance boots.

```typescript
// @prisma/streams-server is the full runtime: SQLite WAL, segmenting,
// R2 upload, recovery, bearer-key auth. This entry just sets defaults.
import { existsSync } from "node:fs";

process.env.DS_HOST ??= "0.0.0.0";
// Keep the hot tier on /tmp; R2 is the durable tier, so losing /tmp is fine.
process.env.DS_ROOT ??= "/tmp/ds-data";
// Seal a segment at least every 5s, so an abrupt instance death can lose
// almost nothing rather than waiting to hit a size threshold.
process.env.DS_SEGMENT_MAX_INTERVAL_MS ??= "5000";

process.argv.push("--auth-strategy", "api-key");
// On a fresh instance (no local WAL yet), rehydrate history from R2.
if (!existsSync(`${process.env.DS_ROOT}/wal.sqlite`)) {
  process.argv.push("--bootstrap-from-r2");
}

await import("@prisma/streams-server/compute");
```


--------------------------------

### Start Hono Node.js server in src/index.ts

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/backend-prisma-typescript-orm-with-postgresql-rest-api-validation-dcba1ps7kip3/index.mdx

Starts the HTTP server using `@hono/node-server` on port 3000 using the app fetch handler.

```ts
import { serve } from "@hono/node-server";
import app from "./app";

serve(
  {
    fetch: app.fetch,
    port: 3000,
  },
  (info) => {
    console.log(`Server is running on http://localhost:${info.port}`);
  },
);
```


--------------------------------

### Create a Prisma project interactively

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-studio-migrations-view/index.mdx

Scaffolds a new Prisma project by answering interactive prompts for database provider, authoring format, and package manager.

```bash
npm create prisma@latest
```


--------------------------------

### Create a new project using npm create prisma

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/building-the-stack-for-the-next-million-products/index.mdx

Initializes a new Prisma project from the terminal.

```bash
npm create prisma@latest
```


--------------------------------

### Plan a database migration with prisma-next

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-next-early-access-write-your-contract-prompt-your-agent-ship-your-app/index.mdx

Runs the migration planner to generate deterministic migration files based on schema contract changes.

```bash
prisma-next migration plan
```


--------------------------------

### Install OpenTelemetry Jaeger exporter package

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/tracing-tutorial-prisma-pmkddgq1lm2/index.mdx

Installs the Jaeger trace exporter package required to export trace data from Node.js applications to Jaeger.

```shell
npm install @opentelemetry/exporter-jaeger
```


--------------------------------

### Export DATABASE_URL and run db:init

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-orm-8-nestjs/index.mdx

Exports the connection string directly in the shell environment and applies starter schema contracts. If a connection error occurs, wait a few seconds for the new database instance to finish starting.

```bash
export DATABASE_URL="<your PostgreSQL connection string>"
npm run db:init
```


--------------------------------

### Install class-validator and class-transformer

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/nestjs-prisma-validation-7D056s1kOla1/index.mdx

Installs the required dependencies for ValidationPipe to validate input data decorators and transform incoming JSON into DTO class instances.

```shell
npm install class-validator class-transformer
```


--------------------------------

### Install GraphQL Codegen dependencies

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/e2e-type-safety-graphql-react-4-JaHA8GbkER/index.mdx

Installs the core graphql library along with GraphQL Codegen CLI, TypeScript plugins, and typed-document-node as development dependencies.

```sh
npm i graphql
npm i -D @graphql-codegen/cli @graphql-codegen/typed-document-node @graphql-codegen/typescript @graphql-codegen/typescript-operations
```


--------------------------------

### Install and consume a shared Prisma extension package

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/client-extensions-preview-8t3w27xkrxxn/index.mdx

Installs an extension package published under the recommended prisma-extension naming convention and applies it to a PrismaClient instance.

```sh
npm install prisma-extension-find-or-create
```

```typescript
import { PrismaClient } from "@prisma/client";
import findOrCreate from "prisma-extension-find-or-create";

const prisma = new PrismaClient().$extends(findOrCreate);
const user = await prisma.user.findOrCreate({ /* ... */ });
```


--------------------------------

### Initialize Prisma ORM with custom client output

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/backend-prisma-typescript-orm-with-postgresql-data-modeling-tsjs1ps7kip1/index.mdx

Bootstraps Prisma ORM in the project with custom client generation targeting `../generated/prisma`. Creates `prisma/schema.prisma`, `prisma.config.ts`, and a `.env` file.

```sh
npx prisma init --output ../generated/prisma
```


--------------------------------

### Install React Apollo dependencies with Yarn

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/tutorial-render-props-in-react-apollo-2-1-199e9e2bd01e/index.mdx

Installs Apollo Client, React Apollo bindings, and GraphQL parsing libraries in the project's root directory.

```sh
cd ..
yarn add apollo-boost react-apollo graphql-tag graphql
```


--------------------------------

### Deprecated prisma2 package installation notice

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-2-beta-b7bcl0gd8d8e/index.mdx

Output message displayed when attempting to install the deprecated `prisma2` npm package, instructing users to switch to `@prisma/cli`.

```text
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   The package prisma2 has been renamed to @prisma/cli.      │
│                                                             │
│   Please uninstall prisma2 from your project or globally.   │
│   Then install @prisma/cli to continue using Prisma 2.0:    │
│                                                             │
│      # Uninstall old CLI                                    │
│      npm uninstall prisma2                                  │
│                                                             │
│      # Install new CLI                                      │
│      npm install @prisma/cli --save-dev                     │
│                                                             │
│      # Invoke via npx                                       │
│      npx prisma2 --help                                     │
│                                                             │
│   Learn more here: https://pris.ly/preview025               │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```


--------------------------------

### Install @prisma/client package

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-2-beta-b7bcl0gd8d8e/index.mdx

Installs Prisma Client as a dependency in your Node.js or TypeScript project. Re-generating the client after schema updates modifies the contents of this package locally.

```bash
npm install @prisma/client
```


--------------------------------

### Install ts-node dependency

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/fullstack-nextjs-graphql-prisma-oklidw1rhw/index.mdx

Installs ts-node as a development dependency to execute TypeScript seeding scripts outside Next.js's default ESNext module resolution.

```shell
npm install --save-dev ts-node
```


--------------------------------

### Install the latest Prisma CLI with npm

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/datamodel-v11-lrzqy1f56c90/index.mdx

Installs the latest version of the Prisma CLI globally. When running Prisma with Docker, upgrade the Docker image to 1.31.

```shell
npm install -g prisma
```


--------------------------------

### Seed database with sample data

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-studio-migrations-view/index.mdx

Populates the migrated database with seed rows to make history and records visible in Studio.

```bash
npm run db:seed
```


--------------------------------

### Scaffold a new project using npm create prisma@latest

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/prisma-next-early-access-write-your-contract-prompt-your-agent-ship-your-app/index.mdx

Scaffolds a new project with Prisma 8 along with built-in agent skills to eliminate the onboarding learning curve.

```bash
npm create prisma@latest
```


--------------------------------

### Install and configure @prisma/adapter-pg driver adapter

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/announcing-prisma-6-19-0/index.mdx

Install the PostgreSQL driver adapter package and pass it as an optional parameter to PrismaClient. This step is not required when using Prisma Postgres.

```shell
npm install @prisma/adapter-pg
```

```tsx
import { PrismaClient } from './generated/prisma'
import { PrismaPg } from '@prisma/adapter-pg'

const adapter = new PrismaPg({ connectionString: env.DATABASE_URL })
const prisma = new PrismaClient({ adapter })
```


--------------------------------

### Configure Apollo Client with react-apollo (Legacy Setup)

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/all-you-need-to-know-about-apollo-client-2-7e27e36d62fd/index.mdx

Legacy setup using Apollo Client 1.x where all client utilities and providers were imported solely from the react-apollo package.

```js
import { ApolloProvider, createNetworkInterface, ApolloClient } from 'react-apollo'

const networkInterface = createNetworkInterface({ uri })
const client = new ApolloClient({ networkInterface })

export default (
  <ApolloProvider client={client}>
    <App />
  </ApolloProvider>
)
```


--------------------------------

### Initialize and push GraphQL API repository to GitHub

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/e2e-type-safety-graphql-react-4-JaHA8GbkER/index.mdx

Example showing initialization and pushing of the GraphQL API repository using a concrete GitHub SSH repository URL.

```sh
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:sabinadams/e2e-type-safety-api.git
git push -u origin main
```


--------------------------------

### Start PostgreSQL database with Docker Compose

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/metrics-tutorial-prisma-pmoldgq10kz/index.mdx

Starts the PostgreSQL container on port 5432 in the foreground. Append -d to run in detached mode without stopping when closing the terminal.

```shell
docker-compose up
```


--------------------------------

### Start local development server and verify database query result

Source: https://github.com/prisma/web/blob/main/apps/blog/content/blog/build-applications-at-the-edge-with-prisma-orm-and-cloudflare-d1-preview/index.mdx

Start the Worker locally and check the resulting JSON response returned from the local database at http://localhost:8787.

```shell
npm run dev
```

```json
[{"id":1,"email":"jane@prisma.io","name":"Jane Doe (Local)"}]
```
