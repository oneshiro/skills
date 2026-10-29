# Supabase — Blog, Examples & Misc

Sourced snippets (163 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Install dependencies, configure environment, and start all applications

Source: https://github.com/supabase/supabase/blob/master/DEVELOPERS.md

Install dependencies at the root workspace, create the local environment file for www, and start all applications concurrently using Turborepo.

```sh
pnpm install # install dependencies
```

```sh
cp apps/www/.env.local.example apps/www/.env.local
```

```sh
pnpm dev # start all the applications
```


--------------------------------

### Install dependencies and run the development server with npm

Source: https://github.com/supabase/supabase/blob/master/apps/kb/src/content/guides/sample-guide.mdx

Installs the required package dependencies and starts the local development server.

```bash
npm install
npm run dev
```


--------------------------------

### Start development from apps/design-system directory

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/README.md

Sets up environment variables, installs dependencies, builds registry and Velite content, and starts the dev server from within apps/design-system.

```bash
# Copy local env vars (sets NEXT_PUBLIC_BASE_PATH for asset URLs)
cp .env.local.example .env.local
# Install dependencies
pnpm i
# Build the registry and Velite content, then start the dev servers
pnpm dev
```


--------------------------------

### Copy environment files and start local Supabase

Source: https://github.com/supabase/supabase/blob/master/apps/ui-library/content/docs/starters/saas-starter.mdx

Copies example environment files and initializes the local Supabase database and migrations. Requires Docker and the Supabase CLI to be installed.

```bash
cp .env.example .env
cp .env.local.example .env.local
pnpm supabase:start
```


--------------------------------

### Start development from repository root

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/README.md

Copies local environment variables, installs dependencies, builds registry and Velite content, and starts development servers from the repo root.

```bash
# Copy local env vars (sets NEXT_PUBLIC_BASE_PATH for asset URLs)
cp apps/design-system/.env.local.example apps/design-system/.env.local
# Move into the design-system app
cd apps/design-system
# Install dependencies
pnpm i
# Build the registry and Velite content, then start the dev servers
pnpm dev
```


--------------------------------

### Install dependencies and run studio dev server with npm

Source: https://github.com/supabase/supabase/blob/master/apps/studio/README.md

Installs project dependencies and starts the Supabase Studio dashboard in development mode.

```bash
npm install
npm run dev
```


--------------------------------

### Install the Supabase client for TanStack Start

Source: https://github.com/supabase/supabase/blob/master/apps/ui-library/content/docs/getting-started/quickstart.mdx

Adds the Supabase client files and dependencies to the project using the shadcn registry URL.

```bash
npx shadcn@latest add https://supabase.com/library/r/supabase-client-tanstack.json
```


--------------------------------

### Install Vitest and initialize local Supabase environment

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2025-08-16-testing-for-vibe-coders-from-zero-to-production-confidence.mdx

Installs testing dependencies and initializes local Supabase development. Pulls the remote schema into local migration files and starts local services.

```bash
npm install vitest @supabase/supabase-js --save-dev
supabase init
supabase link --project-ref YOUR_PROJECT_ID
supabase db pull
supabase start
```


--------------------------------

### Install cmdk dependency for manual setup

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/command.mdx

Install the cmdk package before copying the component source files into your project.

```bash
npm install cmdk
```


--------------------------------

### Start simple HTTP server with Python

Source: https://github.com/supabase/supabase/blob/master/examples/storage/protomaps/README.md

Starts a local web server to serve index.html on port 8000.

```bash
python3 -m http.server
```


--------------------------------

### Start development server and run tests with pnpm

Source: https://github.com/supabase/supabase/blob/master/apps/studio/README.md

Requires Node v22 in the studio directory. Provides installation, development server startup, mise runner commands for internal contributors, and test execution commands.

```bash
# You'll need to be on Node v22
# in /studio

## For external contributors
pnpm install # install dependencies
pnpm run dev # start dev server

## For internal contributors
## First clone the private supabase/platform repo and follow instructions for setting up mise
mise studio  # Run from supabase/platform alongside `mise infra`

## For all
pnpm run test # run tests
pnpm run test -- --watch # run tests in watch mode
```


--------------------------------

### Install react-resizable-panels dependency manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/resizable.mdx

Install the underlying react-resizable-panels package for manual setup.

```bash
npm install react-resizable-panels
```


--------------------------------

### Install Radix UI Tooltip dependency

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/tooltip.mdx

Install the underlying Radix UI Tooltip primitive for manual setup.

```bash
npm install @radix-ui/react-tooltip
```


--------------------------------

### Install Radix UI Toggle dependency

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/toggle.mdx

Install the underlying @radix-ui/react-toggle dependency for manual component setup.

```bash
npm install @radix-ui/react-toggle
```


--------------------------------

### Install Radix UI Switch dependency

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/switch.mdx

Install the underlying Radix UI switch package for manual setup.

```bash
npm install @radix-ui/react-switch
```


--------------------------------

### Install Radix UI Avatar primitive manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/avatar.mdx

Install the underlying @radix-ui/react-avatar dependency for manual component setup.

```bash
npm install @radix-ui/react-avatar
```


--------------------------------

### Start local database for development

Source: https://github.com/supabase/supabase/blob/master/examples/database/employees/README.md

Starts the local Supabase database instance using the Supabase CLI.

```bash
npx supabase db start
```


--------------------------------

### Install Radix UI Dropdown Menu dependency manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/dropdown-menu.mdx

Install the underlying @radix-ui/react-dropdown-menu primitive package for manual component setup.

```bash
npm install @radix-ui/react-dropdown-menu
```


--------------------------------

### Install Radix UI Aspect Ratio dependency manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/aspect-ratio.mdx

Install the required Radix UI Aspect Ratio package when performing manual component setup.

```bash
npm install @radix-ui/react-aspect-ratio
```


--------------------------------

### Install vaul dependency manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/drawer.mdx

Install the vaul package as a dependency for manual component setup.

```bash
npm install vaul
```


--------------------------------

### Verify psql installation on Windows

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/_partials/postgres_installation.mdx

Check if psql is accessible from the Windows terminal after installation and PATH setup.

```sh
psql --version
```


--------------------------------

### Set up and run Docker containers for Supabase Studio

Source: https://github.com/supabase/supabase/blob/master/DEVELOPERS.md

Navigate to the docker directory, create a local environment configuration by copying .env.example, and initialize containers using docker compose up. The local Supabase instance becomes accessible at http://localhost:8082 once startup completes.

```sh
cd docker
```

```sh
cp .env.example .env
```

```sh
docker compose up
```


--------------------------------

### Install Radix UI Tabs dependency manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/tabs.mdx

Install the underlying @radix-ui/react-tabs package for manual component setup.

```bash
npm install @radix-ui/react-tabs
```


--------------------------------

### Start development server

Source: https://github.com/supabase/supabase/blob/master/apps/ui-library/content/docs/starters/saas-starter.mdx

Starts the Next.js local development server in another terminal.

```bash
pnpm dev
```


--------------------------------

### Set up Ubuntu migration VM with PostgreSQL client tools

Source: https://github.com/supabase/supabase/blob/master/apps/kb/src/content/guides/migrate-from-postgres.mdx

Installs Postgres client tools, tmux, and monitoring utilities on an Ubuntu VM, then attaches to or creates a tmux session.

```bash
# Install Postgres client and tools
sudo apt update
sudo apt install software-properties-common
sudo sh -c 'echo "deb http://apt.Postgres.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
wget --quiet -O - https://www.Postgres.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt update
sudo apt install Postgres-client-17 tmux htop iotop moreutils

# Start or attach to tmux session
tmux a -t migration || tmux new -s migration
```


--------------------------------

### Launch a new project with Supabase bootstrap

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2024-04-15-supabase-bootstrap.mdx

Spins up a new hosted Supabase project from starter templates and links it to your local environment without needing a pre-installed CLI.

```bash
npx supabase bootstrap
```


--------------------------------

### Start Docker development environment

Source: https://github.com/supabase/supabase/blob/master/apps/studio/README.md

Navigates to the docker directory and launches the local development compose stack.

```bash
cd ..
cd docker
docker compose -f docker-compose.yml -f ./dev/docker-compose.dev.yml up
```


--------------------------------

### Start the development server with pnpm

Source: https://github.com/supabase/supabase/blob/master/apps/kb/AGENTS.md

Run the local Astro development server from either the project root or the apps/kb directory.

```bash
# From the root directory of the project
pnpm dev:kb

# From the apps/kb directory
pnpm dev
```


--------------------------------

### Create a TanStack Start app with shadcn

Source: https://github.com/supabase/supabase/blob/master/apps/ui-library/content/docs/getting-started/quickstart.mdx

Initializes a new TanStack Start project configured with Tailwind CSS, import aliases, and shadcn/ui, then navigates into the project directory.

```bash
npx shadcn@latest init --template start --name my-app --base radix
cd my-app
```


--------------------------------

### Install Calendar manual dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/calendar.mdx

Install react-day-picker and date-fns dependencies required for manual installation.

```bash
npm install react-day-picker date-fns
```


--------------------------------

### Install Radix UI Navigation Menu dependency

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/navigation-menu.mdx

Install the required Radix UI navigation menu primitive for manual component setup.

```bash
npm install @radix-ui/react-navigation-menu
```


--------------------------------

### Install PGlite and Transformers dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2024-08-29-in-browser-semantic-search-pglite.mdx

Installs the required client-side database and transformer packages.

```bash
npm install @electric-sql/pglite @huggingface/transformers
```


--------------------------------

### Set up database schema, RLS policies, Realtime, and Storage

Source: https://github.com/supabase/supabase/blob/master/examples/user-management/vue3-user-management/README.md

Creates the profiles table with Row Level Security policies, configures Realtime replication, and initializes the avatars storage bucket.

```sql
-- Create a table for public "profiles"
create table profiles (
  id uuid references auth.users not null,
  updated_at timestamp with time zone,
  username text unique,
  avatar_url text,
  website text,

  primary key (id),
  unique(username),
  constraint username_length check (char_length(username) >= 3)
);

alter table profiles enable row level security;

create policy "Public profiles are viewable by everyone."
  on profiles for select
  using ( true );

create policy "Users can insert their own profile."
  on profiles for insert
  with check ( (select auth.uid()) = id );

create policy "Users can update own profile."
  on profiles for update
  using ( (select auth.uid()) = id );

-- Set up Realtime!
begin;
  drop publication if exists supabase_realtime;
  create publication supabase_realtime;
commit;
alter publication supabase_realtime add table profiles;

-- Set up Storage!
insert into storage.buckets (id, name)
values ('avatars', 'avatars');

create policy "Avatar images are publicly accessible."
  on storage.objects for select
  using ( bucket_id = 'avatars' );

create policy "Anyone can upload an avatar."
  on storage.objects for insert
  with check ( bucket_id = 'avatars' );
```


--------------------------------

### Example migration filename

Source: https://github.com/supabase/supabase/blob/master/examples/prompts/database-create-migration.md

Demonstrates the required naming format `YYYYMMDDHHmmss_short_description.sql` using a UTC timestamp and descriptive slug.

```text
20240906123045_create_profiles.sql

```


--------------------------------

### Install Radix UI Progress dependency

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/progress.mdx

Install the underlying @radix-ui/react-progress package as the first step of manual installation.

```bash
npm install @radix-ui/react-progress
```


--------------------------------

### Install @supabase/server using Yarn

Source: https://github.com/supabase/supabase/blob/master/apps/docs/docs/ref/server/installing.mdx

Installs the @supabase/server package using Yarn.

```sh
yarn add @supabase/server
```


--------------------------------

### Set up a new React application with supabase-js

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2021-03-31-supabase-cli.mdx

Creates a fresh React app using npm, navigates to the project directory, and installs the @supabase/supabase-js library.

```bash
# create a fresh React app
npx create-react-app react-demo --use-npm

# move into the new folder
cd react-demo

# Save the install supabase-js library
npm install --save @supabase/supabase-js
```


--------------------------------

### Reset project starter code with npm

Source: https://github.com/supabase/supabase/blob/master/examples/auth/expo-social-auth/README.md

Moves starter code into an app-example directory and generates a blank app directory to start fresh development.

```bash
npm run reset-project
```


--------------------------------

### Send GET request with competition parameters

Source: https://github.com/supabase/supabase/blob/master/examples/edge-functions/supabase/functions/get-tshirt-competition/README.md

Example URL showing how to pass required query parameters (email, twitter, size, and answer) to the GET T-Shirt competition endpoint.

```text
https://obuldanrptloktxcffvn.supabase.co/functions/v1/get-tshirt-competition?email=testr@test.de&twitter=thorwebdev&size=2XL&answer=20
```


--------------------------------

### Install @radix-ui/react-context-menu manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/context-menu.mdx

Installs the underlying Radix UI context menu primitive required when manually setting up the component.

```bash
npm install @radix-ui/react-context-menu
```


--------------------------------

### Install @supabase/server using pnpm

Source: https://github.com/supabase/supabase/blob/master/apps/docs/docs/ref/server/installing.mdx

Installs the @supabase/server package using pnpm.

```sh
pnpm add @supabase/server
```


--------------------------------

### Create a TanStack Start app

Source: https://github.com/supabase/supabase/blob/master/apps/ui-library/content/docs/tanstack/headless-app.mdx

Initializes a new TanStack Start application using the shadcn CLI template and navigates into the newly created project folder.

```bash
pnpm dlx shadcn@latest init --template start --name my-app
cd my-app
```


--------------------------------

### Install the password authentication block

Source: https://github.com/supabase/supabase/blob/master/apps/ui-library/content/docs/getting-started/quickstart.mdx

Installs the password-based authentication block files and their UI dependencies from the registry.

```bash
npx shadcn@latest add https://supabase.com/library/r/password-based-auth-tanstack.json
```


--------------------------------

### Install @rneui/themed

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2023-11-16-react-native-authentication.mdx

Installs the @rneui/themed package to provide cross-platform button and input UI elements.

```bash
npm install @rneui/themed
```


--------------------------------

### Install @supabase/supabase-js with npm

Source: https://github.com/supabase/supabase/blob/master/examples/with-cloudflare-workers/README.md

Installs the Supabase JavaScript client package into the project.

```bash
npm i @supabase/supabase-js
```


--------------------------------

### Create Astro Project with Basics Template

Source: https://github.com/supabase/supabase/blob/master/apps/kb/README.md

Initializes a new Astro project using the official basics starter template.

```sh
npm create astro@latest -- --template basics
```


--------------------------------

### Install Input OTP manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/input-otp.mdx

Install the input-otp dependency and update tailwind.config.js with caret-blink animations.

```bash
npm install input-otp
```

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  theme: {
    extend: {
      keyframes: {
        'caret-blink': {
          '0%,70%,100%': { opacity: '1' },
          '20%,50%': { opacity: '0' },
        },
      },
      animation: {
        'caret-blink': 'caret-blink 1.25s ease-out infinite',
      },
    },
  },
}
```


--------------------------------

### Pipe setup instructions to Claude

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2026-04-01-supabase-docs-over-ssh.mdx

Streams setup instructions directly to Claude to allow the agent to configure its own Supabase documentation instructions.

```bash
ssh supabase.sh setup | claude
```


--------------------------------

### Install project dependencies

Source: https://github.com/supabase/supabase/blob/master/examples/user-management/solid-user-management/README.md

Run this command to install the necessary npm dependencies for the SolidJS application.

```bash
$ npm install
```


--------------------------------

### Role Context Format Example

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2024-04-11-postgres-roles-and-privileges.mdx

Example showing how instructions specify which role terminal should execute subsequent commands.

```bash
# as junior_dev
postgres=> this command should be executed from the junior_dev's terminal
```


--------------------------------

### Install Select via shadcn-ui CLI

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/select.mdx

Add the Select component to your project using the shadcn-ui CLI.

```bash
npx shadcn-ui@latest add select
```


--------------------------------

### Run Supabase stdio MCP Server via npx

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2025-10-03-remote-mcp-server.mdx

Runs the Supabase MCP server locally over standard I/O. Requires Node.js installed in the environment and manual authentication token setup.

```bash
npx -y @supabase/mcp-server-supabase@latest ...
```


--------------------------------

### Configure Supabase Environment Variables in .env.local

Source: https://github.com/supabase/supabase/blob/master/apps/ui-library/content/docs/react/client.mdx

Defines the environment variables generated in .env.local after installing the Supabase React block. Populate these with values from the Supabase dashboard or from local CLI output (supabase start / status).

```env
VITE_SUPABASE_URL=
VITE_SUPABASE_PUBLISHABLE_KEY=
```


--------------------------------

### Install Poetry and initialize project

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2024-03-26-semantic-image-search-amazon-bedrock.mdx

Installs Poetry packaging and dependency manager via pip, then initializes a new Python project directory named aws_bedrock_image_search.

```shell
pip install poetry
```

```shell
poetry new aws_bedrock_image_search
```


--------------------------------

### Validate user JWTs without manual JWKS setup

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2026-05-06-introducing-supabase-server.mdx

Destructures `supabase` from the context parameter to query data with automatic user JWT validation. Eliminates manual `jose` installation and JWKS endpoint configuration.

```typescript
export default {
  // auth: 'user' will handle incoming user JWT validation for you
  fetch: withSupabase({ auth: 'user' }, async (req, { supabase }) => {
    const { data } = await supabase.from('subscriptions').select('*')
    return Response.json(data)
  }),
}
```


--------------------------------

### Install Radix UI Checkbox dependency

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/checkbox.mdx

Install the @radix-ui/react-checkbox dependency when performing manual installation.

```bash
npm install @radix-ui/react-checkbox
```


--------------------------------

### Install Supabase CLI globally

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2021-03-31-supabase-cli.mdx

Installs the Supabase CLI tool globally using npm.

```bash
npm install -g supabase
```


--------------------------------

### Install @radix-ui/react-menubar dependency

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/menubar.mdx

Install the Radix UI menubar primitive package for manual component installation.

```bash
npm install @radix-ui/react-menubar
```


--------------------------------

### Install Embla Carousel dependency manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/carousel.mdx

Install the required embla-carousel-react package for manual component installation.

```bash
npm install embla-carousel-react
```


--------------------------------

### Install Playwright browser binaries in e2e/studio

Source: https://github.com/supabase/supabase/blob/master/e2e/studio/README.md

Navigates to the `e2e/studio` directory and installs the necessary Playwright browser binaries.

```bash
cd e2e/studio

