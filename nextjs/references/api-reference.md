# App Router — API Reference

Sourced snippets from the Next.js docs dump (131 entries).
Search this file for the topic at hand; treat snippets as patterns and
reconcile with the installed Next.js version before applying.

### Inspect system details with next info output

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/06-cli/next.mdx

Shows example output of next info, which reports OS platform details, installed binary versions, relevant Next.js package versions, and configuration settings.

```bash
Operating System:
  Platform: darwin
  Arch: arm64
  Version: Darwin Kernel Version 23.6.0
  Available memory (MB): 65536
  Available CPU cores: 10
Binaries:
  Node: 20.12.0
  npm: 10.5.0
  Yarn: 1.22.19
  pnpm: 9.6.0
Relevant Packages:
  next: 15.0.0-canary.115 // Latest available version is detected (15.0.0-canary.115).
  eslint-config-next: 14.2.5
  react: 19.0.0-rc
  react-dom: 19.0.0
  typescript: 5.5.4
Next.js Config:
  output: N/A
```


--------------------------------

### Build and start application with testing API enabled

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/exposeTestingApiInProductionBuild.mdx

Sets the environment variable when executing next build, then serves the build with next start. Setting the variable only during next start will not add the testing API to an existing build.

```bash
EXPOSE_TESTING_API=1 pnpm build
pnpm start
```


--------------------------------

### Install TypeScript 7 with Bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/useTypeScriptCli.mdx

Install TypeScript 7 as a development dependency using Bun.

```bash
bun add -D typescript@^7
```


--------------------------------

### Project directory layout for per-directory PostCSS configs

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/turbopackLocalPostcssConfig.mdx

Example structure illustrating how per-directory `postcss.config.js` files take precedence over the root fallback in multi-package or monorepo setups.

```plaintext
my-app/
├── postcss.config.js          ← fallback (applied if no local config is found)
├── app/
│   └── page.module.css        ← uses root config
└── packages/
    └── ui/
        ├── postcss.config.js  ← takes precedence for files in this directory
        └── button.module.css  ← uses packages/ui/postcss.config.js
```


--------------------------------

### Install @next/eslint-plugin-next

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/03-eslint.mdx

Installs the standalone `@next/eslint-plugin-next` development dependency across different package managers.

```bash
pnpm add -D @next/eslint-plugin-next
```

```bash
npm i -D @next/eslint-plugin-next
```

```bash
yarn add --dev @next/eslint-plugin-next
```

```bash
bun add -d @next/eslint-plugin-next
```


--------------------------------

### Install ESLint and eslint-config-next using bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/03-eslint.mdx

Installs ESLint and the Next.js ESLint configuration as dev dependencies using bun.

```bash
bun add -d eslint eslint-config-next
```


--------------------------------

### Install ESLint and eslint-config-next using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/03-eslint.mdx

Installs ESLint and the Next.js ESLint configuration as dev dependencies using npm.

```bash
npm i -D eslint eslint-config-next
```


--------------------------------

### Install TypeScript 7 with Yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/useTypeScriptCli.mdx

Install TypeScript 7 as a development dependency using Yarn.

```bash
yarn add -D typescript@^7
```


--------------------------------

### Install TypeScript 7 with pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/useTypeScriptCli.mdx

Install TypeScript 7 as a development dependency using pnpm.

```bash
pnpm add -D typescript@^7
```


--------------------------------

### Install TypeScript 7 with npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/useTypeScriptCli.mdx

Install TypeScript 7 as a development dependency using npm.

```bash
npm install -D typescript@^7
```


--------------------------------

### Install babel-plugin-react-compiler using bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/reactCompiler.mdx

Install the required React Compiler Babel plugin as a development dependency using bun.

```bash
bun add -D babel-plugin-react-compiler
```


--------------------------------

### Install ESLint and eslint-config-next using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/03-eslint.mdx

Installs ESLint and the Next.js ESLint configuration as dev dependencies using pnpm.

```bash
pnpm add -D eslint eslint-config-next
```


--------------------------------

### Install ESLint and eslint-config-next using yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/03-eslint.mdx

Installs ESLint and the Next.js ESLint configuration as dev dependencies using yarn.

```bash
yarn add --dev eslint eslint-config-next
```


--------------------------------

### Install babel-plugin-react-compiler using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/reactCompiler.mdx

Install the required React Compiler Babel plugin as a development dependency using npm.

```bash
npm install -D babel-plugin-react-compiler
```


--------------------------------

### Install babel-plugin-react-compiler using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/reactCompiler.mdx

Install the required React Compiler Babel plugin as a development dependency using pnpm.

```bash
pnpm add -D babel-plugin-react-compiler
```


--------------------------------

### Install eslint-config-prettier using bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/03-eslint.mdx

Installs eslint-config-prettier as a dev dependency to resolve rule conflicts between ESLint and Prettier.

```bash
bun add -d eslint-config-prettier
```


--------------------------------

### Install babel-plugin-react-compiler using yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/reactCompiler.mdx

Install the required React Compiler Babel plugin as a development dependency using yarn.

```bash
yarn add -D babel-plugin-react-compiler
```


--------------------------------

### Create a new Next.js app with create-next-app

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/06-cli/create-next-app.mdx

Initializes a new Next.js application using the default template or a public GitHub example repository across supported package managers.

```bash
pnpm create next-app [project-name] [options]
```

```bash
npx create-next-app@latest [project-name] [options]
```

```bash
yarn create next-app [project-name] [options]
```

```bash
bun create next-app [project-name] [options]
```


--------------------------------

### Install eslint-config-prettier using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/03-eslint.mdx

Installs eslint-config-prettier as a dev dependency to resolve rule conflicts between ESLint and Prettier.

```bash
pnpm add -D eslint-config-prettier
```


--------------------------------

### Install eslint-config-prettier using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/03-eslint.mdx

Installs eslint-config-prettier as a dev dependency to resolve rule conflicts between ESLint and Prettier.

```bash
npm i -D eslint-config-prettier
```


--------------------------------

### Export onRouterTransitionStart in an injected client module

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/instrumentationClientInject.mdx

Performs side-effectful setup at load time and exports onRouterTransitionStart to track client-side navigations.

```javascript
// Side-effectful setup runs at load time.
setupSentry()

export function onRouterTransitionStart(url, navigationType) {
  recordNavigationBreadcrumb(url, navigationType)
}
```


--------------------------------

### Install eslint-config-prettier using yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/03-eslint.mdx

Installs eslint-config-prettier as a dev dependency to resolve rule conflicts between ESLint and Prettier.

```bash
yarn add --dev eslint-config-prettier
```


--------------------------------

### Define basic adapter structure in my-adapter.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/07-adapters/02-creating-an-adapter.mdx

Demonstrates a minimal adapter implementation exporting modifyConfig and onBuildComplete hooks to handle build outputs and routing data.

```javascript
/** @type {import('next').NextAdapter} */
const adapter = {
  name: 'my-custom-adapter',

  async modifyConfig(config, { phase }) {
    // Modify the Next.js config based on the build phase
    if (phase === 'phase-production-build') {
      return {
        ...config,
        // Add your modifications
      }
    }
    return config
  },

  async onBuildComplete({
    routing,
    outputs,
    projectDir,
    repoRoot,
    distDir,
    config,
    nextVersion,
    buildId,
  }) {
    // Process the build output
    console.log('Build completed with', outputs.pages.length, 'pages')
    console.log('Build ID:', buildId)
    console.log('Dynamic routes:', routing.dynamicRoutes.length)

    // Access emitted output entries
    for (const page of outputs.pages) {
      console.log('Page:', page.pathname, 'at', page.filePath)
    }

    for (const apiRoute of outputs.pagesApi) {
      console.log('API Route:', apiRoute.pathname, 'at', apiRoute.filePath)
    }

    for (const appPage of outputs.appPages) {
      console.log('App Page:', appPage.pathname, 'at', appPage.filePath)
    }

    for (const prerender of outputs.prerenders) {
      console.log('Prerendered:', prerender.pathname)
    }
  },
}

module.exports = adapter
```


--------------------------------

### Run next analyze using package managers

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/06-cli/next.mdx

Analyzes the application's bundle output using Turbopack without producing an application build. Starts a local server by default to allow exploring route bundles, import chains, and boundaries in the browser.

```bash
pnpm next analyze
```

```bash
npx next analyze
```

```bash
yarn next analyze
```

```bash
bunx next analyze
```


--------------------------------

### Enable HTTPS with custom certificates using CLI flags

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/06-cli/next.mdx

Provide custom SSL certificates and private keys to next dev using --experimental-https-key and --experimental-https-cert.

```bash
next dev --experimental-https --experimental-https-key ./certificates/localhost-key.pem --experimental-https-cert ./certificates/localhost.pem
```


--------------------------------

### Apply phase-specific configuration with next/constants

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/index.mdx

Import phase constants such as PHASE_DEVELOPMENT_SERVER from next/constants to return phase-specific configuration options.

```javascript
// @ts-check

const { PHASE_DEVELOPMENT_SERVER } = require('next/constants')

module.exports = (phase, { defaultConfig }) => {
  if (phase === PHASE_DEVELOPMENT_SERVER) {
    return {
      /* development only config options here */
    }
  }

  return {
    /* config options for all phases except development here */
  }
}
```


--------------------------------

### Configure GitHub Actions workflow for adapter end-to-end deployment tests

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/07-adapters/04-testing-adapters.mdx

Sets up a CI workflow in `.github/workflows/test-e2e-deploy.yml` to build Next.js and the custom adapter, then runs sharded end-to-end deployment tests using required lifecycle scripts and environment variables.

