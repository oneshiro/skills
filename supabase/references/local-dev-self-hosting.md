# Supabase — Local Dev, Self-Hosting & Deployment

Sourced snippets (25 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Start a new deployment with Postgres 17

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/self-hosting/postgres-upgrade-17.mdx

Starts a new self-hosted Supabase instance with Postgres 17. No configuration override is needed for fresh installations without existing data.

```sh
sh run.sh start
```


--------------------------------

### Configure shared extensions and test helpers in 000-setup-tests-hooks.sql

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/testing/pgtap-extended.mdx

Installs necessary testing extensions including pgtap, pg_tle, http, dbdev, and basejump-supabase_test_helpers, then verifies the setup with an always-green test.

```sql
-- install tests utilities
-- install pgtap extension for testing
create extension if not exists pgtap with schema extensions;
/*
---------------------
---- install dbdev ----
----------------------
Requires:
  - pg_tle: https://github.com/aws/pg_tle
  - pgsql-http: https://github.com/pramsey/pgsql-http
*/
create extension if not exists http with schema extensions;
create extension if not exists pg_tle;
drop extension if exists "supabase-dbdev";
select pgtle.uninstall_extension_if_exists('supabase-dbdev');
select
    pgtle.install_extension(
        'supabase-dbdev',
        resp.contents ->> 'version',
        'PostgreSQL package manager',
        resp.contents ->> 'sql'
    )
from extensions.http(
    (
        'GET',
        'https://api.database.dev/rest/v1/'
        || 'package_versions?select=sql,version'
        || '&package_name=eq.supabase-dbdev'
        || '&order=version.desc'
        || '&limit=1',
        array[
            ('apiKey', 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6InhtdXB0cHBsZnZpaWZyYndtbXR2Iiwicm9sZSI6ImFub24iLCJpYXQiOjE2ODAxMDczNzIsImV4cCI6MTk5NTY4MzM3Mn0.z2CN0mvO2No8wSi46Gw59DFGCTJrzM0AQKsu_5k134s')::extensions.http_header
        ],
        null,
        null
    )
) x,
lateral (
    select
        ((row_to_json(x) -> 'content') #>> '{}')::json -> 0
) resp(contents);
create extension "supabase-dbdev";
select dbdev.install('supabase-dbdev');
drop extension if exists "supabase-dbdev";
create extension "supabase-dbdev";
-- Install test helpers
select dbdev.install('basejump-supabase_test_helpers');
create extension if not exists "basejump-supabase_test_helpers" version '0.0.6';

-- Verify setup with a no-op test
begin;
select plan(1);
select ok(true, 'Pre-test hook completed successfully');
select * from finish();
rollback;
```


--------------------------------

### Start the Supabase stack using run.sh

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/self-hosting/docker.mdx

Navigates into the created project directory and starts all configured Supabase Docker containers.

```sh
cd supabase-project && \
sh run.sh start
```


--------------------------------

### Install Supabase CLI beta on Windows using Scoop

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/cli/getting-started.mdx

Adds the Supabase bucket and installs supabase-beta using Scoop on Windows.

```powershell
scoop bucket add supabase https://github.com/supabase/scoop-bucket.git
scoop install supabase-beta
```


--------------------------------

### Start a local project with excluded services using --exclude

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/running-multiple-local-projects.mdx

Starts the local Supabase stack while excluding optional services like Studio and Mailpit. The Postgres database cannot be excluded, and excluding REST requires excluding Studio as well.

```bash
supabase start --exclude studio,mail
```


--------------------------------

### Start local project in the native runtime

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/docker-and-native-runtimes.mdx

Starts a Supabase local project using the native runtime.

```bash
supabase start --runtime native
```


--------------------------------

### Start a named test project with supabase start --stack

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/running-multiple-local-projects.mdx

Starts an additional named local project in the same directory to keep test runs separate from development data.

```bash
supabase start --stack test
```


--------------------------------

### Create a pre-test setup file with supabase test new

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/testing/pgtap-extended.mdx

Generates a new test hook file named 000-setup-tests-hooks to execute first in alphabetical test order for global environment configuration.

```bash
supabase test new 000-setup-tests-hooks
```


--------------------------------

### Start a named dev project with supabase start --stack

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/running-multiple-local-projects.mdx

Starts a named local project for the current app directory. Named local projects run independently of the default local project.

```bash
supabase start --stack dev
```


--------------------------------

### Initialize project with SUPABASE_EXPERIMENTAL_STACK=1

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/running-multiple-local-projects.mdx

Initializes a new Supabase project without fixed port keys in config.toml, writing [experimental] stack = true to allow multiple local projects to run simultaneously.

```bash
SUPABASE_EXPERIMENTAL_STACK=1 supabase init
```


--------------------------------

### Verify custom extension installation in database container

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/self-hosting/custom-postgres-extensions.mdx

Execute psql within the database container to create and test an extension function. The example demonstrates verifying pg_uuidv7 alongside its expected output.

```sh
docker compose exec db psql -U postgres \
  -c "CREATE EXTENSION IF NOT EXISTS pg_uuidv7;" \
  -c "SELECT uuid_generate_v7();"
```

```text
           uuid_generate_v7
--------------------------------------
 019f897b-1003-7175-b9b5-be46fc0c3990
(1 row)
```


--------------------------------

### Run automated Linux setup script for Docker

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/self-hosting/docker.mdx

Installs Docker prerequisites, fetches the Supabase configuration files, generates secrets and JWT signing keys, and pulls required Docker images on supported Linux distributions.

```sh
curl -fsSL https://supabase.link/setup.sh | sh
```


--------------------------------

### Project directory layout for environment variables and config

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/managing-config.mdx

Place .env and .env.example files at the project root alongside the supabase/config.toml file.

```text
.
├── .env
├── .env.example
└── supabase
    └── config.toml
```


--------------------------------

### Set up supabase-dbdev package manager in PostgreSQL

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/testing/pgtap-extended.mdx

Installs the http and pg_tle extensions, fetches the latest supabase-dbdev package from database.dev, and initializes the extension. It drops and recreates the extension to ensure a clean installation.

```sql
create extension if not exists http with schema extensions;
create extension if not exists pg_tle;
drop extension if exists "supabase-dbdev";
select pgtle.uninstall_extension_if_exists('supabase-dbdev');
select
    pgtle.install_extension(
        'supabase-dbdev',
        resp.contents ->> 'version',
        'PostgreSQL package manager',
        resp.contents ->> 'sql'
    )
from extensions.http(
    (
        'GET',
        'https://api.database.dev/rest/v1/'
        || 'package_versions?select=sql,version'
        || '&package_name=eq.supabase-dbdev'
        || '&order=version.desc'
        || '&limit=1',
        array[
            ('apiKey', 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6InhtdXB0cHBsZnZpaWZyYndtbXR2Iiwicm9sZSI6ImFub24iLCJpYXQiOjE2ODAxMDczNzIsImV4cCI6MTk5NTY4MzM3Mn0.z2CN0mvO2No8wSi46Gw59DFGCTJrzM0AQKsu_5k134s')::extensions.http_header
        ],
        null,
        null
    )
) x,
lateral (
    select
        ((row_to_json(x) -> 'content') #>> '{}')::json -> 0
) resp(contents);
create extension "supabase-dbdev";
select dbdev.install('supabase-dbdev');

-- Drop and recreate the extension to ensure a clean installation
drop extension if exists "supabase-dbdev";
create extension "supabase-dbdev";
```


--------------------------------

### Install Supabase CLI on Windows with Scoop

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/cli/getting-started.mdx

Adds the official Supabase bucket and installs the Supabase CLI on Windows using Scoop.

```powershell
scoop bucket add supabase https://github.com/supabase/scoop-bucket.git
scoop install supabase
```


--------------------------------

### Enable extension as superuser using init scripts

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/self-hosting/custom-postgres-extensions.mdx

Mount an initialization SQL script to /docker-entrypoint-initdb.d/migrations/ to create the extension automatically as supabase_admin on first boot. Init scripts only execute when the data directory is empty.

```yaml
db:
  volumes:
    # ...keep the existing mounts (the data dir, roles.sql, etc.) and add:
    - ./volumes/db/pg_uuidv7.sql:/docker-entrypoint-initdb.d/migrations/99-pg_uuidv7.sql:Z
```

```sql
CREATE EXTENSION IF NOT EXISTS pg_uuidv7;
```


--------------------------------

### Initialize local Supabase repository with supabase init

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/deployment/managing-environments.mdx

Initializes a local repository with the Supabase CLI, creating a new supabase directory.

```bash
supabase init
```


--------------------------------

### Install Supabase CLI beta on macOS using Homebrew

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/cli/getting-started.mdx

Installs and links the separate supabase-beta package using Homebrew on macOS.

```sh
brew install supabase/tap/supabase-beta
brew link --overwrite supabase-beta
```


--------------------------------

### Output project start metadata in JSON format

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/running-multiple-local-projects.mdx

Returns JSON-formatted metadata for scripts and agents, including project id, runtime, lazy services, endpoints, and environment variables.

```bash
supabase start --output-format json
```


--------------------------------

### Start local project in the Docker runtime

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/docker-and-native-runtimes.mdx

Requires Docker when starting a new local Supabase project.

```bash
supabase start --runtime docker
```


--------------------------------

### Install Supabase CLI on macOS with Homebrew

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/cli/getting-started.mdx

Installs the Supabase CLI on macOS using the official Homebrew tap.

```sh
brew install supabase/tap/supabase
```


--------------------------------

### Start Supabase services

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/self-hosting/docker.mdx

Starts all Supabase services in detached mode and waits until they are healthy. Execute this from the directory containing docker-compose.yml.

```sh
sh run.sh start
```


--------------------------------

### Install Supabase CLI beta via npm

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/cli/getting-started.mdx

Installs the Supabase CLI pre-release beta build as a project dev dependency.

```sh
npm install supabase@beta --save-dev
```


--------------------------------

### Initialize and restore local Postgres database from backup

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/local-development/restoring-downloaded-backup.mdx

Initializes Supabase, sets the targeted Postgres version, and starts the database from a backup file. Requires Postgres version 15.1.0.55 or later for local restore compatibility.

```sh
supabase init
echo '15.6.1.115' > supabase/.temp/postgres-version
supabase db start --from-backup db_cluster.backup
```


--------------------------------

### Commit changes and start local Supabase stack

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/deployment/managing-environments.mdx

Commits the initial local changes to Git and starts the local Supabase development containers.

```bash
git add .
git commit -m "init supabase"
supabase start
```