pnpm exec playwright install
```


--------------------------------

### Install Slider dependencies manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/slider.mdx

Install the Radix UI Slider primitive package when performing a manual installation.

```bash
npm install @radix-ui/react-slider
```


--------------------------------

### Install AlertDialog using shadcn CLI

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/alert-dialog.mdx

Installs the AlertDialog component using the shadcn CLI tool.

```bash
npx shadcn-ui@latest add alert-dialog
```


--------------------------------

### Install Radix UI Separator dependency manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/separator.mdx

Install the required @radix-ui/react-separator package when performing a manual component installation.

```bash
npm install @radix-ui/react-separator
```


--------------------------------

### Start self-hosted stack with docker compose up

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2021-03-31-supabase-cli.mdx

Starts the ejected Supabase stack containers after configuring environment variables, routing, and database settings.

```bash
docker compose up
```


--------------------------------

### Create production build

Source: https://github.com/supabase/supabase/blob/master/apps/lite-studio/README.md

Compiles and bundles the application for production deployment.

```bash
npm run build
```


--------------------------------

### Check and install extensions in Supabase

Source: https://github.com/supabase/supabase/blob/master/apps/kb/src/content/guides/migrate-from-postgres.mdx

Lists available and installed PostgreSQL extensions in Supabase to compare against the source database and install needed extensions.

```sql
-- Connect to your Supabase database and check available extensions
SELECT name, comment FROM pg_available_extensions ORDER BY name;

