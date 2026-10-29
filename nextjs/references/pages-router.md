# Pages Router

Sourced snippets from the Next.js docs dump (40 entries).
Search this file for the topic at hand; treat snippets as patterns and
reconcile with the installed Next.js version before applying.

### Set port using PORT environment variable

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/upgrading/version-11.mdx

Runs next start on a custom port configured via the PORT environment variable.

```bash
PORT=4000 next start
```


--------------------------------

### Upgrade to Next.js 13 using Bun

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/upgrading/version-13.mdx

Installs Next.js 13 along with the latest versions of React, React DOM, and eslint-config-next using Bun.

```bash
bun add next@13 react@latest react-dom@latest eslint-config-next@13
```


--------------------------------

### Upgrade to Next.js 13 using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/upgrading/version-13.mdx

Installs Next.js 13 along with the latest versions of React, React DOM, and eslint-config-next using npm.

```bash
npm i next@13 react@latest react-dom@latest eslint-config-next@13
```


--------------------------------

### Upgrade to Next.js 13 using pnpm

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/upgrading/version-13.mdx

Installs Next.js 13 along with the latest versions of React, React DOM, and eslint-config-next using pnpm.

```bash
pnpm i next@13 react@latest react-dom@latest eslint-config-next@13
```


--------------------------------

### Upgrade to Next.js 13 using Yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/upgrading/version-13.mdx

Installs Next.js 13 along with the latest versions of React, React DOM, and eslint-config-next using Yarn.

```bash
yarn add next@13 react@latest react-dom@latest eslint-config-next@13
```


--------------------------------

### Upgrade to Next.js 12 using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/upgrading/version-12.mdx

Installs Next.js 12, React 17, React DOM 17, and eslint-config-next 12 using npm. If using TypeScript, also upgrade @types/react and @types/react-dom to corresponding versions.

```bash
npm i next@12 react@17 react-dom@17 eslint-config-next@12
```


--------------------------------

### Upgrade React to the minimum supported version

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/upgrading/version-12.mdx

Installs the latest React and React DOM packages to satisfy the minimum requirement of React 17.0.2 for Next.js 12.

```bash
npm install react@latest react-dom@latest

yarn add react@latest react-dom@latest

pnpm update react@latest react-dom@latest

bun add react@latest react-dom@latest
```


--------------------------------

### Upgrade to Next.js 10 using Bun

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/upgrading/version-10.mdx

Installs Next.js version 10 in your project using Bun. If using TypeScript, also upgrade @types/react and @types/react-dom to corresponding versions.

```bash
bun add next@10
```


--------------------------------

### Configure default PostCSS plugins in postcss.config.json

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/post-css.mdx

Create a `postcss.config.json` file in the project root to customize PostCSS plugins. Custom configuration disables Next.js's default behavior, requiring plugins and features to be manually configured and installed.

```json
{
  "plugins": [
    "postcss-flexbugs-fixes",
    [
      "postcss-preset-env",
      {
        "autoprefixer": {
          "flexbox": "no-2009"
        },
        "stage": 3,
        "features": {
          "custom-properties": false
        }
      }
    ]
  ]
}
```


--------------------------------

### Configure global unoptimized setting in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/04-api-reference/01-components/image-legacy.mdx

Enables unoptimized behavior across all images application-wide via next.config.js starting from Next.js 12.3.0.

```javascript
module.exports = {
  images: {
    unoptimized: true,
  },
}
```


--------------------------------

### Load multiple modules using deprecated next/dynamic syntax (Before)

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/upgrading/version-9.mdx

Demonstrates the deprecated syntax where next/dynamic loaded multiple modules at once using modules and render properties.

```jsx
import dynamic from 'next/dynamic'

const HelloBundle = dynamic({
  modules: () => {
    const components = {
      Hello1: () => import('../components/hello1').then((m) => m.default),
      Hello2: () => import('../components/hello2').then((m) => m.default),
    }

    return components
  },
  render: (props, { Hello1, Hello2 }) => (
    <div>
      <h1>{props.title}</h1>
      <Hello1 />
      <Hello2 />
    </div>
  ),
})

function DynamicBundle() {
  return <HelloBundle title="Dynamic Bundle" />
}

export default DynamicBundle
```


