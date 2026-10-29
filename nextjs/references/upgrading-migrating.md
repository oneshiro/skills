# Upgrading & Migrating

Sourced snippets from the Next.js docs dump (70 entries).
Search this file for the topic at hand; treat snippets as patterns and
reconcile with the installed Next.js version before applying.

### Start agent upgrade with experimental-future policy

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/agent-upgrade.mdx

Applies the latest policy and prepares adoption guides and Skills for future defaults like Cache Components on Next.js 16.3+ App Router projects.

```bash
npx next@canary upgrade --agent=experimental-future
```


--------------------------------

### Install Next.js using bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/from-vite.mdx

Installs the latest Next.js package as a project dependency using Bun.

```bash
bun add next@latest
```


--------------------------------

### Install Next.js using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/from-vite.mdx

Installs the latest Next.js package as a project dependency using npm.

```bash
npm install next@latest
```


--------------------------------

### Install Next.js using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/from-vite.mdx

Installs the latest Next.js package as a project dependency using pnpm.

```bash
pnpm add next@latest
```


--------------------------------

### Install Next.js using yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/from-vite.mdx

Installs the latest Next.js package as a project dependency using Yarn.

```bash
yarn add next@latest
```


--------------------------------

### Start Next.js development server with Turbopack

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/from-create-react-app.mdx

Runs the Next.js local development server using Turbopack by default.

```bash
next dev  # Uses Turbopack by default
```


--------------------------------

### Import ImageResponse from next/server (Before transform)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/codemods.mdx

Example showing ImageResponse imported from next/server prior to running the codemod.

```js
import { ImageResponse } from 'next/server'
```


--------------------------------

### Start agent upgrade with default or configured policy

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/agent-upgrade.mdx

Omit the policy argument to use the value configured in experimental.agentUpgrade, or default to security. Note that --agent cannot be combined with --revision.

```bash
npx next@canary upgrade --agent
```


--------------------------------

### Start agent upgrade from workspace root

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/agent-upgrade.mdx

Pass the specific app directory path when initiating the agent upgrade from the root of a workspace or monorepo.

```bash
npx next@canary upgrade apps/web --agent=latest
```


--------------------------------

### Install Next.js and React packages manually

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Manually installs the latest releases of next, react, and react-dom. If using TypeScript, also upgrade @types/react and @types/react-dom to matching versions.

```bash
pnpm add next@latest react@latest react-dom@latest
```

```bash
npm install next@latest react@latest react-dom@latest
```

```bash
yarn add next@latest react@latest react-dom@latest
```

```bash
bun add next@latest react@latest react-dom@latest
```


--------------------------------

### Start Next.js development server with Webpack

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/from-create-react-app.mdx

Runs the Next.js development server using Webpack instead of Turbopack for compatibility with Create React App configurations.

```bash
next dev --webpack
```


--------------------------------

### Adopt Cache Components using the next-cache-components-adoption skill

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating-to-cache-components.mdx

Install the adoption skill and run the prompt with a coding agent to migrate route segment configs to Cache Components. Supports both incremental and direct adoption workflows.

```bash
npx skills add vercel/next.js --skill next-cache-components-adoption
```

```prompt
Adopt Cache Components in this project using the next-cache-components-adoption skill.
```


--------------------------------

### Define SPA entrypoint in app/[[...slug]]/page

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/from-vite.mdx

Sets up an optional catch-all Server Component page entrypoint for an SPA migration. Uses generateStaticParams to prerender only the root index route during build time.

```tsx
import '../../index.css'

export function generateStaticParams() {
  return [{ slug: [''] }]
}

export default function Page() {
  return '...' // We'll update this
}
```

```jsx
import '../../index.css'

export function generateStaticParams() {
  return [{ slug: [''] }]
}

export default function Page() {
  return '...' // We'll update this
}
```


--------------------------------

### Create optional catch-all route directory structure

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/from-create-react-app.mdx

Sets up the `app` directory structure with an optional catch-all route `[[...slug]]` to intercept all routes in the application.