```yaml
name: test-e2e-deploy

on:
  workflow_dispatch:
    inputs:
      nextjsRef:
        description: 'Next.js repo ref (branch/tag/SHA)'
        default: 'canary'
        type: string
  # schedule:
  #   - cron: '0 2 * * *'

jobs:
  build:
    name: Build Next.js + adapter
    runs-on: ubuntu-latest
    timeout-minutes: 30
    steps:
      - uses: actions/checkout@v4
        with:
          path: adapter

      - uses: actions/checkout@v4
        with:
          repository: vercel/next.js
          ref: ${{ inputs.nextjsRef || 'canary' }}
          path: nextjs
          fetch-depth: 25

      - uses: actions/setup-node@v4
        with: { node-version: '20' }

      - name: Setup pnpm
        run: npm i -g corepack@0.31 && corepack enable

      - name: Install & build Next.js
        working-directory: nextjs
        run: pnpm install && pnpm build && pnpm install

      - name: Install Playwright
        working-directory: nextjs
        run: pnpm playwright install --with-deps chromium

      - name: Build adapter
        working-directory: adapter
        run: pnpm install && pnpm build

      - uses: actions/cache/save@v4
        with:
          path: |
            nextjs
            adapter
            ~/.cache/ms-playwright
          key: build-${{ github.sha }}-${{ github.run_id }}

  test:
    name: Tests (${{ matrix.group }})
    needs: build
    runs-on: ubuntu-latest
    timeout-minutes: 60
    strategy:
      fail-fast: false
      matrix:
        group:
          [
            1/16,
            2/16,
            3/16,
            4/16,
            5/16,
            6/16,
            7/16,
            8/16,
            9/16,
            10/16,
            11/16,
            12/16,
            13/16,
            14/16,
            15/16,
            16/16,
          ]
    steps:
      - uses: actions/cache/restore@v4
        with:
          path: |
            nextjs
            adapter
            ~/.cache/ms-playwright
          key: build-${{ github.sha }}-${{ github.run_id }}

      - uses: actions/setup-node@v4
        with: { node-version: '20' }

      - name: Setup pnpm
        run: npm i -g corepack@0.31 && corepack enable

      - name: Ensure Playwright browser
        working-directory: nextjs
        run: pnpm playwright install chromium

      - name: Make scripts executable
        run: chmod +x adapter/scripts/e2e-deploy.sh
          adapter/scripts/e2e-logs.sh
          adapter/scripts/e2e-cleanup.sh

      - name: Run deploy tests
        working-directory: nextjs
        env:
          NEXT_TEST_MODE: deploy
          NEXT_E2E_TEST_TIMEOUT: 240000
          NEXT_EXTERNAL_TESTS_FILTERS: test/deploy-tests-manifest.json
          ADAPTER_DIR: ${{ github.workspace }}/adapter
          IS_TURBOPACK_TEST: 1
          NEXT_TEST_JOB: 1
          NEXT_TELEMETRY_DISABLED: 1

          # Change these to your adapter's scripts
          # Keep as-is if the scripts are in the adapter repository `scripts` directory
          NEXT_TEST_DEPLOY_SCRIPT_PATH: ${{ github.workspace }}/adapter/scripts/e2e-deploy.sh
          NEXT_TEST_DEPLOY_LOGS_SCRIPT_PATH: ${{ github.workspace }}/adapter/scripts/e2e-logs.sh
          NEXT_TEST_CLEANUP_SCRIPT_PATH: ${{ github.workspace }}/adapter/scripts/e2e-cleanup.sh
        run: node run-tests.js --timings -g ${{ matrix.group }} -c 2 --type e2e
```


--------------------------------

### next analyze

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/06-cli/next.mdx

Analyzes the application bundle output using Turbopack without producing an application build. By default, it starts a local server to inspect bundle composition.

```APIDOC
## next analyze

### Description
Analyzes your application's bundle output using Turbopack. This command helps you understand the size and composition of your bundles, including JavaScript, CSS, and other assets without producing an application build. By default, starts a local server to explore bundle composition in the browser.

### Usage
```bash
next analyze [directory] [options]
```

### Arguments
- **[directory]** (string) - Optional - A directory on which to analyze the application. Defaults to the current directory.

### Options
- **-h, --help** - Show all available options.
- **--no-mangling** - Disables mangling. This may affect performance and should only be used for debugging purposes.
- **--profile** - Enables production profiling for React. This may affect performance.
- **-o, --output** - Build and save binary analyzer data and UI files to `<distDir>/diagnostics/analyze` without serving.
- **--snapshot <name>** (string) - Save a named snapshot, replacing an earlier capture with the same name.
- **--port <port>** (number) - Specify a port number to serve the analyzer on. (default: 4000, env: PORT)

### Examples
```bash
# Analyze and start local server
npx next analyze

# Build and save a snapshot without starting the UI server
npx next analyze --output --snapshot audit-1
```
```


--------------------------------

### Using ReactDOM.preload for <link rel="preload">

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/generate-metadata.mdx

Starts loading a resource early in the browser page rendering lifecycle. Produces a <link rel="preload"> element in the document head.

```tsx
ReactDOM.preload(href: string, options: { as: string })
```

```html
<link rel="preload" href="..." as="..." />
```


--------------------------------

### Run ESLint using bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/03-eslint.mdx

Executes ESLint against all project files using bunx.

```bash
bunx eslint .
```


--------------------------------

### Gracefully handling fast navigation with CSS animation delay

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/use-link-status.mdx

Applies an animation delay and starts with zero opacity to prevent flashing the pending hint when route navigation completes quickly. Only displays the hint animation if the navigation takes longer than 100ms.

```css
.link-hint {
  display: inline-block;
  width: 0.6em;
  height: 0.6em;
  margin-left: 0.25rem;
  border-radius: 9999px;
  background: currentColor;
  opacity: 0;
  visibility: hidden; /* reserve space without showing the hint */
}

.link-hint.is-pending {
  /* Animation 1: fade in after 100ms and keep final opacity */
  /* Animation 2: subtle pulsing while pending */
  visibility: visible;
  animation-name: fadeIn, pulse;
  animation-duration: 200ms, 1s;
  /* Appear only if navigation actually takes time */
  animation-delay: 100ms, 100ms;
  animation-timing-function: ease, ease-in-out;
  animation-iteration-count: 1, infinite;
  animation-fill-mode: forwards, none;
}

@keyframes fadeIn {
  to {
    opacity: 0.35;
  }
}
@keyframes pulse {
  50% {
    opacity: 0.15;
  }
}
```


--------------------------------

### get(key, ctx)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/incrementalCacheHandlerPath.mdx

Retrieves a cached value for the given opaque key and context from the custom cache handler.

```APIDOC
## get(key, ctx)

### Description
Retrieves a cached entry from the cache handler based on an opaque cache key and context object.

### Method Signature
```ts
get(key: string, ctx: { kind: string }): Promise<any | null> | any | null
```

### Parameters
- **key** (`string`) - Required. The opaque key to the cached value.
- **ctx** (`object`) - Required. Context including the cache entry kind (`'APP_PAGE'`, `'APP_ROUTE'`, `'PAGES'`, `'FETCH'`, or `'IMAGE'`).

### Returns
- Returns the cached value or `null` if not found.
```


--------------------------------

### Get all cookies from NextRequest using request.cookies.getAll

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/next-request.mdx

Returns values for a specific cookie name or all cookies on the request if no name is provided.

```ts
// Given incoming request /home
// [
//   { name: 'experiments', value: 'new-pricing-page', Path: '/home' },
//   { name: 'experiments', value: 'winter-launch', Path: '/home' },
// ]
request.cookies.getAll('experiments')
// Alternatively, get all cookies for the request
request.cookies.getAll()
```


--------------------------------

### Enable HTTPS with self-signed certificate using --experimental-https

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/06-cli/next.mdx

Generate a locally trusted self-signed certificate using mkcert for local development on https://localhost:3000.

```bash
next dev --experimental-https
```


--------------------------------

### Set outputFileTracingRoot for monorepos in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/output.mdx

Set outputFileTracingRoot to include files outside the project package directory during tracing in a monorepo setup.

```javascript
const path = require('path')

module.exports = {
  // this includes files from the monorepo base two directories up
  outputFileTracingRoot: path.join(__dirname, '../../'),
}
```


--------------------------------

### Configure custom loaderFile in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/02-components/image.mdx

Sets up a custom image optimization service path relative to the project root.

```js
module.exports = {
  images: {
    loader: 'custom',
    loaderFile: './my/image/loader.js',
  },
}
```


--------------------------------

### next analyze export

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/06-cli/next.mdx

Streams an existing bundle analysis snapshot as a series of JSON Lines without running analysis or starting the UI server.

```APIDOC
## next analyze export

### Description
Streams an existing snapshot as a series of JSON Lines. It does not run analysis itself or start the web UI.

### Usage
```bash
next analyze export [directory] [options]
```

### Arguments
- **[directory]** (string) - Optional - The application directory containing the saved analysis. Defaults to the current directory.

### Options
- **-h, --help** - Show all available export options.
- **--snapshot <name>** (string) - Select a saved snapshot by name. Defaults to the newest retained snapshot.
- **--route <route>** (string) - Restrict export to one route (still includes the full module graph).
- **--dist-dir <directory>** (string) - Select an explicit relative or absolute build directory without reading `next.config`.

### Examples
```bash
# Stream saved graph as JSON Lines
npx next analyze export --snapshot audit-1 > graph.jsonl
```
```


--------------------------------

### Using ReactDOM.preconnect for <link rel="preconnect">

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/generate-metadata.mdx

Preemptively initiates a connection to an origin. Generates a <link rel="preconnect"> tag in the document head.

```tsx
ReactDOM.preconnect(href: string, options?: { crossOrigin?: string })
```

```html
<link rel="preconnect" href="..." crossorigin />
```


--------------------------------

### Get a cookie from NextRequest using request.cookies.get

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/next-request.mdx

Retrieves the value of a cookie by name. Returns undefined if not found, or the first matching cookie if multiple exist.

```ts
// Given incoming request /home
// { name: 'show-banner', value: 'false', Path: '/home' }
request.cookies.get('show-banner')
```


--------------------------------

### async onBuildComplete(context)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/07-adapters/03-api-reference.mdx

Called after the build process completes with detailed information about routes and outputs.

```APIDOC
## onBuildComplete(context)

### Description
Called after the build process completes with detailed information about routes and outputs.

### Parameters
- **context.routing** (Object) - Object containing Next.js routing phases and metadata
  - **routing.beforeMiddleware** - Routes executed before middleware (includes header and redirect handling)
  - **routing.middlewareMatchers** - Middleware matcher definitions for this build, used to decide whether middleware should be invoked for a given request
  - **routing.beforeFiles** - Rewrite routes checked before filesystem route matching
  - **routing.afterFiles** - Rewrite routes checked after filesystem route matching
  - **routing.dynamicRoutes** - Dynamic route matching table
  - **routing.onMatch** - Routes applied after a successful match (for example immutable static asset cache headers)
  - **routing.fallback** - Final rewrite fallback routes
  - **routing.shouldNormalizeNextData** - Whether `/_next/data/<buildId>/...` URLs should be normalized during matching
  - **routing.rsc** - Route metadata used for React Server Components routing behavior
- **context.outputs** (Object) - Detailed information about all build outputs organized by type
- **context.projectDir** (string) - Absolute path to the Next.js project directory
- **context.repoRoot** (string) - Absolute path to the detected repository root
- **context.distDir** (string) - Absolute path to the build output directory
- **context.config** (Object) - The final Next.js configuration (with `modifyConfig` applied)
- **context.nextVersion** (string) - Version of Next.js being used
- **context.buildId** (string) - Unique identifier for the current build
```