--------------------------------

### Upgrade to Next.js 10 using Yarn

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/upgrading/version-10.mdx

Installs Next.js version 10 in your project using Yarn. If using TypeScript, also upgrade @types/react and @types/react-dom to corresponding versions.

```bash
yarn add next@10
```


--------------------------------

### Upgrade to Next.js 10 using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/upgrading/version-10.mdx

Installs Next.js version 10 in your project using npm. If using TypeScript, also upgrade @types/react and @types/react-dom to corresponding versions.

```bash
npm i next@10
```


--------------------------------

### Handle form submission errors with React state

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/forms.mdx

Manage loading and error states in a React component during form submission, clearing previous errors when a new request starts.

```tsx
import React, { useState, SubmitEvent } from 'react'

export default function Page() {
  const [isLoading, setIsLoading] = useState<boolean>(false)
  const [error, setError] = useState<string | null>(null)

  async function onSubmit(event: SubmitEvent<HTMLFormElement>) {
    event.preventDefault()
    setIsLoading(true)
    setError(null) // Clear previous errors when a new request starts

    try {
      const formData = new FormData(event.currentTarget)
      const response = await fetch('/api/submit', {
        method: 'POST',
        body: formData,
      })

      if (!response.ok) {
        throw new Error('Failed to submit the data. Please try again.')
      }

      // Handle response if necessary
      const data = await response.json()
      // ...
    } catch (error) {
      // Capture the error message to display to the user
      setError(error.message)
      console.error(error)
    } finally {
      setIsLoading(false)
    }
  }

  return (
    <div>
      {error && <div style={{ color: 'red' }}>{error}</div>}
      <form onSubmit={onSubmit}>
        <input type=
```


--------------------------------

### Enable AVIF and WebP formats in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/04-api-reference/01-components/image-legacy.mdx

Configures both AVIF and WebP formats, prioritizing AVIF for supported browsers and falling back to WebP.

```javascript
module.exports = {
  images: {
    formats: ['image/avif', 'image/webp'],
  },
}
```


--------------------------------

### Fetch data on the client using SWR in pages/index.js

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/03-building-your-application/02-rendering/05-client-side-rendering.mdx

Demonstrates client-side data fetching using the SWR library with error and loading state handling. Using a data-fetching library is recommended over useEffect for caching, performance, and optimistic updates.

```jsx
import useSWR from 'swr'

export function Page() {
  const { data, error, isLoading } = useSWR(
    'https://api.example.com/data',
    fetcher
  )

  if (error) return <p>Failed to load.</p>
  if (isLoading) return <p>Loading...</p>

  return <p>Your Data: {data}</p>
}
```


--------------------------------

### Upgrade to Next.js 12 using Bun

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/upgrading/version-12.mdx

Adds Next.js 12, React 17, React DOM 17, and eslint-config-next 12 dependencies using Bun.

```bash
bun add next@12 react@17 react-dom@17 eslint-config-next@12
```


--------------------------------

### Implement client-side data fetching with useEffect in pages/index.js

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/03-building-your-application/02-rendering/05-client-side-rendering.mdx

Fetches data on the client using React's useEffect hook and manages state with useState. The component starts by rendering a loading message until data is retrieved and state is updated.

```jsx
import React, { useState, useEffect } from 'react'

export function Page() {
  const [data, setData] = useState(null)

  useEffect(() => {
    const fetchData = async () => {
      const response = await fetch('https://api.example.com/data')
      if (!response.ok) {
        throw new Error(`HTTP error! status: ${response.status}`)
      }
      const result = await response.json()
      setData(result)
    }

    fetchData().catch((e) => {
      // handle the error as needed
      console.error('An error occurred while fetching the data: ', e)
    })
  }, [])

  return <p>{data ? `Your data: ${data}` : 'Loading...'}</p>
}
```


--------------------------------

### Prerender dynamic pages with fallback: false

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/04-api-reference/03-functions/get-static-paths.mdx

Builds only the paths returned by getStaticPaths and serves a 404 page for any unreturned paths. Fetches external data at build time inside pages/posts/[id].js.