```bash
app
 ┣ [[...slug]]
 ┃ ┗ page.tsx
 ┣ layout.tsx
```


--------------------------------

### Middleware function before proxy migration

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/codemods.mdx

Example middleware.ts file defining the middleware export before running middleware-to-proxy.

```ts
import { NextResponse } from 'next/server'

export function middleware() {
  return NextResponse.next()
}
```


--------------------------------

### Deprecated images.domains configuration in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Example of the deprecated `images.domains` configuration option.

```javascript
// image.domains is deprecated
module.exports = {
  images: {
    domains: ['example.com'],
  },
}
```


--------------------------------

### Upgrade to Next.js 14 using Bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-14.mdx

Installs Next.js 14, React 18, and the corresponding ESLint configuration using Bun. If using TypeScript, ensure `@types/react` and `@types/react-dom` are also upgraded to their latest versions.

```bash
bun add next@next-14 react@18 react-dom@18 && bun add eslint-config-next@next-14 -D
```


--------------------------------

### Opt Route Handler GET Methods into Caching

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-15.mdx

Set `dynamic = 'force-static'` in `app/api/route.js` to cache `GET` methods in Route Handlers, which are no longer cached by default in Next.js 15.

```javascript
export const dynamic = 'force-static'

export async function GET() {}
```


--------------------------------

### Update Next.js and React dependencies using Bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/app-router-migration.mdx

Installs the latest versions of next, react, and react-dom using Bun to update to Next.js 13. Requires Node.js v18.17 or higher.

```bash
bun add next@latest react@latest react-dom@latest
```


--------------------------------

### Creating a Route Handler GET request in App Router

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/app-router-migration.mdx

Defines a custom GET request handler using the Web Request API in the `app` directory, replacing traditional Pages Router API routes.

```ts
export async function GET(request: Request) {}
```

```js
export async function GET(request) {}
```


--------------------------------

### Static GET route handler using dynamic = 'force-static' (Before)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating-to-cache-components.mdx

Legacy pattern for opting a GET Route Handler into caching prior to Cache Components. Use export const dynamic = 'force-static' at the route module level.

```typescript
// Before
export const dynamic = 'force-static'

export async function GET() {
  const products = await db.query('SELECT * FROM products')
  return Response.json(products)
}
```

```javascript
// Before
export const dynamic = 'force-static'

export async function GET() {
  const products = await db.query('SELECT * FROM products')
  return Response.json(products)
}
```


--------------------------------

### Caching GET route handler data with use cache and cacheLife (After)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating-to-cache-components.mdx

Recommended pattern using Cache Components. The use cache directive cannot be applied directly to the GET export, so data access is moved into a cached helper function.

```typescript
// After
import { cacheLife } from 'next/cache'

export async function GET() {
  const products = await getProducts()
  return Response.json(products)
}

async function getProducts() {
  'use cache'
  cacheLife('hours')
  return db.query('SELECT * FROM products')
}
```

```javascript
// After
import { cacheLife } from 'next/cache'

export async function GET() {
  const products = await getProducts()
  return Response.json(products)
}

async function getProducts() {
  'use cache'
  cacheLife('hours')
  return db.query('SELECT * FROM products')
}
```


--------------------------------

### Configure experimental.dynamicIO (Legacy)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Legacy configuration using the removed `experimental.dynamicIO` flag in `next.config.js`.

```javascript
// Before: experimental.dynamicIO
module.exports = {
  experimental: {
    dynamicIO: true,
  },
}
```


--------------------------------

### Run next-request-geo-ip codemod

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/codemods.mdx

Installs `@vercel/functions` and replaces deprecated `geo` and `ip` properties on `NextRequest`.

```bash
npx @next/codemod@latest next-request-geo-ip .
```


--------------------------------

### Upgrade to Next.js 14 using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-14.mdx

Installs Next.js 14, React 18, and the corresponding ESLint configuration using npm. If using TypeScript, ensure `@types/react` and `@types/react-dom` are also upgraded to their latest versions.

```bash
npm i next@next-14 react@18 react-dom@18 && npm i eslint-config-next@next-14 -D
```


