# Architecture & Community

Sourced snippets from the Next.js docs dump (10 entries).
Search this file for the topic at hand; treat snippets as patterns and
reconcile with the installed Next.js version before applying.

### Order documentation routes with two-digit numerical prefixes

Source: https://github.com/vercel/next.js/blob/canary/docs/04-community/01-contribution-guide.mdx

Demonstrates custom sequential ordering by prepending two-digit numbers (00-) to file names, useful for structured learning flows like the App Router getting started guide.

```txt
01-getting-started
├── 01-installation.mdx
├── 02-project-structure.mdx
├── 03-layouts-and-pages.mdx
└── ...
```


--------------------------------

### Minimum working example with Link component in app/page.tsx

Source: https://github.com/vercel/next.js/blob/canary/docs/04-community/01-contribution-guide.mdx

Provides a complete, runnable code example including both the import statement and component usage.

```tsx
import Link from 'next/link'

export default function Page() {
  return <Link href="/about">About</Link>
}
```


--------------------------------

### Configuring package manager variants for CLI commands in MDX

Source: https://github.com/vercel/next.js/blob/canary/docs/04-community/01-contribution-guide.mdx

Demonstrates using the package prop to display equivalent CLI commands across pnpm, npm, yarn, and bun.

```mdx
```bash package="pnpm"
pnpm create next-app
```

```bash package="npm"
npx create-next-app@latest
```

```bash package="yarn"
yarn create next-app
```

```bash package="bun"
bun create next-app
```
```


--------------------------------

### Organize documentation routes alphabetically

Source: https://github.com/vercel/next.js/blob/canary/docs/04-community/01-contribution-guide.mdx

Demonstrates file structure sorted alphabetically without numeric prefixes for individual files, suitable for reference sections like the functions API reference.

```txt
04-functions
├── after.mdx
├── cacheLife.mdx
├── cacheTag.mdx
└── ...
```


--------------------------------

### Configure experimental SWC plugins in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/03-architecture/nextjs-compiler.mdx

Configures SWC transformations to use experimental WASM plugins. Accepts an array of tuples with the plugin path (an npm package name or absolute path to the `.wasm` binary) and configuration options.

```javascript
module.exports = {
  experimental: {
    swcPlugins: [
      [
        'plugin',
        {
          ...pluginOptions,
        },
      ],
    ],
  },
}
```


--------------------------------

### Configure Emotion transform options in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/03-architecture/nextjs-compiler.mdx

Enable and configure Emotion support in next.config.js, including source maps, auto-labeling, label formatting, and custom import mappings.

```javascript

module.exports = {
  compiler: {
    emotion: boolean | {
      // default is true. It will be disabled when build type is production.
      sourceMap?: boolean,
      // default is 'dev-only'.
      autoLabel?: 'never' | 'dev-only' | 'always',
      // default is '[local]'.
      // Allowed values: `[local]` `[filename]` and `[dirname]`
      // This option only works when autoLabel is set to 'dev-only' or 'always'.
      // It allows you to define the format of the resulting label.
      // The format is defined via string where variable parts are enclosed in square brackets [].
      // For example labelFormat: "my-classname--[local]", where [local] will be replaced with the name of the variable the result is assigned to.
      labelFormat?: string,
      // default is undefined.
      // This option allows you to tell the compiler what imports it should
      // look at to determine what it should transform so if you re-export
      // Emotion's exports, you can still use transforms.
      importMap?: {
        [packageName: string]: {
          [exportName: string]: {
            canonicalImport?: [string, string],
            styledBaseImport?: [string, string],
          }
        }
      },
    },
  },
}
```


--------------------------------

### Configure Jest with next/jest in jest.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/03-architecture/nextjs-compiler.mdx

Sets up Jest transpilation with the Next.js Compiler. Passing custom configuration to next/jest enables automatic mocking, SWC transforms, and loading of environment variables.

```javascript
const nextJest = require('next/jest')

// Providing the path to your Next.js app which will enable loading next.config.js and .env files
const createJestConfig = nextJest({ dir: './' })

// Any custom config you want to pass to Jest
const customJestConfig = {
  setupFilesAfterEnv: ['<rootDir>/jest.setup.js'],
}

// createJestConfig is exported in this way to ensure that next/jest can load the Next.js configuration, which is async
module.exports = createJestConfig(customJestConfig)
```


--------------------------------

### Configure VSCode to preview MDX files in settings.json

Source: https://github.com/vercel/next.js/blob/canary/docs/04-community/01-contribution-guide.mdx

Associates .mdx files with the markdown language mode in VSCode user settings. Use this configuration to enable VSCode's built-in markdown previewer for documentation files.

```json
{
  "files.associations": {
    "*.mdx": "markdown"
  }
}
```


--------------------------------

### Linking TypeScript and JavaScript code blocks with switcher prop

Source: https://github.com/vercel/next.js/blob/canary/docs/04-community/01-contribution-guide.mdx

Demonstrates how to write consecutive TypeScript and JavaScript code blocks linked with the switcher attribute.

```mdx
```tsx filename="app/page.tsx" switcher

```

```jsx filename="app/page.js" switcher

```
```


--------------------------------

### Statically replace build variables using define and defineServer in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/03-architecture/nextjs-compiler.mdx

Use compiler.define to statically replace variables across all environments at build time, or compiler.defineServer to restrict replacements to server-side and edge code.

```javascript
module.exports = {
  compiler: {
    define: {
      MY_VARIABLE: 'my-string',
      'process.env.MY_ENV_VAR': 'my-env-var',
    },
    defineServer: {
      MY_SERVER_VARIABLE: 'my-server-var',
    },
  },
}
```