--------------------------------

### Read and mutate cookies with next/headers cookies()

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/03-file-conventions/route.mdx

Read, set, or delete cookies using the asynchronous cookies() helper from next/headers within a GET Route Handler.

```typescript
import { cookies } from 'next/headers'

export async function GET(request: NextRequest) {
  const cookieStore = await cookies()

  const a = cookieStore.get('a')
  const b = cookieStore.set('b', '1')
  const c = cookieStore.delete('c')
}
```

```javascript
import { cookies } from 'next/headers'

export async function GET(request) {
  const cookieStore = await cookies()

  const a = cookieStore.get('a')
  const b = cookieStore.set('b', '1')
  const c = cookieStore.delete('c')
}
```


--------------------------------

### Runtime flow for serving cached shell and resuming PPR

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/07-adapters/06-implementing-ppr-in-an-adapter.mdx

Shows the lifecycle where the adapter retrieves the cached shell, streams initial bytes to the client, and concatenates resumed render chunks generated with the postponed state.

```text
Client
  | GET /ppr-route
  v
Adapter Router
  |
  |-- read cached shell + postponedState ---> Platform Cache
  |<------------- cache hit -----------------|
  |
  |-- create responseStream = concat(shellStream, resumedStream)
  |
  |-- start piping shellStream ------------> Client (first bytes)
  |
  |-- invoke handler(req, res, { requestMeta: { postponed } })
  |   -------------------------------------> Entrypoint (handler)
  |   <------------------------------------- resumed chunks/cache entry
  |
  |-- append resumed chunks to resumedStream
  |
  '-- client receives one HTTP response:
      [shell bytes........][resumed bytes........]
```


--------------------------------

### Configure experimental.turbopackAdditionalRoots in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/turbopack.mdx

Configure `experimental.turbopackAdditionalRoots` to allow Turbopack to follow symbolic links pointing outside `turbopack.root`. Each key defines a unique root name with a target path, and paths must not overlap with `turbopack.root` or each other.

```javascript
const path = require('path')

module.exports = {
  experimental: {
    turbopackAdditionalRoots: {
      linkedPackages: { path: path.join(__dirname, '../packages') },
    },
  },
}
```


--------------------------------

### <Link>

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/02-components/link.mdx

Next.js `<Link>` component properties for handling routing behavior, localization, event lifecycle during navigation, and view transitions.

```APIDOC
### Component
`Link` (imported from `next/link`)

### Props

- **locale** (`string | false`) - Optional
  - The active locale is automatically prepended. Providing a string specifies a different locale. When set to `false`, `href` must include the locale explicitly as default locale prepending is disabled.

- **as** (`string`) - Optional
  - Optional decorator for the path that will be shown in the browser URL bar. Used when the displayed path differs from the one provided in `href`.

- **onNavigate** (`(e: { preventDefault: () => void }) => void`) - Optional
  - An event handler called during client-side navigation. The handler receives an event object with a `preventDefault()` method to cancel client-side navigation. Only executes during client-side/same-origin navigation (does not execute for modifier-clicks or download links).

- **transitionTypes** (`string[]`) - Optional (App Router only)
  - A list of transition types to apply to the navigation, passed to `React.addTransitionType` inside the navigation transition to enable `<ViewTransition>` animations.

### Usage Example

```tsx
import Link from 'next/link'

export default function Page() {
  return (
    <>
      {/* Custom locale */}
      <Link href="/dashboard" locale="fr">
        Dashboard (French)
      </Link>

      {/* Navigation interception */}
      <Link
        href="/dashboard"
        onNavigate={(e) => {
          console.log('Navigating...')
          // e.preventDefault()
        }}
      >
        Dashboard
      </Link>

      {/* View Transition types */}
      <Link href="/about" transitionTypes={['slide-in']}>
        About
      </Link>
    </>
  )
}
```
```


--------------------------------

### handler(req, res, ctx) (Node.js runtime)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/07-adapters/08-invoking-entrypoints.mdx

Invokes a Next.js Node.js build entrypoint using standard Node.js request and response objects with adapter runtime context. Adapters can supply custom helper functions and metadata via the requestMeta object.

```APIDOC
### Description
Invokes a Next.js Node.js build entrypoint using standard Node.js `IncomingMessage` and `ServerResponse` objects along with adapter context.

### Signature
```typescript
handler(
  req: IncomingMessage,
  res: ServerResponse,
  ctx: {
    waitUntil?: (promise: Promise<void>) => void
    requestMeta?: RequestMeta
  }
): Promise<void>
```

### Parameters
- **req** (`IncomingMessage`) - Node.js HTTP request object.
- **res** (`ServerResponse`) - Node.js HTTP response object.
- **ctx** (`object`) - Adapter runtime execution context.
  - **waitUntil** (`(promise: Promise<void>) => void`, optional) - Function to extend the lifetime of the execution context.
  - **requestMeta** (`RequestMeta`, optional) - Helpers and metadata passed to the entrypoint handler.
    - **relativeProjectDir** (`string`, optional) - Relative path from `process.cwd()` to the Next.js project directory.
    - **hostname** (`string`, optional) - Hostname used by route handlers when constructing absolute URLs.
    - **revalidate** (`(opts: { urlPath: string, headers: any, opts: any }) => Promise<any>`, optional) - Platform-specific revalidation implementation to avoid network requests.
    - **render404** (`(req: any, res: any, parsedUrl: any, setHeaders: any) => Promise<any>`, optional) - Platform-specific 404 rendering implementation.

### Returns
- `Promise<void>` - Resolves when the request has been handled and the response is sent.
```


--------------------------------

### Define static sitemap in app/sitemap.xml

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/03-file-conventions/01-metadata/sitemap.mdx

Place a static sitemap.xml file in the root of the app directory for smaller applications.

```xml
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://acme.com</loc>
    <lastmod>2023-04-06T15:02:24.021Z</lastmod>
    <changefreq>yearly</changefreq>
    <priority>1</priority>
  </url>
  <url>
    <loc>https://acme.com/about</loc>
    <lastmod>2023-04-06T15:02:24.021Z</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://acme.com/blog</loc>
    <lastmod>2023-04-06T15:02:24.021Z</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.5</priority>
  </url>
</urlset>
```


--------------------------------

### Configure named parameter path matching in redirects

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/redirects.mdx

Matches single-segment paths like `/old-blog/first-post` and forwards the matched `:slug` parameter to the destination. Does not match nested paths or URLs not anchored at the start.

```js
module.exports = {
  redirects() {
    return [
      {
        source: '/old-blog/:slug',
        destination: '/news/:slug', // Matched parameters can be used in the destination
        permanent: true,
      },
    ]
  },
}
```


--------------------------------

### prefetch()

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/prefetch.mdx

Defers runtime rendering of content out of the App Shell so that it renders during a per-link prefetch or navigation.

```APIDOC
## prefetch()

### Description
Awaiting `prefetch()` during runtime rendering keeps content out of the App Shell, allowing it to render during a per-link prefetch or navigation. It requires `cacheComponents` and `partialPrefetching` to be enabled.

### Import
```ts
import { prefetch } from 'next/cache'
```

### Syntax
```ts
await prefetch()
```

### Requirements
- Requires `cacheComponents: true` in `next.config.ts` (throws an error if not enabled).
- Requires `partialPrefetching: true` in `next.config.ts`.
- Cannot be awaited inside a cached scope such as `use cache` or `use cache: private`.

### Usage Example
```tsx
import { Suspense } from 'react'
import { cacheLife, prefetch } from 'next/cache'
import { cookies } from 'next/headers'

export default function Page() {
  return (
    <Suspense fallback={<p>Loading recommendations...</p>}>
      <Recommendations />
    </Suspense>
  )
}

async function Recommendations() {
  await prefetch() // runtime work below renders on a per-link prefetch or navigation
  const items = await getRecommendations()
  return <List items={items} />
}

async function getRecommendations() {
  'use cache: private'
  cacheLife('hours')
  const session = (await cookies()).get('session')?.value
  return db.recommendations.rank({ session })
}
```
```


--------------------------------

### Generate dynamic images in Route Handlers with ImageResponse

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/image-response.mdx

Use ImageResponse within a Route Handler GET function to dynamically generate images at request time using JSX and CSS styles.

```javascript
import { ImageResponse } from 'next/og'

export async function GET() {
  try {
    return new ImageResponse(
      (
        <div
          style={{
            height: '100%',
            width: '100%',
            display: 'flex',
            flexDirection: 'column',
            alignItems: 'center',
            justifyContent: 'center',
            backgroundColor: 'white',
            padding: '40px',
          }}
        >
          <div
            style={{
              fontSize: 60,
              fontWeight: 'bold',
              color: 'black',
              textAlign: 'center',
            }}
          >
            Welcome to My Site
          </div>
          <div
            style={{
              fontSize: 30,
              color: '#666',
              marginTop: '20px',
            }}
          >
            Generated with Next.js ImageResponse
          </div>
        </div>
      ),
      {
        width: 1200,
        height: 630,
      }
    )
  } catch (e) {
    console.log(`${e.message}`)
    return new Response(`Failed to generate the image`, {
      status: 500,
    })
  }
}
```


--------------------------------

### Match Regex Paths in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/headers.mdx

Wrap regex constraints in parentheses after a parameter name (for example, `(\d{1,})` to match numeric slugs). This ensures the header is applied only when the parameter matches the pattern.

```javascript
module.exports = {
  headers() {
    return [
      {
        source: '/blog/:post(\d{1,})',
        headers: [
          {            key: 'x-post',
            value: ':post',
          },
        ],
      },
    ]
  },
}
```


--------------------------------

### Managed agent instructions block in AGENTS.md

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/agentRules.mdx

