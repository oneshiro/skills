# React — Reference (react-dom)

Sourced snippets (70 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Complete Leaflet map widget portal integration example

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/createPortal.md

Full multi-file example showing how to mount a Leaflet map widget and render a React component inside its popup using createPortal.

```json
{
  "dependencies": {
    "leaflet": "1.9.1",
    "react": "latest",
    "react-dom": "latest",
    "react-scripts": "latest",
    "remarkable": "2.0.1"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test --env=jsdom",
    "eject": "react-scripts eject"
  }
}
```

```javascript
import { useRef, useEffect, useState } from 'react';
import { createPortal } from 'react-dom';
import { createMapWidget, addPopupToMapWidget } from './map-widget.js';

export default function Map() {
  const containerRef = useRef(null);
  const mapRef = useRef(null);
  const [popupContainer, setPopupContainer] = useState(null);

  useEffect(() => {
    if (mapRef.current === null) {
      const map = createMapWidget(containerRef.current);
      mapRef.current = map;
      const popupDiv = addPopupToMapWidget(map);
      setPopupContainer(popupDiv);
    }
  }, []);

  return (
    <div style={{ width: 250, height: 250 }} ref={containerRef}>
      {popupContainer !== null && createPortal(
        <p>Hello from React!</p>,
        popupContainer
      )}
    </div>
  );
}
```

```javascript
import 'leaflet/dist/leaflet.css';
import * as L from 'leaflet';

export function createMapWidget(containerDomNode) {
  const map = L.map(containerDomNode);
  map.setView([0, 0], 0);
  L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
    maxZoom: 19,
    attribution: '© OpenStreetMap'
  }).addTo(map);
  return map;
}

export function addPopupToMapWidget(map) {
  const popupDiv = document.createElement('div');
  L.popup()
    .setLatLng([0, 0])
    .setContent(popupDiv)
    .openOn(map);
  return popupDiv;
}
```

```css
button { margin: 5px; }
```


--------------------------------

### Full client-side application setup

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/client/createRoot.md

Configures an HTML target container, mounts the application at startup with createRoot, and defines interactive React components.

```html
<!DOCTYPE html>
<html>
  <head><title>My app</title></head>
  <body>
    <!-- This is the DOM node -->
    <div id="root"></div>
  </body>
</html>
```

```javascript
import { createRoot } from 'react-dom/client';
import App from './App.js';
import './styles.css';

const root = createRoot(document.getElementById('root'));
root.render(<App />);
```

```javascript
import { useState } from 'react';

export default function App() {
  return (
    <>
      <h1>Hello, world!</h1>
      <Counter />
    </>
  );
}

function Counter() {
  const [count, setCount] = useState(0);
  return (
    <button onClick={() => setCount(count + 1)}>
      You clicked me {count} times
    </button>
  );
}
```


--------------------------------

### Preconnecting in an event handler

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preconnect.md

Call preconnect inside an event handler before initiating transitions that require resources from another host, starting connection setup as early as possible.

```javascript
import { preconnect } from 'react-dom';

function CallToAction() {
  const onClick = () => {
    preconnect('http://example.com');
    startWizard();
  }
  return (
    <button onClick={onClick}>Start Wizard</button>
  );
}
```


--------------------------------

### Calling preinit from react-dom

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preinit.md

Provide a hint to the browser to start downloading and executing a resource during component execution.

```javascript
import { preinit } from 'react-dom';

function AppRoot() {
  preinit("https://example.com/script.js", {as: "script"});
  // ...
}
```


--------------------------------

### Full example of hydrating server-rendered HTML

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/client/hydrateRoot.md

Demonstrates hydrating pre-rendered server HTML markup in public/index.html with the React counter component defined in App.js via index.js.

```html
<!--
  HTML content inside <div id="root">...</div>
  was generated from App by react-dom/server.
-->
<div id="root"><h1>Hello, world!</h1><button>You clicked me <!-- -->0<!-- --> times</button></div>
```

```javascript
import './styles.css';
import { hydrateRoot } from 'react-dom/client';
import App from './App.js';

hydrateRoot(
  document.getElementById('root'),
  <App />
);
```

```javascript
import { useState } from 'react';

export default function App() {
  return (
    <>
      <h1>Hello, world!</h1>
      <Counter />
    </>
  );
}

function Counter() {
  const [count, setCount] = useState(0);
  return (
    <button onClick={() => setCount(count + 1)}>
      You clicked me {count} times
    </button>
  );
}
```


--------------------------------

### Building a live markdown editor with controlled textarea

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/components/textarea.md

Complete example of a controlled text area updating a markdown preview on every keystroke across multiple files.

```javascript
import { useState } from 'react';
import MarkdownPreview from './MarkdownPreview.js';

export default function MarkdownEditor() {
  const [postContent, setPostContent] = useState('_Hello,_ **Markdown**!');
  return (
    <>
      <label>
        Enter some markdown:
        <textarea
          value={postContent}
          onChange={e => setPostContent(e.target.value)}
        />
      </label>
      <hr />
      <MarkdownPreview markdown={postContent} />
    </>
  );
}
```

```javascript
import { Remarkable } from 'remarkable';

const md = new Remarkable();

export default function MarkdownPreview({ markdown }) {
  const renderedHTML = md.render(markdown);
  return <div dangerouslySetInnerHTML={{__html: renderedHTML}} />;
}
```

```json
{
  "dependencies": {
    "react": "latest",
    "react-dom": "latest",
    "react-scripts": "latest",
    "remarkable": "2.0.1"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test --env=jsdom",
    "eject": "react-scripts eject"
  }
}
```

```css
textarea { display: block; margin-top: 5px; margin-bottom: 10px; }
```


--------------------------------

### preinit(href, options)

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preinit.md

Eagerly fetches and evaluates a stylesheet or external script. Scripts execute upon download completion, and stylesheets are inserted into the document immediately.

```APIDOC
### Function: `preinit(href, options)`

#### Description
`preinit` lets you eagerly fetch and evaluate a stylesheet or external script.

#### Import
```js
import { preinit } from 'react-dom';
```

#### Parameters
- **href** (`string`) - Required. The URL of the resource you want to download and execute.
- **options** (`object`) - Required. Configuration options for preinitializing the resource:
  - **as** (`string`) - Required. The type of resource. Possible values: `"script"`, `"style"`.
  - **precedence** (`string`) - Required for stylesheets. Specifies where to insert the stylesheet relative to others. Possible values: `"reset"`, `"low"`, `"medium"`, `"high"`.
  - **crossOrigin** (`string`) - Optional. The CORS policy to use. Possible values: `"anonymous"`, `"use-credentials"`.
  - **integrity** (`string`) - Optional. A cryptographic hash of the resource to verify authenticity.
  - **nonce** (`string`) - Optional. A cryptographic nonce to allow the resource when using a strict Content Security Policy.
  - **fetchPriority** (`string`) - Optional. Suggests relative fetch priority. Possible values: `"auto"` (default), `"high"`, `"low"`.

#### Returns
- `void` - `preinit` returns nothing.

#### Usage Examples

##### Preiniting an external script
```js
import { preinit } from 'react-dom';

function AppRoot() {
  preinit("https://example.com/script.js", {as: "script"});
  return <div>App</div>;
}
```

##### Preiniting a stylesheet
```js
import { preinit } from 'react-dom';

function AppRoot() {
  preinit("https://example.com/style.css", {as: "style", precedence: "medium"});
  return <div>App</div>;
}
```
```


--------------------------------

### Create a root and render a React app

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/client/createRoot.md

Initializes a single root for an app fully built with React and renders the root component inside the DOM container node.

```javascript
import { createRoot } from 'react-dom/client';

const root = createRoot(document.getElementById('root'));
root.render(<App />);
```


--------------------------------

### preinitModule(href, options)

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preinitModule.md

Eagerly fetches and evaluates an ESM module. Provides a browser hint to download and execute the module as soon as it finishes downloading.

```APIDOC
## preinitModule(href, options)

### Description
`preinitModule` lets you eagerly fetch and evaluate an ESM module. It provides the browser with a hint that it should start downloading and executing the given module, which can save time. Modules that you `preinit` are executed when they finish downloading.

### Function Signature
```js
preinitModule(href, options)
```

### Parameters
- **href** (`string`) - Required. The URL of the module you want to download and execute.
- **options** (`object`) - Required. An options object containing configuration properties:
  - **as** (`string`) - Required. Must be `'script'`.
  - **crossOrigin** (`string`) - Optional. The CORS policy to use. Possible values are `'anonymous'` and `'use-credentials'`.
  - **integrity** (`string`) - Optional. A cryptographic hash of the module to verify its authenticity.
  - **nonce** (`string`) - Optional. A cryptographic nonce to allow the module when using a strict Content Security Policy.

### Returns
- `void` - `preinitModule` returns nothing.

### Usage Example
```js
import { preinitModule } from 'react-dom';

function AppRoot() {
  preinitModule("https://example.com/module.js", { as: "script" });
  return <div>App content</div>;
}
```

### Caveats
- Multiple calls to `preinitModule` with the same `href` have the same effect as a single call.
- In the browser, you can call `preinitModule` in any situation (while rendering, in an Effect, in an event handler, etc.).
- In SSR or Server Components, it only has an effect if called while rendering a component or in an async context originating from rendering a component.
```


--------------------------------

### Preloading a font with preload

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preload.md

Preload fonts alongside stylesheets when rendering so the browser can start downloading the font before parsing the stylesheet that references it.

```javascript
import { preload } from 'react-dom';

function AppRoot() {
  preload("https://example.com/style.css", {as: "style"});
  preload("https://example.com/font.woff2", {as: "font"});
  return ...;
}
```


--------------------------------

### preloadModule(href, options)

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preloadModule.md

Preloads an ESM module by providing the browser with a hint to start downloading it eagerly. Can be called when rendering a component or inside event handlers.

```APIDOC
### preloadModule(href, options)

### Description
Lets you eagerly fetch an ESM module that you expect to use, providing the browser with a hint that it should start downloading the given module.

### Import
```js
import { preloadModule } from 'react-dom';
```

### Syntax
```js
preloadModule(href, options)
```

### Parameters
- **href** (string) - Required. The URL of the module you want to download.
- **options** (object) - Required. Configuration object with the following properties:
  - **as** (string) - Required. Must be `'script'`.
  - **crossOrigin** (string) - Optional. The CORS policy to use. Possible values are `'anonymous'` and `'use-credentials'`.
  - **integrity** (string) - Optional. A cryptographic hash of the module to verify its authenticity.
  - **nonce** (string) - Optional. A cryptographic nonce to allow the module when using a strict Content Security Policy.

### Returns
`void` - `preloadModule` returns nothing.

### Usage Example
```js
import { preloadModule } from 'react-dom';

function AppRoot() {
  preloadModule("https://example.com/module.js", { as: "script" });
  // ...
}
```
```


--------------------------------

### Calling preinit to fetch and evaluate a script

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preinit.md

Eagerly fetch and evaluate an external script or stylesheet resource.

```javascript
preinit("https://example.com/script.js", {as: "script"});
```


--------------------------------

### Preload an ESM module in an event handler

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preinitModule.md

Call preinitModule inside an event handler to start downloading and evaluating the module earlier than waiting for the next render transition.

```javascript
import { preinitModule } from 'react-dom';

function CallToAction() {
  const onClick = () => {
    preinitModule("https://example.com/module.js", {as: "script"});
    startWizard();
  }
  return (
    <button onClick={onClick}>Start Wizard</button>
  );
}
```


--------------------------------

### Calling useFormStatus

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/hooks/useFormStatus.md

Call `useFormStatus` to get status information of the last form submission, including `pending`, `data`, `method`, and `action` properties.

```javascript
const { pending, data, method, action } = useFormStatus();
```


--------------------------------

### Eagerly connecting to a server with preconnect

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preconnect.md

Provides the browser with an early hint to open a connection to an external server before requesting resources.

```javascript
preconnect("https://example.com");
```


--------------------------------

### Call preinitModule in a component

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preinitModule.md

Hints the browser to download and execute an ESM module as soon as the module finishes downloading.

```javascript
import { preinitModule } from 'react-dom';

function AppRoot() {
  preinitModule("https://example.com/module.js", {as: "script"});
  // ...
}

```


--------------------------------

### Prefetching DNS in an event handler

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/prefetchDNS.md

Call prefetchDNS inside an event handler before initiating state transitions or navigation to start DNS resolution earlier.

```javascript
import { prefetchDNS } from 'react-dom';

function CallToAction() {
  const onClick = () => {
    prefetchDNS('http://example.com');
    startWizard();
  }
  return (
    <button onClick={onClick}>Start Wizard</button>
  );
}
```


--------------------------------

### Define component shell and view resulting initial HTML structure

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/server/renderToPipeableStream.md

Shows the component hierarchy outside of Suspense boundaries and the corresponding earliest loading shell that the client receives.

```javascript
function ProfilePage() {
  return (
    <ProfileLayout>
      <ProfileCover />
      <Suspense fallback={<BigSpinner />}>
        <Sidebar>
          <Friends />
          <Photos />
        </Sidebar>
        <Suspense fallback={<PostsGlimmer />}>
          <Posts />
        </Suspense>
      </Suspense>
    </ProfileLayout>
  );
}
```

```javascript
<ProfileLayout>
  <ProfileCover />
  <BigSpinner />
</ProfileLayout>
```


--------------------------------

### Preloading an ESM module in an event handler

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preloadModule.md

Call preloadModule inside an event handler before initiating state transitions or navigation to start downloading the module earlier.

```javascript
import { preloadModule } from 'react-dom';

function CallToAction() {
  const onClick = () => {
    preloadModule("https://example.com/module.js", {as: "script"});
    startWizard();
  }
  return (
    <button onClick={onClick}>Start Wizard</button>
  );
}
```


--------------------------------

### Render component to HTML on the client using createRoot and flushSync

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/server/renderToString.md

Render a component into a detached DOM node using `createRoot` and read its `innerHTML` property. Wrap the render call in `flushSync` so the DOM is fully updated before reading the HTML string.

```javascript
import { createRoot } from 'react-dom/client';
import { flushSync } from 'react-dom';

const div = document.createElement('div');
const root = createRoot(div);
flushSync(() => {
  root.render(<MyIcon />);
});
console.log(div.innerHTML); // For example, "<svg>...</svg>"
```


--------------------------------

### Syntax structure for createPortal

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/createPortal.md

Basic structure demonstrating how to call `createPortal` inside JSX with children, target DOM node, and an optional key.

```js
<div>
  <SomeComponent />
  {createPortal(children, domNode, key?)}
</div>
```


--------------------------------

### Passing configuration options to createRoot instead of root.render

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/client/createRoot.md

Pass root options like onUncaughtError to createRoot rather than root.render, which only accepts a single argument.

```javascript
// 🚩 Wrong: root.render only takes one argument.
root.render(App, {onUncaughtError});

// ✅ Correct: pass options to createRoot.
const root = createRoot(container, {onUncaughtError});
root.render(<App />);
```


--------------------------------

### Attach TouchEvent handlers to a DOM element

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/components/common.md

Demonstrates listening to touch interactions including start, move, end, and cancel. The event object provides TouchEvent and UIEvent properties.

```javascript
<div
  onTouchStart={e => console.log('onTouchStart')}
  onTouchMove={e => console.log('onTouchMove')}
  onTouchEnd={e => console.log('onTouchEnd')}
  onTouchCancel={e => console.log('onTouchCancel')}
/>
```


--------------------------------

### Rendering multiple React roots on a partially built page

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/client/createRoot.md

Call createRoot multiple times to manage separate top-level UI pieces within existing HTML DOM nodes.

```html
<!DOCTYPE html>
<html>
  <head><title>My app</title></head>
  <body>
    <nav id="navigation"></nav>
    <main>
      <p>This paragraph is not rendered by React (open index.html to verify).</p>
      <section id="comments"></section>
    </main>
  </body>
</html>
```

```js
import './styles.css';
import { createRoot } from 'react-dom/client';
import { Comments, Navigation } from './Components.js';

const navDomNode = document.getElementById('navigation');
const navRoot = createRoot(navDomNode);
navRoot.render(<Navigation />);

const commentDomNode = document.getElementById('comments');
const commentRoot = createRoot(commentDomNode);
commentRoot.render(<Comments />);
```

```js
export function Navigation() {
  return (
    <ul>
      <NavLink href="/">Home</NavLink>
      <NavLink href="/about">About</NavLink>
    </ul>
  );
}

function NavLink({ href, children }) {
  return (
    <li>
      <a href={href}>{children}</a>
    </li>
  );
}

export function Comments() {
  return (
    <>
      <h2>Comments</h2>
      <Comment text="Hello!" author="Sophie" />
      <Comment text="How are you?" author="Sunil" />
    </>
  );
}

function Comment({ text, author }) {
  return (
    <p>{text} — <i>{author}</i></p>
  );
}
```

```css
nav ul { padding: 0; margin: 0; }
nav ul li { display: inline-block; margin-right: 20px; }
```


--------------------------------

### Submitting a form with an action handler

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/components/form.md

Demonstrates rendering a basic `<form>` component with an `action` prop function to handle submitted form data.

```jsx
<form action={search}>
    <input name="query" />
    <button type="submit">Search</button>
</form>
```


--------------------------------

### Using renderToString on the client (discouraged)

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/server/renderToString.md

Shows the discouraged pattern of importing `react-dom/server` on the client to convert a component into HTML. Importing server packages on the client unnecessarily increases your bundle size.

```javascript
// 🚩 Unnecessary: using renderToString on the client
import { renderToString } from 'react-dom/server';

const html = renderToString(<MyIcon />);
console.log(html); // For example, "<svg>...</svg>"
```


--------------------------------

### Rendering an app into a created root

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/client/createRoot.md

Call root.render after creating the root with createRoot to ensure the application renders into the DOM.

```javascript
import { createRoot } from 'react-dom/client';
import App from './App.js';

const root = createRoot(document.getElementById('root'));
root.render(<App />);
```


--------------------------------

### Handle request and return Response with renderToReadableStream

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/server/renderToReadableStream.md

Awaits renderToReadableStream once the initial shell is rendered and returns a Response with the stream.

```js
async function handler(request) {
  const stream = await renderToReadableStream(<App />, {
    bootstrapScripts: ['/main.js']
  });
  return new Response(stream, {
    headers: { 'content-type': 'text/html' },
  });
}
```


--------------------------------

### createRoot(domNode, options?)

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/client/createRoot.md

Creates a React root for displaying content inside a browser DOM element. React takes over managing the DOM inside the target node and returns an object with render and unmount methods.

```APIDOC
### Function Signature
```js
const root = createRoot(domNode, options?)
```

### Description
Call `createRoot` to create a React root for displaying content inside a browser DOM element. After creating a root, call `root.render(...)` to display a React component inside of it.

### Parameters
- **domNode** (DOM element) - Required - A DOM element. React will create a root for this DOM element and allow you to call functions on the root, such as `render`.
- **options** (object) - Optional - An object with options for this React root.
  - **onCaughtError** (Function) - Optional - Callback called when React catches an error in an Error Boundary. Called with `(error, errorInfo)`.
  - **onUncaughtError** (Function) - Optional - Callback called when an error is thrown and not caught by an Error Boundary. Called with `(error, errorInfo)`.
  - **onRecoverableError** (Function) - Optional - Callback called when React automatically recovers from errors. Called with `(error, errorInfo)`.
  - **identifierPrefix** (string) - Optional - A string prefix React uses for IDs generated by `useId`. Useful to avoid conflicts when using multiple roots on the same page.

### Returns
`createRoot` returns an object with two methods: `render` and `unmount`.

### Usage Example
```js
import { createRoot } from 'react-dom/client';

const domNode = document.getElementById('root');
const root = createRoot(domNode);
root.render(<App />);
```
```


--------------------------------

### Resuming a prerender with resume

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/server/resume.md

Demonstrates how to prerender a React component tree, abort unresolved data requests, and later resume rendering with resume using the postponed state before hydrating on the client.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <iframe id="container"></iframe>
</body>
</html>
```

```javascript
import {
  flushReadableStreamToFrame,
  getUser,
  Postponed,
  sleep,
} from "./demo-helpers";
import { StrictMode, Suspense, use, useEffect } from "react";
import { prerender } from "react-dom/static";
import { resume } from "react-dom/server";
import { hydrateRoot } from "react-dom/client";

function Header() {
  return <header>Me and my descendants can be prerendered</header>;
}

const { promise: cookies, resolve: resolveCookies } = Promise.withResolvers();

function Main() {
  const { sessionID } = use(cookies);
  const user = getUser(sessionID);

  useEffect(() => {
    console.log("reached interactivity!");
  }, []);

  return (
    <main>
      Hello, {user.name}!
      <button onClick={() => console.log("hydrated!")}>
        Clicking me requires hydration.
      </button>
    </main>
  );
}

function Shell({ children }) {
  // In a real app, this is where you would put your html and body.
  // We're just using tags here we can include in an existing body for demonstration purposes
  return (
    <html>
      <body>{children}</body>
    </html>
  );
}

function App() {
  return (
    <Shell>
      <Suspense fallback="loading header">
        <Header />
      </Suspense>
      <Suspense fallback="loading main">
        <Main />
      </Suspense>
    </Shell>
  );
}

async function main(frame) {
  // Layer 1
  const controller = new AbortController();
  const prerenderedApp = prerender(<App />, {
    signal: controller.signal,
    onError(error) {
      if (error instanceof Postponed) {
      } else {
        console.error(error);
      }
    },
  });
  // We're immediately aborting in a macrotask.
  // Any data fetching that's not available synchronously, or in a microtask, will not have finished.
  setTimeout(() => {
    controller.abort(new Postponed());
  });

  const { prelude, postponed } = await prerenderedApp;
  await flushReadableStreamToFrame(prelude, frame);

  // Layer 2
  // Just waiting here for demonstration purposes.
  // In a real app, the prelude and postponed state would've been serialized in Layer 1 and Layer would deserialize them.
  // The prelude content could be flushed immediated as plain HTML while
  // React is continuing to render from where the prerender left off.
  await sleep(2000);

  // You would get the cookies from the incoming HTTP request
  resolveCookies({ sessionID: "abc" });

  const stream = await resume(<App />, postponed);

  await flushReadableStreamToFrame(stream, frame);

  // Layer 3
  // Just waiting here for demonstration purposes.
  await sleep(2000);

  hydrateRoot(frame.contentWindow.document, <App />);
}

main(document.getElementById("container"));

```

```javascript
export async function flushReadableStreamToFrame(readable, frame) {
  const document = frame.contentWindow.document;
  const decoder = new TextDecoder();
  const reader = readable.getReader();

  while (true) {
    const {done, value} = await reader.read();
    if (done) {
      break;
    }
    const partialHTML = decoder.decode(value, {stream: true});
    document.write(partialHTML);
  }

  document.write(decoder.decode());
}

// This doesn't need to be an error.
// You can use any other means to check if an error during prerender was
// from an intentional abort or a real error.
export class Postponed extends Error {}

// We're just hardcoding a session here.
export function getUser(sessionID) {
  return {
    name: "Alice",
  };
}

export function sleep(timeoutMS) {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve();
    }, timeoutMS);
  });
}

