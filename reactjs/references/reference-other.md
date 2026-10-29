# React — Compiler, RSC & ESLint

Sourced snippets (43 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Install react-compiler-runtime

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-compiler/compiling-libraries.md

Installs react-compiler-runtime as a dependency to support React versions prior to version 19.

```bash
npm install react-compiler-runtime@latest
```


--------------------------------

### Install babel-plugin-react-compiler

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-compiler/compiling-libraries.md

Adds React Compiler as a development dependency to the library build process.

```bash
npm install -D babel-plugin-react-compiler@latest
```


--------------------------------

### Configure and install runtime for React 17 or 18

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-compiler/target.md

Targeting React 17 or 18 requires installing the `react-compiler-runtime` package and setting the corresponding target string. The compiler outputs imports using the standalone polyfill package.

```bash
npm install react-compiler-runtime@latest
```

```javascript
// For React 18
{
  target: '18'
}

// For React 17
{
  target: '17'
}
```

```javascript
// Compiled output uses the polyfill
import { c as _c } from 'react-compiler-runtime';
```


--------------------------------

### Invalid React Compiler configuration examples

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/config.md

Shows invalid configuration settings including typos in option names and unsupported option values.

```javascript
// ❌ Unknown option name
module.exports = {
  plugins: [
    ['babel-plugin-react-compiler', {
      compileMode: 'all' // Typo: should be compilationMode
    }]
  ]
};

// ❌ Invalid option value
module.exports = {
  plugins: [
    ['babel-plugin-react-compiler', {
      compilationMode: 'everything' // Invalid: use 'all' or 'infer'
    }]
  ]
};
```


--------------------------------

### Configuring React Compiler for React 17/18

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-compiler/configuration.md

Install the runtime package and set the target version configuration when using React 17 or 18.

```bash
npm install react-compiler-runtime@latest
```

```javascript
{
  target: '18' // or '17'
}
```


--------------------------------

### Create a Server Component reading from the filesystem (CounterContainer)

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/rsc/use-client.md

Does not require 'use client' because it is non-interactive and must run as a Server Component to read from the local filesystem.

```js
import { readFile } from 'node:fs/promises';
import Counter from './Counter';

export default async function CounterContainer() {
  const initialValue = await readFile('/path/to/counter_value');
  return <Counter initialValue={initialValue} />
}
```


--------------------------------

### Declare react-compiler-runtime and peerDependencies in package.json

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-compiler/compiling-libraries.md

Lists react-compiler-runtime in dependencies so it is bundled or installed for consumers, while declaring supported React versions in peerDependencies.

```json
{
  "dependencies": {
    "react-compiler-runtime": "^1.0.0"
  },
  "peerDependencies": {
    "react": "^17.0.0 || ^18.0.0 || ^19.0.0"
  }
}
```


--------------------------------

### Valid gating configurations for babel-plugin-react-compiler

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/gating.md

Demonstrates valid gating setups, including specifying both importSpecifierName and source for gradual adoption, as well as omitting gating to compile all components.

```js
// ✅ Complete gating configuration
module.exports = {
  plugins: [
    ['babel-plugin-react-compiler', {
      gating: {
        importSpecifierName: 'isCompilerEnabled', // exported function name
        source: 'featureFlags' // module name
      }
    }]
  ]
};

// featureFlags.js
export function isCompilerEnabled() {
  // ...
}

// ✅ No gating (compile everything)
module.exports = {
  plugins: [
    ['babel-plugin-react-compiler', {
      // No gating field - compiles all components
    }]
  ]
};
```


--------------------------------

### Adopting React Compiler gradually with annotation and infer modes

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-compiler/directives.md

Start compiler adoption using 'annotation' mode with 'use memo' for stable components, then switch to 'infer' mode while opting out problematic components using 'use no memo'.

```javascript
// Start with annotation mode
{
  compilationMode: 'annotation'
}

// Opt in stable components
function StableComponent() {
  "use memo";
  // Well-tested component
}

// Later, switch to infer mode and opt out problematic ones
function ProblematicComponent() {
  "use no memo"; // Fix issues before removing
  // ...
}
```


--------------------------------

### Correct configuration with valid options

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/config.md

Provides a correct configuration structure using documented options and supported option values.

```javascript
// ✅ Better: Valid configuration
module.exports = {
  plugins: [
    ['babel-plugin-react-compiler', {
      compilationMode: 'all', // or 'infer'
      panicThreshold: 'none', // or 'critical_errors', 'all_errors'
      // Only use documented options
    }]
  ]
};
```


--------------------------------

### Set up feature flag gating workflow

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-compiler/gating.md

Demonstrates defining the feature flag helper module, configuring the compiler gating option, and the resulting gated code output generated by the compiler.

```javascript
// src/utils/feature-flags.js
export function shouldUseCompiler() {
  // your logic here
  return getFeatureFlag('react-compiler-enabled');
}
```

```javascript
{
  gating: {
    source: './src/utils/feature-flags',
    importSpecifierName: 'shouldUseCompiler'
  }
}
```

```javascript
// Input
function Button(props) {
  return <button>{props.label}</button>;
}

// Output (simplified)
import { shouldUseCompiler } from './src/utils/feature-flags';

const Button = shouldUseCompiler()
  ? function Button_optimized(props) { /* compiled version */ }
  : function Button_original(props) { /* original version */ };
```


--------------------------------

### Valid ref access, state usage, and lazy initialization

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/refs.md

Examples of correct code patterns: reading refs inside effects or handlers, using useState for UI values, and initializing ref.current lazily.

```javascript
// ✅ Read ref in effects/handlers
function Component() {
  const ref = useRef(null);

  useEffect(() => {
    if (ref.current) {
      console.log(ref.current.offsetWidth); // OK in effect
    }
  });

  return <div ref={ref} />;
}

// ✅ Use state for UI values
function Component() {
  const [count, setCount] = useState(0);

  return (
    <button onClick={() => setCount(count + 1)}>
      {count}
    </button>
  );
}

// ✅ Lazy initialization of ref value
function Component() {
  const ref = useRef(null);

  // Initialize only once on first use
  if (ref.current === null) {
    ref.current = expensiveComputation(); // OK - lazy initialization
  }

  const handleClick = () => {
    console.log(ref.current); // Use the initialized value
  };

  return <button onClick={handleClick}>Click</button>;
}
```


--------------------------------

### Gradually adopting React Compiler across components

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-compiler/directives/use-memo.md

Demonstrates gradual adoption by applying "use memo" to leaf components first before moving up the component tree.

```javascript
// Start by optimizing leaf components
function Button({ onClick, children }) {
  "use memo";
  // ...
}

// Gradually move up the tree as you verify behavior
function ButtonGroup({ buttons }) {
  "use memo";
  // ...
}
```


--------------------------------

### Create an environment-agnostic component (FancyText)

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/rsc/use-client.md

Omits 'use client' because it uses neither server-only nor client-only features, allowing it to render on either side depending on where it is imported.

```js
export default function FancyText({title, text}) {
  return title
    ? <h1 className='fancy title'>{text}</h1>
    : <h3 className='fancy cursive'>{text}</h3>
}
```


--------------------------------

### Manual useMemo implementation

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/preserve-manual-memoization.md

Shows manual sorting memoization using useMemo with explicit dependencies.

```javascript
// Do I still need this?
function Component({items, sortBy}) {
  const sorted = useMemo(() => {
    return [...items].sort((a, b) => {
      return a[sortBy] - b[sortBy];
    });
  }, [items, sortBy]);

  return <List items={sorted} />;
}
```


--------------------------------

### Position "use no memo" before function body code

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-compiler/directives/use-no-memo.md

The directive must appear at the very start of the function body. Placing it after other statements will cause the directive to be ignored.

```javascript
// ❌ Wrong - directive after code
function Component() {
  const data = getData();
  "use no memo"; // Too late!
}

// ✅ Correct - directive first
function Component() {
  "use no memo";
  const data = getData();
}
```


--------------------------------

### Setting target React version for React 18

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-compiler/configuration.md

Specifies the React version for code generation compatibility. Using target '18' also requires installing the react-compiler-runtime package.

```javascript
// For React 18 projects
{
  target: '18' // Also requires react-compiler-runtime package
}
```


--------------------------------

### Invalid ref usage during render

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/refs.md

Examples of invalid code showing ref.current being read or modified during component rendering. Reading or writing refs during render breaks React expectations.

```javascript
// ❌ Reading ref during render
function Component() {
  const ref = useRef(0);
  const value = ref.current; // Don't read during render
  return <div>{value}</div>;
}

// ❌ Modifying ref during render
function Component({value}) {
  const ref = useRef(null);
  ref.current = value; // Don't modify during render
  return <div />;
}
```


--------------------------------

### Invalid unsupported syntax examples in React Compiler

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/unsupported-syntax.md

Demonstrates invalid uses of eval, with statements, and dynamic property evaluation inside components that prevent static analysis by React Compiler.

```javascript
// ❌ Using eval in component
function Component({ code }) {
  const result = eval(code); // Can't be analyzed
  return <div>{result}</div>;
}

// ❌ Using with statement
function Component() {
  with (Math) {
    // Changes scope dynamically
    return <div>{sin(PI / 2)}</div>;
  }
}

// ❌ Dynamic property access with eval
function Component({propName}) {
  const value = eval(`props.${propName}`);
  return <div>{value}</div>;
}
```


--------------------------------

### Common invalid hook usage patterns

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/rules-of-hooks.md

Examples of hook violations flagged by `rules-of-hooks`, including hooks in conditions, after early returns, inside callbacks, within `try/catch` blocks, or at the module level.

```javascript
// ❌ Hook in condition
if (isLoggedIn) {
  const [user, setUser] = useState(null);
}

// ❌ Hook after early return
if (!data) return <Loading />;
const [processed, setProcessed] = useState(data);

// ❌ Hook in callback
<button onClick={() => {
  const [clicked, setClicked] = useState(false);
}}/>

// ❌ `use` in try/catch
try {
  const data = use(promise);
} catch (e) {
  // error handling
}

// ❌ Hook at module level
const globalState = useState(0); // Outside component
```


--------------------------------

### Rendering static content at build time with Server Components

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/rsc/server-components.md

Renders static markdown at build time by reading directly from the filesystem. Excludes dependencies like marked and sanitize-html from the client bundle.

```javascript
import marked from 'marked'; // Not included in bundle
import sanitizeHtml from 'sanitize-html'; // Not included in bundle

async function Page({page}) {
  // NOTE: loads *during* render, when the app is built.
  const content = await file.readFile(`${page}.md`);

  return <div>{sanitizeHtml(marked(content))}</div>;
}
```


--------------------------------

### Troubleshoot missing compiler runtime errors

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-compiler/target.md

Resolves runtime errors when the compiler runtime module cannot be found. Check your React major version, install the runtime package if on React 17/18, and set the matching target string.

```bash
npm why react
```

```bash
npm install react-compiler-runtime@latest
```

```javascript
{
  target: '18' // Must match your React major version
}
```


--------------------------------

### Valid manual memoization and compiler-managed alternatives

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/preserve-manual-memoization.md

Demonstrates valid manual memoization with complete dependency arrays, as well as omitting manual memoization entirely so the React Compiler can optimize automatically.

```javascript
// ✅ Complete dependencies
function Component({ data, filter }) {
  const filtered = useMemo(
    () => data.filter(filter),
    [data, filter] // All dependencies included
  );

  return <List items={filtered} />;
}

// ✅ Or let the compiler handle it
function Component({ data, filter }) {
  // No manual memoization needed
  const filtered = data.filter(filter);
  return <List items={filtered} />;
}
```


--------------------------------

### Configuring dynamic component behavior with props

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/component-hook-factories.md

Shows the recommended pattern of passing props and JSX children directly to a module-level component instead of using a factory.

```javascript
// ✅ Better: Pass JSX as children
function Button({color, children}) {
  return (
    <button style={{backgroundColor: color}}>
      {children}
    </button>
  );
}

function App() {
  return (
    <>
      <Button color="red">Red</Button>
      <Button color="blue">Blue</Button>
    </>
  );
}
```


--------------------------------

### Mark client module boundary with 'use client'

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/rsc/use-client.md

Add 'use client' at the very top of a file above any imports to mark the module and its transitive dependencies as client code. When imported from a Server Component, bundlers treat this import as a client boundary.

```javascript
'use client';

import { useState } from 'react';
import { formatDate } from './formatters';
import Button from './button';

export default function RichTextEditor({ timestamp, text }) {
  const date = formatDate(timestamp);
  // ...
  const editButton = <Button />;
  // ...
}
```


--------------------------------

### Document reasons when using "use no memo"

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-compiler/directives/use-no-memo.md

Include an inline comment and issue reference explaining why optimization is disabled so it can be tracked and resolved later.

```javascript
// ✅ Good - clear explanation and tracking
function DataProcessor() {
  "use no memo"; // TODO: Remove after fixing rule of react violation
  // ...
}

// ❌ Bad - no explanation
function Mystery() {
  "use no memo";
  // ...
}
```


--------------------------------

### Defining client-server boundary using 'use client' in InspirationGenerator.js

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/rsc/use-client.md

Adding the 'use client' directive at the top of InspirationGenerator.js marks it and its imported modules as Client Components. The parent App component and passed children like Copyright remain Server Components.

```javascript
import FancyText from './FancyText';
import InspirationGenerator from './InspirationGenerator';
import Copyright from './Copyright';

export default function App() {
  return (
    <>
      <FancyText title text="Get Inspired App" />
      <InspirationGenerator>
        <Copyright year={2004} />
      </InspirationGenerator>
    </>
  );
}

```

```javascript
export default function FancyText({title, text}) {
  return title
    ? <h1 className='fancy title'>{text}</h1>
    : <h3 className='fancy cursive'>{text}</h3>
}
```

```javascript
'use client';

import { useState } from 'react';
import inspirations from './inspirations';
import FancyText from './FancyText';

export default function InspirationGenerator({children}) {
  const [index, setIndex] = useState(0);
  const quote = inspirations[index];
  const next = () => setIndex((index + 1) % inspirations.length);

  return (
    <>
      <p>Your inspirational quote is:</p>
      <FancyText text={quote} />
      <button onClick={next}>Inspire me again</button>
      {children}
    </>
  );
}
```

```javascript
export default function Copyright({year}) {
  return <p className='small'>©️ {year}</p>;
}
```

```javascript
export default [
  "Don’t let yesterday take up too much of today.” — Will Rogers",
  "Ambition is putting a ladder against the sky.",
  "A joy that's shared is a joy made double.",
];
```

```css
.fancy {
  font-family: 'Georgia';
}
.title {
  color: #007AA3;
  text-decoration: underline;
}
.cursive {
  font-style: italic;
}
.small {
  font-size: 10px;
}
```


--------------------------------

### Specify valid source path for gating module

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-compiler/gating.md

Shows valid package resolution paths and project root paths versus incorrect relative config paths.

```javascript
// ❌ Wrong: Relative to babel.config.js
{
  source: './src/flags',
  importSpecifierName: 'flag'
}

// ✅ Correct: Module resolution path
{
  source: '@myapp/feature-flags',
  importSpecifierName: 'flag'
}

// ✅ Also correct: Absolute path from project root
{
  source: './src/utils/flags',
  importSpecifierName: 'flag'
}
```


--------------------------------

### Valid patterns: managing state with React hooks and effects

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/globals.md

Illustrates valid alternatives including using useState for counters, useContext for shared values, and useEffect for synchronizing external globals.

```js
// ✅ Use state for counters
function Component() {
  const [clickCount, setClickCount] = useState(0);

  const handleClick = () => {
    setClickCount(c => c + 1);
  };

  return (
    <button onClick={handleClick}>
      Clicked: {clickCount} times
    </button>
  );
}

// ✅ Use context for global values
function Component() {
  const user = useContext(UserContext);
  return <div>User: {user.id}</div>;
}

// ✅ Synchronize external state with React
function Component({title}) {
  useEffect(() => {
    document.title = title; // OK in effect
  }, [title]);

  return <div>Page: {title}</div>;
}
```


--------------------------------

### Rendering a Client Component context provider in a Server Component

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/rsc/server-components.md

Server Components cannot create context directly, but can import and render a context provider created in a Client Component file.

```javascript
// user-context.js
'use client';
import { createContext } from 'react';

export const UserContext = createContext(null);
```

```javascript
// server-component.js
import { UserContext } from './user-context';

export async function Layout({ children }) {
  const currentUser = await getCurrentUser();

  return (
    <UserContext value={currentUser}>
      {children}
    </UserContext>
  );
}
```


--------------------------------

### Run effects with dependencies or guard execution using a ref

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/exhaustive-deps.md

Includes all dependencies in the array or uses a useRef guard to ensure an effect's logic only executes once while remaining compliant.

```javascript
// ✅ Include dependency
useEffect(() => {
  sendAnalytics(userId);
}, [userId]);

// ✅ Or use a ref guard inside an effect
const sent = useRef(false);

useEffect(() => {
  if (sent.current) {
    return;
  }

  sent.current = true;
  sendAnalytics(userId);
}, [userId]);
```


--------------------------------

### Fetching dynamic data using client Effects and API routes

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/rsc/server-components.md

Illustrates the traditional client-side fetching pattern where components fetch data sequentially in useEffect, causing network waterfalls and requiring separate API endpoints.

```javascript
// bundle.js
function Note({id}) {
  const [note, setNote] = useState('');
  // NOTE: loads *after* first render.
  useEffect(() => {
    fetch(`/api/notes/${id}`).then(data => {
      setNote(data.note);
    });
  }, [id]);

  return (
    <div>
      <Author id={note.authorId} />
      <p>{note}</p>
    </div>
  );
}

function Author({id}) {
  const [author, setAuthor] = useState('');
  // NOTE: loads *after* Note renders.
  // Causing an expensive client-server waterfall.
  useEffect(() => {
    fetch(`/api/authors/${id}`).then(data => {
      setAuthor(data.author);
    });
  }, [id]);

  return <span>By: {author.name}</span>;
}
```

```javascript
// api
import db from './database';

app.get(`/api/notes/:id`, async (req, res) => {
  const note = await db.notes.get(id);
  res.send({note});
});

app.get(`/api/authors/:id`, async (req, res) => {
  const author = await db.authors.get(id);
  res.send({author});
});
```


--------------------------------

### Valid state updates using spread syntax

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/immutability.md

Demonstrates valid immutable state updates by creating new array and object references with spread syntax.

```javascript
// ✅ Create new array
function Component() {
  const [items, setItems] = useState([1, 2, 3]);

  const addItem = () => {
    setItems([...items, 4]); // New array
  };
}

// ✅ Create new object
function Component() {
  const [user, setUser] = useState({name: 'Alice'});

  const updateName = () => {
    setUser({...user, name: 'Bob'}); // New object
  };
}
```


--------------------------------

### Valid array item addition using spread syntax

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/immutability.md

Demonstrates the correct way to add items to an array state by spreading elements into a new array.

```javascript
// ✅ Better: Create a new array
function TodoList() {
  const [todos, setTodos] = useState([]);

  const addTodo = (id, text) => {
    setTodos([...todos, {id, text}]);
    // Or: setTodos(todos => [...todos, {id: Date.now(), text}])
  };

  return (
    <ul>
      {todos.map(todo => <li key={todo.id}>{todo.text}</li>)}
    </ul>
  );
}
```


--------------------------------

### Valid syntax alternatives for React Compiler

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/unsupported-syntax.md

Demonstrates static and analyzable alternatives to eval and with statements, such as direct property indexing and standard Math namespace access.

```javascript
// ✅ Use normal property access
function Component({propName, props}) {
  const value = props[propName]; // Analyzable
  return <div>{value}</div>;
}

// ✅ Use standard Math methods
function Component() {
  return <div>{Math.sin(Math.PI / 2)}</div>;
}
```


--------------------------------

### Build interactive component with 'use client' and useState (src/App.js)

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/rsc/use-client.md

Requires the 'use client' directive at the top because it uses the useState Hook and event handlers to handle user interactivity.

```js
'use client';

import { useState } from 'react';

export default function Counter({initialValue = 0}) {
  const [countValue, setCountValue] = useState(initialValue);
  const increment = () => setCountValue(countValue + 1);
  const decrement = () => setCountValue(countValue - 1);
  return (
    <>
      <h2>Count Value: {countValue}</h2>
      <button onClick={increment}>+1</button>
      <button onClick={decrement}>-1</button>
    </>
  );
}
```


--------------------------------

### Configure Babel with babel-plugin-react-compiler in babel.config.js

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-compiler/compiling-libraries.md

Adds babel-plugin-react-compiler to the plugins array in babel.config.js to compile library code.

```javascript
// babel.config.js
module.exports = {
  plugins: [
    'babel-plugin-react-compiler',
  ],
  // ... other config
};
```


--------------------------------

### Reading data directly in async Server Components

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/rsc/server-components.md

Demonstrates loading data directly during rendering inside async Server Components without creating dedicated API endpoints.

```javascript
import db from './database';

async function Note({id}) {
  // NOTE: loads *during* render.
  const note = await db.notes.get(id);
  return (
    <div>
      <Author id={note.authorId} />
      <p>{note}</p>
    </div>
  );
}

async function Author({id}) {
  // NOTE: loads *after* Note,
  // but is fast if data is co-located.
  const author = await db.authors.get(id);
  return <span>By: {author.name}</span>;
}
```


--------------------------------

### Common configuration mistakes in Babel config

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/config.md

Illustrates errors that cause configuration failures, such as misspelled option names, incorrect types, and unrecognized options.

```javascript
// ❌ Wrong: Common configuration mistakes
module.exports = {
  plugins: [
    ['babel-plugin-react-compiler', {
      // Typo in option name
      compilationMod: 'all',
      // Wrong value type
      panicThreshold: true,
      // Unknown option
      optimizationLevel: 'max'
    }]
  ]
};
```


--------------------------------

### Import and invoke a Server Function in a Client Component

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/rsc/server-functions.md

Export a Server Function from a dedicated 'use server' module and import it into a Client Component. The bundler replaces the import with a server reference that triggers a server request upon invocation.

```js
"use server";

export async function createNote() {
  await db.notes.create();
}
```

```js
"use client";
import {createNote} from './actions';

function EmptyNote() {
  console.log(createNote);
  // {$$typeof: Symbol.for("react.server.reference"), $$id: 'createNote'}
  <button onClick={() => createNote()} />
}
```


--------------------------------

### Basic logging for compilation results

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/react-compiler/logger.md

Tracks compilation success and skips by switching on the event kind property.

```javascript
{
  logger: {
    logEvent(filename, event) {
      switch (event.kind) {
        case 'CompileSuccess': {
          console.log(`✅ Compiled: ${filename}`);
          break;
        }
        case 'CompileError': {
          console.log(`❌ Skipped: ${filename}`);
          break;
        }
        default: {}
      }
    }
  }
}
```


--------------------------------

### Viewing rendered client output from Server Components

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/rsc/server-components.md

Shows the rendered HTML output sent to the client browser instead of original component definitions and bundle code.

```javascript
<div>
  <span>By: The React Team</span>
  <p>React 19 is...</p>
</div>
```


--------------------------------

### Incorrect component factory for dynamic behavior

Source: https://github.com/reactjs/react.dev/blob/main/src/content/reference/eslint-plugin-react-hooks/lints/component-hook-factories.md

Demonstrates an incorrect factory pattern used to generate customized button components dynamically.

```javascript
// ❌ Wrong: Factory pattern
function makeButton(color) {
  return function Button({children}) {
    return (
      <button style={{backgroundColor: color}}>
        {children}
      </button>
    );
  };
}

const RedButton = makeButton('red');
const BlueButton = makeButton('blue');
```