Example of the managed block created or updated in `AGENTS.md` when `agentRules` is enabled and an AI coding agent is detected. Next.js modifies only the content between the comment markers.

```markdown
<!-- BEGIN:nextjs-agent-rules -->

## This is NOT the Next.js you know

This version has breaking changes — APIs, conventions, and file structure may all differ from your training data. Read the relevant guide in `node_modules/next/dist/docs/` (resolved from this file's directory; in monorepos the `next` package may not be visible from the repo root) before writing any code. Heed deprecation notices.

This block is written and re-added by `next dev` — verify at `node_modules/next/dist/server/lib/generate-agent-files.js`. Removing it from a diff only re-creates the uncommitted change; committing it with your work keeps the tree clean.

<!-- END:nextjs-agent-rules -->
```


--------------------------------

### Import asset using new URL constructor

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/urlImports.mdx

Resolves static external assets via the URL constructor and import.meta.url, producing a hashed static media pathname during build.

```javascript
const logo = new URL('https://example.com/assets/file.txt', import.meta.url)

console.log(logo.pathname)

// prints "/_next/static/media/file.a9727b5d.txt"
```


--------------------------------

### Set keep-alive timeout for downstream proxies with --keepAliveTimeout

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/06-cli/next.mdx

Configure the HTTP server keep-alive timeout in milliseconds for next start to prevent unexpected connection termination behind load balancers and proxies.

```bash
next start --keepAliveTimeout 70000
```


--------------------------------

### Import multiple modules with import.meta.glob

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/08-turbopack.mdx

Imports multiple matching modules as an object keyed by relative file paths with thunk values returning module promises.

```js
const modules = import.meta.glob('./dir/*.js')
// {
//   './dir/foo.js': () => import('./dir/foo.js'),
//   './dir/bar.js': () => import('./dir/bar.js'),
// }
```


--------------------------------

### Using ReactDOM.prefetchDNS for <link rel="dns-prefetch">

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/generate-metadata.mdx

Attempts to resolve a domain name before resources get requested. Emits a corresponding <link rel="dns-prefetch"> in the document head.

```tsx
ReactDOM.prefetchDNS(href: string)
```

```html
<link rel="dns-prefetch" href="..." />
```


--------------------------------

### Configure serverExternalPackages in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/serverExternalPackages.mdx

Opt out specific dependencies from Server Components bundling so they use native Node.js require.

```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  serverExternalPackages: ['@acme/ui'],
}

module.exports = nextConfig
```


--------------------------------

### Include native and runtime assets with outputFileTracingIncludes in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/output.mdx

Trace native modules and runtime binaries from node_modules for all server routes.

```javascript
module.exports = {
  outputFileTracingIncludes: {
    '/*': ['node_modules/sharp/**/*', 'node_modules/aws-crt/dist/bin/**/*'],
  },
}
```


--------------------------------

### Enable exposeTestingApiInProductionBuild in next.config

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/exposeTestingApiInProductionBuild.mdx

Enables the Instant Navigation testing API conditionally for production builds. Requires cacheComponents to be enabled.

```typescript
import type { NextConfig } from 'next'

const exposeTestingApi = process.env.EXPOSE_TESTING_API === '1'

const nextConfig: NextConfig = {
  cacheComponents: true,
  experimental: {
    exposeTestingApiInProductionBuild: exposeTestingApi,
  },
}

export default nextConfig
```

```javascript
const exposeTestingApi = process.env.EXPOSE_TESTING_API === '1'

/** @type {import('next').NextConfig} */
const nextConfig = {
  cacheComponents: true,
  experimental: {
    exposeTestingApiInProductionBuild: exposeTestingApi,
  },
}

module.exports = nextConfig
```


--------------------------------

### Static asset request with deployment query parameter

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/supportsImmutableAssets.mdx

Shows the URL format for static asset requests containing a deployment-specific query parameter when skew protection is enabled.

```plain
GET https://foo.com/_next/static/chunks/0d_ks0ow7ur6m.js?dpl=<unique-deployment-id>
```


--------------------------------

### Define a not-found UI component

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/03-file-conventions/not-found.mdx

Renders UI when the notFound function is invoked within a route segment. Next.js returns a 404 status code before streaming starts and injects a noindex robots meta tag.

```tsx
import Link from 'next/link'

export default function NotFound() {
  return (
    <div>
      <h2>Not Found</h2>
      <p>Could not find requested resource</p>
      <Link href="/">Return Home</Link>
    </div>
  )
}
```

```jsx
import Link from 'next/link'

export default function NotFound() {
  return (
    <div>
      <h2>Not Found</h2>
      <p>Could not find requested resource</p>
      <Link href="/">Return Home</Link>
    </div>
  )
}
```


--------------------------------

### Define a forbidden UI component

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/03-file-conventions/forbidden.mdx

Renders UI when the forbidden() function is invoked. Next.js returns a 403 status code before streaming starts, and injects a noindex robots meta tag in both pre-streaming and post-streaming responses.

```tsx
import Link from 'next/link'

export default function Forbidden() {
  return (
    <div>
      <h2>Forbidden</h2>
      <p>You are not authorized to access this resource.</p>
      <Link href="/">Return Home</Link>
    </div>
  )
}
```

```jsx
import Link from 'next/link'

export default function Forbidden() {
  return (
    <div>
      <h2>Forbidden</h2>
      <p>You are not authorized to access this resource.</p>
      <Link href="/">Return Home</Link>
    </div>
  )
}
```


--------------------------------

### Use generateStaticParams in Route Handlers with Cache Components

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/generate-static-params.mdx

Combine generateStaticParams with 'use cache' inside a Route Handler for cached static generation. In this example, dynamic params are resolved and passed to a cached helper function.

```ts
export async function generateStaticParams() {
  return [{ id: '1' }, { id: '2' }, { id: '3' }]
}

async function getPost(id: Promise<string>) {
  'use cache'
  const resolvedId = await id
  const response = await fetch(`https://api.example.com/posts/${resolvedId}`)
  return response.json()
}

export async function GET(
  request: Request,
  { params }: RouteContext<'/api/posts/[id]'>
) {
  const post = await getPost(params.then((p) => p.id))
  return Response.json(post)
}
```


--------------------------------

### Defining an unauthorized file component in Next.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/03-file-conventions/unauthorized.mdx

Renders UI when the unauthorized function is triggered. Next.js returns a 401 status code before streaming or 200 after streaming starts, injecting a noindex robots meta tag in both cases.

```tsx
import Login from '@/app/components/Login'

export default function Unauthorized() {
  return (
    <main>
      <h1>401 - Unauthorized</h1>
      <p>Please log in to access this page.</p>
      <Login />
    </main>
  )
}
```

```jsx
import Login from '@/app/components/Login'

export default function Unauthorized() {
  return (
    <main>
      <h1>401 - Unauthorized</h1>
      <p>Please log in to access this page.</p>
      <Login />
    </main>
  )
}
```


--------------------------------

### Configure Header Overriding in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/headers.mdx

If two headers match the same path and set the same header key, the last matching header overrides previous ones. For example, requests to `/hello` receive the header `x-hello: world` instead of `there`.

```javascript
module.exports = {
  headers() {
    return [
      {
        source: '/:path*',
        headers: [
          {            key: 'x-hello',
            value: 'there',
          },
        ],
      },
      {
        source: '/hello',
        headers: [
          {            key: 'x-hello',
            value: 'world',
          },
        ],
      },
    ]
  },
}
```


--------------------------------

### Configure remotePatterns with wildcard hostname in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/02-components/image.mdx

Allows subdomains such as image.example.com using the double wildcard pattern on the hostname.

```js
module.exports = {
  images: {
    remotePatterns: [
      {
        protocol: 'https',
        hostname: '**.example.com',
        port: '',
        search: '',
      },
    ],
  },
}
```


--------------------------------

### Calling forbidden() after streaming has started in app/projects/page.tsx

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/forbidden.mdx

Trigger forbidden() inside a Data Access Layer function wrapped in a Suspense boundary so the page shell streams while the session is verified. When triggered, the error propagates to the nearest forbidden boundary.

```tsx
import { Suspense } from 'react'
import { verifySession } from '@/app/lib/dal'
import { forbidden } from 'next/navigation'

async function getProjects() {
  const session = await verifySession()
  if (session?.role !== 'admin') {
    forbidden()
  }
  return db.projects.findMany()
}

async function Projects() {
  const projects = await getProjects()
  return (
    <ul>
      {projects.map((project) => (
        <li key={project.id}>{project.name}</li>
      ))}
    </ul>
  )
}

export default function ProjectsPage() {
  return (
    <main>
      <h1>Projects</h1>
      <Suspense fallback={<p>Loading...</p>}>
        <Projects />
      </Suspense>
    </main>
  )
}
```

```jsx
import { Suspense } from 'react'
import { verifySession } from '@/app/lib/dal'
import { forbidden } from 'next/navigation'

async function getProjects() {
  const session = await verifySession()
  if (session?.role !== 'admin') {
    forbidden()
  }
  return db.projects.findMany()
}

async function Projects() {
  const projects = await getProjects()
  return (
    <ul>
      {projects.map((project) => (
        <li key={project.id}>{project.name}</li>
      ))}
    </ul>
  )
}

export default function ProjectsPage() {
  return (
    <main>
      <h1>Projects</h1>
      <Suspense fallback={<p>Loading...</p>}>
        <Projects />
      </Suspense>
    </main>
  )
}
```


--------------------------------

### Configure custom qualities allowlist in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/02-components/image.mdx

Expands the allowlist of permitted image quality values. Unmatched quality prop values resolve to the closest allowed value, and direct REST requests with invalid values return a 400 Bad Request.

```js
module.exports = {
  images: {
    qualities: [25, 50, 75, 100],
  },
}
```


--------------------------------

### Revalidating tags in a Route Handler

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/revalidateTag.mdx

Extract a tag from request query parameters in a GET Route Handler to revalidate cache entries on-demand. Using profile "max" marks matching tagged data as stale.

```typescript
import type { NextRequest } from 'next/server'
import { revalidateTag } from 'next/cache'

export async function GET(request: NextRequest) {
  const tag = request.nextUrl.searchParams.get('tag')

  if (tag) {
    revalidateTag(tag, 'max')
    return Response.json({ revalidated: true, now: Date.now() })
  }

  return Response.json({
    revalidated: false,
    now: Date.now(),
    message: 'Missing tag to revalidate',
  })
}
```

```javascript
import { revalidateTag } from 'next/cache'