```


--------------------------------

### Handle CSS animation events with AnimationEvent handlers

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/components/common.md

Attaches handlers for CSS animation lifecycle events including start, iteration, and end. The passed React event object includes animationName, elapsedTime, and pseudoElement properties.

```javascript
<div
  onAnimationStart={e => console.log('onAnimationStart')}
  onAnimationIteration={e => console.log('onAnimationIteration')}
  onAnimationEnd={e => console.log('onAnimationEnd')}
/>
```


--------------------------------

### Unmount a root with root.unmount

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/client/hydrateRoot.md

Destroys a rendered tree inside a React root and detaches React from the root DOM node. Use this when the root's DOM node may get removed from the DOM by external code.

```javascript
root.unmount();
```


--------------------------------

### Calling createRoot

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/client/createRoot.md

Defines the signature for creating a React root attached to a browser DOM node with optional configuration settings.

```javascript
const root = createRoot(domNode, options?)
```


--------------------------------

### Define full-document root App component

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/static/prerender.md

The root component passed to prerender must return the entire document, including the root <html>, <head>, and <body> tags.

```javascript
export default function App() {
  return (
    <html>
      <head>
        <meta charSet="utf-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1" />
        <link rel="stylesheet" href="/styles.css"></link>
        <title>My app</title>
      </head>
      <body>
        <Router />
      </body>
    </html>
  );
}
```


--------------------------------

### Eagerly fetch and evaluate an ESM module with preinitModule

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preinitModule.md

Eagerly fetches and executes an ESM module at the specified URL using preinitModule.

```javascript
preinitModule("https://example.com/module.js", {as: "script"});
```


--------------------------------

### Preiniting an external script during render

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preinit.md

Call preinit during render if the component or its children need an external script executed immediately upon download.

```javascript
import { preinit } from 'react-dom';