--------------------------------

### Example of cacheTag import after codemod

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/codemods.mdx

Resulting code with stabilized cacheTag import after running remove-unstable-prefix.

```ts
import { cacheTag } from 'next/cache'

cacheTag()
```


--------------------------------

### Example of unstable_cacheTag import before codemod

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/codemods.mdx

Original code importing unstable_cacheTag with an alias before running remove-unstable-prefix.

```ts
import { unstable_cacheTag as cacheTag } from 'next/cache'

cacheTag()
```


--------------------------------

### Configure experimental.useCache (Legacy)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Legacy configuration using the removed `experimental.useCache` flag in `next.config.js`.

```javascript
// Before: experimental.useCache
module.exports = {
  experimental: {
    useCache: true,
  },
}
```


--------------------------------

### Run Turbopack tracing with bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Executes Turbopack internal tracing using bunx against the generated profile binary.

```bash
bunx next internal trace .next-profiles/trace-turbopack.bin
```


--------------------------------

### Configuring custom Webpack in next.config.ts

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/from-create-react-app.mdx

Extends the Next.js Webpack configuration to handle custom webpack or Babel setups from CRA. Requires adding --webpack to your dev script.

```typescript
import { NextConfig } from 'next'

const nextConfig: NextConfig = {
  webpack: (config, { isServer }) => {
    // Modify the webpack config here
    return config
  },
}

export default nextConfig
```


--------------------------------

### Update Next.js and React dependencies using Yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/app-router-migration.mdx

Installs the latest versions of next, react, and react-dom using Yarn to update to Next.js 13. Requires Node.js v18.17 or higher.

```bash
yarn add next@latest react@latest react-dom@latest
```


--------------------------------

### Update Next.js and React dependencies using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/app-router-migration.mdx

Installs the latest versions of next, react, and react-dom using npm to update to Next.js 13. Requires Node.js v18.17 or higher.

```bash
npm install next@latest react@latest react-dom@latest
```


--------------------------------

### Update Next.js and React dependencies using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/app-router-migration.mdx

Installs the latest versions of next, react, and react-dom using pnpm to update to Next.js 13. Requires Node.js v18.17 or higher.

```bash
pnpm add next@latest react@latest react-dom@latest
```


--------------------------------

### Configuring package.json scripts with Turbopack flag (Next.js 15 and earlier)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Shows the previous approach where Turbopack required explicitly passing `--turbopack` or `--turbo` in `package.json` scripts.

```json
{
  "scripts": {
    "dev": "next dev --turbopack",
    "build": "next build --turbopack",
    "start": "next start"
  }
}
```


--------------------------------

### Upgrade ESLint configuration using Bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/app-router-migration.mdx

Installs the latest eslint-config-next package as a development dependency using Bun. You may need to restart the ESLint server in VS Code for changes to take effect.

```bash
bun add -D eslint-config-next@latest
```


--------------------------------

### Upgrade ESLint configuration using Yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/app-router-migration.mdx

Installs the latest eslint-config-next package as a development dependency using Yarn. You may need to restart the ESLint server in VS Code for changes to take effect.

```bash
yarn add -D eslint-config-next@latest
```


--------------------------------

### Upgrade ESLint configuration using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/app-router-migration.mdx

Installs the latest eslint-config-next package as a development dependency using npm. You may need to restart the ESLint server in VS Code for changes to take effect.

```bash
npm install -D eslint-config-next@latest
```


--------------------------------

### Upgrade ESLint configuration using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/app-router-migration.mdx

Installs the latest eslint-config-next package as a development dependency using pnpm. You may need to restart the ESLint server in VS Code for changes to take effect.

```bash
pnpm add -D eslint-config-next@latest
```


--------------------------------

### Run next-og-import codemod

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/codemods.mdx

Transforms imports from next/server to next/og for Dynamic OG Image Generation.

```bash
npx @next/codemod@latest next-og-import .
```


--------------------------------

### Upgrade to Next.js 14 using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-14.mdx

