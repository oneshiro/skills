# App Router — Guides

Sourced snippets from the Next.js docs dump (146 entries).
Search this file for the topic at hand; treat snippets as patterns and
reconcile with the installed Next.js version before applying.

### Example project directory structure

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/keeping-pages-static.mdx

Outlines the file organization for the store, guides, UI components, and utility libraries.

```txt
app/
├── store/
│   ├── layout.tsx         # Shared layout with the cart
│   ├── page.tsx           # Product catalog
│   └── products/
│       └── [slug]/
│           └── page.tsx   # Product details and cart status
├── guides/
│   └── [id]/
│       └── page.tsx       # Editorial buying guides
└── ui/
    ├── cart.tsx
    └── product.tsx
lib/
└── guides.ts
```


--------------------------------

### Run development server to trigger Partytown setup

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/scripts.mdx

Runs the Next.js development server, which will prompt instructions to install `@qwik.dev/partytown`.

```bash
pnpm dev
```

```bash
npm run dev
```

```bash
yarn dev
```

```bash
bun dev
```


--------------------------------

### Set up client instrumentation in instrumentation-client.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/analytics.mdx

Create an instrumentation-client.js or instrumentation-client.ts file in the application root directory to run code before frontend execution starts. Use this setup to initialize global analytics or attach window error listeners.

```javascript
// Initialize analytics before the app starts
console.log('Analytics initialized')

// Set up global error tracking
window.addEventListener('error', (event) => {
  // Send to your error tracking service
  reportError(event.error)
})
```


--------------------------------

### Install @next/bundle-analyzer

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/package-bundling.mdx

Install the bundle analyzer plugin using your preferred package manager.

```bash
pnpm add @next/bundle-analyzer
```

```bash
npm install @next/bundle-analyzer
```

```bash
yarn add @next/bundle-analyzer
```

```bash
bun add @next/bundle-analyzer
```


--------------------------------

### Install @next/third-parties using bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/third-party-libraries.mdx

Install the experimental `@next/third-parties` package alongside `next` using bun.

```bash
bun add @next/third-parties@latest next@latest
```


--------------------------------

### Install web-push globally using bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/progressive-web-apps.mdx

Installs the `web-push` CLI globally using bun for generating VAPID keys.

```bash
bun add -g web-push
```


--------------------------------

### Install the next-partial-prefetching-adoption skill

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/adopting-partial-prefetching.mdx

Installs the adoption skill into your project to drive Partial Prefetching migration with a coding agent.

```bash
npx skills add vercel/next.js --skill next-partial-prefetching-adoption

```


--------------------------------

### Install and run next-partial-prefetching-adoption skill

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/ai-agents.mdx

Installs the adoption skill and prompts the agent to migrate the project to Partial Prefetching. Requires Cache Components to already be adopted and a production-like build available for verification.

```bash
npx skills add vercel/next.js --skill next-partial-prefetching-adoption
```

```prompt
Adopt Partial Prefetching in this project using the next-partial-prefetching-adoption Skill.
```


--------------------------------

### Install next-partial-prefetching-optimizer skill

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/optimizing-prefetching.mdx

Installs the partial prefetching optimizer skill for coding agents via the npx CLI.

```bash
npx skills add vercel/next.js --skill next-partial-prefetching-optimizer
```


--------------------------------

### Install web-push globally using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/progressive-web-apps.mdx

Installs the `web-push` CLI globally using pnpm for generating VAPID keys.

```bash
pnpm add -g web-push
```


--------------------------------

### Install @next/third-parties using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/third-party-libraries.mdx

Install the experimental `@next/third-parties` package alongside `next` using npm.

```bash
npm install @next/third-parties@latest next@latest
```


--------------------------------

### Install web-push globally using yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/progressive-web-apps.mdx

Installs the `web-push` CLI globally using yarn for generating VAPID keys.

```bash
yarn global add web-push
```


--------------------------------

### Install @next/third-parties using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/third-party-libraries.mdx

Install the experimental `@next/third-parties` package alongside `next` using pnpm.

```bash
pnpm add @next/third-parties@latest next@latest
```


--------------------------------

### Implement InstallPrompt and Page components for PWA

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/progressive-web-apps.mdx

Checks whether the client is iOS or already in standalone display mode before rendering the install prompt. Returns null if already installed to avoid showing redundant install buttons.

```tsx
function InstallPrompt() {
  const [isIOS, setIsIOS] = useState(false)
  const [isStandalone, setIsStandalone] = useState(false)

  useEffect(() => {
    setIsIOS(
      /iPad|iPhone|iPod/.test(navigator.userAgent) && !(window as any).MSStream
    )

    setIsStandalone(window.matchMedia('(display-mode: standalone)').matches)
  }, [])

  if (isStandalone) {
    return null // Don't show install button if already installed
  }

  return (
    <div>
      <h3>Install App</h3>
      <button>Add to Home Screen</button>
      {isIOS && (
        <p>
          To install this app on your iOS device, tap the share button
          <span role="img" aria-label="share icon">
            {' '}
            ⎋{' '}
          </span>
          and then "Add to Home Screen"
          <span role="img" aria-label="plus icon">
            {' '}
            ➕{' '}
          </span>
          .
        </p>
      )}
    </div>
  )
}

export default function Page() {
  return (
    <div>
      <PushNotificationManager />
      <InstallPrompt />
    </div>
  )
}
```

```jsx
function InstallPrompt() {
  const [isIOS, setIsIOS] = useState(false);
  const [isStandalone, setIsStandalone] = useState(false);

  useEffect(() => {
    setIsIOS(
      /iPad|iPhone|iPod/.test(navigator.userAgent) && !(window as any).MSStream
    );

    setIsStandalone(window.matchMedia('(display-mode: standalone)').matches);
  }, []);

  if (isStandalone) {
    return null; // Don't show install button if already installed
  }

  return (
    <div>
      <h3>Install App</h3>
      <button>Add to Home Screen</button>
      {isIOS && (
        <p>
          To install this app on your iOS device, tap the share button
          <span role="img" aria-label="share icon">
            {' '}
            ⎋{' '}
          </span>
          and then "Add to Home Screen"
          <span role="img" aria-label="plus icon">
            {' '}
            ➕{' '}
          </span>
          .
        </p>
      )}
    </div>
  );
}

export default function Page() {
  return (
    <div>
      <PushNotificationManager />
      <InstallPrompt />
    </div>
  );
}
```


--------------------------------

### Install web-push globally using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/progressive-web-apps.mdx

Installs the `web-push` CLI globally using npm for generating VAPID keys.

```bash
npm install -g web-push
```


--------------------------------

### Install OpenTelemetry packages

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/open-telemetry.mdx

Install `@vercel/otel` along with required OpenTelemetry logging and instrumentation dependencies.

```bash
pnpm add @vercel/otel @opentelemetry/sdk-logs @opentelemetry/api-logs @opentelemetry/instrumentation
```

```bash
npm install @vercel/otel @opentelemetry/sdk-logs @opentelemetry/api-logs @opentelemetry/instrumentation
```

```bash
yarn add @vercel/otel @opentelemetry/sdk-logs @opentelemetry/api-logs @opentelemetry/instrumentation
```

```bash
bun add @vercel/otel @opentelemetry/sdk-logs @opentelemetry/api-logs @opentelemetry/instrumentation
```


--------------------------------

### Install Tailwind CSS v3 using Bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/tailwind-v3-css.mdx

Install Tailwind CSS v3 with PostCSS and Autoprefixer, then run the init command using Bun.

```bash
bun add -D tailwindcss@^3 postcss autoprefixer
bunx tailwindcss init -p
```


--------------------------------

### Start Next.js development server

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/mcp.mdx

Starts the local development server required for the next-devtools-mcp agent connection.

```bash
pnpm dev

```

```bash
npm run dev

```

```bash
yarn dev

```

```bash
bun dev

```


--------------------------------

### Install and run next-partial-prefetching-optimizer skill

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/ai-agents.mdx

Installs the optimizer skill and prompts the agent to optimize prefetching behavior for specific routes. Requires Cache Components and Partial Prefetching to already be adopted.

```bash
npx skills add vercel/next.js --skill next-partial-prefetching-optimizer
```

```prompt
Make the product title instant when navigating from /products to /products/[id]. Use the next-partial-prefetching-optimizer Skill.
```


--------------------------------

### Install Sass using Bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/sass.mdx

Installs the `sass` package as a development dependency using Bun.

```bash
bun add -D sass
```


--------------------------------

### Install @next/third-parties using yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/third-party-libraries.mdx

Install the experimental `@next/third-parties` package alongside `next` using yarn.

```bash
yarn add @next/third-parties@latest next@latest
```


--------------------------------

### Install @opentelemetry/api

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/open-telemetry.mdx

Install the OpenTelemetry API package to instrument custom spans in your application.

```bash
pnpm add @opentelemetry/api
```

```bash
npm install @opentelemetry/api
```

```bash
yarn add @opentelemetry/api
```

```bash
bun add @opentelemetry/api
```


--------------------------------

### Install and prompt next-cache-components-optimizer skill

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/ai-agents.mdx

Installs the `next-cache-components-optimizer` skill and prompts the agent to expand a route's static shell by writing tests and refactoring UI.

```bash
npx skills add vercel/next.js --skill next-cache-components-optimizer
```

```prompt
Optimize the static shell for /dashboard using the next-cache-components-optimizer Skill. On an initial load, the header and project list should be available immediately.
```


--------------------------------

### Install @next/playwright and @playwright/test using bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/instant-navigation.mdx

Install @next/playwright alongside @playwright/test as development dependencies using bun.

```bash
bun add -D @next/playwright @playwright/test
```


--------------------------------

### Install and prompt next-dev-loop skill

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/ai-agents.mdx