function AppRoot() {
  preinit("https://example.com/script.js", {as: "script"});
  return ...;
}
```


--------------------------------

### resume(reactNode, postponedState, options?)

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/server/resume.md

Streams a pre-rendered React tree to a Readable Web Stream. It resumes rendering using postponed state generated from a prerender API call.

```APIDOC
### `resume(reactNode, postponedState, options?)`

### Description
Streams a pre-rendered React tree to a Readable Web Stream. Call `resume` to resume rendering a pre-rendered React tree as HTML into a Readable Web Stream using saved postponed state.

### Parameters
- **reactNode** (`ReactNode`) - Required - The React node you called `prerender` with (e.g., `<App />`). Expected to represent the entire document including the `<html>` tag.
- **postponedState** (`object`) - Required - The opaque `postpone` object returned from a prerender API, loaded from storage (e.g., Redis, a file, or S3).
- **options** (`object`) - Optional - An object with streaming options:
  - **nonce** (`string`) - Optional - A nonce string to allow scripts for `script-src` Content-Security-Policy.
  - **signal** (`AbortSignal`) - Optional - An abort signal that lets you abort server rendering and render the rest on the client.
  - **onBrowserBailout** (`(error: Error, errorInfo: { componentStack: string }) => void`) - Optional - Callback invoked when React recovers from `browser()` by leaving a Suspense fallback. If a reason was passed to `browser`, it is available as `error.cause`.
  - **onError** (`(error: unknown) => void`) - Optional - Callback invoked whenever there is a server error, whether recoverable or not. Defaults to calling `console.error`.

