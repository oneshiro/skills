# App Router — Getting Started

Sourced snippets from the Next.js docs dump (44 entries).
Search this file for the topic at hand; treat snippets as patterns and
reconcile with the installed Next.js version before applying.

### Create and run Next.js app with pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Initializes a new Next.js application named `my-app` and starts the development server using pnpm. The `--yes` flag automatically applies default setup configurations including TypeScript, Tailwind CSS, ESLint, App Router, and Turbopack.

```bash
pnpm create next-app@latest my-app --yes
cd my-app
pnpm dev
```


--------------------------------

### Install Next.js with Bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Installs the required Next.js, React, and React DOM packages using Bun.

```bash
bun add next@latest react@latest react-dom@latest
```


--------------------------------

### Install Next.js with npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Installs the required Next.js, React, and React DOM packages using npm.

```bash
npm i next@latest react@latest react-dom@latest
```


--------------------------------

### Create and run Next.js app with npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Initializes a new Next.js application named `my-app` and starts the development server using npm. The `--yes` flag skips interactive prompts using saved preferences or defaults.

```bash
npx create-next-app@latest my-app --yes
cd my-app
npm run dev
```


--------------------------------

### Install Next.js with Yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Installs the required Next.js, React, and React DOM packages using Yarn.

```bash
yarn add next@latest react@latest react-dom@latest
```


--------------------------------

### Install Next.js with pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Installs the required Next.js, React, and React DOM packages using pnpm.

```bash
pnpm i next@latest react@latest react-dom@latest
```


--------------------------------

### Create and run Next.js app with Bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Initializes a new Next.js application named `my-app` and starts the development server using Bun. The `--yes` flag bypasses CLI prompts and applies default settings.

```bash
bun create next-app@latest my-app --yes
cd my-app
bun dev
```


--------------------------------

### View default create-next-app prompts

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Displays the initial interactive prompts presented in the terminal on installation.

```txt
What is your project named? my-app
Would you like to use the recommended Next.js defaults?
    Yes, use recommended defaults - TypeScript, ESLint, No React Compiler, Tailwind CSS, No src/ directory, App Router, Cache Components, AGENTS.md
    No, reuse previous settings
    No, customize settings - Choose your own preferences
```


--------------------------------

### Install server-only package using bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/05-server-and-client-components.mdx

Installing server-only is optional in Next.js unless required by your linting rules to avoid extraneous dependency flags.

```bash
bun add server-only
```


--------------------------------

### Create and run Next.js app with Yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Initializes a new Next.js application named `my-app` and starts the development server using Yarn. The `--yes` flag skips prompts to quickly bootstrap with default configurations.

```bash
yarn create next-app@latest my-app --yes
cd my-app
yarn dev
```


--------------------------------

### Configure build and start scripts in package.json

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/17-deploying.mdx

Defines the required build and start scripts in package.json for building and running a Next.js application on a Node.js server.

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

### Install server-only package using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/05-server-and-client-components.mdx

Installing server-only is optional in Next.js unless required by your linting rules to avoid extraneous dependency flags.

```bash
pnpm add server-only
```


--------------------------------

### Install Tailwind CSS using bun in App Router

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/11-css.mdx

Installs Tailwind CSS and the `@tailwindcss/postcss` plugin as development dependencies using bun.

```bash
bun add -D tailwindcss @tailwindcss/postcss
```


--------------------------------

### Install server-only package using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/05-server-and-client-components.mdx

Installing server-only is optional in Next.js unless required by your linting rules to avoid extraneous dependency flags.

```bash
npm install server-only
```


--------------------------------

### Install server-only package using yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/05-server-and-client-components.mdx

Installing server-only is optional in Next.js unless required by your linting rules to avoid extraneous dependency flags.

```bash
yarn add server-only
```


--------------------------------

### Upgrade Next.js and React dependencies manually

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/18-upgrading.mdx

Manually install the latest versions of `next`, `react`, `react-dom`, and `eslint-config-next`.

```bash
pnpm i next@latest react@latest react-dom@latest eslint-config-next@latest
```

```bash
npm i next@latest react@latest react-dom@latest eslint-config-next@latest
```

```bash
yarn add next@latest react@latest react-dom@latest eslint-config-next@latest
```

```bash
bun add next@latest react@latest react-dom@latest eslint-config-next@latest
```


--------------------------------

### Install Tailwind CSS using yarn in App Router

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/11-css.mdx

Installs Tailwind CSS and the `@tailwindcss/postcss` plugin as development dependencies using yarn.

```bash
yarn add -D tailwindcss @tailwindcss/postcss
```


--------------------------------