Installs the `next-dev-loop` skill and instructs the AI agent to verify page functionality against a running dev server after every edit.

```bash
npx skills add vercel/next.js --skill next-dev-loop
```

```prompt
After every edit, verify the page still works at runtime using the next-dev-loop Skill.
```


--------------------------------

### Fetch guide data from database

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/keeping-pages-static.mdx

Helper function querying the database for a guide by its unique ID.

```ts
import { db } from '@/lib/db'

export async function getGuide(id: string) {
  return db.guide.findUniqueOrThrow({ where: { id } })
}
```


--------------------------------

### Install the vercel-react-view-transitions skill via npx

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/view-transitions.mdx

Installs the agent skill to teach coding agents view transition patterns, CSS recipes, and troubleshooting.

```bash
npx skills add vercel-labs/agent-skills --skill vercel-react-view-transitions
```


--------------------------------

### Install next-devtools-mcp using add-mcp

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/mcp.mdx

Installs next-devtools-mcp for coding agents across your machine using add-mcp.

```bash
npx add-mcp next-devtools-mcp@latest
```


--------------------------------

### Install the next-bundle-optimizer AI skill

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/package-bundling.mdx

Installs the `next-bundle-optimizer` skill to allow AI agents to access Turbopack bundle analysis data.

```bash
npx skills add vercel/next.js --skill next-bundle-optimizer
```


--------------------------------

### Install Sass using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/sass.mdx

Installs the `sass` package as a development dependency using pnpm.

```bash
pnpm add -D sass
```


--------------------------------

### Install Sass using Yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/sass.mdx

Installs the `sass` package as a development dependency using Yarn.

```bash
yarn add -D sass
```


--------------------------------

### Install Sass using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/sass.mdx

Installs the `sass` package as a development dependency using npm.

```bash
npm install --save-dev sass
```


--------------------------------

### Install @next/playwright and @playwright/test using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/instant-navigation.mdx

Install @next/playwright alongside @playwright/test as development dependencies using pnpm.

```bash
pnpm add -D @next/playwright @playwright/test
```


--------------------------------

### Install and prompt next-bundle-optimizer skill

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/ai-agents.mdx

Installs the `next-bundle-optimizer` skill and prompts the AI agent to run an initial load performance audit using Turbopack's bundle analyzer.

```bash
npx skills add vercel/next.js --skill next-bundle-optimizer
```

```prompt
Use the next-bundle-optimizer skill to produce a report of the initial load performance of this site.
```


--------------------------------

### Install @next/playwright and @playwright/test using yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/instant-navigation.mdx

Install @next/playwright alongside @playwright/test as development dependencies using yarn.

```bash
yarn add -D @next/playwright @playwright/test
```


--------------------------------

### Install @next/mdx and related dependencies

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/mdx.mdx

Install required packages to configure Next.js to compile markdown and MDX sourced from local files.

```bash
pnpm add @next/mdx @mdx-js/loader @mdx-js/react @types/mdx
```

```bash
npm install @next/mdx @mdx-js/loader @mdx-js/react @types/mdx
```

```bash
yarn add @next/mdx @mdx-js/loader @mdx-js/react @types/mdx
```

```bash
bun add @next/mdx @mdx-js/loader @mdx-js/react @types/mdx
```


--------------------------------

### Render guide page reading theme from cookies

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/keeping-pages-static.mdx

Wraps the guide component in a `<Suspense>` boundary and retrieves dynamic theme data from cookies alongside database content.

```tsx
import { Suspense } from 'react'
import { cookies } from 'next/headers'
import { getGuide } from '@/lib/guides'

export default function GuidePage({ params }: PageProps<'/guides/[id]'>) {
  return (
    <Suspense fallback={<p>Loading guide...</p>}>
      <Guide params={params} />
    </Suspense>
  )
}

async function Guide({ params }: { params: Promise<{ id: string }> }) {
  const { id } = await params
  const guide = await getGuide(id)
  const theme = (await cookies()).get('theme')?.value
  return <article data-theme={theme}>{guide.content}</article>
}
```


--------------------------------

### Install @next/playwright and @playwright/test using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/instant-navigation.mdx

Install @next/playwright alongside @playwright/test as development dependencies using npm.

```bash
npm install -D @next/playwright @playwright/test
```


--------------------------------

### Install OpenTelemetry packages

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/open-telemetry.mdx

Install the required OpenTelemetry Node.js SDK, resources, semantic conventions, and OTLP exporter packages using your preferred package manager.

```bash
pnpm add @opentelemetry/sdk-node @opentelemetry/resources @opentelemetry/semantic-conventions @opentelemetry/sdk-trace-node @opentelemetry/exporter-trace-otlp-http
```

```bash
npm install @opentelemetry/sdk-node @opentelemetry/resources @opentelemetry/semantic-conventions @opentelemetry/sdk-trace-node @opentelemetry/exporter-trace-otlp-http
```

```bash
yarn add @opentelemetry/sdk-node @opentelemetry/resources @opentelemetry/semantic-conventions @opentelemetry/sdk-trace-node @opentelemetry/exporter-trace-otlp-http
```

```bash
bun add @opentelemetry/sdk-node @opentelemetry/resources @opentelemetry/semantic-conventions @opentelemetry/sdk-trace-node @opentelemetry/exporter-trace-otlp-http
```


--------------------------------

### Install the next-cache-components-optimizer skill

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/optimizing-the-static-shell.mdx

Installs the Cache Components optimizer skill using the Next.js skills CLI to assist coding agents in optimizing route static shells.

```bash
npx skills add vercel/next.js --skill next-cache-components-optimizer
```


--------------------------------

### Run Turbopack Bundle Analyzer with Bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/package-bundling.mdx

Starts the Next.js bundle analyzer using Bun and opens the interactive view in the browser.

```bash
bunx next analyze
```


--------------------------------

### Run Turbopack Bundle Analyzer with npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/package-bundling.mdx

Starts the Next.js bundle analyzer and opens the interactive module graph visualization in the browser.

```bash
npx next analyze
```


--------------------------------

### Install Tailwind CSS v3 using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/tailwind-v3-css.mdx

Install Tailwind CSS v3 and peer dependencies as dev dependencies and run the init command to generate tailwind.config.js and postcss.config.js using npm.

```bash
npm install -D tailwindcss@^3 postcss autoprefixer
npx tailwindcss init -p
```


--------------------------------

### Prompt an agent to adopt Cache Components and Partial Prefetching

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/instant-navigation.mdx

Use this prompt with an AI agent to guide the step-by-step migration process using dedicated skills.

```prompt
Adopt Cache Components and Partial Prefetching in this app so its navigations become instant. There is a Skill for each migration.

1. Before you change anything, explain to me in plain terms what Instant Navigation is and what adopting it will change.

2. Install the Skills you need, then verify your changes against a running dev server with next-dev-loop and agent-browser as you go:
   - next-cache-components-adoption: https://www.skills.sh/vercel/next.js/next-cache-components-adoption
   - next-partial-prefetching-adoption: https://www.skills.sh/vercel/next.js/next-partial-prefetching-adoption
   - next-dev-loop: https://www.skills.sh/vercel/next.js/next-dev-loop

3. Each Skill leaves decisions to me, like how much of the work lands in each pull request. Put those questions to me and wait for my answers instead of deciding on my behalf. Adopt Cache Components first, then Partial Prefetching, following the workflow each Skill lays out. Don't rush to a passing build.

4. When you finish a step, show me a table of the routes you touched and what changed on each, and talk me through what it means for the app. Keep it to the outcome, not the implementation details.
```


--------------------------------

### Generate a Turbopack trace file during development

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/local-development.mdx

Start the development server with the --internal-trace flag to produce a trace-turbopack.bin file in the .next-profiles folder.

```bash
pnpm dev --internal-trace
```

```bash
npm run dev -- --internal-trace
```

```bash
yarn dev --internal-trace
```

```bash
bun dev --internal-trace
```


--------------------------------

### Install @next/env package

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/environment-variables.mdx

Installs the @next/env utility package to load environment variables outside of the Next.js runtime.

```bash
pnpm add @next/env
```

```bash
npm install @next/env
```

```bash
yarn add @next/env
```

```bash
bun add @next/env
```


--------------------------------

### Run next build with debug-prerender and debug-build-paths

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/building.mdx

Use the `--debug-prerender` and `--debug-build-paths` flags to generate a detailed stack trace pinpointing the blocking line.

```bash
next build --debug-prerender --debug-build-paths="app/products/[id]/page.tsx"
```


--------------------------------

### Install Tailwind CSS v3 using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/tailwind-v3-css.mdx

Install Tailwind CSS v3, PostCSS, and Autoprefixer as development dependencies and generate configuration files using pnpm.

```bash
pnpm add -D tailwindcss@^3 postcss autoprefixer
npx tailwindcss init -p
```


--------------------------------

### Run Turbopack Bundle Analyzer with pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/package-bundling.mdx

Starts the Next.js bundle analyzer using pnpm and opens the interactive view in the browser.

```bash
pnpm next analyze
```


--------------------------------

### Run Turbopack Bundle Analyzer with Yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/package-bundling.mdx

Starts the Next.js bundle analyzer using Yarn and opens the interactive view in the browser.

```bash
yarn next analyze
```


--------------------------------

### Initialize NodeSDK in instrumentation.node.ts

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/open-telemetry.mdx

Configure and start the OpenTelemetry NodeSDK with an OTLP HTTP trace exporter and service name attributes.