### Returns
- **Promise<ReadableStream & { allReady: Promise<void> }>**:
  - Resolves to a `ReadableStream` if the shell was successfully produced.
  - Rejects with an error if an error happens in the shell.
  - The returned stream has an `allReady` promise property that resolves when all rendering is complete.

### Example
```js
import { resume } from 'react-dom/server';
import { getPostponedState } from './storage';

async function handler(request, writable) {
  const postponed = await getPostponedState(request);
  const resumeStream = await resume(<App />, postponed);
  return resumeStream.pipeTo(writable);
}
```
```


--------------------------------

### Implement production error reporting with hydrateRoot

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/client/hydrateRoot.md

Configure onCaughtError, onUncaughtError, and onRecoverableError in hydrateRoot to build a complete error reporting setup across caught exceptions, uncaught crashes, and hydration mismatch errors. Remove these custom options in development to preserve React's default error overlay.

```javascript
function reportError({ type, error, errorInfo }) {
  // The specific implementation is up to you.
  // `console.error()` is only used for demonstration purposes.
  console.error(type, error, "Component Stack: ");
  console.error("Component Stack: ", errorInfo.componentStack);
}

export function onCaughtErrorProd(error, errorInfo) {
  if (error.message !== "Known error") {
    reportError({ type: "Caught", error, errorInfo });
  }
}