Installs Next.js 14, React 18, and the corresponding ESLint configuration using pnpm. If using TypeScript, ensure `@types/react` and `@types/react-dom` are also upgraded to their latest versions.

```bash
pnpm i next@next-14 react@18 react-dom@18 && pnpm i eslint-config-next@next-14 -D
```


--------------------------------

### Upgrade to Next.js 14 using Yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-14.mdx

Installs Next.js 14, React 18, and the corresponding ESLint configuration using Yarn. If using TypeScript, ensure `@types/react` and `@types/react-dom` are also upgraded to their latest versions.

```bash
yarn add next@next-14 react@18 react-dom@18 && yarn add eslint-config-next@next-14 -D
```


--------------------------------

### Run next-lint-to-eslint-cli codemod

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/codemods.mdx

Execute the codemod to migrate project linting from next lint to the standard ESLint CLI.

```bash
npx @next/codemod@canary next-lint-to-eslint-cli .
```


--------------------------------

### Create a Root Layout in Next.js App Router

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/app-router-migration.mdx

Defines the required root layout in the app directory containing html and body tags. Layouts must accept a children prop that gets populated with nested layouts or pages.

```tsx
export default function RootLayout({
  // Layouts must accept a children prop.
  // This will be populated with nested layouts or pages
  children,
}: {
  children: React.ReactNode
}) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  )
}
```

```jsx
export default function RootLayout({
  // Layouts must accept a children prop.
  // This will be populated with nested layouts or pages
  children,
}) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  )
}
```


--------------------------------

### Run cache-components-instant-false codemod

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/codemods.mdx

Adds 'export const instant = false' to page, layout, and default files that do not declare instant. Pass './src/app' if your project uses a src directory.

```bash
npx @next/codemod@canary cache-components-instant-false ./app
```


--------------------------------

### Configure remote image optimization with images.remotePatterns

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Use `images.remotePatterns` instead of `images.domains` for improved security when optimizing remote images.

```javascript
// Use image.remotePatterns instead
module.exports = {
  images: {
    remotePatterns: [
      {
        protocol: 'https',
        hostname: 'example.com',
      },
    ],
  },
}
```


--------------------------------

### Run next-image-experimental codemod

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/codemods.mdx

Migrates from next/legacy/image to next/image by adding inline styles and removing unused props like layout, objectFit, and lazyBoundary.

```bash
npx @next/codemod@latest next-image-experimental .
```


--------------------------------

### Run app-dir-runtime-config-experimental-edge codemod

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/codemods.mdx

Execute the App Router codemod to update runtime configuration from experimental-edge to edge.

```bash
npx @next/codemod@latest app-dir-runtime-config-experimental-edge .
```


--------------------------------

### Create initial RootLayout in app/layout

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/from-vite.mdx

Defines the initial Next.js root layout replicating the HTML structure from Vite's index.html. Wrap the children inside the root container within the body element.

```tsx
export default function RootLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return (
    <html lang="en">
      <head>
        <meta charSet="UTF-8" />
        <link rel="icon" type="image/svg+xml" href="/icon.svg" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>My App</title>
        <meta name="description" content="My App is a..." />
      </head>
      <body>
        <div id="root">{children}</div>
      </body>
    </html>
  )
}
```

```jsx
export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <head>
        <meta charSet="UTF-8" />
        <link rel="icon" type="image/svg+xml" href="/icon.svg" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>My App</title>
        <meta name="description" content="My App is a..." />
      </head>
      <body>
        <div id="root">{children}</div>
      </body>
    </html>
  )
}
```


--------------------------------

### Migrate experimental.serverComponentsExternalPackages to serverExternalPackages

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-15.mdx

Update next.config.js to replace experimental.serverComponentsExternalPackages with the stabilized serverExternalPackages configuration.

```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  // Before
  experimental: {
    serverComponentsExternalPackages: ['package-name'],
  },

  // After
  serverExternalPackages: ['package-name'],
}

module.exports = nextConfig
```


--------------------------------

### Migrate from serverRuntimeConfig and publicRuntimeConfig (Next.js 15 pattern)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Shows the legacy Next.js 15 runtime configuration pattern using next/config and next.config.js, which has been removed in Next.js 16.

