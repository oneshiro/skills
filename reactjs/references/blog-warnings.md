# React — Blog & Warnings

Sourced snippets (7 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Check for duplicate React installations using npm ls react

Source: https://github.com/reactjs/react.dev/blob/main/src/content/warnings/invalid-hook-call-warning.md

Runs a dependency check in your project folder to verify whether more than one copy of the react package is installed.

```bash
npm ls react
```


--------------------------------

### Inspect react.dev Source Directory Layout

Source: https://github.com/reactjs/react.dev/blob/main/CLAUDE.md

Directory structure of the src/ folder showing MDX documentation content organization, components, pages, hooks, utils, and styling files.

```text
src/
├── content/           # Documentation content (MDX files)
│   ├── learn/         # Tutorial/learning content
│   ├── reference/     # API reference docs
│   ├── blog/          # Blog posts
│   └── community/     # Community pages
├── components/        # React components
├── pages/             # Next.js pages
├── hooks/             # Custom React hooks
├── utils/             # Utility functions
└── styles/            # CSS/Tailwind styles
```


--------------------------------

### Style view transitions, loaders, and video thumbnail layouts with CSS

Source: https://github.com/reactjs/react.dev/blob/main/src/content/blog/2026/09/09/react-19-3.md

Defines CSS layout, shimmer animation keyframes for loading placeholders, and view transition pseudo-elements for fallback rendering.

```css
::view-transition-old(*),
::view-transition-new(*) {
  /* animation-duration: 750ms; */
  /* animation-timing-function: cubic-bezier(0.22, 1, 0.36, 1); */
}
#root {
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 200px;
}
button {
  border: none;
  border-radius: 50%;
  width: 50px;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #f0f8ff;
  color: white;
  font-size: 20px;
  cursor: pointer;
  transition: background-color 0.3s, border 0.3s;
}
button:hover {
  border: 2px solid #ccc;
  background-color: #e0e8ff;
}
.thumbnail {
  position: relative;
  aspect-ratio: 16 / 9;
  display: flex;
  overflow: hidden;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-radius: 0.5rem;
  outline-offset: 2px;
  width: 8rem;
  vertical-align: middle;
  background-color: #ffffff;
  background-size: cover;
  user-select: none;
}
.thumbnail.blue {
  background-image: conic-gradient(at top right, #c76a15, #087ea4, #2b3491);
}
.loading {
  background-image: linear-gradient(
    90deg,
    rgba(173, 216, 230, 0.3) 25%,
    rgba(135, 206, 250, 0.5) 50%,
    rgba(173, 216, 230, 0.3) 75%
  );
  background-size: 200% 100%;
  animation: shimmer 1.5s infinite;
  z-index: 999;
}
@keyframes shimmer {
  0% {
    background-position: -200% 0;
  }
  100% {
    background-position: 200% 0;
  }
}
.video {
  display: flex;
  flex-direction: row;
  gap: 0.75rem;
  align-items: center;
  margin-top: 1em;
}
.video .link {
  display: flex;
  flex-direction: row;
  flex: 1 1 0;
  gap: 0.125rem;
  outline-offset: 4px;
}
.video .info {
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin-left: 8px;
  gap: 0.125rem;
}
.video-title {
  font-size: 15px;
  line-height: 1.25;
  font-weight: 700;
  color: #23272f;
}
.video-title.loading {
  height: 20px;
  width: 80px;
  border-radius: 0.5rem;
}
.video-description {
  color: #5e687e;
  font-size: 13px;
  border-radius: 0.5rem;
}
.video-description.loading {
  height: 15px;
  width: 100px;
}
```


--------------------------------

### Invalid Hook call patterns breaking the Rules of Hooks

Source: https://github.com/reactjs/react.dev/blob/main/src/content/warnings/invalid-hook-call-warning.md

Examples of unsupported Hook call patterns that trigger the invalid Hook call warning. Hooks cannot be placed inside conditions, loops, event handlers, useMemo callbacks, class components, or after conditional returns.

```javascript
function Bad({ cond }) {
  if (cond) {
    // 🔴 Bad: inside a condition (to fix, move it outside!)
    const theme = useContext(ThemeContext);
  }
  // ...
}

function Bad() {
  for (let i = 0; i < 10; i++) {
    // 🔴 Bad: inside a loop (to fix, move it outside!)
    const theme = useContext(ThemeContext);
  }
  // ...
}

function Bad({ cond }) {
  if (cond) {
    return;
  }
  // 🔴 Bad: after a conditional return (to fix, move it before the return!)
  const theme = useContext(ThemeContext);
  // ...
}

function Bad() {
  function handleClick() {
    // 🔴 Bad: inside an event handler (to fix, move it outside!)
    const theme = useContext(ThemeContext);
  }
  // ...
}

function Bad() {
  const style = useMemo(() => {
    // 🔴 Bad: inside useMemo (to fix, move it outside!)
    const theme = useContext(ThemeContext);
    return createStyle(theme);
  });
  // ...
}

class Bad extends React.Component {
  render() {
    // 🔴 Bad: inside a class component (to fix, write a function component instead of a class!)
    useEffect(() => {})
    // ...
  }
}
```


--------------------------------

### Implement Video and VideoPlaceholder components in src/Video.js

Source: https://github.com/reactjs/react.dev/blob/main/src/content/blog/2026/09/09/react-19-3.md

Exports the Video component and its corresponding shimmer placeholder component used as fallback UI during Suspense transitions.

```js
import { ViewTransition } from 'react';

function Thumbnail({video, children}) {
  return (
    <div
      aria-hidden="true"
      tabIndex={-1}
      className={`thumbnail ${video.image}`}
    />
  );
}

export function Video({video}) {
  return (
    <div className="video">
      <div className="link">
        <Thumbnail video={video}></Thumbnail>
        <div className="info">
          <div className="video-title">{video.title}</div>
          <div className="video-description">{video.description}</div>
        </div>
      </div>
    </div>
  );
}

export function VideoPlaceholder() {
  const video = {image: 'loading'};
  return (
    <div className="video">
      <div className="link">
        <Thumbnail video={video}></Thumbnail>
        <div className="info">
          <div className="video-title loading" />
          <div className="video-description loading" />
        </div>
      </div>
    </div>
  );
}
```


--------------------------------

### Define CSS styles for thumbnail and video components

Source: https://github.com/reactjs/react.dev/blob/main/src/content/blog/2026/09/09/react-19-3.md

Provides layout and styling rules for root layout, button interactions, thumbnail gradients, and video list items.

```css
#root {
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 200px;
}
button {
  border: none;
  border-radius: 50%;
  width: 50px;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #f0f8ff;
  color: white;
  font-size: 20px;
  cursor: pointer;
  transition: background-color 0.3s, border 0.3s;
}
button:hover {
  border: 2px solid #ccc;
  background-color: #e0e8ff;
}
.thumbnail {
  position: relative;
  aspect-ratio: 16 / 9;
  display: flex;
  overflow: hidden;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-radius: 0.5rem;
  outline-offset: 2px;
  width: 8rem;
  vertical-align: middle;
  background-color: #ffffff;
  background-size: cover;
  user-select: none;
}
.thumbnail.blue {
  background-image: conic-gradient(at top right, #c76a15, #087ea4, #2b3491);
}
.video {
  display: flex;
  flex-direction: row;
  gap: 0.75rem;
  align-items: center;
  margin-top: 1em;
}
.video .link {
  display: flex;
  flex-direction: row;
  flex: 1 1 0;
  gap: 0.125rem;
  outline-offset: 4px;
  cursor: pointer;
}
.video .info {
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin-left: 8px;
  gap: 0.125rem;
}
.video .info:hover {
  text-decoration: underline;
}
.video-title {
  font-size: 15px;
  line-height: 1.25;
  font-weight: 700;
  color: #23272f;
}
.video-description {
  color: #5e687e;
  font-size: 13px;
}
```


--------------------------------

### Execute Development and Verification Commands

Source: https://github.com/reactjs/react.dev/blob/main/CLAUDE.md

Standard yarn commands used for building, linting, TypeScript type checking, and running aggregated repository checks.

```bash
yarn build         # Production build
yarn lint          # Run ESLint
yarn lint:fix      # Auto-fix lint issues
yarn tsc           # TypeScript type checking
yarn check-all     # Run prettier, lint:fix, tsc, and rss together
```