export function onUncaughtErrorProd(error, errorInfo) {
  reportError({ type: "Uncaught", error, errorInfo });
}

export function onRecoverableErrorProd(error, errorInfo) {
  reportError({ type: "Recoverable", error, errorInfo });
}
```

```javascript
import { hydrateRoot } from "react-dom/client";
import App from "./App.js";
import {
  onCaughtErrorProd,
  onRecoverableErrorProd,
  onUncaughtErrorProd,
} from "./reportError";

const container = document.getElementById("root");
hydrateRoot(container, <App />, {
  // Keep in mind to remove these options in development to leverage
  // React's default handlers or implement your own overlay for development.
  // The handlers are only specfied unconditionally here for demonstration purposes.
  onCaughtError: onCaughtErrorProd,
  onRecoverableError: onRecoverableErrorProd,
  onUncaughtError: onUncaughtErrorProd,
});
```

```javascript
import { Component, useState } from "react";

function Boom() {
  foo.bar = "baz";
}

class ErrorBoundary extends Component {
  state = { hasError: false };

  static getDerivedStateFromError(error) {
    return { hasError: true };
  }

  render() {
    if (this.state.hasError) {
      return <h1>Something went wrong.</h1>;
    }
    return this.props.children;
  }
}

export default function App() {
  const [triggerUncaughtError, settriggerUncaughtError] = useState(false);
  const [triggerCaughtError, setTriggerCaughtError] = useState(false);

  return (
    <>
      <button onClick={() => settriggerUncaughtError(true)}>
        Trigger uncaught error
      </button>
      {triggerUncaughtError && <Boom />}
      <button onClick={() => setTriggerCaughtError(true)}>
        Trigger caught error
      </button>
      {triggerCaughtError && (
        <ErrorBoundary>
          <Boom />
        </ErrorBoundary>
      )}
    </>
  );
}
```

```html
<!DOCTYPE html>
<html>
<head>
  <title>My app</title>
</head>
<body>
<!--
  Purposefully using HTML content that differs from the server-rendered content to trigger recoverable errors.
-->
<div id="root">Server content before hydration.</div>
</body>
</html>
```


--------------------------------

### Rendering a React root into a dynamically created DOM node

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/client/createRoot.md

Create a new DOM node manually with document.createElement, render a React component into it, and append it anywhere in the document.

```js
const domNode = document.createElement('div');
const root = createRoot(domNode);
root.render(<Comment />);
document.body.appendChild(domNode); // You can add it anywhere in the document
```


--------------------------------

### Render a modal dialog using createPortal

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/createPortal.md

Use createPortal to render a modal dialog into document.body so that parent container styles like overflow: hidden do not clip the dialog. The example contrasts rendering a modal directly in parent JSX versus using a portal. When creating modals with portals, ensure keyboard focus and accessibility standards are properly managed.

```javascript
import NoPortalExample from './NoPortalExample';
import PortalExample from './PortalExample';

export default function App() {
  return (
    <>
      <div className="clipping-container">
        <NoPortalExample  />
      </div>
      <div className="clipping-container">
        <PortalExample />
      </div>
    </>
  );
}
```

```javascript
import { useState } from 'react';
import ModalContent from './ModalContent.js';

export default function NoPortalExample() {
  const [showModal, setShowModal] = useState(false);
  return (
    <>
      <button onClick={() => setShowModal(true)}>
        Show modal without a portal
      </button>
      {showModal && (
        <ModalContent onClose={() => setShowModal(false)} />
      )}
    </>
  );
}
```

```javascript
import { useState } from 'react';
import { createPortal } from 'react-dom';
import ModalContent from './ModalContent.js';

export default function PortalExample() {
  const [showModal, setShowModal] = useState(false);
  return (
    <>
      <button onClick={() => setShowModal(true)}>
        Show modal using a portal
      </button>
      {showModal && createPortal(
        <ModalContent onClose={() => setShowModal(false)} />,
        document.body
      )}
    </>
  );
}
```

```javascript
export default function ModalContent({ onClose }) {
  return (
    <div className="modal">
      <div>I'm a modal dialog</div>
      <button onClick={onClose}>Close</button>
    </div>
  );
}
```

```css
.clipping-container {
  position: relative;
  border: 1px solid #aaa;
  margin-bottom: 12px;
  padding: 12px;
  width: 250px;
  height: 80px;
  overflow: hidden;
}

.modal {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  box-shadow: rgba(100, 100, 111, 0.3) 0px 7px 29px 0px;
  background-color: white;
  border: 2px solid rgb(240, 240, 240);
  border-radius: 12px;
  position:  absolute;
  width: 250px;
  top: 70px;
  left: calc(50% - 125px);
  bottom: 70px;
}
```


--------------------------------

### Eagerly prefetching DNS for a server

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/prefetchDNS.md

Provides the browser with an early hint to look up the IP address of a server.

```javascript
prefetchDNS("https://example.com");
```


--------------------------------

### Creating a React root with createRoot

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/client/createRoot.md

Creates a React root for a specified DOM node, allowing React to take over managing the DOM inside it.

```javascript
import { createRoot } from 'react-dom/client';

const domNode = document.getElementById('root');
const root = createRoot(domNode);
```


--------------------------------

### Render an inline script

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/components/script.md

Demonstrates rendering a basic inline `<script>` tag in React.

```js
<script> alert("hi!") </script>
```


--------------------------------

### resumeToPipeableStream(reactNode, postponedState, options?)

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/server/resumeToPipeableStream.md

Resumes rendering a pre-rendered React tree as HTML into a Node.js Stream. Returns an object with `pipe` and `abort` methods to control streaming output.

```APIDOC
### Function
`resumeToPipeableStream(reactNode, postponedState, options?)`

### Description
Resumes rendering a pre-rendered React tree as HTML into a Node.js Writable Stream.