### Install Tailwind CSS using npm in App Router

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/11-css.mdx

Installs Tailwind CSS and the `@tailwindcss/postcss` plugin as development dependencies using npm.

```bash
npm install -D tailwindcss @tailwindcss/postcss
```


--------------------------------

### Install Tailwind CSS using pnpm in App Router

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/11-css.mdx

Installs Tailwind CSS and the `@tailwindcss/postcss` plugin as development dependencies using pnpm.

```bash
pnpm add -D tailwindcss @tailwindcss/postcss
```


--------------------------------

### Configure development and build scripts in package.json

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Defines scripts in package.json for starting development with Turbopack, building for production, running the production server, and linting.

```json
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "eslint",
    "lint:fix": "eslint --fix"
  }
}
```


--------------------------------

### Upgrade to the Next.js canary version

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/18-upgrading.mdx

Install the canary release of Next.js after verifying that your application is working on the latest stable version.

```bash
pnpm add next@canary
```

```bash
npm i next@canary
```

```bash
yarn add next@canary
```

```bash
bun add next@canary
```


--------------------------------

### Create a Next.js app using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Runs create-next-app with npx to set up a new Next.js project automatically.

```bash
npx create-next-app@latest
```


--------------------------------

### View customize settings prompts

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Displays the detailed configuration options presented in the terminal when choosing to customize settings.