```js
module.exports = {
  serverRuntimeConfig: {
    dbUrl: process.env.DATABASE_URL,
  },
  publicRuntimeConfig: {
    apiUrl: '/api',
  },
}
```

```tsx
import getConfig from 'next/config'

export default function Page() {
  const { publicRuntimeConfig } = getConfig()
  return <p>API URL: {publicRuntimeConfig.apiUrl}</p>
}
```


--------------------------------

### Run Turbopack tracing with npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Executes Turbopack internal tracing using npx against the generated profile binary.

```bash
npx next internal trace .next-profiles/trace-turbopack.bin
```


--------------------------------

### Import font from @next/font/google (Before transform)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/codemods.mdx

Font import using the legacy @next/font package before migration.

```js
import { Inter } from '@next/font/google'
```


--------------------------------

### Read environment variables dynamically at runtime with connection()

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Calls connection() from next/server prior to reading process.env to ensure variables are evaluated at runtime rather than bundled at build time.

```tsx
import { connection } from 'next/server'

export default async function Page() {
  await connection()
  const config = process.env.RUNTIME_CONFIG
  return <p>{config}</p>
}
```


--------------------------------

### Run cra-to-next codemod

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/codemods.mdx

Migrates a Create React App project to Next.js by setting up Pages Router and initial client-side rendering.

```bash
npx @next/codemod cra-to-next
```


--------------------------------

### Configuring experimental.turbopack in next.config.ts (Next.js 15)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Shows the legacy Next.js 15 location for Turbopack options inside `experimental.turbopack` in `next.config.ts`.

```ts
import type { NextConfig } from 'next'

// Next.js 15 - experimental.turbopack
const nextConfig: NextConfig = {
  experimental: {
    turbopack: {
      // options
    },
  },
}

export default nextConfig
```


--------------------------------

### Run Turbopack tracing with pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Executes Turbopack internal tracing using pnpm against the generated profile binary.

```bash
pnpm next internal trace .next-profiles/trace-turbopack.bin
```


--------------------------------

### Configuring ISR with fetch in App Router

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/app-router-migration.mdx

Demonstrates data fetching in the `app` directory with `fetch()`, using the `next.revalidate` option to cache the request for a specific number of seconds.

```jsx
// `app` directory

async function getPosts() {
  const res = await fetch(`https://.../posts`, { next: { revalidate: 60 } })
  const data = await res.json()

  return data.posts
}

export default async function PostList() {
  const posts = await getPosts()

  return posts.map((post) => <div>{post.name}</div>)
}
```


--------------------------------

### Fetch Data in a Server Component Page

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/app-router-migration.mdx

Create an async Server Component page in the app directory to fetch data directly with fetch. The retrieved data is then forwarded as props to the imported Client Component.

```tsx
// Import your Client Component
import HomePage from './home-page'

async function getPosts() {
  const res = await fetch('https://...')
  const posts = await res.json()
  return posts
}

export default async function Page() {
  // Fetch data directly in a Server Component
  const recentPosts = await getPosts()
  // Forward fetched data to your Client Component
  return <HomePage recentPosts={recentPosts} />
}
```

```jsx
// Import your Client Component
import HomePage from './home-page'

async function getPosts() {
  const res = await fetch('https://...')
  const posts = await res.json()
  return posts
}

export default async function Page() {
  // Fetch data directly in a Server Component
  const recentPosts = await getPosts()
  // Forward fetched data to your Client Component
  return <HomePage recentPosts={recentPosts} />
}
```


--------------------------------

### Import ImageResponse from next/og (After transform)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/codemods.mdx

Target syntax where ImageResponse is imported from next/og after transformation.

```js
import { ImageResponse } from 'next/og'
```


--------------------------------

### Define initial entrypoint page with generateStaticParams

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/from-create-react-app.mdx

Configures `generateStaticParams` to return a single empty slug route (`/`), mapping all routes to this static Server Component.

```tsx
export function generateStaticParams() {
  return [{ slug: [''] }]
}