export async function GET(request) {
  const tag = request.nextUrl.searchParams.get('tag')

  if (tag) {
    revalidateTag(tag, 'max')
    return Response.json({ revalidated: true, now: Date.now() })
  }

  return Response.json({
    revalidated: false,
    now: Date.now(),
    message: 'Missing tag to revalidate',
  })
}
```


--------------------------------

### Enable AVIF and WebP image formats in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/02-components/image.mdx

Enables both AVIF and WebP formats, prioritizing AVIF for supported browsers with WebP as a fallback.

```js
module.exports = {
  images: {
    formats: ['image/avif', 'image/webp'],
  },
}
```


--------------------------------

### Run ESLint using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/03-eslint.mdx

Executes ESLint against all project files using npx.

```bash
npx eslint .
```


--------------------------------

### Define a basic proxy function with route matcher

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/03-file-conventions/proxy.mdx

Create a `proxy.ts` (or `.js`) file in the project root or inside `src` at the same level as `pages` or `app`. Redirects incoming requests matching `/about/:path*` to `/home`.

```tsx
import { NextResponse } from 'next/server'
import type { NextRequest } from 'next/server'

// This function can be marked `async` if using `await` inside
export function proxy(request: NextRequest) {
  return NextResponse.redirect(new URL('/home', request.url))
}

export const config = {
  matcher: '/about/:path*',
}
```

```js
import { NextResponse } from 'next/server'

// This function can be marked `async` if using `await` inside
export function proxy(request) {
  return NextResponse.redirect(new URL('/home', request.url))
}

export const config = {
  matcher: '/about/:path*',
}
```


--------------------------------

### Configure custom Turbopack garbage collection timings in next.config

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/turbopackGc.mdx

Overrides default garbage collection timings by setting minProgressMs and rootTtlMs. In this example, garbage collection passes run for at least 200 ms before interruption and unanchored roots expire after one day.

```typescript
import type { NextConfig } from 'next'

const nextConfig: NextConfig = {
  experimental: {
    turbopackGc: {
      minProgressMs: 200,
      rootTtlMs: 24 * 60 * 60 * 1000,
    },
  },
}

export default nextConfig
```

```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  experimental: {
    turbopackGc: {
      minProgressMs: 200,
      rootTtlMs: 24 * 60 * 60 * 1000,
    },
  },
}

module.exports = nextConfig
```


--------------------------------

### Configure custom thresholds for experimental.prefetchInlining

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/prefetchInlining.mdx

Pass an object to `experimental.prefetchInlining` to configure `maxSize` and `maxBundleSize` in bytes of the gzip-compressed segment response. Any omitted property retains its default threshold.

```typescript
import type { NextConfig } from 'next'

const nextConfig: NextConfig = {
  experimental: {
    prefetchInlining: {
      maxSize: 2048,
      maxBundleSize: 10240,
    },
  },
}

export default nextConfig
```

```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  experimental: {
    prefetchInlining: {
      maxSize: 2048,
      maxBundleSize: 10240,
    },
  },
}

module.exports = nextConfig
```


--------------------------------

### Save analysis snapshot and stream graph using next analyze export

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/06-cli/next.mdx

Builds and writes analyzer data and UI files to disk without starting the web UI using --output. Streams the saved snapshot graph as JSON Lines with the export subcommand without triggering a rebuild.

```bash
# Build and save a snapshot without starting the UI server
npx next analyze --output --snapshot audit-1

# Stream that saved graph as one JSON object per line, without rebuilding
npx next analyze export --snapshot audit-1 > graph.jsonl
```


--------------------------------

### Allow local IP image optimization in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/02-components/image.mdx

Enables image optimization from local IP addresses on private networks, such as in a VPC with split-horizon DNS.

```javascript
module.exports = {
  images: {
    dangerouslyAllowLocalIP: true,
  },
}
```


--------------------------------

### Configure package.json scripts to use Webpack instead of Turbopack

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/08-turbopack.mdx

Add the `--webpack` flag to `dev` and `build` scripts in `package.json` to opt out of Turbopack and use Webpack.

```json
{
  "scripts": {
    "dev": "next dev --webpack",
    "build": "next build --webpack",
    "start": "next start"
  }
}
```


--------------------------------

### Configure assetPrefix in next.config.mjs

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/assetPrefix.mdx

Sets a CDN URL prefix for static assets in production while omitting it during development. Use phase detection to avoid CDN redirection during local development.

```javascript
// @ts-check
import { PHASE_DEVELOPMENT_SERVER } from 'next/constants'

export default (phase) => {
  const isDev = phase === PHASE_DEVELOPMENT_SERVER
  /**
   * @type {import('next').NextConfig}
   */
  const nextConfig = {
    assetPrefix: isDev ? undefined : 'https://cdn.mydomain.com',
  }
  return nextConfig
}
```


--------------------------------

### Render full-screen background image

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/02-components/image.mdx

Use the fill prop with 100vw sizes and objectFit cover to cover the entire screen background.

```jsx
import Image from 'next/image'
import mountains from '../public/mountains.jpg'

export default function Background() {
  return (
    <Image
      alt="Mountains"
      src={mountains}
      placeholder="blur"
      quality={100}
      fill
      sizes="100vw"
      style={{
        objectFit: 'cover',
      }}
    />
  )
}
```


--------------------------------

### Combine outputFileTracingRoot with outputFileTracingIncludes in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/output.mdx

Combine outputFileTracingRoot with outputFileTracingIncludes to trace files located outside the app folder in a monorepo.

```javascript
const path = require('path')

module.exports = {
  // Trace from the monorepo root
  outputFileTracingRoot: path.join(__dirname, '../../'),
  outputFileTracingIncludes: {
    '/route1': ['../shared/assets/**/*'],
  },
}
```


--------------------------------

### Enable Rust MDX compiler with experimental.mdxRs in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/mdxRs.mdx

Configures @next/mdx to compile MDX files using the experimental Rust compiler by enabling experimental.mdxRs.

```javascript
const withMDX = require('@next/mdx')()

/** @type {import('next').NextConfig} */
const nextConfig = {
  pageExtensions: ['ts', 'tsx', 'mdx'],
  experimental: {
    mdxRs: true,
  },
}

module.exports = withMDX(nextConfig)
```


--------------------------------

### Define configuration as a function in next.config.mjs

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/index.mdx

Export a function accepting the current phase and default configuration object to return dynamic configuration.

```javascript
// @ts-check

export default (phase, { defaultConfig }) => {
  /**
   * @type {import('next').NextConfig}
   */
  const nextConfig = {
    /* config options here */
  }
  return nextConfig
}
```


--------------------------------

### import.meta.glob(pattern, options?)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/08-turbopack.mdx

Vite-compatible API for importing multiple modules at once using glob patterns. Supports lazy loading, eager loading, and named exports.

```APIDOC
## import.meta.glob(pattern, [options])

### Description
A Vite-compatible API supported in Turbopack for importing multiple modules at once using glob patterns. The result is an object keyed by the file path relative to the calling file (or absolute from project root).

### Parameters
- **pattern** (string | string[]) - Required - A glob pattern relative to the importing file (`./`, `../`) or absolute from the project root (`/`).
- **options** (object) - Optional - Configuration options for module loading.
  - **eager** (boolean) - Optional - When set to `true`, imports modules immediately rather than as lazy-loaded thunks returning promises.
  - **import** (string) - Optional - Selects a specific named export from each matched module (e.g., `'default'`).

### Returns
- **Record<string, Function | object>** - An object with keys as matching file paths. In default lazy mode, values are thunks `() => Promise<Module>`. In eager mode (`{ eager: true }`), values are the imported modules or named export values directly.

### Usage Example
```js
// Lazy loading (default)
const modules = import.meta.glob('./dir/*.js')
for (const path in modules) {
  const module = await modules[path]()
  console.log(path, module)
}

// Eager loading
const eagerModules = import.meta.glob('./dir/*.js', { eager: true })

// Named imports
const defaults = import.meta.glob('./dir/*.js', { import: 'default' })
const setups = import.meta.glob('./dir/*.js', { import: 'setup', eager: true })
```
```


--------------------------------

### Create custom deploy script in scripts/e2e-deploy.sh

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/07-adapters/04-testing-adapters.mdx

Implements the NEXT_TEST_DEPLOY_SCRIPT_PATH contract to build and deploy an isolated test application. The script outputs only the deployment URL to stdout, routing diagnostics and build metadata to stderr and working directory files.

```bash
#!/usr/bin/env bash
set -euo pipefail

# Install the adapter, build the app, and deploy or start it.
node -e "
const pkg=JSON.parse(require('fs').readFileSync('package.json','utf8'));
pkg.dependencies=pkg.dependencies||{};
pkg.dependencies['adapter']='file:${ADAPTER_DIR}';
require('fs').writeFileSync('package.json',JSON.stringify(pkg,null,2));
" >&2

# Set the adapter path so that the app uses it.
export NEXT_ADAPTER_PATH="${ADAPTER_DIR}/dist/index.js"

# Build the app
pnpm build

# Write any metadata needed later to files in the working directory.
BUILD_ID="$(cat .next/BUILD_ID)"
DEPLOYMENT_ID="my-adapter-local"
# If your adapter enables immutable static assets, set this to "1".
NEXT_SUPPORTS_IMMUTABLE_ASSETS="0"

{
  echo "BUILD_ID: $BUILD_ID"
  echo "DEPLOYMENT_ID: $DEPLOYMENT_ID"
  echo "NEXT_SUPPORTS_IMMUTABLE_ASSETS: $NEXT_SUPPORTS_IMMUTABLE_ASSETS"
} >> .adapter-build.log

# Start or deploy the app. Capture the URL at this point or make the script output the URL to stdout.
provider-cli-to-deploy