```txt
Would you like to use TypeScript? No / Yes
Which linter would you like to use? ESLint / Biome / None
Would you like to use React Compiler? No / Yes
Would you like to use Tailwind CSS? No / Yes
Would you like your code inside a `src/` directory? No / Yes
Would you like to use App Router? (recommended) No / Yes
Would you like to use Cache Components? No / Yes
Would you like to customize the import alias (`@/*` by default)? No / Yes
What import alias would you like configured? @/*
Would you like to include AGENTS.md to guide coding agents to write up-to-date Next.js code? No / Yes
```


--------------------------------

### Create a Next.js app using Bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Runs create-next-app with Bun to set up a new Next.js project automatically.

```bash
bun create next-app
```


--------------------------------

### Create a Next.js app using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Runs create-next-app with pnpm to set up a new Next.js project automatically.

```bash
pnpm create next-app
```


--------------------------------

### Define a GET Route Handler in route.ts or route.js

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/15-route-handlers.mdx

Defines a custom request handler for GET requests inside a route file in the app directory. Route Handlers cannot exist at the same route segment level as a page.js file.

```ts
export async function GET(request: Request) {}
```

```js
export async function GET(request) {}
```


--------------------------------

### Configure baseUrl in tsconfig.json or jsconfig.json

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Sets the baseUrl configuration option to enable absolute imports starting from the specified root directory.

```json
{
  "compilerOptions": {
    "baseUrl": "src/"
  }
}
```


--------------------------------

### Upgrade Next.js using Bun

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Run `bunx next upgrade` to update your Next.js project using Bun.

```bash
bunx next upgrade
```


--------------------------------

### Create a blog page in app/blog/page

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/03-layouts-and-pages.mdx

Defines UI for the `/blog` route segment by fetching and rendering a list of posts. Place this file inside the `app/blog` directory to make the route publicly accessible.

```tsx
// Dummy imports
import { getPosts } from '@/lib/posts'
import { Post } from '@/ui/post'

export default async function Page() {
  const posts = await getPosts()

  return (
    <ul>
      {posts.map((post) => (
        <Post key={post.id} post={post} />
      ))}
    </ul>
  )
}
```

```jsx
// Dummy imports
import { getPosts } from '@/lib/posts'
import { Post } from '@/ui/post'

export default async function Page() {
  const posts = await getPosts()

  return (
    <ul>
      {posts.map((post) => (
        <Post key={post.id} post={post} />
      ))}
    </ul>
  )
}
```


--------------------------------

### Reference static assets from public folder in app/page

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Loads static assets stored in the public folder by referencing them starting from the base URL path (/).

```tsx
import Image from 'next/image'

export default function Page() {
  return <Image src="/profile.png" alt="Profile" width={100} height={100} />
}
```

```jsx
import Image from 'next/image'

export default function Page() {
  return <Image src="/profile.png" alt="Profile" width={100} height={100} />
}
```


--------------------------------

### Upgrade Next.js using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Run `npx next upgrade` to upgrade Next.js to the latest release.

```bash
npx next upgrade
```


--------------------------------

### Create a Client Component context provider in app/theme-provider

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/05-server-and-client-components.mdx

Create a Client Component with `'use client'` to initialize React Context since context is not supported directly in Server Components. Accept `children` so downstream components can be wrapped.

```tsx
'use client'

import { createContext } from 'react'

export const ThemeContext = createContext({})

export default function ThemeProvider({
  children,
}: {
  children: React.ReactNode
}) {
  return <ThemeContext.Provider value="dark">{children}</ThemeContext.Provider>
}
```

```jsx
'use client'

import { createContext } from 'react'

export const ThemeContext = createContext({})

export default function ThemeProvider({ children }) {
  return <ThemeContext.Provider value="dark">{children}</ThemeContext.Provider>
}
```


--------------------------------

### Configure ESLint scripts in package.json

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Defines scripts to run ESLint directly via npm. Note that starting with Next.js 16, next build no longer runs the linter automatically.

```json
{
  "scripts": {
    "lint": "eslint",
    "lint:fix": "eslint --fix"
  }
}
```


--------------------------------

### Create a Next.js app using Yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Runs create-next-app with Yarn to set up a new Next.js project automatically.

```bash
yarn create next-app
```


--------------------------------

### Upgrade Next.js using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Run `pnpm next upgrade` to update Next.js to the latest version and refresh the bundled documentation.

```bash
pnpm next upgrade
```


--------------------------------

### Create home page in app/page

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Defines the root home page component rendered when visiting the root path (/).

```tsx
export default function Page() {
  return <h1>Hello, Next.js!</h1>
}
```

```jsx
export default function Page() {
  return <h1>Hello, Next.js!</h1>
}
```


--------------------------------

### Configure module path aliases with paths and baseUrl

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Maps module path aliases using the paths option relative to the baseUrl configuration.

```json
{
  "compilerOptions": {
    "baseUrl": "src/",
    "paths": {
      "@/styles/*": ["styles/*"],
      "@/components/*": ["components/*"]
    }
  }
}
```


--------------------------------

### Upgrade Next.js using a coding agent

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/18-upgrading.mdx

Execute the upgrade command with the `--agent=latest` flag to have a coding agent perform and verify the upgrade process.

```bash
npx next@canary upgrade --agent=latest
```


--------------------------------

### Upgrade Next.js to the latest version

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/18-upgrading.mdx

Run the `upgrade` command with your preferred package manager to update Next.js to the latest version.

```bash
pnpm next upgrade
```

```bash
npx next upgrade
```

```bash
yarn next upgrade
```

```bash
bunx next upgrade
```


--------------------------------

### Import modules using path aliases vs relative paths

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Demonstrates replacing deeply nested relative import paths with an absolute path alias.

```jsx
// Before
import { Button } from '../../../components/button'

// After
import { Button } from '@/components/button'
```


--------------------------------

### Wrap children with a context provider in app/layout

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/05-server-and-client-components.mdx

Import and render the context provider directly inside a Server Component layout to make context available across all Client Components. Render providers as deep as possible by wrapping `{children}` instead of the `<html>` tag to optimize static rendering.

```tsx
import ThemeProvider from './theme-provider'

export default function RootLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return (
    <html>
      <body>
        <ThemeProvider>{children}</ThemeProvider>
      </body>
    </html>
  )
}
```

```jsx
import ThemeProvider from './theme-provider'

export default function RootLayout({ children }) {
  return (
    <html>
      <body>
        <ThemeProvider>{children}</ThemeProvider>
      </body>
    </html>
  )
}
```


--------------------------------

### Import Global CSS in App Router Root Layout (JavaScript)

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/11-css.mdx

Apply global styles across every route by importing `app/global.css` inside the root layout component.

```css
body {
  padding: 20px 20px 60px;
  max-width: 680px;
  margin: 0 auto;
}
```

```jsx
// These styles apply to every route in the application
import './global.css'

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  )
}
```


--------------------------------

### Prompt coding agent to set up custom editor labels

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Instruct an AI coding agent to configure custom editor tab labels in .vscode/settings.json based on Next.js documentation.

```prompt
Set up custom editor labels so my Next.js App Router files are easy to tell apart. Read https://nextjs.org/docs/app/getting-started/installation#set-up-your-editor and add the workbench.editor.customLabels.patterns config shown there to my .vscode/settings.json, creating the file if it doesn't exist. Adjust the labels to taste. If I use a different editor, apply the equivalent setting or tell me it's automatic, and leave my other settings untouched.
```


--------------------------------

### Create root layout in app/layout

Source: https://github.com/vercel/next.js/blob/canary/docs/01-app/01-getting-started/01-installation.mdx

Defines the required root layout file containing the html and body tags. If omitted, Next.js will automatically create this file during next dev.

```tsx
export default function RootLayout({
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
export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  )
}
```