```ts
import { OTLPTraceExporter } from '@opentelemetry/exporter-trace-otlp-http'
import { resourceFromAttributes } from '@opentelemetry/resources'
import { NodeSDK } from '@opentelemetry/sdk-node'
import { SimpleSpanProcessor } from '@opentelemetry/sdk-trace-node'
import { ATTR_SERVICE_NAME } from '@opentelemetry/semantic-conventions'

const sdk = new NodeSDK({
  resource: resourceFromAttributes({
    [ATTR_SERVICE_NAME]: 'next-app',
  }),
  spanProcessor: new SimpleSpanProcessor(new OTLPTraceExporter()),
})
sdk.start()
```

```js
import { OTLPTraceExporter } from '@opentelemetry/exporter-trace-otlp-http'
import { resourceFromAttributes } from '@opentelemetry/resources'
import { NodeSDK } from '@opentelemetry/sdk-node'
import { SimpleSpanProcessor } from '@opentelemetry/sdk-trace-node'
import { ATTR_SERVICE_NAME } from '@opentelemetry/semantic-conventions'

const sdk = new NodeSDK({
  resource: resourceFromAttributes({
    [ATTR_SERVICE_NAME]: 'next-app',
  }),
  spanProcessor: new SimpleSpanProcessor(new OTLPTraceExporter()),
})
sdk.start()
```


--------------------------------

### Prompt AI agent to run partial prefetching adoption

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/adopting-partial-prefetching.mdx

Instructs the AI coding agent to execute the migration using the installed adoption skill.

```prompt
Adopt Partial Prefetching in this project using the next-partial-prefetching-adoption skill.

```


--------------------------------

### Run next upgrade with a coding agent

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/ai-agents.mdx

Checks for available Next.js upgrades, gathers version-matched migration guides, and hands the upgrade task to a coding agent to apply changes and verify the application.

```bash
npx next@canary upgrade --agent=latest
```


--------------------------------

### Install Tailwind CSS v3 using Yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/tailwind-v3-css.mdx

Add Tailwind CSS v3 and required peer dependencies to devDependencies and initialize configuration files using Yarn.

```bash
yarn add -D tailwindcss@^3 postcss autoprefixer
npx tailwindcss init -p
```


--------------------------------

### Define Web App Manifest in manifest.ts or manifest.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/progressive-web-apps.mdx

Define metadata such as name, display mode, theme colors, and icons for device installation. Place this file in the app directory as either manifest.ts or manifest.js.

```tsx
import type { MetadataRoute } from 'next'

export default function manifest(): MetadataRoute.Manifest {
  return {
    name: 'Next.js PWA',
    short_name: 'NextPWA',
    description: 'A Progressive Web App built with Next.js',
    start_url: '/',
    display: 'standalone',
    background_color: '#ffffff',
    theme_color: '#000000',
    icons: [
      {
        src: '/icon-192x192.png',
        sizes: '192x192',
        type: 'image/png',
      },
      {
        src: '/icon-512x512.png',
        sizes: '512x512',
        type: 'image/png',
      },
    ],
  }
}
```

```jsx
export default function manifest() {
  return {
    name: 'Next.js PWA',
    short_name: 'NextPWA',
    description: 'A Progressive Web App built with Next.js',
    start_url: '/',
    display: 'standalone',
    background_color: '#ffffff',
    theme_color: '#000000',
    icons: [
      {
        src: '/icon-192x192.png',
        sizes: '192x192',
        type: 'image/png',
      },
      {
        src: '/icon-512x512.png',
        sizes: '512x512',
        type: 'image/png',
      },
    ],
  }
}
```


--------------------------------

### Configure Manual Graceful Shutdowns with NEXT_MANUAL_SIG_HANDLE

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/self-hosting.mdx

Set NEXT_MANUAL_SIG_HANDLE=true directly in the package.json start script and register SIGTERM/SIGINT signal listeners in pages/_document.js. Manual signal handling is not available during next dev.

```json
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "NEXT_MANUAL_SIG_HANDLE=true next start"
  }
}
```

```javascript
if (process.env.NEXT_MANUAL_SIG_HANDLE) {
  process.on('SIGTERM', () => {
    console.log('Received SIGTERM: cleaning up')
    process.exit(0)
  })
  process.on('SIGINT', () => {
    console.log('Received SIGINT: cleaning up')
    process.exit(0)
  })
}
```


--------------------------------

### Start Next.js dev server with Node.js --inspect flag

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/debugging.mdx

Passes the --inspect flag to the underlying Node.js process to enable debugging of server-side code via browser DevTools.

```bash
pnpm dev --inspect
```

```bash
npm run dev -- --inspect
```

```bash
yarn dev --inspect
```

```bash
bun run dev --inspect
```


--------------------------------

### Create a basic GET Route Handler in /app/api/route

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/backend-for-frontend.mdx

Defines a public HTTP GET handler function at `/api` using the `route.ts` or `route.js` file convention.

```typescript
export function GET(request: Request) {}
```

```javascript
export function GET(request) {}
```


--------------------------------

### Prompt an agent to add view transitions

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/view-transitions.mdx

Instructs the AI agent to apply view transitions across the application using the installed skill.

```prompt
Add view transitions to this app using the vercel-react-view-transitions skill.
```


--------------------------------

### Configure package.json scripts for custom server

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/custom-server.mdx

Updates `package.json` scripts to run `server.js` directly with Node.js for development and production instead of using `next start`.

```json
{
  "scripts": {
    "dev": "node server.js",
    "build": "next build",
    "start": "NODE_ENV=production node server.js"
  }
}
```


--------------------------------

### Define static Route Handler with GET

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/static-exports.mdx

Prerender a static response file (e.g. data.json) during next build by exporting `dynamic = 'force-static'`. Only the GET HTTP verb is supported in static exports.

```typescript
export const dynamic = 'force-static'

export async function GET() {
  return Response.json({ name: 'Lee' })
}
```

```javascript
export const dynamic = 'force-static'

export async function GET() {
  return Response.json({ name: 'Lee' })
}
```


--------------------------------

### Configure static GET Route Handler for static exports

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/backend-for-frontend.mdx

Sets the dynamic segment configuration to 'force-static' so GET Route Handlers can generate static files in export mode. In static export mode, only GET Route Handlers using this configuration are supported.

```javascript
export const dynamic = 'force-static'

export function GET() {
  return new Response('Hello World', { status: 200 })
}
```


--------------------------------

### Create an MDX page with imported React component

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/mdx.mdx

Example MDX content embedding a custom React component alongside standard markdown syntax.

```mdx
import { MyComponent } from 'my-component'

# Welcome to my MDX page!

This is some **bold** and _italics_ text.

This is a list in markdown:

- One
- Two
- Three

Checkout my React component:

<MyComponent />
```


--------------------------------

### Agent response for error diagnosis

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/mcp.mdx

Example agent output demonstrating discovery of hydration mismatch errors across active browser sessions.

```txt
> fix errors on the page

⏺ I'll check which errors the running app reports before changing anything.

⏺ next-devtools - nextjs_index (MCP)
⏺ next-devtools - nextjs_call (MCP)(port: 3000, toolName: "get_errors")
  ⎿ # Found errors in 1 browser session(s)

    ## Session: /about

    **1 error(s) found**

    ### Runtime Errors

    #### Error 1 (Type: recoverable)

    **Error**: Hydration failed because the server rendered text didn't match the client.

⏺ The /about page renders "server" on the server and "client" in the browser,
  which causes a hydration mismatch. I'll fix the component and check again.

```


--------------------------------

### Convert Markdown syntax to HTML

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/mdx.mdx

Example showing how standard markdown text with bold formatting and hyperlinks translates to semantic HTML markup.

```md
I **love** using [Next.js](https://nextjs.org/)
```

```html
<p>I <strong>love</strong> using <a href="https://nextjs.org/">Next.js</a></p>
```


--------------------------------

### Configure exposeTestingApiInProductionBuild in next.config.ts

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/instant-navigation.mdx

Enable exposeTestingApiInProductionBuild conditionally for production test builds. Ensure EXPOSE_TESTING_API=1 is set during next build rather than next start.

```ts
import type { NextConfig } from 'next'

const exposeTestingApi = process.env.EXPOSE_TESTING_API === '1'

const nextConfig: NextConfig = {
  cacheComponents: true,
  experimental:
    exposeTestingApiInProductionBuild: exposeTestingApi,
  },
}

export default nextConfig
```


--------------------------------

### View build output with Partial Prerendering

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/keeping-pages-static.mdx

Displays the build output summary indicating which routes are partially prerendered and which need complete static generation.

```text
Route (app)
├   /guides/[id]
│ └ ◐ /guides/[id]
├ ◐ /store
└   /store/products/[slug]
  ├ ◐ /store/products/[slug]
  └ ◐ /store/products/coffee-grinder

◐  (Partial Prerender)  prerendered as static HTML with dynamic server-streamed content
```


--------------------------------

### Implement generateStaticParams for dynamic guide route

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/keeping-pages-static.mdx

Export `generateStaticParams()` using a helper function in `lib/guides.ts` to supply static parameters for prerendering at build time.

```ts
export async function getGuideIds() {
  const guides = await db.guide.findMany({ select: { id: true } })
  return guides.map(({ id }) => id)
}
```

```tsx
import { Suspense } from 'react'
import { cookies } from 'next/headers'
import { getGuide, getGuideIds } from '@/lib/guides'

export const ensureStatic = 'navigation'

export async function generateStaticParams() {
  const ids = await getGuideIds()
  return ids.map((id) => ({ id }))
}

export default function GuidePage({ params }: PageProps<'/guides/[id]'>) {
  return (
    <Suspense fallback={<p>Loading guide...</p>}>
      <Guide params={params} />
    </Suspense>
  )
}

async function Guide({ params }: { params: Promise<{ id: string }> }) {
  const { id } = await params
  const guide = await getGuide(id)
  const theme = (await cookies()).get('theme')?.value
  return <article data-theme={theme}>{guide.content}</article>
}
```