### Parameters
- **reactNode** (`ReactNode`) - Required - The React node you called `prerender` with (e.g. `<App />`). Represents the entire document including the `<html>` tag.
- **postponedState** (`object`) - Required - The opaque `postpone` object returned from a prerender API, loaded from storage.
- **options** (`object`) - Optional - Configuration options for streaming.
  - **nonce** (`string`) - Optional - A nonce string for `script-src` Content-Security-Policy.
  - **onAllReady** (`() => void`) - Optional - Callback fired when all rendering is complete, including the shell and additional content.
  - **onBrowserBailout** (`(error: Error, errorInfo: { componentStack: string }) => void`) - Optional - Callback fired when recovering from `browser()` by leaving a Suspense fallback.
  - **onError** (`(error: unknown) => void`) - Optional - Callback fired whenever a server error occurs.
  - **onShellReady** (`() => void`) - Optional - Callback fired right after the shell finishes rendering.
  - **onShellError** (`(error: unknown) => void`) - Optional - Callback fired if there was an error rendering the shell.

### Returns
An object containing:
- **pipe** (`(destination: WritableStream) => void`) - Outputs the HTML into the provided Writable Node.js Stream.
- **abort** (`() => void`) - Aborts server rendering and renders the rest on the client.

### Usage Example
```js
import { resumeToPipeableStream } from 'react-dom/server';
import { getPostponedState } from './storage';

async function handler(request, response) {
  const postponed = await getPostponedState(request);
  const { pipe } = resumeToPipeableStream(<App />, postponed, {
    onShellReady: () => {
      pipe(response);
    }
  });
}
```
```


--------------------------------

### Displaying an image with custom styling

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/components/img.md

Pass the image URL to src and a description to alt, specifying width and height so the browser reserves layout space before loading. Use alt="" for decorative images so screen readers ignore them.

```js
export default function Profile() {
  return (
    <img
      src="https://react.dev/images/docs/scientists/yXOvdOSs.jpg"
      alt="Hedy Lamarr"
      width={100}
      height={100}
    />
  );
}
```

```css
img {
  border-radius: 50%;
  object-fit: cover;
}
```


--------------------------------

### Syntax for resume

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/server/resume.md

Calls resume with a root React node, postponed state, and optional settings to return a promise resolving to a stream.

```javascript
const stream = await resume(reactNode, postponedState, options?)
```


--------------------------------

### Preloading a stylesheet with preload

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preload.md

Call preload to initiate downloading a stylesheet before it is rendered. Use preinit instead if the stylesheet needs to be inserted and parsed immediately by the browser.

```javascript
import { preload } from 'react-dom';

function AppRoot() {
  preload("https://example.com/style.css", {as: "style"});
  return ...;
}
```


--------------------------------

### Preiniting a stylesheet with precedence

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preinit.md

Preinit a stylesheet with the required precedence option to specify document insertion order and override rules.

```javascript
import { preinit } from 'react-dom';

function AppRoot() {
  preinit("https://example.com/style.css", {as: "style", precedence: "medium"});
  return ...;
}
```


--------------------------------

### Waiting for all content to load with stream.allReady

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/server/renderToReadableStream.md

Await stream.allReady before returning a response when serving crawlers or generating static pages. Regular visitors receive a progressively loaded stream while crawlers receive the final HTML after all data loads.

```js
async function handler(request) {
  try {
    let didError = false;
    const stream = await renderToReadableStream(<App />, {
      bootstrapScripts: ['/main.js'],
      onError(error) {
        didError = true;
        console.error(error);
        logServerCrashReport(error);
      }
    });
    let isCrawler = // ... depends on your bot detection strategy ...
    if (isCrawler) {
      await stream.allReady;
    }
    return new Response(stream, {
      status: didError ? 500 : 200,
      headers: { 'content-type': 'text/html' },
    });
  } catch (error) {
    return new Response('<h1>Something went wrong</h1>', {
      status: 500,
      headers: { 'content-type': 'text/html' },
    });
  }
}
```


--------------------------------

### <link>

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/components/link.md

Renders a built-in browser <link> element to link external resources or metadata. React handles resource precedence and automatically places the element in the document head when appropriate.

```APIDOC
### Component: `<link>`

#### Description
To link to external resources such as stylesheets, fonts, and icons, or to annotate the document with link metadata, render the built-in browser `<link>` component. React places the corresponding DOM element in the document head in most cases.

#### Props

- **rel** (string, required): Specifies the relationship to the resource (e.g., `"stylesheet"`, `"preload"`, `"icon"`).
- **href** (string, optional): The URL of the linked resource.
- **crossOrigin** (string, optional): The CORS policy to use (`"anonymous"` or `"use-credentials"`). Required when `as` is `"fetch"`.
- **referrerPolicy** (string, optional): The Referrer header to send (`"no-referrer-when-downgrade"`, `"no-referrer"`, `"origin"`, `"origin-when-cross-origin"`, `"unsafe-url"`).
- **fetchPriority** (string, optional): Suggests relative priority for fetching (`"auto"`, `"high"`, `"low"`).
- **hrefLang** (string, optional): The language of the linked resource.
- **integrity** (string, optional): Cryptographic hash to verify resource authenticity.
- **type** (string, optional): The MIME type of the linked resource.

##### Props when `rel="stylesheet"`
- **precedence** (string, optional): Tells React where to rank the `<link>` DOM node relative to others in the document `<head>`.
- **media** (string, optional): Restricts the stylesheet to a certain media query.
- **title** (string, optional): Specifies the name of an alternative stylesheet.
- **disabled** (boolean, optional): Disables the stylesheet (disables React special treatment).
- **onError** (function, optional): Callback invoked when the stylesheet fails to load.
- **onLoad** (function, optional): Callback invoked when the stylesheet finishes loading.

##### Props when `rel="preload"` or `rel="modulepreload"`
- **as** (string, optional): Type of resource (`"audio"`, `"document"`, `"embed"`, `"fetch"`, `"font"`, `"image"`, `"object"`, `"script"`, `"style"`, `"track"`, `"video"`, `"worker"`).
- **imageSrcSet** (string, optional): Applicable when `as="image"`. Specifies the source set.
- **imageSizes** (string, optional): Applicable when `as="image"`. Specifies image sizes.

##### Props when `rel="icon"` or `rel="apple-touch-icon"`
- **sizes** (string, optional): Specifies icon sizes.

##### Not Recommended Props
- **blocking** (string, optional): If set to `"render"`, instructs browser not to render until stylesheet loads. React recommends using Suspense instead.
```


--------------------------------

### prerender(reactNode, options?)

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/static/prerender.md

Renders a React node representing the full document to static HTML with optional configuration for bootstrap scripts, error handling, resource hints, and abort signals.

```APIDOC
### prerender(reactNode, options?)