-- Compare with source database extensions
SELECT extname FROM pg_extension ORDER BY extname;

-- Install needed extensions
CREATE EXTENSION IF NOT EXISTS extension_name;
```


--------------------------------

### Example Nix Store Package Path

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2024-04-25-nix-postgres.mdx

Demonstrates the directory structure of a package stored in `/nix/store`, where the unique hash prefix captures all dependencies.

```sh
/nix/store/b6gvzjyb2pg0kjfwrjmg1vfhh54ad73z-firefox-33.1/

```


--------------------------------

### Download the Next.js 13 Caching Example

Source: https://github.com/supabase/supabase/blob/master/examples/caching/with-nextjs-13/README.md

Downloads and extracts the with-nextjs-13 caching example directly from the Supabase repository.

```bash
curl https://codeload.github.com/supabase/supabase/tar.gz/master | tar -xz --strip=3 supabase-master/examples/caching/with-nextjs-13
```


--------------------------------

### Bootstrap a local Supabase project

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2024-08-21-mozilla-llamafile-in-supabase-edge-functions.mdx

Initializes a new Supabase project locally from scratch after starting your Llamafile server.

```bash
npx supabase bootstrap scratch
```


--------------------------------

### Install Playwright Chromium browser

Source: https://github.com/supabase/supabase/blob/master/e2e/docs/README.md

Run once from the e2e/docs directory to install the required Chromium browser binary.

```bash
cd e2e/docs
pnpm exec playwright install chromium
```


--------------------------------

### Install Radix UI AlertDialog package manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/alert-dialog.mdx

Installs the Radix UI Alert Dialog dependency required for manual component installation.

```bash
npm install @radix-ui/react-alert-dialog
```


--------------------------------

### Install middleware package and copy framework bridge

Source: https://github.com/supabase/supabase/blob/master/apps/docs/spec/reference/server/v1/partials/frameworks.mdx

Install `@supabase/middleware` and download the framework bridge into `src/lib/supabase-middleware.ts`. Retain all code comments and structure from the bridge as-is.

```bash
npm install @supabase/middleware
mkdir -p src/lib
curl --fail -o src/lib/supabase-middleware.ts \
  https://raw.githubusercontent.com/supabase/server/main/examples/frameworks/hono/supabase-middleware.ts