--------------------------------

### View terminal output when launching with --inspect

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/debugging.mdx

Displays the WebSocket debugging URL and local server address output by Node.js when the development server starts with debugging enabled.

```bash
Debugger listening on ws://127.0.0.1:9229/0cf90313-350d-4466-a748-cd60f4e47c95
For help, see: https://nodejs.org/learn/getting-started/debugging
ready - started server on 0.0.0.0:3000, url: http://localhost:3000
```


--------------------------------

### Initialize Next.js application instance

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/custom-server.mdx

Imports the `next` module and invokes it to instantiate the Next.js application before connecting it to a custom server.

```javascript
import next from 'next'

const app = next({})
```


--------------------------------

### Load environment variables in tests using loadEnvConfig

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/environment-variables.mdx

Use loadEnvConfig from @next/env in a Jest global setup file or similar testing environment setup to load environment variables in the same manner as Next.js. Pass the project root directory using process.cwd().

```js
// The below can be used in a Jest global setup file or similar for your testing set-up
import { loadEnvConfig } from '@next/env'

export default async () => {
  const projectDir = process.cwd()
  loadEnvConfig(projectDir)
}
```


--------------------------------

### Build dynamic route with streaming fallback

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/building.mdx

Run the Next.js build command and inspect the output showing partial prerendering (◐) for dynamic routes using a static shell.

```bash
next build
```

```bash
Route (app)
┌ ○ /
├ ○ /_not-found
└ ◐ /products/[id]

○  (Static)             prerendered as static content
◐  (Partial Prerender)  prerendered as static HTML with dynamic server-streamed content
```


--------------------------------

### Run build with bundle analysis enabled

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/package-bundling.mdx

Execute the build command with the ANALYZE environment variable set to true to generate and open the visual bundle report in browser tabs.

```bash
ANALYZE=true npm run build
# or
ANALYZE=true yarn build
# or
ANALYZE=true pnpm build
```


--------------------------------

### Test instant navigation with instant() in e2e/navigation.test.ts

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/instant-navigation.mdx

Assert on static UI for initial page loads and prefetched UI for client navigations using the instant() helper. Pass baseURL when page.goto() is the first navigation, and wait for destination URLs during client navigations before asserting.

```typescript
import { test, expect } from '@playwright/test'
import { instant } from '@next/playwright'

test.describe('Product page (/store/[slug])', () => {
  test('is instant on an initial page load', async ({ page, baseURL }) => {
    await instant(
      page,
      async () => {
        await page.goto('/store/hats')
        await expect(page.locator('h1')).toContainText('Baseball Cap')
        await expect(page.getByText('In stock')).toHaveCount(0)
      },
      { baseURL }
    )
    await expect(page.getByText('In stock')).toBeVisible()
  })

  test('is instant on a client navigation', async ({ page }) => {
    await page.goto('/store/shoes')
    await instant(page, async () => {
      await page.click('a[href="/store/hats"]')
      await page.waitForURL((url) => url.pathname === '/store/hats')
      await expect(page.locator('h1')).toContainText('Baseball Cap')
      await expect(page.getByText('In stock')).toHaveCount(0)
    })
    await expect(page.getByText('In stock')).toBeVisible()
  })
})
```


--------------------------------

### Create a custom server with http and next

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/custom-server.mdx

Programmatically initializes Next.js and creates an HTTP server using Node.js's `http` module. Note that custom servers cannot be used with standalone output mode and do not run through the Next.js compiler.

```typescript
import { createServer } from 'http'
import next from 'next'

const port = parseInt(process.env.PORT || '3000', 10)
const dev = process.env.NODE_ENV !== 'production'
const app = next({ dev })
const handle = app.getRequestHandler()

app.prepare().then(() => {
  createServer((req, res) => {
    handle(req, res)
  }).listen(port)

  console.log(
    `> Server listening at http://localhost:${port} as ${
      dev ? 'development' : process.env.NODE_ENV
    }`
  )
})
```

```javascript
import { createServer } from 'http'
import next from 'next'

const port = parseInt(process.env.PORT || '3000', 10)
const dev = process.env.NODE_ENV !== 'production'
const app = next({ dev })
const handle = app.getRequestHandler()

app.prepare().then(() => {
  createServer((req, res) => {
    handle(req, res)
  }).listen(port)

  console.log(
    `> Server listening at http://localhost:${port} as ${
      dev ? 'development' : process.env.NODE_ENV
    }`
  )
})
```


--------------------------------

### Define signup Server Action stub

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/authentication.mdx

Declare the initial `signup` Server Action in `app/actions/auth` that receives the submitted `FormData`.

```tsx
export async function signup(formData: FormData) {}
```

```jsx
export async function signup(formData) {}
```


--------------------------------

### Ask agent conceptual App Router questions

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/mcp.mdx

Prompt for querying App Router guidelines using version-matched bundled Next.js documentation.

```prompt
When should I use 'use client' in the App Router?

```


--------------------------------

### Save bundle analysis to disk with Bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/package-bundling.mdx

Saves the bundle analysis output statically to `.next/diagnostics/analyze` using Bun.

```bash
bunx next analyze --output
```


--------------------------------

### Inspect static prerender output with next build

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/public-static-pages.mdx

Displays the build output in the terminal confirming that the route is prerendered as static content.

```bash
Route (app)      Revalidate  Expire
┌ ○ /products           15m      1y
└ ○ /_not-found

○  (Static)  prerendered as static content
```


--------------------------------

### Capture user credentials in a signup form component

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/authentication.mdx

Create a form component in `app/ui/signup-form` that invokes the `signup` Server Action upon submission.

```tsx
import { signup } from '@/app/actions/auth'

export function SignupForm() {
  return (
    <form action={signup}>
      <div>
        <label htmlFor="name">Name</label>
        <input id="name" name="name" placeholder="Name" />
      </div>
      <div>
        <label htmlFor="email">Email</label>
        <input id="email" name="email" type="email" placeholder="Email" />
      </div>
      <div>
        <label htmlFor="password">Password</label>
        <input id="password" name="password" type="password" />
      </div>
      <button type="submit">Sign Up</button>
    </form>
  )
}
```

```jsx
import { signup } from '@/app/actions/auth'

export function SignupForm() {
  return (
    <form action={signup}>
      <div>
        <label htmlFor="name">Name</label>
        <input id="name" name="name" placeholder="Name" />
      </div>
      <div>
        <label htmlFor="email">Email</label>
        <input id="email" name="email" type="email" placeholder="Email" />
      </div>
      <div>
        <label htmlFor="password">Password</label>
        <input id="password" name="password" type="password" />
      </div>
      <button type="submit">Sign Up</button>
    </form>
  )
}
```


--------------------------------

### Create a user in a Server Action (app/actions/auth.js)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/authentication.mdx

Hashes the user password and inserts the user record into the database during signup. Returns an error message if record creation fails.

```jsx
export async function signup(state, formData) {
  // 1. Validate form fields
  // ...

  // 2. Prepare data for insertion into database
  const { name, email, password } = validatedFields.data
  // e.g. Hash the user's password before storing it
  const hashedPassword = await bcrypt.hash(password, 10)

  // 3. Insert the user into the database or call an Library API
  const data = await db
    .insert(users)
    .values({
      name,
      email,
      password: hashedPassword,
    })
    .returning({ id: users.id })

  const user = data[0]

  if (!user) {
    return {
      message: 'An error occurred while creating your account.',
    }
  }

  // TODO:
  // 4. Create user session
  // 5. Redirect user
}
```


--------------------------------

### Download version-matched docs using npx @next/codemod agents-md

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/ai-agents.mdx

Downloads a version-matched copy of the documentation to .next-docs/ and indexes it in AGENTS.md for Next.js 16.1 and earlier.

```bash
npx @next/codemod@canary agents-md
```


--------------------------------

### Render image with relative path in page component

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/static-exports.mdx

Use `next/image` with a relative path that gets resolved and optimized through the configured custom image loader.

```typescript
import Image from 'next/image'

export default function Page() {
  return <Image alt="turtles" src="/turtles.jpg" width={300} height={300} />
}
```

```javascript
import Image from 'next/image'

export default function Page() {
  return <Image alt="turtles" src="/turtles.jpg" width={300} height={300} />
}
```


--------------------------------

### Initialize client imports and VAPID key converter for push notifications

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/progressive-web-apps.mdx

Set up the client component with required imports and a helper function to convert base64 VAPID public keys to Uint8Array. Use this in app/page.tsx or app/page.js.

```tsx
'use client'

import { useState, useEffect } from 'react'
import { subscribeUser, unsubscribeUser, sendNotification } from './actions'

function urlBase64ToUint8Array(base64String: string) {
  const padding = '='.repeat((4 - (base64String.length % 4)) % 4)
  const base64 = (base64String + padding).replace(/-/g, '+').replace(/_/g, '/')

  const rawData = window.atob(base64)
  const outputArray = new Uint8Array(rawData.length)

  for (let i = 0; i < rawData.length; ++i) {
    outputArray[i] = rawData.charCodeAt(i)
  }
  return outputArray
}
```

```jsx
'use client'

import { useState, useEffect } from 'react'
import { subscribeUser, unsubscribeUser, sendNotification } from './actions'

function urlBase64ToUint8Array(base64String) {
  const padding = '='.repeat((4 - (base64String.length % 4)) % 4)
  const base64 = (base64String + padding)
    .replace(/\\-/g, '+')
    .replace(/_/g, '/')

  const rawData = window.atob(base64)
  const outputArray = new Uint8Array(rawData.length)

  for (let i = 0; i < rawData.length; ++i) {
    outputArray[i] = rawData.charCodeAt(i)
  }
  return outputArray
}
```