```jsx
function Post({ post }) {
  // Render post...
}

// This function gets called at build time
export async function getStaticPaths() {
  // Call an external API endpoint to get posts
  const res = await fetch('https://.../posts')
  const posts = await res.json()

  // Get the paths we want to prerender based on posts
  const paths = posts.map((post) => ({
    params: { id: post.id },
  }))

  // We'll prerender only these paths at build time.
  // { fallback: false } means other routes should 404.
  return { paths, fallback: false }
}

// This also gets called at build time
export async function getStaticProps({ params }) {
  // params contains the post `id`.
  // If the route is like /posts/1, then params.id is 1
  const res = await fetch(`https://.../posts/${params.id}`)
  const post = await res.json()

  // Pass post data to the page via props
  return { props: { post } }
}

export default Post
```


--------------------------------

### View build output for statically optimized page

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/03-building-your-application/02-rendering/04-automatic-static-optimization.mdx

Next.js emits a static HTML file during `next build` when a page contains no blocking data requirements.

```bash
.next/server/pages/about.html
```


--------------------------------

### Read files in getStaticProps with process.cwd()

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/04-api-reference/03-functions/get-static-props.mdx

Use process.cwd() to construct full filesystem paths when reading files in getStaticProps. Do not use __dirname since Next.js compiles code into a separate directory.

```jsx
import { promises as fs } from 'fs'
import path from 'path'

// posts will be populated at build time by getStaticProps()
function Blog({ posts }) {
  return (
    <ul>
      {posts.map((post) => (
        <li>
          <h3>{post.filename}</h3>
          <p>{post.content}</p>
        </li>
      ))}
    </ul>
  )
}

// This function gets called at build time on server-side.
// It won't be called on client-side, so you can even do
// direct database queries.
export async function getStaticProps() {
  const postsDirectory = path.join(process.cwd(), 'posts')
  const filenames = await fs.readdir(postsDirectory)

  const posts = filenames.map(async (filename) => {
    const filePath = path.join(postsDirectory, filename)
    const fileContents = await fs.readFile(filePath, 'utf8')

    // Generally you would parse/transform the contents
    // For example you can transform markdown to HTML here

    return {
      filename,
      content: fileContents,
    }
  })
  // By returning { props: { posts } }, the Blog component
  // will receive `posts` as a prop at build time
  return {
    props: {
      posts: await Promise.all(posts),
    },
  }
}

export default Blog
```


--------------------------------

### router.push(url, as, options)

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/04-api-reference/03-functions/use-router.mdx

Handles client-side transitions when next/link is not sufficient. Supports navigating to predefined and dynamic routes with options for shallow routing, scroll behavior, and locale management.

```APIDOC
## router.push(url, as, options)

### Description
Handles client-side transitions, useful for cases where `next/link` is not enough.

### Parameters
- **url** (`UrlObject | String`) - Required - The URL to navigate to.
- **as** (`UrlObject | String`) - Optional - Decorator for the path that will be shown in the browser URL bar.
- **options** (`Object`) - Optional - Configuration object with the following options:
  - **scroll** (`Boolean`) - Optional - Controls scrolling to the top of the page after navigation. Defaults to `true`.
  - **shallow** (`Boolean`) - Optional - Update the path of the current page without rerunning `getStaticProps`, `getServerSideProps` or `getInitialProps`. Defaults to `false`.
  - **locale** (`String`) - Optional - Indicates locale of the new page.

### Usage Examples

#### Predefined Route
```jsx
import { useRouter } from 'next/router'

export default function Page() {
  const router = useRouter()

  return (
    <button type="button" onClick={() => router.push('/about')}>
      Click me
    </button>
  )
}
```

