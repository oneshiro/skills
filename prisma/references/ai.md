# Prisma — AI

Sourced snippets (18 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Install fx and Sign In

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/tools/mcp-server.mdx

Downloads and installs fx via the setup script, then initiates login.

```bash
curl -fsSL https://fx.sh/setup.sh | bash
fx login
```


--------------------------------

### Bootstrap Database with Prompt via Prisma CLI

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/index.mdx

Initializes a new database setup using a natural language prompt with Prisma CLI.

```npm
npx prisma@prev init --prompt "Create a habit tracker application"
```


--------------------------------

### Initialize Prisma and create cloud database with CLI

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/prompts/nextjs.mdx

Scaffolds Prisma files to the custom output location and creates a Prisma Postgres database.

```bash
# Initialize Prisma and scaffold the Prisma files
npx prisma init --output ../app/generated/prisma

# Then create a Prisma Postgres database
npx create-db
```


--------------------------------

### Install UploadThing

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/tutorials/typefully-clone.mdx

Install UploadThing and its React integration packages.

```npm
npm install uploadthing @uploadthing/react
```


--------------------------------

### Verify Ollama API tags endpoint

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/tutorials/typefully-clone.mdx

Sends a GET request to the local Ollama API to confirm that gemma3:4b is installed and inspect the returned JSON response.

```bash
curl http://localhost:11434/api/tags
```

```json
{
  "models": [{
    "name": "gemma3:4b",
    "family": "gemma3",
    "parameter_size": "4.3B",
    "quantization_level": "Q4_K_M"
  }]
}
```


--------------------------------

### Prompt for adding Lucide React icons to the UI

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/tutorials/linktree-clone.mdx

Guides the installation of lucide-react and the addition of icons to view buttons, delete buttons, and empty list states.

```markdown
Add Lucide React icons to improve the UI.

First install: npm install lucide-react

Add icons to these elements:

- View button: ExternalLink icon
- Delete button: Trash2 icon (replace text with icon)
- Empty links state: Link icon

Import icons from 'lucide-react' and use with size prop (e.g., size={18}).

Keep buttons minimal — only add icons where they improve clarity.
```


--------------------------------

### List available Prisma skills before installing

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/tools/skills.mdx

Lists the skills available in the Prisma repository prior to installation.

```npm
npx skills add prisma/skills --list
```


--------------------------------

### Initialize Prisma with custom output and create database

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/prompts/nuxt.mdx

Scaffolds Prisma configuration files targeting a custom generated client directory and provisions a Prisma Postgres database.

```bash
# Initialize Prisma and scaffold the Prisma files
npx prisma init --output ./generated

# Then create a Prisma Postgres database
npx create-db
```


--------------------------------

### Install Prisma, PostgreSQL adapter, and dev dependencies

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/prompts/nuxt.mdx

Installs the required production packages including Prisma Client v7, PostgreSQL adapter, pg, and dotenv, along with development dependencies.

```bash
# Production dependencies
npm install @prisma/client@7 @prisma/adapter-pg pg dotenv

# Dev dependencies
npm install -D prisma@prev @types/pg tsx
```


--------------------------------

### List installed skills in project

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/tools/skills.mdx

Lists the agent skills currently installed in your project.

```npm
npx skills list
```


--------------------------------

### Install Prisma and PostgreSQL adapter dependencies

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/prompts/nextjs.mdx

Installs the required development and production dependencies for Prisma with the PostgreSQL driver adapter.

```bash
# Dev dependencies
npm install prisma@prev tsx --save-dev

# Production dependencies
npm install @prisma/adapter-pg @prisma/client@7 dotenv
```


--------------------------------

### Install a specific Prisma skill

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/tools/skills.mdx

Installs only a specific skill from the registry using the --skill flag.

```npm
npx skills add prisma/skills --skill prisma-client-api
```


--------------------------------

### Launch Prisma Studio with npm run db:studio

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/prompts/astro.mdx

Opens Prisma Studio at localhost:5555 to inspect tables such as User and review stored database records.

```bash
npm run db:studio
```


--------------------------------

### Test setup with npm script

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/prompts/nextjs.mdx

Runs the database test script defined in package.json to verify the connection and configuration.

```bash
npm run db:test
```


--------------------------------

### Prompt Codex to set up Prisma ORM

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/tools/codex.mdx

Example prompt instructing Codex to configure Prisma ORM with the appropriate database adapter.

```text
Set up Prisma ORM in this project with the right database adapter.
```


--------------------------------

### Verify setup with test script in scripts/test-database.ts

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/prompts/nextjs.mdx

Loads environment variables and checks the connection to the Prisma Postgres database.

```typescript
import "dotenv/config"; // ✅ CRITICAL: Load environment variables
import prisma from "../lib/prisma";

async function testDatabase() {
  console.log("🔍 Testing Prisma Postgres connection...\n");

  try {
    // Test 1: Check connection
    console.log("✅ Connected to database!");
```


--------------------------------

### Create a Next.js Project

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/prompts/nextjs.mdx

Initialize a new Next.js project using `create-next-app` and change into the project directory prior to adding Prisma.

```bash
npx create-next-app@latest my-app
cd my-app
```


--------------------------------

### Initialize a new Nuxt project

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/ai/prompts/nuxt.mdx

Initializes a new Nuxt application named hello-prisma using nuxi and changes into the project directory.

```bash
npx nuxi@latest init hello-prisma
cd hello-prisma
```