--------------------------------

### Set up TanStack Query client provider and layout

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/client-side-data-fetching/tanstack-query.mdx

Create a QueryClientProvider component that isolates server requests while reusing the browser query client across renders, then render it in the nearest shared layout.

```tsx
'use client'

import type { ReactNode } from 'react'
import { QueryClient, QueryClientProvider } from '@tanstack/react-query'

let browserQueryClient: QueryClient | undefined

function getQueryClient() {
  // Keep server requests isolated and preserve the browser cache across renders.
  if (typeof window === 'undefined') return new QueryClient()
  browserQueryClient ??= new QueryClient()
  return browserQueryClient
}

export function Providers({ children }: { children: ReactNode }) {
  return (
    <QueryClientProvider client={getQueryClient()}>
      {children}
    </QueryClientProvider>
  )
}
```

```tsx
import { Providers } from './providers'

export default function Layout({ children }: LayoutProps<'/products'>) {
  return <Providers>{children}</Providers>
}
```


--------------------------------

### Redirect inside a Route Handler using redirect

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/backend-for-frontend.mdx

Trigger a redirect to an external or internal URL from a GET Route Handler using Next.js navigation utilities.

```typescript
import { redirect } from 'next/navigation'

export async function GET(request: Request) {
  redirect('https://nextjs.org/')
}
```

```javascript
import { redirect } from 'next/navigation'

export async function GET(request) {
  redirect('https://nextjs.org/')
}
```


--------------------------------

### Isolate independent data queries into sibling Suspense boundaries

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/optimizing-the-static-shell.mdx

Moves URL-independent queries into a dedicated sibling component so data fetching can start alongside the page render.

```tsx
// After: the independent plan query starts with the page
import { Suspense } from 'react'

export default function SettingsPage({
  params,
  searchParams,
}: PageProps<'/[team]/settings'>) {
  return (
    <main>
      <h1>Settings</h1>
      <Suspense fallback={<PlanOptionsSkeleton />}>
        <PlanOptions />
      </Suspense>
      <Suspense fallback={<SettingsContentSkeleton />}>
        <SettingsTabs />
        <Suspense fallback={<SettingsFormSkeleton />}>
          <TeamSettings params={params} searchParams={searchParams} />
        </Suspense>
      </Suspense>
    </main>
  )
}
```

```tsx
export async function PlanOptions() {
  const plans = await db.plan.findMany()
  return <PlanList plans={plans} />
}
```


--------------------------------

### Remove cookie access to enable static prerendering in app/guides/[id]/page.tsx

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/keeping-pages-static.mdx

Remove runtime cookie retrieval to eliminate dynamic server-rendering requirements for static buying guides.

```diff
  import { Suspense } from 'react'
- import { cookies } from 'next/headers'
  import { getGuide, getGuideIds } from '@/lib/guides'

  // ...

  async function Guide({ params }) {
    const { id } = await params
    const guide = await getGuide(id)
-   const theme = (await cookies()).get('theme')?.value
-   return <article data-theme={theme}>{guide.content}</article>
+   return <article>{guide.content}</article>
  }
```


--------------------------------

### Construct CMS draft preview URL

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/draft-mode.mdx

Construct a draft preview URL pointing to your Route Handler. Replace placeholders with your deployment domain, generated secret token, and the path to view.

```bash
https://<your-site>/api/draft?secret=<token>&slug=<path>
```


--------------------------------

### Build routes with generateStaticParams and loading.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/building.mdx

Output showing build-time prerendering for each known parameter ID under the dynamic route pattern.

```bash
next build
```

```bash
Route (app)
┌ ○ /
├ ○ /_not-found
└   /products/[id]      # Route pattern group
  ├ ◐ /products/[id]    # Fallback row
  ├ ◐ /products/1       # Product content streams into the static shell
  ├ ◐ /products/2
  └ ◐ /products/3

○  (Static)             prerendered as static content
◐  (Partial Prerender)  prerendered as static HTML with dynamic server-streamed content
```


--------------------------------

### Calling preload before blocking operations in app/item/[id]/page

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/caching-without-cache-components.mdx

Call the preload function early in an async Server Component before awaiting other asynchronous tasks so data fetching starts immediately.

```tsx
import { getItem, preload, checkIsAvailable } from '@/lib/data'

export default async function Page({
  params,
}: {
  params: Promise<{ id: string }>
}) {
  const { id } = await params
  // Start loading item data
  preload(id)
  // Perform another asynchronous task
  const isAvailable = await checkIsAvailable()

  return isAvailable ? <Item id={id} /> : null
}

async function Item({ id }: { id: string }) {
  const result = await getItem(id)
  // ...
}
```

```jsx
import { getItem, preload, checkIsAvailable } from '@/lib/data'

export default async function Page({ params }) {
  const { id } = await params
  // Start loading item data
  preload(id)
  // Perform another asynchronous task
  const isAvailable = await checkIsAvailable()

  return isAvailable ? <Item id={id} /> : null
}

async function Item({ id }) {
  const result = await getItem(id)
  // ...
}
```


--------------------------------

### Configure serverActions.allowedOrigins in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/data-security.mdx

Defines an array of trusted origin strings or wildcards in next.config.js. Recommended for large applications with reverse proxies or multi-layered backend setups to prevent CSRF mismatches.

```javascript
/** @type {import('next').NextConfig} */
module.exports = {
  experimental: {
    serverActions: {
      allowedOrigins: ['my-proxy.com', '*.my-proxy.com'],
    },
  },
}
```


--------------------------------

### Configure a blocking product page route with instant = false

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/building.mdx

Set instant = false to disable instant-navigation validation when request-time blocking is needed. Removing loading files and use cache ensures the server waits for parameters and dynamic data fetching before responding.

```tsx
import { notFound } from 'next/navigation'

export const instant = false

export async function generateStaticParams() {
  const res = await fetch('https://api.example.com/products')
  const products = await res.json()
  return products.map((product) => ({ id: product.id }))
}

export default async function Page(props: PageProps<'/products/[id]'>) {
  const { id } = await props.params
  const res = await fetch(`https://api.example.com/products/${id}`)
  if (!res.ok) {
    notFound()
  }
  const product = await res.json()
  return <div>{product.name}</div>
}
```

```jsx
import { notFound } from 'next/navigation'

export const instant = false

export async function generateStaticParams() {
  const res = await fetch('https://api.example.com/products')
  const products = await res.json()
  return products.map((product) => ({ id: product.id }))
}

export default async function Page({ params }) {
  const { id } = await params
  const res = await fetch(`https://api.example.com/products/${id}`)
  if (!res.ok) {
    notFound()
  }
  const product = await res.json()
  return <div>{product.name}</div>
}
```


--------------------------------

### Verify static build output in Terminal

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/keeping-pages-static.mdx

Terminal build output confirming that routes are prerendered as static content.

```text
Route (app)
├   /guides/[id]
│ ├ ◐ /guides/[id]
│ └ ○ /guides/coffee
├ ◐ /store
└   /store/products/[slug]
  ├ ◐ /store/products/[slug]
  └ ◐ /store/products/coffee-grinder

○  (Static)             prerendered as static content
◐  (Partial Prerender)  prerendered as static HTML with dynamic server-streamed content
```


--------------------------------

### Save bundle analysis to disk with pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/package-bundling.mdx

Saves the bundle analysis output statically to `.next/diagnostics/analyze` using pnpm.

```bash
pnpm next analyze --output
```


--------------------------------

### Pass an unawaited Promise from a layout to a Context Provider

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/single-page-applications.mdx

Start data fetching in a Server Component without awaiting it to allow immediate streaming to the client. Pass the resulting Promise directly into a context provider.

```tsx
import { UserProvider } from './user-provider'
import { getUser } from './user' // some server-side function

export default function RootLayout({ children }: LayoutProps<'/'>) {
  let userPromise = getUser() // do NOT await

  return (
    <html lang="en">
      <body>
        <UserProvider userPromise={userPromise}>{children}</UserProvider>
      </body>
    </html>
  )
}
```

```jsx
import { UserProvider } from './user-provider'
import { getUser } from './user' // some server-side function

export default function RootLayout({ children }) {
  let userPromise = getUser() // do NOT await

  return (
    <html lang="en">
      <body>
        <UserProvider userPromise={userPromise}>{children}</UserProvider>
      </body>
    </html>
  )
}
```


--------------------------------

### Server-side syntax highlighting in a Server Component

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/package-bundling.mdx

Move rendering and parsing dependencies like Shiki into an async Server Component so client bundles only receive plain HTML markup.

```tsx
import { codeToHtml } from 'shiki'

export default async function Page() {
  const code = `export function hello() {
    console.log("hi")
  }`

  // The Shiki package runs on the server and is never bundled for the client.
  const highlightedHtml = await codeToHtml(code, {
    lang: 'tsx',
    theme: 'github-dark',
  })

  return (
    <article>
      <h1>Blog Post Title</h1>

      {/* Client receives plain markup */}
      <pre>
        <code dangerouslySetInnerHTML={{ __html: highlightedHtml }} />
      </pre>
    </article>
  )
}
```


--------------------------------

### Directory structure with dynamic product route

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/building.mdx

Directory layout for a store application with a dynamic `[id]` segment under the products route.

```txt
app/
├── layout.tsx
├── page.tsx
└── products/
    └── [id]/
        └── page.tsx