export default function Page() {
  return '...' // We'll update this
}
```

```jsx
export function generateStaticParams() {
  return [{ slug: [''] }]
}

export default function Page() {
  return '...' // We'll update this
}
```


--------------------------------

### Run Turbopack tracing with yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Executes Turbopack internal tracing using yarn against the generated profile binary.

```bash
yarn next internal trace .next-profiles/trace-turbopack.bin
```


--------------------------------

### Run next-async-request-api codemod

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Runs the codemod to migrate legacy synchronous params, searchParams, cookies(), headers(), or draftMode() usage to async APIs.

```bash
npx @next/codemod@canary next-async-request-api .
```


--------------------------------

### Run cache-components-instant-false codemod

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating-to-cache-components.mdx

Applies the `cache-components-instant-false` codemod to add `instant = false` across all page, layout, and default files that do not already declare it. For projects using a `src/` directory, specify `./src/app` instead.

```bash
npx @next/codemod@canary cache-components-instant-false ./app

```


--------------------------------

### Allow local IP image optimization with dangerouslyAllowLocalIP

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Enable `images.dangerouslyAllowLocalIP` only for private networks when hosting Next.js in a VPC with split-horizon DNS to prevent 400 Bad Request errors.

```typescript
import type { NextConfig } from 'next'

const nextConfig: NextConfig = {
  images: {
    dangerouslyAllowLocalIP: true, // Only for private networks
  },
}

export default nextConfig
```

```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  images: {
    dangerouslyAllowLocalIP: true, // Only for private networks
  },
}

module.exports = nextConfig
```


--------------------------------

### Prerender pages at build time with getStaticProps

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/app-router-migration.mdx

Fetches data at build time in the Pages directory and passes it down as props to the page component for static site generation.

```jsx
// `pages` directory

export async function getStaticProps() {
  const res = await fetch(`https://...`)
  const projects = await res.json()

  return { props: { projects } }
}

export default function Index({ projects }) {
  return projects.map((project) => <div>{project.name}</div>)
}
```


--------------------------------

### Run metadata-to-viewport-export codemod

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/codemods.mdx

Migrates viewport-related metadata properties to a dedicated viewport export.

```bash
npx @next/codemod@latest metadata-to-viewport-export .
```


--------------------------------

### Import next/legacy/image and next/image (After transform)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/codemods.mdx

Renamed Next.js 13 image imports in pages/index.js after running next-image-to-legacy-image.

```jsx
// 'next/image' becomes 'next/legacy/image'
import Image1 from 'next/legacy/image'
// 'next/future/image' becomes 'next/image'
import Image2 from 'next/image'

export default function Home() {
  return (
    <div>
      <Image1 src="/test.jpg" width="200" height="300" />
      <Image2 src="/test.png" width="500" height="400" />
    </div>
  )
}
```


--------------------------------

### Configure images.localPatterns for search query strings

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/upgrading/version-16.mdx

Add localPatterns with search query parameters to next.config to allow query strings on local images and protect against enumeration attacks.

```typescript
import type { NextConfig } from 'next'

const nextConfig: NextConfig = {
  images: {
    localPatterns: [
      {
        pathname: '/assets/**',
        search: '?v=1',
      },
    ],
  },
}

export default nextConfig
```

```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  images: {
    localPatterns: [
      {
        pathname: '/assets/**',
        search: '?v=1',
      },
    ],
  },
}

module.exports = nextConfig
```


--------------------------------

### Configure SPA export in next.config.mjs

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/from-vite.mdx

Sets output to 'export' for a client-side SPA and directs build files to the './dist' directory.

```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  output: 'export', // Outputs a Single-Page Application (SPA).
  distDir: './dist', // Changes the build output directory to `./dist/`.
}

export default nextConfig
```


--------------------------------

### Create root layout component in app directory

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/02-guides/migrating/from-vite.mdx

Defines the required root layout Server Component wrapping application pages in Next.js App Router.

```tsx
export default function RootLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return '...'
}
```

```jsx
export default function RootLayout({ children }) {
  return '...'
}
```