```


--------------------------------

### Create Expo app and install dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2023-08-01-react-native-storage.mdx

Sets up a new Expo app using the tabs template and installs `@supabase/supabase-js`, polyfills, UI utilities, and Expo filesystem and image picker packages.

```sh
# Create a new Expo app
npx create-expo-app@latest cloudApp --template tabs@49

# Install dependencies
npm i @supabase/supabase-js
npm i react-native-url-polyfill base64-arraybuffer react-native-loading-spinner-overlay @react-native-async-storage/async-storage

# Install Expo packages
npx expo install expo-image-picker
npx expo install expo-file-system
```


--------------------------------

### Initialize Ionic Angular project and install dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2023-03-01-geo-queries-with-postgis-in-ionic-angular.mdx

Sets up a new Ionic Angular project, generates pages and services, adds Capacitor platforms, and installs Google Maps, Geolocation, and Supabase client packages.

```bash
ionic start supaMap blank --type=angular
cd ./supaMap

ionic g page store
ionic g page nearby
ionic g service services/stores

ionic build
ionic cap add ios
ionic cap add android


# Add Maps and Geolocation plugins
npm install @capacitor/google-maps
npm install @capacitor/geolocation

# Install Supabase
npm install @supabase/supabase-js

# Ionic 7 wasn't released so I installed the next version
# not required if you are already on Ionic 7
npm install @ionic/core@next @ionic/angular@next
```


--------------------------------

### Start local Supabase stack and dev server

Source: https://github.com/supabase/supabase/blob/master/examples/slack-clone/nextjs-slack-clone-dotenvx/README.md

Starts the local Supabase container stack and launches the Next.js development server at localhost:3000.

```bash
npx supabase start
npm run dev
```


--------------------------------

### Install Drawer using shadcn CLI

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/drawer.mdx

Add the drawer component to your project using the shadcn-ui CLI.

```bash
npx shadcn-ui@latest add drawer
```


--------------------------------

### Install Legend State and Supabase dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2024-09-23-local-first-expo-legend-state.mdx

Installs Legend State, Supabase JS, Async Storage, and random values dependencies using expo install.

```bash
npx expo install @legendapp/state@beta @supabase/supabase-js react-native-get-random-values @react-native-async-storage/async-storage
```


--------------------------------

### Start local Supabase services and React app

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2021-03-31-supabase-cli.mdx

Starts the local Supabase Docker containers and launches the React development server.

```bash
supabase start  # Start Supabase
npm start       # Start the React app
```


--------------------------------

### Install and initialize Supabase CLI

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2025-08-17-the-vibe-coders-guide-to-supabase-environments.mdx

Installs the Supabase CLI as a developer dependency and initializes the local supabase/ directory for managing migrations, edge functions, and seed data.

```bash
npm install supabase --save-dev
supabase init
```


--------------------------------

### Scaffold SaaS Starter with create-next-app

Source: https://github.com/supabase/supabase/blob/master/apps/ui-library/content/docs/starters/saas-starter.mdx

Scaffolds the subscription starter template using create-next-app and navigates into the project directory. Dependency updates should be reviewed prior to deployment.

```bash
npx create-next-app@latest my-saas --example https://github.com/supabase-community/nextjs-subscription-payments --use-pnpm
cd my-saas
```


--------------------------------

### Install Switch via CLI

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/switch.mdx

Add the Switch component to your project using the shadcn-ui CLI.

```bash
npx shadcn-ui@latest add switch
```


--------------------------------

### Clone example with sparse Git checkout

Source: https://github.com/supabase/supabase/blob/master/apps/ui-library/content/docs/starters/flutter-starter.mdx

Performs a shallow, sparse Git clone to fetch only the Flutter user management example directory.

```bash
git clone --depth 1 --filter=blob:none --sparse https://github.com/supabase/supabase.git my-flutter-app
cd my-flutter-app
git sparse-checkout set examples/user-management/flutter-user-management
cd examples/user-management/flutter-user-management
```


--------------------------------

### Install iceberg-js via npm

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2025-12-08-introducing-iceberg-js.mdx

Install the iceberg-js package into your project using npm.

```bash
npm install iceberg-js
```


--------------------------------

### Install supabase-js v2 using npm

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2022-08-16-supabase-js-v2.mdx

Run this command to upgrade to version 2 of @supabase/supabase-js.

```bash
npm i @supabase/supabase-js@2
```


--------------------------------

### Install dependencies with npm

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2023-04-04-infinite-scroll-with-nextjs-framer-motion.mdx

Installs the required dependencies including @supabase/supabase-js, lodash, and framer-motion.

```bash
npm install @supabase/supabase-js lodash framer-motion
```


--------------------------------

### Install daemontools for envdir

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2020-08-02-continuous-postgresql-backup-walg.mdx

Installs the daemontools package to obtain the envdir command on Ubuntu.

```shell
$ sudo apt-get install -y daemontools
```


--------------------------------

### Install Radix UI Select dependency manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/select.mdx

Install the @radix-ui/react-select package when setting up the Select component manually.

```bash
npm install @radix-ui/react-select
```


--------------------------------

### Install dependencies and copy environment file

Source: https://github.com/supabase/supabase/blob/master/apps/ui-library/content/docs/starters/flutter-starter.mdx

Fetches Flutter package dependencies and copies the template environment file to `.env`.

```bash
flutter pub get
cp .env.example .env
```


--------------------------------

### Download and transform specs into docs using make

Source: https://github.com/supabase/supabase/blob/master/apps/docs/spec/README.md

Run this command to download and transform specification files into the reference documentation.

```bash

make                # download and transform specs into docs

```


--------------------------------

### Install Input component via CLI

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/input.mdx

Add the Input component to your project using the shadcn-ui CLI.

```bash
npx shadcn-ui@latest add input
```


--------------------------------

### Applying background classes

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/tailwind-classes.mdx

Examples of background utility shorthand classes and cross-utility usage with text.

```text
bg-surface-100
bg-overlay
bg-alternative
text-background-surface-100
```


--------------------------------

### Install required dependencies

Source: https://github.com/supabase/supabase/blob/master/examples/ai/llamaindex/llamaindex.ipynb

Install required packages including vecs, datasets, llama_index, and html2text.

```python
!pip install -qU vecs datasets llama_index html2text
```


--------------------------------

### Serve index.html locally with Python or npm

Source: https://github.com/supabase/supabase/blob/master/examples/storage/resumable-upload-signed-uppy/README.md

Starts a local HTTP server using either Python's built-in HTTP server module or npm's http-server package to test the client-side upload application.

```bash
# python http server
python3 -m http.server