```


--------------------------------

### Configure serverActions in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/server-actions.mdx

Configure framework-level behavior for Server Actions such as allowed origins and body size limit in next.config.js.

```javascript
/** @type {import('next').NextConfig} */
module.exports = {
  experimental: {
    serverActions: {
      allowedOrigins: ['my-proxy.com', '*.my-proxy.com'],
      bodySizeLimit: '2mb',
    },
  },
}
```


--------------------------------

### Save bundle analysis to disk with npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/package-bundling.mdx

Skips the interactive view and writes the bundle analysis output to the `.next/diagnostics/analyze` directory.

```bash
npx next analyze --output
```


--------------------------------

### Creating a preload utility with React cache and server-only in utils/get-item

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/caching-without-cache-components.mdx

Combine the server-only package with React cache to define a reusable preload utility that initiates fetching without blocking.

```ts
import { cache } from 'react'
import 'server-only'

export const getItem = cache(async (id: string) => {
  // ...
})

export const preload = (id: string) => {
  void getItem(id)
}
```

```js
import { cache } from 'react'
import 'server-only'

export const getItem = cache(async (id) => {
  // ...
})

export const preload = (id) => {
  void getItem(id)
}
```


--------------------------------

### Pass unawaited data promise to a Client Component with use()

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/optimizing-the-static-shell.mdx

Starts server data fetching without awaiting it in the page, passing the promise to a Client Component wrapped in Suspense that unwraps it using React's use() hook.

```tsx
// After: the heading can render while the chart waits
import { Suspense } from 'react'
import { getActivity } from '@/app/lib/data'
import { ActivityChart } from './activity-chart'

export default function DashboardPage() {
  const activityPromise = getActivity()

  return (
    <Suspense fallback={<ActivityChartSkeleton />}>
      <ActivityChart dataPromise={activityPromise} />
    </Suspense>
  )
}
```

```tsx
'use client'

import { use } from 'react'

type Activity = { date: string; value: number }

export function ActivityChart({
  dataPromise,
}: {
  dataPromise: Promise<Activity[]>
}) {
  const activity = use(dataPromise)

  return <Chart data={activity} />
}
```


--------------------------------

### Set response headers before calling handle

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/custom-server.mdx

Sets response headers before delegating request processing to Next.js. Next.js starts sending the response inside `handle(req, res)`, causing any subsequent `res.setHeader()` calls to be silently discarded.

```javascript
res.setHeader('Set-Cookie', 'sessionId=abc123; Max-Age=2592000')

await handle(req, res)
```


--------------------------------

### Interpret Turbopack trace file with next internal trace

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/local-development.mdx

Run the internal trace server on the generated trace-turbopack.bin file to view results at https://trace.nextjs.org/.

```bash
npx next internal trace .next-profiles/trace-turbopack.bin
```


--------------------------------

### Build an Instantly Navigating Dynamic Product Page

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/instant-navigation.mdx

Wraps separate data-fetching components in independent Suspense boundaries when awaiting dynamic route params. Combines cached database queries using 'use cache' with uncached streaming inventory requests to keep navigations instant.

```tsx
import { Suspense } from 'react'
import { db } from '@/lib/db'

export default function ProductPage(props: PageProps<'/store/[slug]'>) {
  return (
    <div>
      <Suspense fallback={<p>Loading product...</p>}>
        <ProductInfo params={props.params} />
      </Suspense>
      <Suspense fallback={<p>Checking availability...</p>}>
        <Inventory params={props.params} />
      </Suspense>
    </div>
  )
}

type Params = PageProps<'/store/[slug]'>['params']

async function ProductInfo({ params }: { params: Params }) {
  const { slug } = await params
  const product = await getProduct(slug)
  return (
    <>
      <h1>{product.name}</h1>
      <p>${product.price}</p>
    </>
  )
}

async function getProduct(slug: string) {
  'use cache'
  return db.products.findBySlug(slug)
}

async function Inventory({ params }: { params: Params }) {
  const { slug } = await params
  const item = await db.inventory.findBySlug(slug)
  return <p>{item.count} in stock</p>
}
```


--------------------------------

### Enable cacheComponents and partialPrefetching in next.config.ts

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/incremental-static-regeneration-cache-components.mdx

Enables cacheComponents and partialPrefetching in Next.js configuration. This setup allows Next.js to prerender an App Shell with fallback UI and upgrade unlisted paths on demand to store completed results in the ISR cache.

```typescript
import type { NextConfig } from 'next'

const nextConfig: NextConfig = {
  cacheComponents: true,
  partialPrefetching: true,
}

export default nextConfig
```


--------------------------------

### Run the Next.js build command

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/building.mdx

Executes the production build using your preferred package manager. After a successful build, Next.js outputs a route table showing rendering classifications for each route.

```bash
pnpm build
```

```bash
npm run build
```

```bash
yarn build
```

```bash
bun run build
```


--------------------------------

### Pass an unresolved fetch promise to a Client Component (app/dashboard/page)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/streaming.mdx

Start a fetch during server rendering without awaiting it, passing the unresolved promise to a Client Component wrapped in Suspense. The fallback renders immediately while the completed HTML is streamed once resolved.

```tsx
import { Suspense } from 'react'
import { StatsChart } from './stats-chart'

type Stats = { revenue: number; orders: number }

async function getStats(): Promise<Stats> {
  const res = await fetch('https://api.example.com/stats')
  return res.json()
}

export default function Dashboard() {
  // Start the fetch during server render, don't await it
  const statsPromise = getStats()

  return (
    <Suspense fallback={<p>Loading chart...</p>}>
      <StatsChart dataPromise={statsPromise} />
    </Suspense>
  )
}
```

```jsx
import { Suspense } from 'react'
import { StatsChart } from './stats-chart'

async function getStats() {
  const res = await fetch('https://api.example.com/stats')
  return res.json()
}

export default function Dashboard() {
  // Start the fetch during server render, don't await it
  const statsPromise = getStats()

  return (
    <Suspense fallback={<p>Loading chart...</p>}>
      <StatsChart dataPromise={statsPromise} />
    </Suspense>
  )
}
```


--------------------------------

### Disable preloading entries on start in next.config

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/memory-usage.mdx

Disables preloading page JavaScript modules into memory at server startup to reduce initial memory footprint. Note that memory usage will eventually match the default footprint as all pages are requested over time.

```typescript
import type { NextConfig } from 'next'

const config: NextConfig = {
  experimental: {
    preloadEntriesOnStart: false,
  },
}

export default config
```

```javascript
/** @type {import('next').NextConfig} */
const config = {
  experimental: {
    preloadEntriesOnStart: false,
  },
}

export default config
```


--------------------------------

### Create shared Route Handler with factory pattern

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/backend-for-frontend.mdx

Creates a shared handler for GET and POST requests in `/app/api/[...path]/route.ts` using a library factory. The library customizes behavior based on the request's method and pathname.

```ts
import { createHandler } from 'third-party-library'

const handler = createHandler({
  /* library-specific options */
})

export const GET = handler
// or
export { handler as POST }
```


--------------------------------

### Prerender hidden content using Activity and Suspense

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/preserving-ui-state.mdx

Start data fetching in a Server Component and pass the unresolved promise to a Client Component. The Client Component uses Activity in hidden mode to render at lower priority and resolves the promise with use() when toggled.

```tsx
import { Suspense } from 'react'
import { ExpandableComments } from './expandable-comments'

async function getCommentsData() {
  return db.comments.findMany()
}

export default function Page() {
  const commentsPromise = getCommentsData()

  return (
    <article>
      <h1>Post Title</h1>
      <p>Main content visible immediately...</p>

      <ExpandableComments commentsPromise={commentsPromise} />
    </article>
  )
}
```

```tsx
'use client'

import { Activity, Suspense, useState, use } from 'react'

type Comment = { id: string; text: string; author: string }

export function ExpandableComments({
  commentsPromise,
}: {
  commentsPromise: Promise<Comment[]>
}) {
  const [expanded, setExpanded] = useState(false)

  return (
    <>
      <button onClick={() => setExpanded((e) => !e)}>
        {expanded ? 'Hide Comments' : 'Show Comments'}
      </button>

      <Activity mode={expanded ? 'visible' : 'hidden'}>
        <Suspense fallback={<CommentsSkeleton />}>
          <Comments commentsPromise={commentsPromise} />
        </Suspense>
      </Activity>
    </>
  )
}

function Comments({
  commentsPromise,
}: {
  commentsPromise: Promise<Comment[]>
}) {
  const comments = use(commentsPromise)
  return (
    <ul>
      {comments.map((c) => (
        <li key={c.id}>{c.text}</li>
      ))}
    </ul>
  )
}

function CommentsSkeleton() {
  return <div>Loading comments...</div>
}
```


--------------------------------

### Reveal related regions in stages with nested Suspense boundaries

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/optimizing-the-static-shell.mdx

Nest Suspense boundaries when content should first appear together and reveal more detail progressively, or to prevent layout shifts. React still starts reachable work concurrently, while nesting controls the visual reveal order.

```tsx
<Suspense fallback={<AccountSkeleton />}>
  <AccountHeader />
  <Suspense fallback={<ActivitySkeleton />}>
    <Activity />
  </Suspense>
</Suspense>
```


--------------------------------

### Configure custom cacheHandler in next.config.js and cache-handler.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/self-hosting.mdx

Configure a custom cache handler path and disable default in-memory caching in `next.config.js`, then implement the `CacheHandler` class in `cache-handler.js`. Use this setup to persist and share cache across multiple pods using durable storage like Redis or S3.

```jsx
module.exports = {
  cacheHandler: require.resolve('./cache-handler.js'),
  cacheMaxMemorySize: 0, // disable default in-memory caching
}
```

```jsx
const cache = new Map()