# Example URL output:
# echo "http://127.0.0.1:3000"
```


--------------------------------

### Target all routes with outputFileTracingIncludes in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/output.mdx

Apply output file tracing rules across all routes using the global /* route glob key.

```javascript
module.exports = {
  outputFileTracingIncludes: {
    '/*': ['src/i18n/locales/**/*.json'],
  },
}
```


--------------------------------

### Match headers, cookies, queries, and hosts in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/headers.mdx

Apply headers conditionally by defining `has` and `missing` rules for request headers, cookies, query parameters, or hostnames. All `has` items and the `source` must match, and all `missing` items must not match for headers to be applied.

```javascript
module.exports = {
  headers() {
    return [
      // if the header `x-add-header` is present,
      // the `x-another-header` header will be applied
      {
        source: '/:path*',
        has: [
          {
            type: 'header',
            key: 'x-add-header',
          },
        ],
        headers: [
          {
            key: 'x-another-header',
            value: 'hello',
          },
        ],
      },
      // if the header `x-no-header` is not present,
      // the `x-another-header` header will be applied
      {
        source: '/:path*',
        missing: [
          {
            type: 'header',
            key: 'x-no-header',
          },
        ],
        headers: [
          {
            key: 'x-another-header',
            value: 'hello',
          },
        ],
      },
      // if the source, query, and cookie are matched,
      // the `x-authorized` header will be applied
      {
        source: '/specific/:path*',
        has: [
          {
            type: 'query',
            key: 'page',
            // the page value will not be available in the
            // header key/values since value is provided and
            // doesn't use a named capture group e.g. (?<page>home)
            value: 'home',
          },
          {
            type: 'cookie',
            key: 'authorized',
            value: 'true',
          },
        ],
        headers: [
          {
            key: 'x-authorized',
            value: ':authorized',
          },
        ],
      },
      // if the header `x-authorized` is present and
      // contains a matching value, the `x-another-header` will be applied
      {
        source: '/:path*',
        has: [
          {
            type: 'header',
            key: 'x-authorized',
            value: '(?<authorized>yes|true)',
          },
        ],
        headers: [
          {
            key: 'x-another-header',
            value: ':authorized',
          },
        ],
      },
      // if the host is `example.com`,
      // this header will be applied
      {
        source: '/:path*',
        has: [
          {
            type: 'host',
            value: 'example.com',
          },
        ],
        headers: [
          {
            key: 'x-another-header',
            value: ':authorized',
          },
        ],
      },
    ]
  },
}
```


--------------------------------

### Check static and dynamic route indicators in build output

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/devIndicators.mdx

Verify whether a route is static (○) or dynamic (ƒ) by reviewing the build output generated by running next build --debug.

```bash
Route (app)
┌ ○ /_not-found
└ ƒ /products/[id]

○  (Static)   prerendered as static content
ƒ  (Dynamic)  server-rendered on demand
```


--------------------------------

### Run Next.js with Webpack CLI flag

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/08-turbopack.mdx

Use the `--webpack` flag for development and build commands on platforms without native Turbopack bindings (such as FreeBSD and OpenBSD).

```bash
next dev --webpack
next build --webpack
```


--------------------------------

### Enable AVIF image format in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/02-components/image.mdx

Enables AVIF image format optimization with a fallback to the original format if unsupported.

```js
module.exports = {
  images: {
    formats: ['image/avif'],
  },
}
```


--------------------------------

### Profile Next.js commands using --experimental-cpu-prof

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/06-cli/next.mdx

Enables V8's CPU profiler and saves generated .cpuprofile files to .next-profiles/ upon process exit. Profiles can be analyzed using Chrome DevTools or other V8-compatible profiling tools.

```bash
# Profile the build process
next build --experimental-cpu-prof

# Profile the dev server (profile saved on Ctrl+C or SIGTERM)
next dev --experimental-cpu-prof

# Profile the production server
next start --experimental-cpu-prof
```


--------------------------------

### Import BlogNavLink into a parent layout Server Component

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/use-selected-layout-segment.mdx

Renders a list of active link Client Components inside a parent layout Server Component.

```tsx
// Import the Client Component into a parent Layout (Server Component)
import { BlogNavLink } from './blog-nav-link'
import getFeaturedPosts from './get-featured-posts'

export default async function Layout({
  children,
}: {
  children: React.ReactNode
}) {
  const featuredPosts = await getFeaturedPosts()
  return (
    <div>
      {featuredPosts.map((post) => (
        <div key={post.id}>
          <BlogNavLink slug={post.slug}>{post.title}</BlogNavLink>
        </div>
      ))}
      <div>{children}</div>
    </div>
  )
}
```

```jsx
// Import the Client Component into a parent Layout (Server Component)
import { BlogNavLink } from './blog-nav-link'
import getFeaturedPosts from './get-featured-posts'

export default async function Layout({ children }) {
  const featuredPosts = await getFeaturedPosts()
  return (
    <div>
      {featuredPosts.map((post) => (
        <div key={post.id}>
          <BlogNavLink slug={post.slug}>{post.title}</BlogNavLink>
        </div>
      ))}
      <div>{children}</div>
    </div>
  )
}
```


--------------------------------

### Import instant helper from @next/playwright

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/03-file-conventions/02-route-segment-config/instant.mdx

Imports the instant testing helper to freeze dynamic content while running assertions against instant UI.

```typescript
import { instant } from '@next/playwright'
```


--------------------------------

### Replay logs in custom logs script (scripts/e2e-logs.sh)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/07-adapters/04-testing-adapters.mdx

Replays build and server logs during adapter testing so the harness can extract required markers such as BUILD_ID, DEPLOYMENT_ID, and NEXT_SUPPORTS_IMMUTABLE_ASSETS. Configured via NEXT_TEST_DEPLOY_LOGS_SCRIPT_PATH, this script runs in the isolated temporary app directory.

```bash
#!/usr/bin/env bash
set -euo pipefail

if [ -f ".adapter-build.log" ]; then
  cat ".adapter-build.log"
fi

if [ -f ".adapter-server.log" ]; then
  echo "=== .adapter-server.log ==="
  cat ".adapter-server.log"
fi
```


--------------------------------

### Preloading resources using ReactDOM methods

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/generate-metadata.mdx

Use ReactDOM methods in a Client Component to safely insert resource hints into the <head> of the document. These methods are supported in Client Components and are still server-side rendered on initial page load.

```tsx
'use client'

import ReactDOM from 'react-dom'

export function PreloadResources() {
  ReactDOM.preload('...', { as: '...' })
  ReactDOM.preconnect('...', { crossOrigin: '...' })
  ReactDOM.prefetchDNS('...')

  return '...'
}
```

```jsx
'use client'

import ReactDOM from 'react-dom'

export function PreloadResources() {
  ReactDOM.preload('...', { as: '...' })
  ReactDOM.preconnect('...', { crossOrigin: '...' })
  ReactDOM.prefetchDNS('...')

  return '...'
}
```


--------------------------------

### navigation()

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/navigation.mdx

Defers runtime work below the call until client navigation occurs, keeping it out of the App Shell and per-link prefetches. Requires Cache Components enabled.

```APIDOC
### Description
Calling `await navigation()` keeps runtime work below it out of the App Shell and per-link prefetches. The deferred work executes when the user navigates, while the fallback of the nearest `<Suspense>` boundary renders in the prefetched output.

### Signature
```ts
function navigation(): Promise<void>
```

### Import
```ts
import { navigation } from 'next/cache'
```

### Requirements
- Requires `cacheComponents: true` in `next.config.ts` (throws without it).
- Designed for routes using Partial Prefetching (`partialPrefetching: true`).

### Example
```tsx
import { Suspense } from 'react'
import { cookies } from 'next/headers'
import { navigation } from 'next/cache'

export default function Page({ params }: PageProps<'/post/[slug]'>) {
  return (
    <Suspense fallback={<p>Loading comments...</p>}>
      <Comments params={params} />
    </Suspense>
  )
}

async function Comments({ params }: { params: Promise<{ slug: string }> }) {
  await navigation() // runtime work below renders on navigation
  const { slug } = await params
  const sort = (await cookies()).get('comment-sort')?.value ?? 'newest'
  const items = await getComments(slug, sort)
  return <CommentList items={items} />
}
```
```


--------------------------------

### Configure basic webpack loader in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/turbopack.mdx

Maps file extensions to loaders such as @svgr/webpack under the turbopack.rules key. Rules are evaluated in order and match by file name or project-relative path.

```javascript
module.exports = {
  turbopack: {
    rules: {
      '*.svg': {
        loaders: ['@svgr/webpack'],
        as: '*.js',
      },
    },
  },
}
```


--------------------------------

### Match rewrites using header, cookie, query, and host in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/rewrites.mdx

Configure conditional rewrites using `has` and `missing` fields matching against `header`, `cookie`, `query`, or `host` keys and values. Both `source` and all `has` items must match while all `missing` items must not match for the rewrite to execute.

```javascript
module.exports = {
  rewrites() {
    return [
      // if the header `x-rewrite-me` is present,
      // this rewrite will be applied
      {
        source: '/:path*',
        has: [
          {
            type: 'header',
            key: 'x-rewrite-me',
          },
        ],
        destination: '/another-page',
      },
      // if the header `x-rewrite-me` is not present,
      // this rewrite will be applied
      {
        source: '/:path*',
        missing: [
          {
            type: 'header',
            key: 'x-rewrite-me',
          },
        ],
        destination: '/another-page',
      },
      // if the source, query, and cookie are matched,
      // this rewrite will be applied
      {
        source: '/specific/:path*',
        has: [
          {
            type: 'query',
            key: 'page',
            // the page value will not be available in the
            // destination since value is provided and doesn't
            // use a named capture group e.g. (?<page>home)
            value: 'home',
          },
          {
            type: 'cookie',
            key: 'authorized',
            value: 'true',
          },
        ],
        destination: '/:path*/home',
      },
      // if the header `x-authorized` is present and
      // contains a matching value, this rewrite will be applied
      {
        source: '/:path*',
        has: [
          {
            type: 'header',
            key: 'x-authorized',
            value: '(?<authorized>yes|true)',
          },
        ],
        destination: '/home?authorized=:authorized',
      },
      // if the host is `example.com`,
      // this rewrite will be applied
      {
        source: '/:path*',
        has: [
          {
            type: 'host',
            value: 'example.com',
          },
        ],
        destination: '/another-page',
      },
    ]
  },
}
```


--------------------------------

### Invoke Node.js entrypoint with requestMeta helpers

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/07-adapters/08-invoking-entrypoints.mdx

Pass custom adapter helpers such as relativeProjectDir, hostname, revalidate, and render404 directly through requestMeta when calling the handler.

```ts
await handler(req, res, {
  requestMeta: {
    // Relative path from process.cwd() to the Next.js project directory.
    relativeProjectDir: '.',
    // Optional hostname used by route handlers when constructing absolute URLs.
    hostname: '127.0.0.1',
    // Optional internal revalidate function to avoid revalidating over the network
    revalidate: async ({ urlPath, headers, opts }) => {
      // platform-specific revalidate implementation
    },
    // Optional function to render the 404 page for pages router `notFound: true`
    render404: async (req, res, parsedUrl, setHeaders) => {
      // platform-specific 404 rendering implementation
    },
  },
})
```


--------------------------------

### Run ESLint using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/03-eslint.mdx

Executes ESLint against all project files using pnpm.

```bash
pnpm exec eslint .
```


--------------------------------

### prefetch()

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/prefetch.mdx

Defers runtime work below it until a per-link prefetch or navigation. Keeps work out of the App Shell while rendering the fallback of the nearest Suspense boundary.

```APIDOC
## prefetch()