#### Parameters
- `reactNode` (ReactNode) - Required. A React node to render to HTML (e.g., `<App />`). Expected to represent the entire document including the `<html>` tag.
- `options` (Object) - Optional. An object containing static generation options:
  - `bootstrapScriptContent` (string) - Optional. String to be placed in an inline `<script>` tag.
  - `bootstrapScripts` (string[]) - Optional. An array of string URLs for `<script>` tags to emit on the page.
  - `bootstrapModules` (string[]) - Optional. An array of string URLs for `<script type="module">` tags to emit.
  - `identifierPrefix` (string) - Optional. A string prefix React uses for IDs generated by `useId`.
  - `importMap` (Object) - Optional. An import map object with `imports` and `scopes` properties emitted as `<script type="importmap">`.
  - `maxHeadersLength` (number) - Optional. The maximum total length of header content passed to `onHeaders` in UTF-16 code units (defaults to 2000).
  - `namespaceURI` (string) - Optional. The root namespace URI for the stream (e.g., `'http://www.w3.org/2000/svg'` or `'http://www.w3.org/1998/Math/MathML'`).
  - `onBrowserBailout` (Function) - Optional. Callback invoked when recovering from `browser()` by leaving a Suspense fallback.
  - `onError` (Function) - Optional. Callback that fires on recoverable or non-recoverable server errors.
  - `onHeaders` (Function) - Optional. Callback that fires when React has determined resource hints (link headers) for the document.
  - `progressiveChunkSize` (number) - Optional. The number of bytes in a chunk.
  - `signal` (AbortSignal) - Optional. An abort signal allowing prerendering to be aborted.
```


--------------------------------

### Hydrate client using window.assetMap

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/static/prerender.md

Pass window.assetMap to the root component during client hydration to match server props and avoid hydration mismatch errors.

```javascript
import { hydrateRoot } from 'react-dom/client';
import App from './App.js';

hydrateRoot(document, <App assetMap={window.assetMap} />);
```


--------------------------------

### prerender(reactNode, options?)

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/static/prerender.md

Renders a React tree to a static HTML string using a Web Stream. Returns a Promise resolving to an object containing the rendered prelude stream and postponed state.

```APIDOC
## prerender(reactNode, options?)

### Description
Renders a React tree to a static HTML string using a Web Stream.

### Syntax
```js
const {prelude, postponed} = await prerender(reactNode, options?)
```

### Parameters
- **reactNode** (`ReactNode`) - The React element/tree to render.
- **options** (`Object`, optional) - Optional configuration object.
  - **bootstrapScripts** (`string[]`, optional) - Array of script URLs to emit before the main application code.

### Returns
A Promise resolving to an object:
- **prelude** (`ReadableStream`) - A Web Stream containing the static HTML.
- **postponed** (`Object | null`) - Postponed state if dynamic rendering was postponed.

### Example Usage
```js
import { prerender } from 'react-dom/static';

async function handler(request, response) {
  const {prelude} = await prerender(<App />, {
    bootstrapScripts: ['/main.js']
  });
  return new Response(prelude, {
    headers: { 'content-type': 'text/html' },
  });
}
```
```


--------------------------------

### Syntax of resumeAndPrerenderToNodeStream

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/static/resumeAndPrerenderToNodeStream.md

Continues a prerendered React tree to a static HTML Node.js stream and returns an object with the prelude stream and postponed state.

```javascript
const {prelude, postponed} = await resumeAndPrerenderToNodeStream(reactNode, postponedState, options?)
```


--------------------------------

### Rendering a React tree to static HTML in a request handler

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/static/prerender.md

Calls prerender to render an App component into a Web Stream prelude and returns it in a Web Response. Includes bootstrapScripts option for hydration on the client.

```javascript
import { prerender } from 'react-dom/static';

async function handler(request, response) {
  const {prelude} = await prerender(<App />, {
    bootstrapScripts: ['/main.js']
  });
  return new Response(prelude, {
    headers: { 'content-type': 'text/html' },
  });
}
```


--------------------------------

### Render a React tree to static HTML with prerender

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/static/prerender.md

Calls prerender to generate static HTML from a React tree and consumes the prelude stream to assemble the full HTML string. Client hydration with hydrateRoot is needed afterward to make the HTML interactive.

```javascript
import { prerender } from 'react-dom/static';

async function renderToString() {
  const {prelude} = await prerender(<App />, {
    bootstrapScripts: ['/main.js']
  });

  const reader = prelude.getReader();
  let content = '';
  while (true) {
    const {done, value} = await reader.read();
    if (done) {
      return content;
    }
    content += Buffer.from(value).toString('utf8');
  }
}
```


--------------------------------

### Calling use(browser())

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/browser.md

Syntax for passing the opaque value returned by browser to use.

```js
use(browser(reason?))
```


--------------------------------

### Render React tree to static HTML in Node.js server

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/static/prerenderToNodeStream.md

Calls prerenderToNodeStream within a route handler and pipes the prelude stream directly to the response. Use hydrateRoot on the client to make the static HTML interactive.

```javascript
import { prerenderToNodeStream } from 'react-dom/static';

// The route handler syntax depends on your backend framework
app.use('/', async (request, response) => {
  const { prelude } = await prerenderToNodeStream(<App />, {
    bootstrapScripts: ['/main.js'],
  });

  response.setHeader('Content-Type', 'text/plain');
  prelude.pipe(response);
});
```


--------------------------------

### Calling renderToStaticMarkup

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/server/renderToStaticMarkup.md

Syntax signature for renderToStaticMarkup, accepting a React node and optional server render options.

```javascript
const html = renderToStaticMarkup(reactNode, options?)
```


--------------------------------

### Calling preconnect from react-dom

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preconnect.md

Imports and calls preconnect to establish an early connection to the specified server host URL.

```javascript
import { preconnect } from 'react-dom';

function AppRoot() {
  preconnect("https://example.com");
  // ...
}
```


--------------------------------

### Preiniting in an event handler

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preinit.md

Trigger resource preiniting within an event handler to fetch stylesheets or scripts before state transitions occur.

```javascript
import { preinit } from 'react-dom';

function CallToAction() {
  const onClick = () => {
    preinit("https://example.com/wizardStyles.css", {as: "style"});
    startWizard();
  }
  return (
    <button onClick={onClick}>Start Wizard</button>
  );
}
```


--------------------------------

### Resuming pre-rendered HTML into a Node.js stream with resumeToPipeableStream

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/server/resumeToPipeableStream.md

Call resumeToPipeableStream with the root React node, the stored postponedState, and callback options to pipe the rendered stream into a Node.js writable response.

```javascript
import { resumeToPipeableStream } from 'react-dom/server';
import {getPostponedState} from './storage';

async function handler(request, response) {
  const postponed = await getPostponedState(request);
  const {pipe} = resumeToPipeableStream(<App />, postponed, {
    onShellReady: () => {
      pipe(response);
    }
  });
}
```


--------------------------------

### Calling renderToReadableStream

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/server/renderToReadableStream.md

Syntax definition for rendering a React node to a Readable Web Stream with optional configuration options.

```js
const stream = await renderToReadableStream(reactNode, options?)
```


--------------------------------

### Rendering a React tree to static HTML with prerenderToNodeStream

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/static/prerenderToNodeStream.md

Renders an application into a readable stream of static HTML and collects chunks from the prelude. The resulting non-interactive HTML must be hydrated on the client using hydrateRoot.

```javascript
import { prerenderToNodeStream } from 'react-dom/static';