module.exports = class CacheHandler {
  constructor(options) {
    this.options = options
  }

  async get(key) {
    // This could be stored anywhere, like durable storage
    return cache.get(key)
  }

  async set(key, data, ctx) {
    // This could be stored anywhere, like durable storage
    cache.set(key, {
      value: data,
      lastModified: Date.now(),
      tags: ctx.tags,
    })
  }

  async revalidateTag(tags) {
    // tags is either a string or an array of strings
    tags = [tags].flat()
    // Iterate over all entries in the cache
    for (let [key, value] of cache) {
      // If the value's tags include the specified tag, delete this entry
      if (value.tags.some((tag) => tags.includes(tag))) {
        cache.delete(key)
      }
    }
  }

  // If you want to have temporary in memory cache for a single request that is reset
  // before the next request you can leverage this method
  resetRequestCache() {}
}
```


--------------------------------

### Transform Markdown to HTML with Unified, Remark, and Rehype

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/mdx.mdx

Demonstrates the step-by-step pipeline used by unified, remark, and rehype to parse markdown into an AST, convert it to an HTML AST, sanitize it, and serialize it to HTML. When using @next/mdx, this transformation is handled automatically.

```javascript
import { unified } from 'unified'
import remarkParse from 'remark-parse'
import remarkRehype from 'remark-rehype'
import rehypeSanitize from 'rehype-sanitize'
import rehypeStringify from 'rehype-stringify'

main()

async function main() {
  const file = await unified()
    .use(remarkParse) // Convert into markdown AST
    .use(remarkRehype) // Transform to HTML AST
    .use(rehypeSanitize) // Sanitize HTML input
    .use(rehypeStringify) // Convert AST into serialized HTML
    .process('Hello, Next.js!')

  console.log(String(file)) // <p>Hello, Next.js!</p>
}
```


--------------------------------

### Confirm partial prerendering in next build output

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/public-static-pages.mdx

Displays the terminal build output confirming the route is partially prerendered with dynamic server-streamed content.

```bash
Route (app)      Revalidate  Expire
┌ ◐ /products    15m      1y
└ ◐ /_not-found

◐  (Partial Prerender)  Prerendered as static HTML with dynamic server-streamed content
```


--------------------------------

### Defining a Client Component in app/hello

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/server-and-client-boundary.mdx

Defines a Client Component using the 'use client' directive. On direct visit, it executes on the server and again during browser hydration; on client navigation, it renders in the browser via the RSC Payload.

```tsx
'use client'

export default function Hello() {
  console.log('Hello rendered') // on a direct visit: server, then browser
  return <p>Hello</p>
}
```

```jsx
'use client'

export default function Hello() {
  console.log('Hello rendered') // on a direct visit: server, then browser
  return <p>Hello</p>
}
```


--------------------------------

### Wrapping static UI in a full-page Suspense boundary (Before)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/optimizing-the-static-shell.mdx

Demonstrates a broad Suspense boundary where a single fallback skeleton temporarily replaces both static UI and dynamic components during suspension.

```tsx
// Before: one loading state replaces the whole page
<Suspense fallback={<ProductsSkeleton />}>
  <h1>Products</h1>
  <p>Browse the latest products.</p>
  <LiveInventory />
</Suspense>
```


--------------------------------

### Configure route with ensureStatic

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/keeping-pages-static.mdx

Export `ensureStatic = 'navigation'` to enforce that the route returns complete static output without request-time server rendering.

```diff
  import { Suspense } from 'react'
  import { cookies } from 'next/headers'

+ export const ensureStatic = 'navigation'

  export default function GuidePage({ params }) {
    // ...
  }
```


--------------------------------

### Save bundle analysis to disk with Yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/package-bundling.mdx

Saves the bundle analysis output statically to `.next/diagnostics/analyze` using Yarn.

```bash
yarn next analyze --output
```


--------------------------------

### Configure time-based ISR in pages/blog/[id].jsx

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/incremental-static-regeneration.mdx

Uses getStaticPaths with fallback 'blocking' and getStaticProps with revalidate: 60 to statically generate pages and invalidate the cache in the background after 60 seconds. Uncached existing paths are generated on-demand while non-existent posts return a 404.

```jsx
export async function getStaticPaths() {
  const posts = await fetch('https://api.vercel.app/blog').then((res) =>
    res.json()
  )
  const paths = posts.map((post) => ({
    params: { id: post.id },
  }))

  return { paths, fallback: 'blocking' }
}

export async function getStaticProps({ params }) {
  const post = await fetch(`https://api.vercel.app/blog/${params.id}`).then(
    (res) => res.json()
  )

  return {
    props: { post },
    // Next.js will invalidate the cache when a
    // request comes in, at most once every 60 seconds.
    revalidate: 60,
  }
}

export default function Page({ post }) {
  return (
    <main>
      <h1>{post.title}</h1>
      <p>{post.content}</p>
    </main>
  )
}
```


--------------------------------

### Configure remark and rehype plugins in next.config.mjs

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/mdx.mdx

Configures MDX transformations using imported plugins such as remark-gfm. Requires next.config.mjs or next.config.ts because the remark and rehype ecosystem is ESM-only.

```javascript
import remarkGfm from 'remark-gfm'
import createMDX from '@next/mdx'

/** @type {import('next').NextConfig} */
const nextConfig = {
  // Allow .mdx extensions for files
  pageExtensions: ['js', 'jsx', 'md', 'mdx', 'ts', 'tsx'],
  // Optionally, add any other Next.js config below
}

const withMDX = createMDX({
  // Add markdown plugins here, as desired
  options: {
    remarkPlugins: [remarkGfm],
    rehypePlugins: [],
  },
})

// Combine MDX and Next.js config
export default withMDX(nextConfig)
```


--------------------------------

### Verify instant UI using Playwright and instant()

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/optimizing-the-static-shell.mdx

Uses instant from @next/playwright to hold back request-time server work and assert that the static shell and client components display immediately.

```ts
import { expect, test, type Page } from '@playwright/test'
import { instant } from '@next/playwright'

async function expectInstantSettingsUI(page: Page) {
  await expect(page.getByRole('heading', { name: 'Settings' })).toBeVisible()
  await expect(page.getByTestId('plan-options')).toBeVisible()
  await expect(page.getByTestId('settings-tabs')).toBeVisible()
  await expect(page.getByTestId('settings-form-skeleton')).toBeVisible()
  await expect(page.getByTestId('settings-content-skeleton')).toHaveCount(0)
  await expect(page.getByTestId('team-settings-form')).toHaveCount(0)
}

test('shows settings UI before request-time work completes', async ({
  page,
  baseURL,
}) => {
  await instant(
    page,
    async () => {
      await page.goto('/acme/settings')
      await expectInstantSettingsUI(page)
    },
    { baseURL }
  )

  await expect(page.getByTestId('team-settings-form')).toBeVisible()
  await expect(page.getByTestId('settings-form-skeleton')).toHaveCount(0)
})
```


--------------------------------

### Inspect dynamic route build output for blocking page

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/building.mdx

Demonstrates the terminal build output when routes are marked dynamic (ƒ) and rendered on request without prerendered HTML.

```bash
Route (app)
┌ ○ /
├ ○ /_not-found
└   /products/[id]      # Route pattern group
  ├ ƒ /products/[id]    # Empty fallback for unlisted IDs
  ├ ƒ /products/1       # Rendered on request with no HTML prerender
  ├ ƒ /products/2
  └ ƒ /products/3

○  (Static)   prerendered as static content
ƒ  (Dynamic)  server-rendered on demand
```


--------------------------------

### Directory structure of bundled Next.js documentation

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/ai-agents.mdx

Shows the layout of version-matched documentation files inside node_modules/next/dist/docs/. This structure mirrors the official Next.js documentation site.

```txt
node_modules/next/dist/docs/
├── 01-app/
│   ├── 01-getting-started/
│   ├── 02-guides/
│   └── 03-api-reference/
├── 02-pages/
├── 03-architecture/
└── index.mdx
```


--------------------------------

### Hash password and insert user into the database in signup action

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/authentication.mdx

Prepares validated form data, hashes the password with bcrypt, and inserts the new user record into the database.

```tsx
export async function signup(state: FormState, formData: FormData) {
  // 1. Validate form fields
  // ...

  // 2. Prepare data for insertion into database
  const { name, email, password } = validatedFields.data
  // e.g. Hash the user's password before storing it
  const hashedPassword = await bcrypt.hash(password, 10)

  // 3. Insert the user into the database or call an Auth Library's API
  const data = await db
    .insert(users)
    .values({
      name,
      email,
      password: hashedPassword,
    })
    .returning({ id: users.id })

  const user = data[0]

  if (!user) {
    return {
      message: 'An error occurred while creating your account.',
    }
  }

  // TODO:
  // 4. Create user session
  // 5. Redirect user
}
```


--------------------------------

### Define multiline environment variables

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/environment-variables.mdx

Shows how to define multiline strings in .env files using line breaks or explicit newline characters.

```bash
# .env

# you can write with line breaks
PRIVATE_KEY="-----BEGIN RSA PRIVATE KEY-----
...
Kh9NV...
...
-----END DSA PRIVATE KEY-----"

# or with `\n` inside double quotes
PRIVATE_KEY="-----BEGIN RSA PRIVATE KEY-----\nKh9NV...\n-----END DSA PRIVATE KEY-----\n"
```


--------------------------------

### Copy diagnostics directory for comparison

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/package-bundling.mdx

Copies the generated `.next/diagnostics/analyze` directory to another location to compare bundle metrics across refactors.

```bash
cp -r .next/diagnostics/analyze ./analyze-before-refactor
```


--------------------------------

### Data flow before React Server Components

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/server-and-client-boundary.mdx

Illustrates the legacy data flow pattern where data was fetched before rendering and passed down to the component tree via props.

```txt
Data
  ↓
Loader or API
  ↓
Props
  ↓