# npm http-server
npx http-server
```


--------------------------------

### Install Menubar via CLI

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/menubar.mdx

Add the Menubar component directly to your project using the shadcn-ui CLI.

```bash
npx shadcn-ui@latest add menubar
```


--------------------------------

### Install vec2pg using pip

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2024-08-16-vec2pg.mdx

Install the vec2pg command-line interface tool via pip.

```bash
pip install vec2pg
```


--------------------------------

### Create a database using default template1

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2020-07-09-postgresql-templates.mdx

Create a new database by copying all objects and configurations directly from template1.

```sql
CREATE DATABASE new_db_name;
```


--------------------------------

### Install @supabase/middleware using pnpm

Source: https://github.com/supabase/supabase/blob/master/apps/docs/docs/ref/middleware/installing.mdx

Installs the @supabase/middleware package using the pnpm package manager.

```sh
pnpm add @supabase/middleware
```


--------------------------------

### Install @supabase/middleware using Yarn

Source: https://github.com/supabase/supabase/blob/master/apps/docs/docs/ref/middleware/installing.mdx

Installs the @supabase/middleware package using the Yarn package manager.

```sh
yarn add @supabase/middleware
```


--------------------------------

### Install @supabase/middleware using npm

Source: https://github.com/supabase/supabase/blob/master/apps/docs/docs/ref/middleware/installing.mdx

Installs the @supabase/middleware package using the npm package manager.

```sh
npm install @supabase/middleware
```


--------------------------------

### Install Toggle via CLI

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/toggle.mdx

Run the shadcn-ui CLI command to add the Toggle component to your project.

```bash
npx shadcn-ui@latest add toggle
```


--------------------------------

### Install Textarea using CLI

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/textarea.mdx

Add the Textarea component to your project using the shadcn-ui CLI command.

```bash
npx shadcn-ui@latest add textarea
```


--------------------------------

### Install Supabase and Community Plugin

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2026-10-02-select-2026-operate-with-confidence.mdx

Install the Supabase package as a development dependency and add the community plugin to enable updated agent skills for monitoring health, security, and performance signals.

```bash
npm install supabase --save-dev
npx plugins add supabase-community/supabase-plugin
```


--------------------------------

### Create a new Vite React project

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2024-08-29-in-browser-semantic-search-pglite.mdx

Initialize a new React project from scratch using the Vite scaffolding tool.

```bash
npm create vite@latest
```


--------------------------------

### Install Playwright Chromium browser

Source: https://github.com/supabase/supabase/blob/master/e2e/www/README.md

Installs the required Playwright Chromium browser binary once from the e2e/www directory.

```bash
cd e2e/www
pnpm exec playwright install chromium
```


--------------------------------

### Install Tooltip via shadcn CLI

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/tooltip.mdx

Add the Tooltip component directly to your project using the shadcn CLI.

```bash
npx shadcn-ui@latest add tooltip
```


--------------------------------

### Install Pagination component via CLI

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/pagination.mdx

Run this command to add the pagination component to your project using the shadcn-ui CLI.

```bash
npx shadcn-ui@latest add pagination
```


--------------------------------

### Install Faker.js development dependency

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2025-08-16-testing-for-vibe-coders-from-zero-to-production-confidence.mdx

Installs the `@faker-js/faker` library for generating realistic mock test data.

```bash
npm install @faker-js/faker --save-dev
```


--------------------------------

### Create products table and configure storage policies

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/_partials/product_management_sql_template.mdx

Creates the public.products table, inserts a 'Product Image' bucket into storage.buckets, and defines permissive storage access policies for select, insert, and update.

```sql
-- Create a table for public profiles

create table
  public.products (
    id uuid not null default gen_random_uuid (),
    name text not null,
    price real not null,
    image text null,
    constraint products_pkey primary key (id)
  ) tablespace pg_default;

-- Set up Storage!
insert into storage.buckets (id, name)
  values ('Product Image', 'Product Image');

-- Set up access controls for storage.
-- See https://supabase.com/docs/guides/storage/security/access-control#policy-examples for more details.
CREATE POLICY "Enable read access for all users" ON "storage"."objects"
AS PERMISSIVE FOR SELECT
TO public
USING (true)

CREATE POLICY "Enable insert for all users" ON "storage"."objects"
AS PERMISSIVE FOR INSERT
TO authenticated, anon
WITH CHECK (true)

CREATE POLICY "Enable update for all users" ON "storage"."objects"
AS PERMISSIVE FOR UPDATE
TO public
USING (true)
WITH CHECK (true)

```


--------------------------------

### Install WatermelonDB and Supabase dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2023-10-08-react-native-offline-first-watermelon-db.mdx

Installs WatermelonDB, Supabase JS client, and expo-build-properties packages into the project.

```sh
npm install @nozbe/watermelondb @supabase/supabase-js expo-build-properties
```


--------------------------------

### Install Context Menu via shadcn CLI

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/context-menu.mdx

Adds the context-menu component to your project using the shadcn CLI.

```bash
npx shadcn-ui@latest add context-menu
```


--------------------------------

### Install @supabase/supabase-js with npm

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2024-07-16-supabase-js-on-jsr.mdx

Adds the Supabase client library from JSR in npm-based environments using npx.

```bash
npx jsr add @supabase/supabase-js
```


--------------------------------

### Install Supabase Agent Skills using npx

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/_partials/quickstart_ai_tooling.mdx

Run this command in the root of your project to install Agent Skills, giving AI coding agents procedural knowledge and up-to-date patterns for Supabase.

```bash
npx skills add supabase/agent-skills
```


--------------------------------

### Run a production build with pnpm

Source: https://github.com/supabase/supabase/blob/master/apps/kb/AGENTS.md

Execute a full production build of the knowledge base from either the repository root or the apps/kb subdirectory.

```bash
# From the root directory of the project
pnpm build:kb

# From the apps/kb directory
pnpm build
```


--------------------------------

### Install Resizable component via CLI

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/resizable.mdx

Add the resizable component to your project using the shadcn-ui CLI tool.

```bash
npx shadcn-ui@latest add resizable
```


--------------------------------

### Install PostgreSQL client on Debian Linux

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/troubleshooting/increase-vector-lookup-speeds-by-applying-an-hsnw-index-ohLHUM.mdx

Installs the PostgreSQL client CLI to allow running long-running indexing queries externally and bypass Dashboard query limits.

```bash
sudo apt-get update
sudo apt-get install postgresql-client
```


--------------------------------

### Install Supabase and React Query dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2024-01-12-react-query-nextjs-app-router-cache-helpers.mdx

Installs the required packages including Supabase client, TanStack React Query, Supabase SSR helpers, and PostgREST React Query cache helpers.

```bash
npm install @supabase/supabase-js @tanstack/react-query @supabase/ssr @supabase-cache-helpers/postgrest-react-query
```


--------------------------------

### Install Dropdown Menu via CLI

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/dropdown-menu.mdx

Add the dropdown-menu component to your project using the shadcn-ui CLI tool.

```bash
npx shadcn-ui@latest add dropdown-menu
```


--------------------------------

### Create Brick output directories

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2024-10-08-offline-first-flutter-apps.mdx

Sets up the target directory structure for generated Brick adapters and database migrations.

```bash
mkdir -p lib/brick/adapters lib/brick/db;
```


--------------------------------

### Install dependencies for Sonner

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/sonner.mdx

Install the required sonner and next-themes packages for toast functionality and theming support.

```bash
npm install sonner next-themes
```


--------------------------------

### Install @radix-ui/react-popover dependency

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/popover.mdx

Install the Radix UI popover primitive package when setting up the component manually.

```bash
npm install @radix-ui/react-popover
```


--------------------------------

### Run the Flutter application

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2022-06-30-flutter-tutorial-building-a-chat-app.mdx

Navigates into the newly created Flutter project directory and launches the application.

```bash
cd my_chat_app
flutter run
```


--------------------------------

### Create Ionic Angular app, install Supabase, and generate project files

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2022-11-08-authentication-in-ionic-angular.mdx

Initializes a blank Ionic Angular application, installs @supabase/supabase-js, and uses the CLI to generate pages, services, and an authentication route guard.

```bash
ionic start supaAuth blank --type=angular
npm install @supabase/supabase-js