### Description
Calling `await prefetch()` keeps runtime work below it out of the route's App Shell. The work can run during a per-link prefetch or navigation, while the fallback of the nearest `<Suspense>` boundary renders in the shell. Use `prefetch()` for content that the App Shell would otherwise render but that is expensive to generate. Static prerenders still include the content in their output.

### Signature
```typescript
async function prefetch(): Promise<void>
```

### Usage Example
```tsx
import { prefetch } from 'next/server'

export default async function Page() {
  await prefetch()
  // Expensive runtime work deferred until prefetch/navigation
}
```
```


--------------------------------

### Directory structure of root parameters vs route parameters

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/next-root-params.mdx

Demonstrates the directory layout where [lang] serves as a root parameter shared by all nested routes, while deeper route parameters like [slug] are localized to specific branches.

```txt
app/
  [lang]/              ← root parameter (shared by all routes below)
    layout.tsx         ← root layout
    page.tsx           ← has no slug, doesn't know about blog or store
    blog/
      [slug]/          ← route parameter
        page.tsx
    store/
      [...slug]/       ← catch-all route parameter with the same name
        page.tsx
```


--------------------------------

### Import static image from URL using next/image

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/urlImports.mdx

Imports an image directly from an external URL and renders it with blur placeholder support in the next/image component.

```javascript
import Image from 'next/image'
import logo from 'https://example.com/assets/logo.png'

export default () => (
  <div>
    <Image src={logo} placeholder="blur" />
  </div>
)
```


--------------------------------

### Configure outputFileTracingExcludes and outputFileTracingIncludes in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/output.mdx

Specify route globs and project-root-relative glob patterns to manually include or exclude files from the output trace.

```javascript
module.exports = {
  outputFileTracingExcludes: {
    '/api/hello': ['./un-necessary-folder/**/*'],
  },
  outputFileTracingIncludes: {
    '/api/another': ['./necessary-folder/**/*'],
    '/api/login/\[\[\.\.\.slug\]\]': [
      './node_modules/aws-crt/dist/bin/**/*',
    ],
  },
}
```


--------------------------------

### requestMeta.onCacheEntryV2 execution flow

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/07-adapters/06-implementing-ppr-in-an-adapter.mdx

Illustrates how onCacheEntryV2 receives cache entries, persists state to the platform cache, and uses its return value to control response delegation.

```text
Entrypoint (handler)
  | onCacheEntryV2(cacheEntry, { url })
  v
requestMeta.onCacheEntryV2 callback
  |
  |-- if APP_PAGE ---> persist html + postponedState + headers ---> Platform Cache
  |
  '-- return false: continue normal Next.js response flow
      return true:  adapter already handled response (short-circuit)
```


--------------------------------

### Render navigation links in app/blog/layout

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/03-file-conventions/layout.mdx

Import and render the NavLink Client Component within a layout to display dynamic post navigation alongside layout children.

```tsx
import { NavLink } from './nav-link'
import getPosts from './get-posts'

export default async function Layout({
  children,
}: {
  children: React.ReactNode
}) {
  const featuredPosts = await getPosts()
  return (
    <div>
      {featuredPosts.map((post) => (
        <div key={post.id}>
          <NavLink slug={post.slug}>{post.title}</NavLink>
        </div>
      ))}
      <div>{children}</div>
    </div>
  )
}
```

```jsx
import { NavLink } from './nav-link'
import getPosts from './get-posts'

export default async function Layout({ children }) {
  const featuredPosts = await getPosts()
  return (
    <div>
      {featuredPosts.map((post) => (
        <div key={post.id}>
          <NavLink slug={post.slug}>{post.title}</NavLink>
        </div>
      ))}
      <div>{children}</div>
    </div>
  )
}
```


--------------------------------

### Configure output file tracing with a src directory in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/output.mdx

Reference paths under the src/ directory in tracing patterns, which are resolved relative to the project root.

```javascript
module.exports = {
  outputFileTracingIncludes: {
    '/products/*': ['src/lib/payments/**/*'],
    '/*': ['src/config/runtime/**/*.json'],
  },
  outputFileTracingExcludes: {
    '/api/*': ['src/temp/**/*', 'public/large-logs/**/*'],
  },
}
```


--------------------------------

### Define static robots.txt in app directory

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/03-file-conventions/01-metadata/robots.mdx

Places a static robots.txt file in the root of the app directory to declare crawling rules and sitemap locations.

```txt
User-Agent: *
Allow: /
Disallow: /private/

Sitemap: https://acme.com/sitemap.xml
```


--------------------------------

### Configure basePath in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/basePath.mdx

Sets a sub-path prefix for deploying the application under a custom domain path. This value must be set at build time and cannot be changed without re-building because it is inlined into client-side bundles.

```js
module.exports = {
  basePath: '/docs',
}
```


--------------------------------

### Configure localPatterns in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/02-components/image.mdx

Restricts image optimization to specific local pathnames and search query rules, returning 400 Bad Request for any other paths.

```javascript
module.exports = {
  images: {
    localPatterns: [
      {
        pathname: '/assets/images/**',
        search: '',
      },
    ],
  },
}
```


--------------------------------

### Illustrating route CSS imports for chunk merging decisions

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/cssChunking.mdx

Represents two routes sharing a stylesheet where one route includes an additional unshared file. Demonstrates the trade-off between merging CSS into a single shared chunk or creating separate requests.

```txt
/a → [shared.css, only-a.css]
/b → [shared.css]
```


--------------------------------

### Build-time environment variable replacement

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/env.mdx

Illustrates how Next.js inlines the configured environment variable value directly into the code during build time.

```jsx
return <h1>The value of customKey is: {process.env.customKey}</h1>
```

```jsx
return <h1>The value of customKey is: {'my-value'}</h1>
```


--------------------------------

### Configure onDemandEntries in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/onDemandEntries.mdx

Adjust how Next.js disposes or keeps built pages in development memory by configuring buffer duration (maxInactiveAge) and simultaneous page retention (pagesBufferLength).

```javascript
module.exports = {
  onDemandEntries: {
    // period (in ms) where the server will keep pages in the buffer
    maxInactiveAge: 25 * 1000,
    // number of pages that should be kept simultaneously without being disposed
    pagesBufferLength: 2,
  },
}
```


--------------------------------

### Create responsive static image with auto height

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/02-components/image.mdx

Make statically imported images responsive across viewports by setting width to 100% and height to auto in the style prop.

```jsx
import Image from 'next/image'
import mountains from '../public/mountains.jpg'

export default function Responsive() {
  return (
    <div style={{ display: 'flex', flexDirection: 'column' }}>
      <Image
        alt="Mountains"
        // Importing an image will
        // automatically set the width and height
        src={mountains}
        sizes="100vw"
        // Make the image display full width
        // and preserve its aspect ratio
        style={{
          width: '100%',
          height: 'auto',
        }}
      />
    </div>
  )
}
```


--------------------------------

### Run next typegen for default or specific directories

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/06-cli/next.mdx

Generates route types in <distDir>/types and creates a next-env.d.ts file for the current project or a specified target directory.

```bash
next typegen
# or for a specific app
next typegen ./apps/web
```


--------------------------------

### Configure redirects with basePath support

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/redirects.mdx

Configure redirects alongside `basePath` in `next.config.js`. Each `source` and `destination` is automatically prefixed with the `basePath` unless `basePath: false` is explicitly set.

```javascript
module.exports = {
  basePath: '/docs',

  redirects() {
    return [
      {
        source: '/with-basePath', // automatically becomes /docs/with-basePath
        destination: '/another', // automatically becomes /docs/another
        permanent: false,
      },
      {
        // does not add /docs since basePath: false is set
        source: '/without-basePath',
        destination: 'https://example.com',
        basePath: false,
        permanent: false,
      },
    ]
  },
}
```


--------------------------------

### Eagerly load modules with eager option in import.meta.glob

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/08-turbopack.mdx

Passes eager: true to import.meta.glob to load all matched modules directly up front instead of as thunks.

```js
const modules = import.meta.glob('./dir/*.js', { eager: true })

for (const path in modules) {
  console.log(path, modules[path].default)
}
```


--------------------------------

### Configure ordered rewrites with beforeFiles, afterFiles, and fallback

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/rewrites.mdx

Finer-grained rewrite control returning an object with beforeFiles, afterFiles, and fallback arrays to control matching order relative to static assets and dynamic routes.

```javascript
module.exports = {
  rewrites() {
    return {
      beforeFiles: [
        // These rewrites are checked after headers/redirects
        // and before all files including _next/static and public files which
        // allows overriding page files
        {
          source: '/some-page',
          destination: '/somewhere-else',
          has: [{ type: 'query', key: 'overrideMe' }],
        },
      ],
      afterFiles: [
        // These rewrites are checked after pages/public files
        // are checked but before dynamic routes
        {
          source: '/non-existent',
          destination: '/somewhere-else',
        },
      ],
      fallback: [
        // These rewrites are checked after both pages/public files
        // and dynamic routes are checked
        {
          source: '/:path*',
          destination: `https://my-old-site.com/:path*`,
        },
      ],
    }
  },
}
```


--------------------------------

### Configure disjoint loader rules with an array in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/turbopack.mdx

Define multiple disjoint loader configurations for a single file pattern using an array of rule objects with built-in conditions like 'browser'. Matching rules are executed in order.

```javascript
module.exports = {
  turbopack: {
    rules: {
      '*.svg': [
        {
          condition: 'browser',
          loaders: ['@svgr/webpack'],
          as: '*.js',
        },
        {
          condition: { not: 'browser' },
          loaders: [require.resolve('./custom-svg-loader.js')],
          as: '*.js',
        },
      ],
    },
  },
}
```


--------------------------------

### Defer client-side dynamic import in a Client Component

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/turbopackLazyDynamicImports.mdx

Demonstrates a Client Component where the dynamic module './get-greeting' remains uncompiled by Turbopack until the button is selected in the browser.

```tsx
'use client'

