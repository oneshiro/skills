# Prisma — Postgres

Sourced snippets (14 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Install PostgreSQL 17 CLI tools on macOS

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/postgres/database/backups.mdx

Installs the PostgreSQL 17 client utilities using Homebrew and verifies the installation paths of pg_dump and pg_restore.

```bash
brew install postgresql@17
which pg_dump
which pg_restore
```


--------------------------------

### Example create-db CLI output

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/postgres/npx-create-db.mdx

Displays the CLI output after creating a temporary database, showing the database connection string and claim URL.

```text
┌  🚀 Creating a Prisma Postgres database
│
│  Provisioning a temporary database in us-east-1...
│  It will be automatically deleted in 24 hours, but you can claim it.
◇  Database created successfully!
│
●  Database Connection
│    Connection String:
│    postgresql://<username>:<password>@db.prisma.io:5432/postgres
│
◆  Claim your database →
│    Keep your database for free:
│    https://create-db.prisma.io?projectID=proj_...
└
```


--------------------------------

### Display CLI help and available options

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/postgres/npx-create-db.mdx

Displays all available create-db options, flags, and supported regions.

```npm
npx create-db@latest --help
```


--------------------------------

### Initialize a new project with Prisma

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/postgres/best-postgres-for-ai-apps.mdx

Run this command to quickly scaffold a new project using Prisma CLI.

```npm
npm create prisma@latest
```


--------------------------------

### Install PostgreSQL 17 client on Linux

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/postgres/database/backups.mdx

Updates apt package repositories, installs postgresql-client-17, and verifies the availability of pg_dump and pg_restore.

```bash
sudo apt-get update
sudo apt-get install postgresql-client-17
which pg_dump
which pg_restore
```


--------------------------------

### Coding agent prompt for Prisma Postgres setup

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/postgres/index.mdx

Prompt instructions for an AI coding agent to initialize a database, populate .env, wire the database client, and test the connection.

```text
Create a Prisma Postgres database for this project.

1. Run `npx create-db@latest`. It creates a temporary Prisma Postgres database without an account and prints a connection string plus a claim URL.
2. Put the connection string in `.env` as DATABASE_URL and wire it into whichever of Prisma ORM, Kysely, Drizzle, TypeORM, or node-postgres the project already uses (detect it from package.json; if none, ask me). Verify the connection with one trivial query such as `select 1`.
3. Remind me to open the claim URL to keep the database in my Prisma workspace.

Current docs: https://www.prisma.io/docs/postgres.md.
```


--------------------------------

### Display available CLI options with --help

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/postgres/npx-create-db.mdx

Run the command with the --help or -h flag to view all available CLI options and supported regions.

```npm
npx create-db@latest --help
```

```text
npx create-db@latest [options]

Options:
  --region <region>, -r <region>  Specify a region
                                  Available regions:
                                  ap-southeast-1, ap-northeast-1,
                                  eu-central-1, eu-west-3,
                                  us-east-1, us-west-1

  --interactive, -i               Run in interactive mode

  --help, -h                      Show this help message
```


--------------------------------

### Install package for raw SQL

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/postgres/database/serverless-driver.mdx

Install the serverless driver package when using raw SQL queries without Prisma ORM.

```npm
npm install @prisma/ppg
```


--------------------------------

### Uninstall Accelerate and install PPG serverless adapter for Prisma 6.19

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/postgres/database/switch-from-accelerate.mdx

Removes Accelerate and installs Prisma 6.19.3 alongside @prisma/adapter-ppg and @prisma/ppg.

```npm
npm uninstall @prisma/extension-accelerate
npm install prisma@6.19.3 @prisma/client@6.19.3 @prisma/adapter-ppg @prisma/ppg
```


--------------------------------

### Initialize Terraform Working Directory

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/postgres/iac/terraform.mdx

Initializes the Terraform working directory and downloads the required prisma-postgres provider plugin.

```bash
terraform init
```


--------------------------------

### Uninstall Accelerate and install PPG serverless adapter for Prisma ORM 7

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/postgres/database/switch-from-accelerate.mdx

Removes Accelerate and installs @prisma/adapter-ppg and @prisma/ppg for serverless driver connections.

```npm
npm uninstall @prisma/extension-accelerate
npm install @prisma/adapter-ppg @prisma/ppg
```


--------------------------------

### Run prisma init --db

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/postgres/troubleshooting.mdx

Fails when using an outdated cached version of the Prisma CLI that does not recognize the --db flag.

```npm
npx prisma init --db
```


--------------------------------

### Verify PostgreSQL CLI tools installation on Windows

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/postgres/database/backups.mdx

Verifies that pg_dump and pg_restore are available in the system PATH on Windows following manual installation of Command Line Tools.

```bash
# Download from the official PostgreSQL website:
# https://www.postgresql.org/download/windows/
# During installation, select "Command Line Tools".
# Then verify with:

where pg_dump
where pg_restore
```


--------------------------------

### Create a database backup file using pg_dump

Source: https://github.com/prisma/web/blob/main/apps/docs/content/docs/postgres/database/backups.mdx

Exports a manual database backup to mydatabase.bak using pg_dump over a direct Prisma Postgres connection string.

```bash
pg_dump --dbname="postgres://USER:PASSWORD@db.prisma.io:5432/?sslmode=require" > ./mydatabase.bak
```