#### Dynamic Route
```jsx
import { useRouter } from 'next/router'

export default function Page() {
  const router = useRouter()

  return (
    <button type="button" onClick={() => router.push('/post/abc')}>
      Click me
    </button>
  )
}
```
```


--------------------------------

### Upgrade Next.js and React using bun

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/upgrading/version-11.mdx

Upgrades Next.js and React to version 11 and 17 using Bun.

```bash
bun add next@11 react@17 react-dom@17
```


--------------------------------

### Configure default WebP format in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/04-api-reference/01-components/image-legacy.mdx

Sets the default acceptable image format to WebP for automatic detection via the request Accept header.

```javascript
module.exports = {
  images: {
    formats: ['image/webp'],
  },
}
```


--------------------------------

### View build output for server-side rendered page

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/03-building-your-application/02-rendering/04-automatic-static-optimization.mdx

Adding `getServerSideProps` to a page switches it to per-request server-side rendering, outputting a JavaScript file instead of HTML.

```bash
.next/server/pages/about.js
```


--------------------------------

### Create a custom App component in pages/_app

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/03-building-your-application/01-routing/05-custom-app.mdx

Override the default App component to manage page initialization and persist shared layouts. Restart the development server after adding `pages/_app` if the file did not previously exist.

```tsx
import type { AppProps } from 'next/app'

export default function MyApp({ Component, pageProps }: AppProps) {
  return <Component {...pageProps} />
}
```

```jsx
export default function MyApp({ Component, pageProps }) {
  return <Component {...pageProps} />
}
```


--------------------------------

### Supporting both app and pages directories with next/compat/router

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/04-api-reference/03-functions/use-router.mdx

Enables a component to function in both app and pages directories by checking router.isReady before reading searchParams. In app/, searchParams is ready immediately, whereas in pages/ it becomes available once the router is ready.

```jsx
import { useEffect } from 'react'
import { useRouter } from 'next/compat/router'
import { useSearchParams } from 'next/navigation'
const MyComponent = () => {
  const router = useRouter() // may be null or a NextRouter instance
  const searchParams = useSearchParams()
  useEffect(() => {
    if (router && !router.isReady) {
      return
    }
    // In `app/`, searchParams will be ready immediately with the values, in
    // `pages/` it will be available after the router is ready.
    const search = searchParams.get('search')
    // ...
  }, [router, searchParams])
  // ...
}
```


--------------------------------

### Upgrade Next.js and React using npm

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/upgrading/version-11.mdx

Upgrades Next.js and React to version 11 and 17 using npm.

```bash
npm i next@11 react@17 react-dom@17
```


--------------------------------

### Define base .babelrc configuration

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/babel.mdx

Defines the base .babelrc configuration file at the root of the project containing the required next/babel preset.

```json
{
  "presets": ["next/babel"],
  "plugins": []
}
```


--------------------------------

### Construct custom preview URL format for Headless CMS

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/preview-mode.mdx

Format for configuring custom preview URLs in a headless CMS using secret token and page slug parameters.

```bash
https://<your-site>/api/preview?secret=<token>&slug=<path>
```


--------------------------------

### Configure remotePatterns with hostname wildcard in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/04-api-reference/01-components/image-legacy.mdx

Allows external images from matching wildcard subdomains using the ** prefix pattern in the hostname property.

```javascript
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

### Create a page component in pages/about.js

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/03-building-your-application/01-routing/01-pages-and-layouts.mdx

Export a default React component from a file in the pages directory to make it accessible as a route at /about.

```jsx
export default function About() {
  return <div>About</div>
}
```


--------------------------------

### Using useRouter from next/router in pages directory

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/04-api-reference/03-functions/use-router.mdx

Standard router usage in the pages directory. Direct destructuring will throw an error if switched directly to next/compat/router because next/compat/router can return null.

```jsx
import { useRouter } from 'next/router'
const MyComponent = () => {
  const { isReady, query } = useRouter()
  // ...
}
```


--------------------------------

### Configure default minimumCacheTTL in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/04-api-reference/01-components/image-legacy.mdx

Sets or shows the default 4-hour Time to Live (TTL) in seconds for cached optimized images when no custom configuration is provided.

```javascript
module.exports = {
  images: {
    minimumCacheTTL: 14400, // 4 hours
  },
}
```


--------------------------------

### Configure Domain Routing in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/internationalization.mdx

Maps specific domains and subdomains to default and redirected locales. Subdomains must be included explicitly in the domain value to match.