import { useState } from 'react'

export function GreetingButton() {
  const [message, setMessage] = useState('')

  async function showGreeting() {
    const { getGreeting } = await import('./get-greeting')
    setMessage(getGreeting('Ada'))
  }

  return (
    <>
      <button onClick={showGreeting}>Show greeting</button>
      <p>{message}</p>
    </>
  )
}
```

```jsx
'use client'

import { useState } from 'react'

export function GreetingButton() {
  const [message, setMessage] = useState('')

  async function showGreeting() {
    const { getGreeting } = await import('./get-greeting')
    setMessage(getGreeting('Ada'))
  }

  return (
    <>
      <button onClick={showGreeting}>Show greeting</button>
      <p>{message}</p>
    </>
  )
}
```


--------------------------------

### Run ESLint using yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/03-eslint.mdx

Executes ESLint against all project files using yarn.

```bash
yarn eslint .
```


--------------------------------

### Create an active link component using useSelectedLayoutSegment

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/use-selected-layout-segment.mdx

Reads the active route segment to apply conditional styling to navigation links. Navigating to `/blog/hello-world` returns `'hello-world'` for the selected layout segment.

```tsx
'use client'

import Link from 'next/link'
import { useSelectedLayoutSegment } from 'next/navigation'

// This *client* component will be imported into a blog layout
export default function BlogNavLink({
  slug,
  children,
}: {
  slug: string
  children: React.ReactNode
}) {
  // Navigating to `/blog/hello-world` will return 'hello-world'
  // for the selected layout segment
  const segment = useSelectedLayoutSegment()
  const isActive = slug === segment

  return (
    <Link
      href={`/blog/${slug}`}
      // Change style depending on whether the link is active
      style={{ fontWeight: isActive ? 'bold' : 'normal' }}
    >
      {children}
    </Link>
  )
}
```

```jsx
'use client'

import Link from 'next/link'
import { useSelectedLayoutSegment } from 'next/navigation'

// This *client* component will be imported into a blog layout
export default function BlogNavLink({ slug, children }) {
  // Navigating to `/blog/hello-world` will return 'hello-world'
  // for the selected layout segment
  const segment = useSelectedLayoutSegment()
  const isActive = slug === segment

  return (
    <Link
      href={`/blog/${slug}`}
      // Change style depending on whether the link is active
      style={{ fontWeight: isActive ? 'bold' : 'normal' }}
    >
      {children}
    </Link>
  )
}
```


--------------------------------

### Enable Partial Prefetching in next.config

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/partialPrefetching.mdx

Enables Partial Prefetching across the app to prefetch static App Shells by default. Requires cacheComponents to be enabled; otherwise next dev and next build throw a configuration validation error.

```typescript
import type { NextConfig } from 'next'

const nextConfig: NextConfig = {
  cacheComponents: true,
  partialPrefetching: true,
}

export default nextConfig
```

```javascript
module.exports = {
  cacheComponents: true,
  partialPrefetching: true,
}
```


--------------------------------

### Configure Turbopack FileSystem Cache in next.config

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/turbopackFileSystemCache.mdx

Configures Turbopack FileSystem caching for dev and build runs. Both options default to true; set either option to false to opt out.

```typescript
import type { NextConfig } from 'next'

const nextConfig: NextConfig = {
  experimental: {
    turbopackFileSystemCacheForDev: true,
    turbopackFileSystemCacheForBuild: true,
  },
}

export default nextConfig
```

```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  experimental: {
    turbopackFileSystemCacheForDev: true,
    turbopackFileSystemCacheForBuild: true,
  },
}

module.exports = nextConfig
```


--------------------------------

### Using a static import for src

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/02-components/image.mdx

Import a local image file directly and assign the imported object to the src prop.

```jsx
import profile from './profile.png'

export default function Page() {
  return <Image src={profile} />
}
```


--------------------------------

### Set X-DNS-Prefetch-Control header

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/headers.mdx

Enables proactive domain name resolution for external resources in the background. This reduces latency when users navigate external links.

```javascript
{
  key: 'X-DNS-Prefetch-Control',
  value: 'on'
}
```


--------------------------------

### connection()

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/connection.mdx

Allows you to indicate rendering should wait for an incoming user request before continuing. It stops prerendering so subsequent code executes only at request time.

```APIDOC
## connection()

### Description
The `connection()` function allows you to indicate rendering should wait for an incoming user request before continuing. It is useful when a component does not use Request-time APIs (such as `cookies` or `headers`) but needs to produce dynamic output per request.

### Import
```ts
import { connection } from 'next/server'
```

### Signature
```ts
function connection(): Promise<void>
```

### Parameters
- The function does not accept any parameters.

### Returns
- `Promise<void>`: Returns a `void` Promise. It is not meant to be consumed.

### Examples

#### Basic Usage
```ts
import { connection } from 'next/server'

export default async function Page() {
  await connection() // prerendering stops here
  // the following code only runs at request time
  const rand = Math.random()
  return <span>{rand}</span>
}
```

#### Synchronous Database Drivers
```ts
import { connection } from 'next/server'
import Database from 'better-sqlite3'

const db = new Database('app.db')

export async function getVisitorCount() {
  await connection()
  return db.prepare('SELECT value FROM counters WHERE name = ?').get('visitors')
}
```
```


--------------------------------

### Implement basic in-memory cache handler (memory-handler.js)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/05-config/01-next-config-js/cacheHandlers.mdx

Demonstrates an in-memory caching handler using a JavaScript Map. It buffers streams to Uint8Array so entries can be reconstructed into new ReadableStreams upon retrieval.

```javascript
// Entries hold the serialized bytes, never the stream they arrived on
const cache = new Map()
const pendingSets = new Map()

function streamFromBytes(bytes) {
  return new ReadableStream({
    start(controller) {
      controller.enqueue(bytes)
      controller.close()
    },
  })
}

module.exports = {
  async get(cacheKey, softTags) {
    // Wait for any pending set operation to complete
    const pendingPromise = pendingSets.get(cacheKey)
    if (pendingPromise) {
      await pendingPromise
    }

    const entry = cache.get(cacheKey)
    if (!entry) {
      return undefined
    }

    // No age check: Next.js compares `timestamp` against `expire` itself.
    // This `Map` also has no eviction, which a real handler needs.

    // Every hit gets its own stream over the stored bytes
    return { ...entry, value: streamFromBytes(entry.value) }
  },

  async set(cacheKey, pendingEntry) {
    // Create a promise to track this set operation
    let resolvePending
    const pendingPromise = new Promise((resolve) => {
      resolvePending = resolve
    })
    pendingSets.set(cacheKey, pendingPromise)

    try {
      // Wait for the entry to be ready
      const entry = await pendingEntry

      // An in-memory store buffers the stream. Storing the stream itself, or
      // a branch of it, keeps the request that produced the entry alive.
      const value = new Uint8Array(
        await new Response(entry.value).arrayBuffer()
      )

      cache.set(cacheKey, { ...entry, value })
    } finally {
      resolvePending()
      pendingSets.delete(cacheKey)
    }
  },

  async refreshTags() {
    // No-op for in-memory cache
  },

  async getExpiration(tags) {
    // Return 0 to indicate no tags have been revalidated
    return 0
  },

  async updateTags(tags, durations) {
    // Implement tag-based invalidation
    for (const [key, entry] of cache.entries()) {
      if (entry.tags.some((tag) => tags.includes(tag))) {
        cache.delete(key)
      }
    }
  },
}
```


--------------------------------

### Configure remotePatterns with query string matching in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/02-components/image.mdx

Restricts external images by enforcing an exact query string parameter via the search property.

```js
module.exports = {
  images: {
    remotePatterns: [
      {
        protocol: 'https',
        hostname: 'assets.example.com',
        search: '?v=1727111025337',
      },
    ],
  },
}
```


--------------------------------

### Define miscellaneous metadata fields and head output

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/04-functions/generate-metadata.mdx

Configure general metadata properties including generator, applicationName, referrer, keywords, authors, creator, publisher, and formatDetection in layout.js or page.js.

```jsx
export const metadata = {
  generator: 'Next.js',
  applicationName: 'Next.js',
  referrer: 'origin-when-cross-origin',
  keywords: ['Next.js', 'React', 'JavaScript'],
  authors: [{ name: 'Seb' }, { name: 'Josh', url: 'https://nextjs.org' }],
  creator: 'Jiachi Liu',
  publisher: 'Sebastian Markbåge',
  formatDetection: {
    email: false,
    address: false,
    telephone: false,
  },
}
```

```html
<meta name="application-name" content="Next.js" />
<meta name="author" content="Seb" />
<link rel="author" href="https://nextjs.org" />
<meta name="author" content="Josh" />
<meta name="generator" content="Next.js" />
<meta name="keywords" content="Next.js,React,JavaScript" />
<meta name="referrer" content="origin-when-cross-origin" />
<meta name="creator" content="Jiachi Liu" />
<meta name="publisher" content="Sebastian Markbåge" />
<meta name="format-detection" content="telephone=no, address=no, email=no" />
```


--------------------------------

### Configuring global unoptimized in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/02-components/image.mdx

Applies the unoptimized configuration to all images across the Next.js application.

```js
module.exports = {
  images: {
    unoptimized: true,
  },
}
```


--------------------------------

### Configure package.json scripts for default Turbopack bundler

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/08-turbopack.mdx

Turbopack runs by default in Next.js without requiring extra configuration or CLI flags.

```json
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start"
  }
}
```


--------------------------------

### Define a static manifest file

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/03-api-reference/03-file-conventions/01-metadata/manifest.mdx

Add a static manifest file in the root of the app directory to provide browser metadata according to the Web Manifest Specification.

```json
{
  "name": "My Next.js Application",
  "short_name": "Next.js App",
  "description": "An application built with Next.js",
  "start_url": "/"
  // ...
}
```