Component tree
```


--------------------------------

### Directory structure for App Router MDX imports

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/mdx.mdx

File layout for importing separate MDX files into App Router page components.

```txt
  .
  ├── app/
  │   └── mdx-page/
  │       └── page.(tsx/js)
  ├── markdown/
  │   └── welcome.(mdx/md)
  ├── mdx-components.(tsx/js)
  └── package.json
```


--------------------------------

### Cache ProductList component using 'use cache' and cacheLife

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/optimizing-the-static-shell.mdx

Cache a component and define its lifetime with `cacheLife('hours')` so the completed UI can render into the static shell.

```tsx
// After: the reusable result can render in the shell
import { cacheLife } from 'next/cache'

export async function ProductList() {
  'use cache'
  cacheLife('hours')

  const products = await db.products.findMany()
  return <List products={products} />
}
```


--------------------------------

### Enable fetch request logging in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/incremental-static-regeneration.mdx

Configures verbose logging in local development to track whether fetch requests are cached or uncached.

```jsx
module.exports = {
  logging: {
    fetches: {
      fullUrl: true,
    },
  },
}
```


--------------------------------

### Implement a Data Access Layer with cached auth, DTOs, and safe page rendering

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/data-security.mdx

Demonstrates setting up a Data Access Layer across data/auth.ts, data/user-dto.tsx, and app/page.tsx. It uses React cache for user authentication, enforces server-only execution, and passes minimized DTOs to the page.

```ts
import { cache } from 'react'
import { cookies } from 'next/headers'

// Cached helper methods makes it easy to get the same value in many places
// without manually passing it around. This discourages passing it from Server
// Component to Server Component which minimizes risk of passing it to a Client
// Component.
export const getCurrentUser = cache(async () => {
  const cookieStore = await cookies()
  const token = cookieStore.get('AUTH_TOKEN')
  const decodedToken = await decryptAndValidate(token)
  // Don't include secret tokens or private information as public fields.
  // Use classes to avoid accidentally passing the whole object to the client.
  return new User(decodedToken.id)
})
```

```tsx
import 'server-only'
import { getCurrentUser } from './auth'

function canSeeUsername(viewer: User) {
  // Public info for now, but can change
  return true
}

function canSeePhoneNumber(viewer: User, team: string) {
  // Privacy rules
  return viewer.isAdmin || team === viewer.team
}

export async function getProfileDTO(slug: string) {
  // Don't pass values, read back cached values, also solves context and easier to make it lazy

  // use a database API that supports safe templating of queries
  const [rows] = await sql`SELECT * FROM user WHERE slug = ${slug}`
  const userData = rows[0]

  const currentUser = await getCurrentUser()

  // only return the data relevant for this query and not everything
  // <https://www.w3.org/2001/tag/doc/APIMinimization>
  return {
    username: canSeeUsername(currentUser) ? userData.username : null,
    phonenumber: canSeePhoneNumber(currentUser, userData.team)
      ? userData.phonenumber
      : null,
  }
}
```

```tsx
import { getProfileDTO } from '../../data/user-dto'

export default async function Page({ params }) {
  const { slug } = await params
  // This page can now safely pass around this profile knowing
  // that it shouldn't contain anything sensitive.
  const profile = await getProfileDTO(slug)
  ...
}
```


--------------------------------

### Define team settings route folder structure

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/optimizing-the-static-shell.mdx

Shows the directory layout containing the settings layout and page files.

```text
app/[team]/settings/
├── layout.tsx
└── page.tsx
```


--------------------------------

### Test prefetched and deferred content using instant in e2e/product-navigation.test.ts

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/optimizing-prefetching.mdx

Use `instant()` from `@next/playwright` during client navigation to pause dynamic content and verify what UI is prefetched. After the callback finishes and releases the pause, assert that deferred dynamic elements render.

```typescript
import { expect, test } from '@playwright/test'
import { instant } from '@next/playwright'

test('prefetches the product summary but not reviews', async ({ page }) => {
  await page.goto('/products')

  await instant(page, async () => {
    await page.click('a[href="/products/baseball-cap"]')
    await page.waitForURL((url) => url.pathname === '/products/baseball-cap')

    await expect(
      page.getByRole('heading', { name: 'Baseball Cap' })
    ).toBeVisible()
    await expect(page.getByTestId('product-summary')).toBeVisible()
    await expect(page.getByTestId('reviews')).toHaveCount(0)
  })

  await expect(page.getByTestId('reviews')).toBeVisible()
})
```


--------------------------------

### Generate VAPID keys using web-push CLI

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/progressive-web-apps.mdx

Runs the web-push CLI command in terminal to generate public and private VAPID key pairs.

```bash
web-push generate-vapid-keys
```


--------------------------------

### Prefetch prerendered product details with Link

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/keeping-pages-static.mdx

Sets `prefetch={true}` on the `<Link>` component to include prerendered product details before navigation.

```tsx
<Link href="/store/products/coffee-grinder" prefetch={true}>
  Coffee grinder
</Link>
```


--------------------------------

### Enable the Experimental Rust-Based MDX Compiler in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/mdx.mdx

Enables the experimental Rust-based MDX compiler by setting experimental.mdxRs to true in next.config.js. Note that this compiler is experimental and not recommended for production use.

```javascript
module.exports = withMDX({
  experimental: {
    mdxRs: true,
  },
})
```


--------------------------------

### Configure Options for Experimental Rust-Based MDX Compiler in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/mdx.mdx

Configures specific transformation options for the Rust-based MDX compiler by passing an object to experimental.mdxRs. Supported fields include custom JSX runtimes, provider import sources, and syntax parsing modes.

```javascript
module.exports = withMDX({
  experimental: {
    mdxRs: {
      jsxRuntime?: string            // Custom jsx runtime
      jsxImportSource?: string       // Custom jsx import source,
      providerImportSource?: string  // Module providing a `useMDXComponents` context
      mdxType?: 'gfm' | 'commonmark' // Configure what kind of mdx syntax will be used to parse & transform
    },
  },
})
```


--------------------------------

### Configure createMDX extension option to handle .md files

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/mdx.mdx

Specify the `extension` regular expression option in `createMDX` to compile `.md` files in addition to default `.mdx` files.

```js
const withMDX = createMDX({
  extension: /\.(md|mdx)$/,
})
```


--------------------------------

### Data fetching in Server Components during static export

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/static-exports.mdx

Demonstrates fetching data inside a Server Component during next build for static export.

```tsx
export default async function Page() {
  // This fetch will run on the server during `next build`
  const res = await fetch('https://api.example.com/...')
  const data = await res.json()

  return <main>...</main>
}
```


--------------------------------

### Configure next-devtools in .mcp.json

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/mcp.mdx

Configures next-devtools-mcp directly within the project root .mcp.json file.

```json
{
  "mcpServers": {
    "next-devtools": {
      "command": "npx",
      "args": ["-y", "next-devtools-mcp@latest"]
    }
  }
}
```


--------------------------------

### Opt into per-link prefetching using prefetch={true}

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/interactive-apps.mdx

Enables per-link prefetching on Next.js Link components to resolve link-specific URL data prior to navigation clicks.

```tsx
<Link href={`/task/${id}`} prefetch={true}>
  {/* … */}
</Link>
```


--------------------------------

### Force dynamic rendering with connection() in app/page

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/content-security-policy.mdx

Explicitly opt a page into server-side dynamic rendering using connection() from next/server. This ensures the page renders per request so Next.js can read the CSP header and apply nonces.

```tsx
import { connection } from 'next/server'

export default async function Page() {
  // wait for an incoming request to render this page
  await connection()
  // Your page content
}
```

```jsx
import { connection } from 'next/server'

export default async function Page() {
  // wait for an incoming request to render this page
  await connection()
  // Your page content
}
```


--------------------------------

### Define custom Partytown configuration in _document.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/scripts.mdx

Adds custom Partytown settings such as debug mode inside `<Head />`. Requires the `data-partytown-config` attribute and defining `lib: "/_next/static/~partytown/"`.

```jsx
import { Html, Head, Main, NextScript } from 'next/document'

export default function Document() {
  return (
    <Html>
      <Head>
        <script
          data-partytown-config
          dangerouslySetInnerHTML={{
            __html: `
              partytown = {
                lib: "/_next/static/~partytown/",
                debug: true
              };
            `,
          }}
        />
      </Head>
      <body>
        <Main />
        <NextScript />
      </body>
    </Html>
  )
}
```


--------------------------------

### Fetch client data with useQuery in app/product-autocomplete.tsx

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/client-side-data-fetching/tanstack-query.mdx

Use `useQuery` from `@tanstack/react-query` to handle inline loading and error states on the client. The `enabled` option delays making the fetch request until an input value is present.

```tsx
'use client'

import { useQuery } from '@tanstack/react-query'

type Product = { id: string; name: string }

async function searchProducts(query: string): Promise<Product[]> {
  const response = await fetch(
    `/api/products?query=${encodeURIComponent(query)}`
  )
  if (!response.ok) throw new Error('Failed to fetch products')
  return response.json()
}

export function ProductAutocomplete({ query }: { query: string }) {
  const {
    data = [],
    error,
    isPending,
  } = useQuery({
    queryKey: ['product-search', query],
    queryFn: () => searchProducts(query),
    enabled: query.length > 0,
  })

  if (!query) return null
  if (error) return <p>Failed to load products.</p>
  if (isPending) return <p>Loading products...</p>

  return (
    <ul>
      {data.map((product) => (
        <li key={product.id}>{product.name}</li>
      ))}
    </ul>
  )
}
```


--------------------------------

### Run remove-partial-prefetch codemod to clean up route-level exports

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/adopting-partial-prefetching.mdx

Strips redundant `export const prefetch = 'partial'` exports from pages and layouts after enabling the global flag. Pass `./src/app` instead when working in a `src/` directory.

```bash
npx @next/codemod@canary remove-partial-prefetch ./app
```