```javascript
module.exports = {
  i18n: {
    locales: ['en-US', 'fr', 'nl-NL', 'nl-BE'],
    defaultLocale: 'en-US',

    domains: [
      {
        // Note: subdomains must be included in the domain value to be matched
        // e.g. www.example.com should be used if that is the expected hostname
        domain: 'example.com',
        defaultLocale: 'en-US',
      },
      {
        domain: 'example.fr',
        defaultLocale: 'fr',
      },
      {
        domain: 'example.nl',
        defaultLocale: 'nl-NL',
        // specify other locales that should be redirected
        // to this domain
        locales: ['nl-BE'],
      },
    ],
  },
}
```


--------------------------------

### Enable CSS Grid layout for IE11 in postcss.config.json

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/post-css.mdx

Configure PostCSS plugins across the entire project to enable IE11 support for CSS Grid Layout using autoprefixer grid autoplace.

```json
{
  "plugins": [
    "postcss-flexbugs-fixes",
    [
      "postcss-preset-env",
      {
        "autoprefixer": {
          "flexbox": "no-2009",
          "grid": "autoplace"
        },
        "stage": 3,
        "features": {
          "custom-properties": false
        }
      }
    ]
  ]
}
```


--------------------------------

### Enable AVIF support in next.config.js

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/04-api-reference/01-components/image-legacy.mdx

Enables AVIF format optimization, falling back to the original source image format if AVIF is unsupported by the browser.

```javascript
module.exports = {
  images: {
    formats: ['image/avif'],
  },
}
```


--------------------------------

### Fetch data from a CMS using getStaticProps

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/03-building-your-application/03-data-fetching/01-get-static-props.mdx

Fetch a list of blog posts at build time on the server side and pass them to the page component as props. Runs exclusively on the server side during build time, allowing direct database queries or external API calls.

```tsx
// posts will be populated at build time by getStaticProps()
export default function Blog({ posts }) {
  return (
    <ul>
      {posts.map((post) => (
        <li>{post.title}</li>
      ))}
    </ul>
  )
}

// This function gets called at build time on server-side.
// It won't be called on client-side, so you can even do
// direct database queries.
export async function getStaticProps() {
  // Call an external API endpoint to get posts.
  // You can use any data fetching library
  const res = await fetch('https://.../posts')
  const posts = await res.json()

  // By returning { props: { posts } }, the Blog component
  // will receive `posts` as a prop at build time
  return {
    props: {
      posts,
    },
  }
}
```

```jsx
// posts will be populated at build time by getStaticProps()
export default function Blog({ posts }) {
  return (
    <ul>
      {posts.map((post) => (
        <li>{post.title}</li>
      ))}
    </ul>
  )
}

// This function gets called at build time on server-side.
// It won't be called on client-side, so you can even do
// direct database queries.
export async function getStaticProps() {
  // Call an external API endpoint to get posts.
  // You can use any data fetching library
  const res = await fetch('https://.../posts')
  const posts = await res.json()

  // By returning { props: { posts } }, the Blog component
  // will receive `posts` as a prop at build time
  return {
    props: {
      posts,
    },
  }
}
```


--------------------------------

### Define catch-all API route pages/api/post/[...slug]

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/03-building-your-application/01-routing/07-api-routes.mdx

Handle multiple path segments where matched parameters are provided as an array in `req.query`.

```typescript
import type { NextApiRequest, NextApiResponse }

export default function handler(req: NextApiRequest, res: NextApiResponse) {
  const { slug } = req.query
  res.end(`Post: ${slug.join(', ')}`)
}
```

```javascript
export default function handler(req, res) {
  const { slug } = req.query
  res.end(`Post: ${slug.join(', ')}`)
}
```


--------------------------------

### Configure PostCSS plugins using object-based format

Source: https://github.com/vercel/next.js/blob/canary/docs/02-pages/02-guides/post-css.mdx

Use the interoperable object-based configuration format in `postcss.config.js` when non-Next.js tools in the same project need to share PostCSS settings.

```javascript
module.exports = {
  plugins: {
    'postcss-flexbugs-fixes': {},
    'postcss-preset-env': {
      autoprefixer: {
        flexbox: 'no-2009',
      },
      stage: 3,
      features: {
        'custom-properties': false,
      },
    },
  },
}
```