# Add some pages
ionic g page pages/login
ionic g page pages/register
ionic g page pages/groups
ionic g page pages/messages

# Generate services
ionic g service services/auth
ionic g service services/data

# Add a guard to protect routes
ionic g guard guards/auth --implements=CanActivate
```


--------------------------------

### Initialize pgbench database with scale factor

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2021-07-26-supabase-postgres-13.mdx

Initializes the pgbench benchmark database schema with a scale factor of 150.

```bash
pgbench -i -s 150
```


--------------------------------

### Set up database schema, RLS policies, realtime, and storage bucket

Source: https://github.com/supabase/supabase/blob/master/examples/user-management/nuxt3-user-management/README.md

Creates the profiles table referencing auth.users, sets up Row Level Security policies, adds the table to realtime publication, and configures the avatars storage bucket with public read and insert policies.

```sql
-- Create a table for public "profiles"
create table profiles (
  id uuid references auth.users not null,
  updated_at timestamp with time zone,
  username text unique,
  avatar_url text,
  website text,

  primary key (id),
  unique(username),
  constraint username_length check (char_length(username) >= 3)
);

alter table profiles enable row level security;

create policy "Public profiles are viewable by everyone."
  on profiles for select
  using ( true );

create policy "Users can insert their own profile."
  on profiles for insert
  with check ( (select auth.uid()) = id );

create policy "Users can update own profile."
  on profiles for update
  using ( (select auth.uid()) = id );

-- Set up Realtime!
begin;
  drop publication if exists supabase_realtime;
  create publication supabase_realtime;
commit;
alter publication supabase_realtime add table profiles;

-- Set up Storage!
insert into storage.buckets (id, name)
values ('avatars', 'avatars');

create policy "Avatar images are publicly accessible."
  on storage.objects for select
  using ( bucket_id = 'avatars' );

create policy "Anyone can upload an avatar."
  on storage.objects for insert
  with check ( bucket_id = 'avatars' );
```


--------------------------------

### Install required dependencies

Source: https://github.com/supabase/supabase/blob/master/examples/ai/semantic_text_deduplication.ipynb

Installs the vecs client, Hugging Face datasets, sentence-transformers, flupy, and tqdm packages.

```python
!pip install -qU vecs datasets sentence_transformers flupy tqdm
```


--------------------------------

### Install @supabase/stripe-sync-engine package

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2025-07-15-stripe-engine-as-sync-library.mdx

Installs the Stripe sync engine package directly into your backend project using npm.

```bash
npm install @supabase/stripe-sync-engine
```


--------------------------------

### React Native project structure

Source: https://github.com/supabase/supabase/blob/master/examples/auth/quickstarts/react-native/README.md

Overview of the directory layout and key files in the React Native example application.

```text
├── App.tsx                 # Main app component
├── components/
│   └── Auth.tsx            # Authentication form component
├── lib/
│   └── supabase.ts         # Supabase client configuration
├── app.json                # Expo configuration
├── package.json            # Dependencies
└── tsconfig.json           # TypeScript configuration
```


--------------------------------

### Install @supabase/supabase-js with Deno

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2024-07-16-supabase-js-on-jsr.mdx

Adds the Supabase JavaScript client package to a Deno project from JSR.

```bash
deno add @supabase/supabase-js
```


--------------------------------

### Install @supabase/supabase-js using pnpm

Source: https://github.com/supabase/supabase/blob/master/apps/docs/docs/ref/javascript/installing.mdx

Installs the Supabase JavaScript client library using the pnpm package manager.

```sh
pnpm add @supabase/supabase-js
```


--------------------------------

### Install @supabase/supabase-js using Yarn

Source: https://github.com/supabase/supabase/blob/master/apps/docs/docs/ref/javascript/installing.mdx

Installs the Supabase JavaScript client library using the Yarn package manager.

```sh
yarn add @supabase/supabase-js
```


--------------------------------

### Prebuild project for file picker support

Source: https://github.com/supabase/supabase/blob/master/examples/user-management/expo-user-management/README.md

Prebuilds the project prior to running the app so that the file picker functions correctly.

```bash
npm run prebuild
```


--------------------------------

### Install Calendar using shadcn CLI

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/calendar.mdx

Add the Calendar component to your project using the shadcn-ui CLI tool.

```bash
npx shadcn-ui@latest add calendar
```


--------------------------------

### Set up instruments table and RLS policies

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/_partials/quickstart_db_setup.mdx

Run this SQL script in the SQL Editor to create the instruments table, insert sample data, grant read permissions to the anon role, and enable Row Level Security with a public read policy.

```sql
-- Create the table
create table instruments (
  id bigint primary key generated always as identity,
  name text not null
);

-- Insert sample data into the table
insert into instruments (name)
values
  ('violin'),
  ('viola'),
  ('cello');

-- Grant the privileges the role needs, which is read access
grant select on public.instruments to anon;

-- Enable row level security for the table
alter table instruments enable row level security;

-- Create a policy to allow the anon role to read from the instruments table
create policy "public can read instruments"
on public.instruments
for select to anon
using (true);
```


--------------------------------

### Explore implementation trade-offs and alternatives

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2025-08-16-vibe-coding-best-practices-for-prompting.mdx

Instruct the AI to explain its technical decisions and compare the chosen implementation against alternative patterns.

```text
Why did you choose this approach over alternatives? What are the trade-offs?

```


--------------------------------

### Outline major section groups at the beginning of a guide

Source: https://github.com/supabase/supabase/blob/master/apps/docs/style-guide/03-page-structure.md

Provides an outline for long guides that links to each major section group and explains when the reader should use it. Do not add section navigation to short guides whose headings already fit on a single screen.

```markdown
Connect your app to Postgres through a connection pooler, a direct connection, or a
Supabase client library.