async function renderToString() {
  const {prelude} = await prerenderToNodeStream(<App />, {
    bootstrapScripts: ['/main.js']
  });

  return new Promise((resolve, reject) => {
    let data = '';
    prelude.on('data', chunk => {
      data += chunk;
    });
    prelude.on('end', () => resolve(data));
    prelude.on('error', reject);
  });
}
```


--------------------------------

### Preloading an image with responsive options

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preload.md

Preload an image using imageSrcSet and imageSizes options to ensure the browser fetches the correctly sized asset for the viewport.

```javascript
import { preload } from 'react-dom';

function AppRoot() {
  preload("/banner.png", {
    as: "image",
    imageSrcSet: "/banner512.png 512w, /banner1024.png 1024w",
    imageSizes: "(max-width: 512px) 512px, 1024px",
  });
  return ...;
}
```


--------------------------------

### Rendering a React tree to a Node.js Stream with renderToPipeableStream

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/server/renderToPipeableStream.md

Renders a root React component into HTML piped to a Node.js response stream once the shell is ready, including a bootstrap script for client-side hydration. The root component should render the full HTML document including the <html> tag.

```javascript
import { renderToPipeableStream } from 'react-dom/server';

const { pipe } = renderToPipeableStream(<App />, {
  bootstrapScripts: ['/main.js'],
  onShellReady() {
    response.setHeader('content-type', 'text/html');
    pipe(response);
  }
});
```


--------------------------------

### Implementing a Custom Production Error Reporting System

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/client/createRoot.md

Define custom handlers for caught, uncaught, and recoverable errors and pass them to createRoot in index.js.

```javascript
function reportError({ type, error, errorInfo }) {
  // The specific implementation is up to you.
  // `console.error()` is only used for demonstration purposes.
  console.error(type, error, "Component Stack: ");
  console.error("Component Stack: ", errorInfo.componentStack);
}

export function onCaughtErrorProd(error, errorInfo) {
  if (error.message !== "Known error") {
    reportError({ type: "Caught", error, errorInfo });
  }
}

export function onUncaughtErrorProd(error, errorInfo) {
  reportError({ type: "Uncaught", error, errorInfo });
}

export function onRecoverableErrorProd(error, errorInfo) {
  reportError({ type: "Recoverable", error, errorInfo });
}
```

```javascript
import { createRoot } from "react-dom/client";
import App from "./App.js";
import {
  onCaughtErrorProd,
  onRecoverableErrorProd,
  onUncaughtErrorProd,
} from "./reportError";

const container = document.getElementById("root");
const root = createRoot(container, {
  // Keep in mind to remove these options in development to leverage
  // React's default handlers or implement your own overlay for development.
  // The handlers are only specfied unconditionally here for demonstration purposes.
  onCaughtError: onCaughtErrorProd,
  onRecoverableError: onRecoverableErrorProd,
  onUncaughtError: onUncaughtErrorProd,
});
root.render(<App />);
```

```javascript
import { Component, useState } from "react";

function Boom() {
  foo.bar = "baz";
}

class ErrorBoundary extends Component {
  state = { hasError: false };

  static getDerivedStateFromError(error) {
    return { hasError: true };
  }

  render() {
    if (this.state.hasError) {
      return <h1>Something went wrong.</h1>;
    }
    return this.props.children;
  }
}

export default function App() {
  const [triggerUncaughtError, settriggerUncaughtError] = useState(false);
  const [triggerCaughtError, setTriggerCaughtError] = useState(false);

  return (
    <>
      <button onClick={() => settriggerUncaughtError(true)}>
        Trigger uncaught error
      </button>
      {triggerUncaughtError && <Boom />}
      <button onClick={() => setTriggerCaughtError(true)}>
        Trigger caught error
      </button>
      {triggerCaughtError && (
        <ErrorBoundary>
          <Boom />
        </ErrorBoundary>
      )}
    </>
  );
}
```


--------------------------------

### resumeAndPrerenderToNodeStream(reactNode, postponedState, options?)

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/static/resumeAndPrerenderToNodeStream.md

Continues rendering a prerendered React tree into a static HTML stream using Node.js Streams. It accepts the original React node, a postponed state object, and optional configuration options, resolving to an object with the stream prelude and any updated postponed state.

```APIDOC
## resumeAndPrerenderToNodeStream(reactNode, postponedState, options?)

### Description
Continues a prerendered React tree to a static HTML string using a Node.js Stream. Unlike `renderToString`, it waits for all data to load before resolving.

### Syntax
```js
const { prelude, postponed } = await resumeAndPrerenderToNodeStream(reactNode, postponedState, options?);
```

### Parameters
- **reactNode** (ReactNode) - Required. The React node passed to `prerender` or a previous `resumeAndPrerenderToNodeStream` call (e.g., `<App />`). It is expected to represent the entire document including the `<html>` tag.
- **postponedState** (Object) - Required. The opaque postpone state object returned from a prerender API, retrieved from storage (such as Redis, a file, or S3).
- **options** (Object) - Optional. An object containing configuration options:
  - **signal** (AbortSignal) - Optional. An abort signal allowing cancellation of server rendering.
  - **onBrowserBailout** (Function) - Optional. Callback triggered when React recovers from `browser()` by leaving a Suspense fallback. Receives an `Error` and an `errorInfo` object containing `componentStack`.
  - **onError** (Function) - Optional. Callback executed whenever a server error occurs (recoverable or unrecoverable). Defaults to calling `console.error`.

### Returns
Returns a `Promise` that resolves to an object containing:
- **prelude** (ReadableStream) - A stream of HTML that can be piped to a response writable stream or read into a string.
- **postponed** (Object) - A JSON-serializable, opaque state object that can be passed to `resumeToNodeStream` or another `resumeAndPrerenderToNodeStream` call if aborted.

If rendering fails, the returned Promise rejects.
```


--------------------------------

### Render React tree to static HTML with prerender

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/static/prerender.md

Call prerender with the root component and bootstrapScripts to generate a Readable Web Stream of static HTML for HTTP responses.

```javascript
import { prerender } from 'react-dom/static';

async function handler(request) {
  const {prelude} = await prerender(<App />, {
    bootstrapScripts: ['/main.js']
  });
  return new Response(prelude, {
    headers: { 'content-type': 'text/html' },
  });
}
```


--------------------------------

### Eagerly fetching an ESM module

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-dom/preloadModule.md

Provides a browser hint to eagerly download an ESM module expected to be used later.

```javascript
preloadModule("https://example.com/module.js", {as: "script"});
```