- [Choose a connection method](#choose-a-connection-method) compares the options and
  their trade-offs. Start here if you aren't sure which one fits your app.
- [Connect your app](#connect-your-app) has the steps for each method.
- [Connection parameters](#connection-parameters) lists every parameter and its
  default.
```


--------------------------------

### Install project dependencies using npm

Source: https://github.com/supabase/supabase/blob/master/examples/user-management/svelte-user-management/README.md

Installs the required npm packages to run the Svelte user management project.

```bash
$ npm install

```


--------------------------------

### Install Radix UI Scroll Area dependency manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/scroll-area.mdx

Install the underlying @radix-ui/react-scroll-area package when setting up the component manually.

```bash
npm install @radix-ui/react-scroll-area
```


--------------------------------

### Initialize Slackbot clients and channel helper functions in Python

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2022-08-09-slack-consolidate-slackbot-to-consolidate-messages.mdx

Sets up WebClient and Supabase client instances, defines the SlackChannel model, and implements helper functions for fetching channel metadata from Supabase and posting messages to destination channels.

```python
import time
import logging
from slack_sdk import WebClient
from slack_sdk.errors import SlackApiError
from supabase import create_client, Client
from datetime import datetime
from dotenv import dotenv_values
logger = logging.getLogger(__name__)
config = dotenv_values(".env")
bot_client = WebClient(token=config['SLACK_BOT_TOKEN'])
client = WebClient(token=config['SLACK_TOKEN'])
SUPABASE_URL=config['SUPABASE_URL']
SUPABASE_KEY=config['SUPABASE_KEY']
supabase: Client = create_client(SUPABASE_URL, SUPABASE_KEY)
SLACK_ORG = config['SLACK_ORG']
SLACK_ORG_LINK = f"https://{SLACK_ORG}.slack.com/archives/"
############
# Config:
############
# 1.4 seconds should be the minimum to avoid passing Slack API limits.
# https://api.slack.com/docs/rate-limits#tier_t3
POOLING_DELAY = 1.4
# Check if new channels were added each hour.
SCAN_CHANNELS_DELAY = 3600.0
BUFFER_SIZE = 20

class SlackChannel:
  def __init__(self, id, name, p_level, dest_channel_id, dest_channel, private):
    """_summary_

      Args:
          id (str): Slack channel ID from the source channel
          name (str): Name of the source channel (used in logging)
          p_level (str): (Optional message) added when posting
          dest_channel_id (str): Slack channel ID for the destination channel
          dest_channel (str): Name of the destination channel (used in logging)
          private (int): Integer to check if the channel is private (private==1) or public channel
      Returns:
          SlackChannel: object
    """
    self.id = id
    self.name = name
    self.p_level = p_level
    self.dest_channel = dest_channel
    self.dest_channel_id  = dest_channel_id
    self.private  = private

def setup():
    """_summary_
        Fetches the list of channels from Supabase and returns them in a dict()
    Returns:
        dict: Dictionary with SlackChannel objects.
    """
    channels = dict()
    data = supabase.from_("slack_channels").select("channel_id, channel, p_level, dest_channel, dest_channel_id, private").execute().data
    data_dic = data
    for row in data_dic:
        channels[row['channel_id']] = SlackChannel(id = row['channel_id'],
        name = row['channel'],
        p_level = row['p_level'],
        dest_channel = row['dest_channel'],
        dest_channel_id = row['dest_channel_id'],
        private = row['private'])
    return channels

def post(src_channel, link, message):
    """_summary_
        Post a message from a source channel into the destination channel
    Args:
        src_channel (SlackChannel): SlackChannel object
        link (_type_):
 The link of the message in slack
        message (_type_): _description_

    Returns:
        _type_: _description_
    """
    try:
        aux_text = ""
        if src_channel.private != 1:
            aux_text = ("Message on <#"+src_channel.id+
                ">. "+src_channel.p_level+" \n"+link)
        else:
            aux_text = ("Message on <#"+src_channel.id+
                ">."+src_channel.p_level+" \n"+message+" \n"+link)
        result = bot_client.chat_postMessage(
                channel= src_channel.dest_channel_id,
                text=aux_text
                )
        logger.info(result)
    except SlackApiError as e:
        logger.error(f"Error posting message: {e}")

def ts_to_strtime(ts):
    """_summary_
        Converts the UNIX time in timestamp to ISO format.
    Args:
        ts (int): TS datetime

    Returns:
        str: ISO format datetime string for compatibility with Postgres.
    """
    aux_ts = int(ts)
    return str(datetime.utcfromtimestamp(aux_ts).isoformat())
```


--------------------------------

### Install Radix UI Radio Group dependency

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/radio-group.mdx

Install the underlying Radix UI primitive when setting up the component manually.

```bash
npm install @radix-ui/react-radio-group
```


--------------------------------

### Create a new Flutter project

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2023-05-04-flutter-multi-factor-authentication.mdx

Initializes a new Flutter project named mfa_app from the command line.

```bash
flutter create mfa_app
```


--------------------------------

### Add Postgres binary to Windows system PATH

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/_partials/postgres_installation.mdx

Example path for adding the PostgreSQL binary directory to the Windows Environment Variables PATH.

```text
C:\Program Files\PostgreSQL\17\bin
```


--------------------------------

### Serve index.html locally with Python

Source: https://github.com/supabase/supabase/blob/master/examples/storage/resumable-upload-uppy/README.md

Run Python's built-in HTTP server to serve the local index.html file and start uploading.

```bash
python3 -m http.server
```


--------------------------------

### Install PostgreSQL 17 on macOS via Homebrew

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/_partials/postgres_installation.mdx

Installs PostgreSQL version 17 using the Homebrew package manager on macOS.

```sh
brew install postgresql@17
```


--------------------------------

### Install Toggle Group dependency manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/toggle-group.mdx

Install the required Radix UI Toggle Group package when setting up the component manually.

```bash
npm install @radix-ui/react-toggle-group
```


--------------------------------

### Initialize Supabase with custom configuration in v1 (Before)

Source: https://github.com/supabase/supabase/blob/master/apps/docs/docs/ref/dart/upgrade-guide.mdx

Demonstrates the legacy v1 format for passing custom configuration directly to Supabase.initialize().

```dart
await Supabase.initialize(
  url: supabaseUrl,
  publishableKey: publishableKey,
  authFlowType: AuthFlowType.pkce,
  storageRetryAttempts: 10,
  realtimeClientOptions: const RealtimeClientOptions(
    logLevel: RealtimeLogLevel.info,
  ),
);
```


--------------------------------

### Example GraphQL AST in Rust

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2024-01-24-how-pg-graphql-works.mdx

Shows the resulting AST structure produced by graphql-parser when parsing an example GraphQL query operation.

```rust
Document {
  definitions: [Operation(Query(Query {
    name: None,
    variable_definitions: [],
    directives: [],
    selection_set: SelectionSet {
      items: [Field(Field {
        alias: None,
        name: "bookCollection",
        arguments: [],
        directives: [],
        selection_set: SelectionSet {
          items: [Field(Field {
            alias: None,
            name: "edges",
            arguments: [],
            directives: [],
            selection_set: SelectionSet {
              items: [Field(Field {
                alias: None,
                name: "node",
                arguments: [],
                directives: [],
                selection_set: SelectionSet {
                  items: [Field(Field {
                    alias: None,
                    name: "id",
                    arguments: [],
                    directives: [],
                    selection_set: SelectionSet { items: [] },
                  })],
                },
              })],
            },
          })],
        },
      })],
    },
  }))],
}
```


--------------------------------

### Configuring guide YAML frontmatter

Source: https://github.com/supabase/supabase/blob/master/apps/docs/CONTRIBUTING.md

Sets the mandatory title and optional display properties such as hideToc, subtitle, or tocVideo in MDX guides.

```yaml
---
title: How to connect to Supabase
hideToc: true
---
```


--------------------------------

### Install @supabase/server and AI Skill

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2026-05-06-introducing-supabase-server.mdx

Installs the @supabase/server package along with the AI skill for coding assistants such as Claude Code, Codex, and Cursor.

```bash
npm install @supabase/server@latest
npx skills add supabase/server
```


--------------------------------

### Production Deployment Preparation Prompt

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2025-08-16-the-vibe-coding-master-checklist.mdx

Use this prompt with AI coding tools to prepare an application for production deployment. It covers environment configuration, error handling, asset optimization, and monitoring setup.

```text
Prepare my application for production deployment:

Current Setup:
- Built with [your AI tool]
- Using Supabase for backend/database
- Deploying to [Vercel/Netlify/other]
- Custom domain: [yourdomain.com]

Implementation Steps:

1. Environment Configuration
   - Move hard-coded config to environment variables
   - Set up production vs. development environments
   - Configure deployment platform settings

2. Error Handling & UX
   - Add error boundaries for component crashes
   - Create user-friendly error pages (404, 500, network errors)
   - Implement loading states for all async operations

3. Production Optimization
   - Optimize images and assets
   - Remove development code and console.logs
   - Add proper meta tags for SEO
   - Ensure responsive design works on all devices

4. Monitoring & Deployment
   - Set up error tracking and basic analytics
   - Configure automatic deployment from GitHub
   - Test custom domain and SSL setup

For each step, provide:
1. Exact code changes needed
2. Platform configuration settings
3. Simple test to verify functionality
4. Troubleshooting guidance

Conclude with a final production checklist.

```


--------------------------------

### Install agent skill plugin in Claude Code

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2026-01-21-postgres-best-practices-for-ai-agents.mdx

Add the marketplace source and install the postgres-best-practices skill plugin when using Claude Code.

```shell
/plugin marketplace add supabase/agent-skills
/plugin install postgres-best-practices@supabase-agent-skills
```


--------------------------------

### Uninstall auth-helpers and install @supabase/ssr

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/troubleshooting/how-to-migrate-from-supabase-auth-helpers-to-ssr-package-5NRunM.mdx

Uninstalls @supabase/auth-helpers-nextjs and installs @supabase/ssr alongside @supabase/supabase-js. Both packages should not be used in the same application to prevent authentication conflicts.

```bash
npm uninstall @supabase/auth-helpers-nextjs @supabase/supabase-js
npm install @supabase/ssr @supabase/supabase-js
```


--------------------------------

### Install PostgreSQL client on Debian Linux

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/troubleshooting/avoiding-timeouts-in-long-running-queries-6nmbdN.mdx

Updates package repositories and installs the postgresql-client utility for connecting to PostgreSQL from Debian-based Linux environments.

```bash
sudo apt-get update
sudo apt-get install postgresql-client
```


--------------------------------

### Install Radix Dialog dependency manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/sheet.mdx

Install the required Radix UI Dialog primitive package when setting up the Sheet component manually.

```bash
npm install @radix-ui/react-dialog
```


--------------------------------

### Create stores table, spatial index, and storage policies

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2023-03-01-geo-queries-with-postgis-in-ionic-angular.mdx

Creates a stores table with a geography POINT column, creates a GiST spatial index on locations, sets up a storage bucket, and adds read/write policies.

```sql
-- create our table
create table if not exists public.stores (
	id int generated by default as identity primary key,
	name text not null,
  description text,
	location geography(POINT) not null
);

-- add the spatial index
create index stores_geo_index
  on public.stores
  using GIST (location);

-- create a storage bucket and allow file upload/download
insert into storage.buckets (id, name)
values ('stores', 'stores');

CREATE POLICY "Select images" ON storage.objects FOR SELECT TO public USING (bucket_id = 'stores');
CREATE POLICY "Upload images" ON storage.objects FOR INSERT TO public WITH CHECK (bucket_id = 'stores');
```


--------------------------------

### Install Radix UI Hover Card dependency manually

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/hover-card.mdx

Install the underlying Radix UI primitive package for the Hover Card component.

```bash
npm install @radix-ui/react-hover-card
```


--------------------------------

### Start local Edge Runtime with Docker Compose

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2023-05-15-building-chatgpt-plugins-template.mdx

Builds and starts the Edge Runtime Docker container for local testing of plugin endpoints.

```bash
docker compose up --build
```


--------------------------------

### Initialize Supabase configuration locally

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2021-03-31-supabase-cli.mdx

Initializes the local Supabase environment and generates default configuration along with local API keys and URLs.

```bash
supabase init

# ✔ Port for Supabase URL: · 8000
# ✔ Port for PostgreSQL database: · 5432
# ✔ Project initialized.
# Supabase URL: http://localhost:8000
# Supabase Key (anon, public): eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJzdXBhYmFzZSIsImlhdCI6MTYwMzk2ODgzNCwiZXhwIjoyNTUwNjUzNjM0LCJyb2xlIjoiYW5vbiJ9.36fUebxgx1mcBo4s19v0SzqmzunP--hm_hep0uLX0ew
# Supabase Key (service_role, private): eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJzdXBhYmFzZSIsImlhdCI6MTYwMzk2ODgzNCwiZXhwIjoyNTUwNjUzNjM0LCJyb2xlIjoiYW5vbiJ9.36fUebxgx1mcBo4s19v0SzqmzunP--hm_hep0uLX0ew
# Database URL: postgres://postgres:postgres@localhost:5432/postgres
```


--------------------------------

### Log in and create a project with Supabase CLI

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2022-08-15-supabase-cli-v1-and-admin-api-beta.mdx

Authenticate with the Supabase CLI, list existing organizations, and create a new project specifying the organization ID, database password, and region.

```bash
supabase login
supabase orgs list
supabase projects create my-project --org-id cool-green-pqdr0qc --db-password ******** --region us-east-1
```


--------------------------------

### Install dependencies for face similarity search

Source: https://github.com/supabase/supabase/blob/master/examples/ai/face_similarity.ipynb

Installs vecs, datasets, face_recognition, flupy, tqdm, numpy, and matplotlib via pip in Google Colab.

```python
!pip install -qU vecs datasets face_recognition flupy tqdm numpy matplotlib
```


--------------------------------

### Install specific Supabase agent skills using npx

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2026-04-07-supabase-agent-skills.mdx

Installs individual agent skills such as supabase or supabase-postgres-best-practices using the --skill flag.

```bash
npx skills add supabase/agent-skills --skill supabase
npx skills add supabase/agent-skills --skill supabase-postgres-best-practices
```


--------------------------------

### Install Supabase Agent Skills as a Claude Code plugin

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2026-04-07-supabase-agent-skills.mdx

Registers the Supabase Agent Skills marketplace and installs the Supabase plugin for Claude Code.

```bash
# 1. Install supabase/agent-skill marketplace
claude plugin marketplace add supabase/agent-skills

# 2. Install the supabase plugin
claude plugin install supabase@supabase-agent-skills
```


--------------------------------

### Install project dependencies with Poetry

Source: https://github.com/supabase/supabase/blob/master/apps/www/_blog/2024-03-26-semantic-image-search-amazon-bedrock.mdx

Installs the Supabase Vector Python client (`vecs`), AWS SDK (`boto3`), and `matplotlib` for displaying search results.

```shell
poetry add vecs boto3 matplotlib
```


--------------------------------

### Install Accordion manually and configure Tailwind CSS

Source: https://github.com/supabase/supabase/blob/master/apps/design-system/content/docs/components/accordion.mdx

Install the Radix UI accordion dependency directly and add the necessary accordion keyframes to tailwind.config.js.

```bash
npm install @radix-ui/react-accordion
```

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  theme: {
    extend: {
      keyframes: {
        'accordion-down': {
          from: { height: '0' },
          to: { height: 'var(--radix-accordion-content-height)' },
        },
        'accordion-up': {
          from: { height: 'var(--radix-accordion-content-height)' },
          to: { height: '0' },
        },
      },
      animation: {
        'accordion-down': 'accordion-down 0.2s ease-out',
        'accordion-up': 'accordion-up 0.2s ease-out',
      },
    },
  },
}
```
