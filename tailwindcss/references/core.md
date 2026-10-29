# Tailwind CSS — Core Concepts & Setup

Sourced snippets (128 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Install dependencies with pnpm

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/README.md

Installs the required project dependencies prior to running the Next.js documentation site locally.

```bash
pnpm install
```


--------------------------------

### Start the development server with pnpm

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/README.md

Launches the local Next.js development server for the Tailwind CSS documentation site.

```bash
pnpm run dev
```


--------------------------------

### Style initial render appearance using the starting variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Use the `starting` variant to set the initial appearance of an element when first rendered or transitioned from `display: none`.

```html
<!-- [!code classes:starting:open:opacity-0] -->
<div>
  <button popovertarget="my-popover">Check for updates</button>
  <div popover id="my-popover" class="opacity-0 starting:open:opacity-0 ...">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Configure and use subpath imports with @reference

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/functions-and-directives.mdx

Configure subpath aliases in package.json to reference CSS files in components across CLI, Vite, or PostCSS setups.

```json
// [!code filename:package.json]
{
  // ...
  "imports": {
    /* [!code highlight:2] */
    "#app.css": "./src/css/app.css"
  }
}
```

```html
<!-- [!code filename:Vue] -->
<template>
  <h1>Hello world!</h1>
</template>

<style>
  /* [!code highlight:2] */
  @reference "#app.css";

  h1 {
    @apply text-2xl font-bold text-red-500;
  }
</style>
```


--------------------------------

### Implement three-way theme toggle with system preference support

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/dark-mode.mdx

Manage theme state between light, dark, and system preferences using `localStorage` and `window.matchMedia()`. Place the script inline within `<head>` to prevent flash of unstyled content (FOUC).

```javascript
// [!code filename:spaghetti.js]
// On page load or when changing themes, best to add inline in `head` to avoid FOUC
document.documentElement.classList.toggle(
  "dark",
  localStorage.theme === "dark" ||
    (!("theme" in localStorage) && window.matchMedia("(prefers-color-scheme: dark)").matches),
);

// Whenever the user explicitly chooses light mode
localStorage.theme = "light";

// Whenever the user explicitly chooses dark mode
localStorage.theme = "dark";

// Whenever the user explicitly chooses to respect the OS preference
localStorage.removeItem("theme");
```


--------------------------------

### Configuring source detection on individual utilities import

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/preflight.mdx

Add source(none) to the utilities.css import to adjust source detection for generated utility classes.

```css
/* [!code filename:CSS] */
@layer theme, base, components, utilities;

@import "tailwindcss/theme.css" layer(theme);
@import "tailwindcss/utilities.css" layer(utilities); /* [!code --] */
@import "tailwindcss/utilities.css" layer(utilities) source(none); /* [!code ++] */
```


--------------------------------

### Apply responsive utility variants using breakpoint prefixes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/responsive-design.mdx

Prefix any utility class with a breakpoint name followed by a colon to apply styles conditionally at specific screen widths.

```html
<!-- [!code filename:HTML]  -->
<!-- [!code word:md\:w-32] -->
<!-- [!code word:lg\:w-48] -->
<!-- Width of 16 by default, 32 on medium screens, and 48 on large screens -->
<img class="w-16 md:w-32 lg:w-48" src="..." />
```


--------------------------------

### Configure prefix in CSS and inspect generated prefixed variables

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/upgrade-guide.mdx

Configure prefixes using prefix() with @import in app.css while defining un-prefixed theme variables, resulting in prefixed CSS variables in dist.css.

```css
@import "tailwindcss" prefix(tw);

@theme {
  --font-display: "Satoshi", "sans-serif";

  --breakpoint-3xl: 120rem;

  --color-avocado-100: oklch(0.99 0 0);
  --color-avocado-200: oklch(0.98 0.04 113.22);
  --color-avocado-300: oklch(0.94 0.11 115.03);

  /* ... */
}
```

```css
:root {
  --tw-font-display: "Satoshi", "sans-serif";

  --tw-breakpoint-3xl: 120rem;

  --tw-color-avocado-100: oklch(0.99 0 0);
  --tw-color-avocado-200: oklch(0.98 0.04 113.22);
  --tw-color-avocado-300: oklch(0.94 0.11 115.03);

  /* ... */
}
```


--------------------------------

### Apply responsive layout using sm: breakpoint prefix

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/styling-with-utility-classes.mdx

Prefixes a utility with a breakpoint name to trigger layout changes at or above that specific screen size.

```html
<!-- [!code classes:sm:grid-cols-3] -->
<div class="grid grid-cols-2 sm:grid-cols-3">
  <!-- ... -->
</div>
```


--------------------------------

### Map props to static complete class names in JSX

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/detecting-classes-in-source-files.mdx

Demonstrates mapping prop values to full static utility class strings.

```jsx
// [!code filename:JSX]
function Button({ color, children }) {
  const colorVariants = {
    blue: "bg-blue-600 hover:bg-blue-500",
    red: "bg-red-600 hover:bg-red-500",
  };

  return <button className={`${colorVariants[color]} ...`}>{children}</button>;
}
```


--------------------------------

### Defining a custom color palette with --color-*: initial

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/colors.mdx

Disable all default colors entirely with `--color-*: initial` and specify an entirely custom color palette.

```css
/* [!code filename:CSS] */
@import "tailwindcss";

@theme {
  /* [!code highlight:7] */
  --color-*: initial;
  --color-white: #fff;
  --color-purple: #3f3cbb;
  --color-midnight: #121063;
  --color-tahiti: #3ab7bf;
  --color-bermuda: #78dcca;
}
```


--------------------------------

### Apply utility classes with a prefix

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/upgrade-guide.mdx

Use prefixed class names where prefixes act like variants placed at the beginning of the class.

```html
<!-- [!code classes:tw:bg-red-500,tw:flex,tw:hover:bg-red-600] -->
<div class="tw:flex tw:bg-red-500 tw:hover:bg-red-600">
  <!-- ... -->
</div>
```


--------------------------------

### Applying color palette shade steps

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/colors.mdx

Demonstrates applying the 11 default color steps ranging from 50 (lightest) to 950 (darkest). These shade steps work across all color-related utility classes.

```html
<!-- [!code classes:bg-sky-50,bg-sky-100,bg-sky-200,bg-sky-300,bg-sky-400,bg-sky-500,bg-sky-600,bg-sky-700,bg-sky-800,bg-sky-900,bg-sky-950] -->
<div>
  <div class="bg-sky-50"></div>
  <div class="bg-sky-100"></div>
  <div class="bg-sky-200"></div>
  <div class="bg-sky-300"></div>
  <div class="bg-sky-400"></div>
  <div class="bg-sky-500"></div>
  <div class="bg-sky-600"></div>
  <div class="bg-sky-700"></div>
  <div class="bg-sky-800"></div>
  <div class="bg-sky-900"></div>
  <div class="bg-sky-950"></div>
</div>
```


--------------------------------

### Disabling Preflight by omitting preflight.css

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/preflight.mdx

Disable Preflight completely by importing theme.css and utilities.css individually while omitting the preflight.css import.

```css
/* [!code filename:CSS] */
@layer theme, base, components, utilities;

@import "tailwindcss/theme.css" layer(theme);
@import "tailwindcss/preflight.css" layer(base); /* [!code --] */
@import "tailwindcss/utilities.css" layer(utilities);
```


--------------------------------

### Load legacy configuration with @config

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/functions-and-directives.mdx

Loads a legacy JavaScript-based configuration file. Options like corePlugins, safelist, and separator are not supported in v4.0.

```css
/* [!code filename:CSS] */
@config "../../tailwind.config.js";
```


--------------------------------

### Load legacy plugin with @plugin

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/functions-and-directives.mdx

Loads a legacy JavaScript-based plugin using either a package name or a local file path.

```css
/* [!code filename:CSS] */
@plugin "@tailwindcss/typography";
```


--------------------------------

### Styling lists with utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/preflight.mdx

Apply list-style-position and list-style-type utility classes to restore styling to lists.

```html
<!-- [!code filename:HTML] -->
<ul class="list-inside list-disc">
  <li>One</li>
  <li>Two</li>
  <li>Three</li>
</ul>
```


--------------------------------

### Build a responsive profile card with state variants in HTML

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/styling-with-utility-classes.mdx

Applies Tailwind utility classes to construct a responsive card component featuring responsive layout adjustments and interactive hover/active button states.

```html
<!-- [!code classes:sm:flex-row,sm:py-4,sm:gap-6,sm:mx-0,sm:shrink-0,sm:text-left,sm:items-center] -->
<!-- [!code classes:hover:text-white,hover:bg-purple-600,hover:border-transparent,active:bg-purple-700] -->
<div class="flex flex-col gap-2 p-8 sm:flex-row sm:items-center sm:gap-6 sm:py-4 ...">
  <img class="mx-auto block h-24 rounded-full sm:mx-0 sm:shrink-0" src="/img/erin-lindford.jpg" alt="" />
  <div class="space-y-2 text-center sm:text-left">
    <div class="space-y-0.5">
      <p class="text-lg font-semibold text-black">Erin Lindford</p>
      <p class="font-medium text-gray-500">Product Engineer</p>
    </div>
    <!-- prettier-ignore -->
    <button class="border-purple-200 text-purple-600 hover:border-transparent hover:bg-purple-600 hover:text-white active:bg-purple-700 ...">
      Message
    </button>
  </div>
</div>
```


--------------------------------

### Define and apply a custom supports-* variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Configure shortcuts for common `@supports` rules using `@custom-variant` and apply them directly in markup.

```css
@custom-variant supports-grid {
  @supports (display: grid) {
    @slot;
  }
}
```

```html
<!-- [!code classes:supports-grid:grid] -->
<div class="supports-grid:grid">
  <!-- ... -->
</div>
```


--------------------------------

### Map props to complex static class combinations in JSX

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/detecting-classes-in-source-files.mdx

Demonstrates mapping prop values to different complete utility class variants including colors and text styling.

```jsx
// [!code filename:JSX]
function Button({ color, children }) {
  const colorVariants = {
    blue: "bg-blue-600 hover:bg-blue-500 text-white",
    red: "bg-red-500 hover:bg-red-400 text-white",
    yellow: "bg-yellow-300 hover:bg-yellow-400 text-black",
  };

  return <button className={`${colorVariants[color]} ...`}>{children}</button>;
}
```


--------------------------------

### Apply color shades with utility classes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/compatibility.mdx

Use predefined utility class shades to handle color adjustments like hover states rather than preprocessing color functions.

```html
<!-- [!code word:hover\:bg-indigo-600] -->
<button class="bg-indigo-500 hover:bg-indigo-600 ...">
  <!-- ... -->
</button>
```


--------------------------------

### Defining functional utilities with @utility and --value()

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/adding-custom-styles.mdx

Create functional utilities that accept arguments using the wildcard syntax `@utility name-*` paired with the `--value()` function.

```css
/* [!code filename:CSS] */
@utility tab-* {
  /* prettier-ignore */
  tab-size: --value(--tab-size-*);
}
```


--------------------------------

### Importing theme utilities in Vue with @reference

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/upgrade-guide.mdx

Imports theme variables, utilities, and variants into isolated component style blocks using @reference without duplicating CSS bundle output.

```html
<!-- [!code filename:Vue] -->
<template>
  <h1>Hello world!</h1>
</template>

<style>
  /* [!code highlight:2] */
  @reference "../../app.css";

  h1 {
    @apply text-2xl font-bold text-red-500;
  }
</style>
```


--------------------------------

### Overriding an entire theme namespace with initial

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/theme.mdx

Set a namespace to initial using asterisk syntax to remove all default utilities in that namespace and supply custom values.

```css
/* [!code filename:app.css] */
@import "tailwindcss";

@theme {
  /* [!code highlight:2] */
  --color-*: initial;
  --color-white: #fff;
  --color-purple: #3f3cbb;
  --color-midnight: #121063;
  --color-tahiti: #3ab7bf;
  --color-bermuda: #78dcca;
}
```


--------------------------------

### Applying prefix to theme and utilities imports

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/preflight.mdx

Add prefix(tw) to both theme.css and utilities.css imports when applying a prefix across variables and utility classes.

```css
/* [!code filename:CSS] */
@layer theme, base, components, utilities;

@import "tailwindcss/theme.css" layer(theme); /* [!code --] */
@import "tailwindcss/utilities.css" layer(utilities); /* [!code --] */
@import "tailwindcss/theme.css" layer(theme) prefix(tw); /* [!code ++] */
@import "tailwindcss/utilities.css" layer(utilities) prefix(tw); /* [!code ++] */
```


--------------------------------

### Disabling the default theme with global initial

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/theme.mdx

Set the global namespace --*: initial to disable all default theme variables and define an entirely custom theme.

```css
/* [!code filename:app.css] */
@import "tailwindcss";

@theme {
  /* [!code highlight:2] */
  --*: initial;

  --spacing: 4px;

  --font-body: Inter, sans-serif;

  --color-lagoon: oklch(0.72 0.11 221.19);
  --color-coral: oklch(0.74 0.17 40.24);
  --color-driftwood: oklch(0.79 0.06 74.59);
  --color-tide: oklch(0.49 0.08 205.88);
  --color-dusk: oklch(0.82 0.15 72.09);
}
```


--------------------------------

### Use complete class names in HTML

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/detecting-classes-in-source-files.mdx

Demonstrates the correct approach of providing full class names in conditional expressions so they can be extracted during scanning.

```html
<!-- [!code filename:HTML] -->
<!-- [!code word:text-red-600] -->
<!-- [!code word:text-green-600] -->
<div class="{{ error ? 'text-red-600' : 'text-green-600' }}"></div>
```


--------------------------------

### Target mobile screens with unprefixed utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/responsive-design.mdx

Apply unprefixed utility classes for default mobile styling, then override them at larger breakpoints using prefixed variants like sm:.

```html
<!-- [!code filename:HTML]  -->
<!-- This will center text on mobile, and left align it on screens 640px and wider -->
<div class="text-center sm:text-left"></div>
```


--------------------------------

### Creating arbitrary peer variants with custom selector matching

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Pass custom selectors in square brackets to create on-the-fly peer variants and inspect the resulting CSS output.

```html
<form>
  <label for="email">Email:</label>
  <input id="email" name="email" type="email" class="is-dirty peer" required />
  <div class="peer-[.is-dirty]:peer-required:block hidden">This field is required.</div>
  <!-- ... -->
</form>
```

```css
.peer-\[\.is-dirty\]\:peer-required\:block {
  &:is(:where(.peer):is(.is-dirty) ~ *) {
    &:is(:where(.peer):required ~ *) {
      display: block;
    }
  }
}
```


--------------------------------

### Using arbitrary properties

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/adding-custom-styles.mdx

Write unstyled or unsupported CSS properties directly using square bracket notation.

```html
<!-- [!code filename:HTML] -->
<!-- [!code classes:[mask-type:luminance]] -->
<div class="[mask-type:luminance]">
  <!-- ... -->
</div>
```


--------------------------------

### Using at-rules in arbitrary variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

At-rules like @media or @supports can be written in arbitrary variants without requiring an '&' nesting placeholder.

```html
<!-- [!code classes:[@supports(display:grid)]:grid] -->
<div class="flex [@supports(display:grid)]:grid">
  <!-- ... -->
</div>
```

```css
.\[\@supports\(display\:grid\)\]\:grid {
  @supports (display:grid) {
    display: grid;
  }
}
```


--------------------------------

### Build a responsive card component using md: breakpoint modifiers

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/responsive-design.mdx

Applies md:flex on medium screens and larger to convert the stacked block layout into a horizontal flex container. Uses md:max-w-2xl, md:shrink-0, and md:h-full md:w-48 to adjust the card width and image dimensions.

```html
<!-- [!code word:md\:max-w-2xl] -->
<div class="mx-auto max-w-md overflow-hidden rounded-xl bg-white shadow-md md:max-w-2xl">
  <!-- [!code word:md\:flex] -->
  <div class="md:flex">
    <!-- [!code word:md\:shrink-0] -->
    <div class="md:shrink-0">
      <!-- [!code word:md\:h-full] -->
      <!-- [!code word:md\:w-48] -->
      <img
        class="h-48 w-full object-cover md:h-full md:w-48"
        src="/img/building.jpg"
        alt="Modern building architecture"
      />
    </div>
    <div class="p-8">
      <div class="text-sm font-semibold tracking-wide text-indigo-500 uppercase">Company retreats</div>
      <a href="#" class="mt-1 block text-lg leading-tight font-medium text-black hover:underline">
        Incredible accommodation for your team
      </a>
      <p class="mt-2 text-gray-500">
        Looking to take your team away on a retreat to enjoy awesome food and take in some sunshine? We have a list of
        places to do just that.
      </p>
    </div>
  </div>
</div>
```


--------------------------------

### Repeating utility classes for avatar elements

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/styling-with-utility-classes.mdx

Demonstrates repeating utility class patterns across multiple image elements in an avatar group list.

```html
<!-- [!code classes:inline-block,h-12,w-12,rounded-full,ring-2,ring-white] -->
<div>
  <div class="flex items-center space-x-2 text-base">
    <h4 class="font-semibold text-slate-900">Contributors</h4>
    <span class="bg-slate-100 px-2 py-1 text-xs font-semibold text-slate-700 ...">204</span>
  </div>
  <div class="mt-3 flex -space-x-2 overflow-hidden">
    <!-- prettier-ignore -->
    <img class="inline-block h-12 w-12 rounded-full ring-2 ring-white" src="https://images.unsplash.com/photo-1491528323818-fdd1faba62cc?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="" />
    <!-- prettier-ignore -->
    <img class="inline-block h-12 w-12 rounded-full ring-2 ring-white" src="https://images.unsplash.com/photo-1550525811-e5869dd03032?ixlib=rb-1.2.1&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="" />
    <!-- prettier-ignore -->
    <img class="inline-block h-12 w-12 rounded-full ring-2 ring-white" src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2.25&w=256&h=256&q=80" alt="" />
    <!-- prettier-ignore -->
    <img class="inline-block h-12 w-12 rounded-full ring-2 ring-white" src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="" />
    <!-- prettier-ignore -->
    <img class="inline-block h-12 w-12 rounded-full ring-2 ring-white" src="https://images.unsplash.com/photo-1517365830460-955ce3ccd263?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="" />
  </div>
  <div class="mt-3 text-sm font-medium">
    <a href="#" class="text-blue-500">+ 198 others</a>
  </div>
</div>
```


--------------------------------

### Run build commands using @tailwindcss/cli

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/upgrade-guide.mdx

Update terminal build commands to execute the dedicated @tailwindcss/cli package instead of the legacy v3 CLI.

```sh
/* [!code filename:Terminal] */
  # [!code --:2]
npx tailwindcss -i input.css -o output.css
  # [!code ++:2]
npx @tailwindcss/cli -i input.css -o output.css
```


--------------------------------

### Migrating from theme() function to CSS variables in CSS

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/upgrade-guide.mdx

Replaces legacy theme() function calls with direct CSS variable references.

```css
/* [!code filename:CSS] */
.my-class {
  /* [!code --:2] */
  background-color: theme(colors.red.500);
  /* [!code ++:2] */
  background-color: var(--color-red-500);
}
```


--------------------------------

### Style an input when placeholder is visible using placeholder-shown

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Applies styling to an input element while its placeholder text remains displayed.

```html
<!-- [!code classes:placeholder-shown:border-gray-500] -->
<input class="placeholder-shown:border-gray-500 ..." placeholder="you@example.com" />
```


--------------------------------

### Using arbitrary values with square brackets

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/adding-custom-styles.mdx

Use square bracket notation to generate utility classes on the fly with custom values.

```html
<!-- [!code filename:HTML] -->
<!-- [!code classes:top-[117px]] -->
<div class="top-[117px]">
  <!-- ... -->
</div>
```


--------------------------------

### Using arbitrary values across various utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/adding-custom-styles.mdx

Arbitrary values work across colors, font sizes, and pseudo-element content.

```html
<!-- [!code filename:HTML] -->
<!-- [!code classes:bg-[#bada55],text-[22px],before:content-['Festivus']] -->
<div class="bg-[#bada55] text-[22px] before:content-['Festivus']">
  <!-- ... -->
</div>
```


--------------------------------

### Apply arbitrary opacity values and CSS variables

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/colors.mdx

Specify custom opacity values using square bracket syntax or reference CSS custom properties using the shorthand parenthesis syntax.

```html
<!-- [!code filename:HTML] -->
<!-- [!code classes:bg-pink-500/[71.37%],bg-cyan-400/(--my-alpha-value)] -->
<div class="bg-pink-500/[71.37%]"><!-- ... --></div>
<div class="bg-cyan-400/(--my-alpha-value)"><!-- ... --></div>
```


--------------------------------

### Setting base path with source()

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/detecting-classes-in-source-files.mdx

Sets an explicit base path for class detection instead of defaulting to the current working directory. Useful in monorepos where build tools run from the repository root.

```css
/* [!code filename:CSS] */
/* [!code word:source("../src")] */
@import "tailwindcss" source("../src");
```


--------------------------------

### Overriding image width constraints with max-w-none

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/preflight.mdx

Use the max-w-none utility class on an image or video element when you need to override Preflight's default max-width constraint.

```html
<!-- [!code filename:HTML] -->
<img class="max-w-none" src="..." alt="..." />
```


--------------------------------

### Use motion-safe versus motion-reduce

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Use the motion-safe variant to only apply transition or animation styles when reduced motion is not requested, avoiding the need to undo styles with motion-reduce.

```html
<!-- [!code classes:motion-reduce:hover:translate-y-0] -->
<!-- [!code classes:motion-reduce:transition-none] -->
<!-- [!code classes:motion-safe:hover:-translate-x-0.5] -->
<!-- [!code classes:motion-safe:transition] -->
<!-- Using `motion-reduce` can mean lots of "undoing" styles -->
<button class="transition hover:-translate-y-0.5 motion-reduce:transition-none motion-reduce:hover:translate-y-0 ...">
  Save changes
</button>

<!-- Using `motion-safe` is less code in these situations -->
<button class="motion-safe:transition motion-safe:hover:-translate-x-0.5 ...">Save changes</button>
```


--------------------------------

### Run @tailwindcss/upgrade migration tool

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/upgrade-guide.mdx

Automates the upgrade from Tailwind CSS v3 to v4, including dependency updates, configuration migration to CSS, and template adjustments. Requires Node.js 20 or higher.

```sh
  # [!code filename:Terminal]
$ npx @tailwindcss/upgrade
```


--------------------------------

### Import global styles using @reference in component style blocks

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/compatibility.mdx

Import global stylesheet references in scoped `<style>` blocks to ensure theme variables are defined when using `@apply`. This is necessary because component style blocks in Vue, Svelte, and Astro are processed independently by build tooling.

```html
<!-- [!code filename:Button.vue] -->
<template>
  <button><slot /></button>
</template>

<style scoped>
  /* [!code highlight:2] */
  @reference "../app.css";

  button {
    @apply bg-blue-500;
  }
</style>
```


--------------------------------

### Conditionally apply styles with contrast-more

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Use the contrast-more variant to increase visibility for borders, placeholders, and opacity when prefers-contrast indicates a request for higher contrast.

```html
<!-- [!code classes:contrast-more:border-gray-400,contrast-more:placeholder-gray-500,contrast-more:opacity-100] -->
<label class="block">
  <span class="block text-sm font-medium text-gray-700">Social Security Number</span>
  <input
    class="border-gray-200 placeholder-gray-400 contrast-more:border-gray-400 contrast-more:placeholder-gray-500 ..."
  />
  <p class="text-gray-600 opacity-10 contrast-more:opacity-100 ...">We need this to steal your identity.</p>
</label>
```


--------------------------------

### Reference container dimensions using container query units

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/responsive-design.mdx

Use units like `cqw` and `cqi` within arbitrary value utilities to size child elements relative to their container.

```html
<!-- [!code filename:HTML] -->
<!-- [!code word:w-\[50cqw\]] -->
<div class="@container">
  <div class="w-[50cqw]">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Transforming bare values with calc() across declarations

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/adding-custom-styles.mdx

Perform calculations on bare values while falling back to theme and arbitrary declarations within the same utility.

```css
/* [!code filename:CSS] */
@utility opacity-* {
  opacity: --value([percentage]);
  /* [!code highlight:2] */
  opacity: calc(--value(integer) * 1%);
  /* prettier-ignore */
  opacity: --value(--opacity-*);
}
```


--------------------------------

### Use --spacing() in arbitrary values

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/functions-and-directives.mdx

Combine the --spacing() function with calc() directly inside arbitrary class value expressions.

```html
<!-- [!code filename:HTML] -->
<!-- [!code classes:py-[calc(--spacing(4)-1px)]] -->
<div class="py-[calc(--spacing(4)-1px)]">
  <!-- ... -->
</div>
```


--------------------------------

### Styling a Notification Card with Utility Classes in HTML

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/styling-with-utility-classes.mdx

Combine utility classes directly in markup to control layout, spacing, sizing, typography, colors, and dark mode styling on a card component.

```html
<!-- prettier-ignore -->
<div class="mx-auto flex max-w-sm items-center gap-x-4 rounded-xl bg-white p-6 shadow-lg outline outline-black/5 dark:bg-slate-800 dark:shadow-none dark:-outline-offset-1 dark:outline-white/10">
  <img class="size-12 shrink-0" src="/img/logo.svg" alt="ChitChat Logo" />
  <div>
    <div class="text-xl font-medium text-black dark:text-white">ChitChat</div>
    <p class="text-gray-500 dark:text-gray-400">You have a new message!</p>
  </div>
</div>
```


--------------------------------

### Configuring custom class prefix with the prefix option

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/styling-with-utility-classes.mdx

Prefixes all generated Tailwind classes and CSS variables using prefix(...) to prevent naming collisions with existing stylesheet rules.

```css
/* [!code filename:app.css] */
/* [!code word:important] */
@import "tailwindcss" prefix(tw);
```

```css
/* [!code filename:Compiled CSS] */
/* [!code word:tw\:] */
@layer theme {
  :root {
    --tw-color-red-500: oklch(0.637 0.237 25.331);
  }
}

@layer utilities {
  .tw\:text-red-500 {
    color: var(--tw-color-red-500);
  }
}
```


--------------------------------

### Define a custom variant using shorthand syntax

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/adding-custom-styles.mdx

Creates a custom variant using the compact shorthand syntax when selector nesting is not required.

```css
@custom-variant theme-midnight (&:where([data-theme="midnight"] *));
```


--------------------------------

### Stack multiple variant prefixes on a utility class

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/styling-with-utility-classes.mdx

Combines variant prefixes to apply a utility class only when all specified conditions match simultaneously.

```html
<!-- [!code classes:disabled:hover:bg-sky-500] -->
<button class="bg-sky-500 disabled:hover:bg-sky-500 ...">Save changes</button>
```


--------------------------------

### Use arbitrary container query values

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/responsive-design.mdx

Use arbitrary container query variants like `@min-[475px]` or `@max-[960px]` for one-off container query breakpoints without modifying your theme.

```html
<!-- [!code filename:HTML] -->
<!-- [!code word:@min-\[475px\]\:flex-row] -->
<div class="@container">
  <div class="flex flex-col @min-[475px]:flex-row">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Combining arbitrary values with responsive modifiers

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/adding-custom-styles.mdx

Arbitrary value utilities can be paired with responsive and state modifiers like lg.

```html
<!-- [!code filename:HTML] -->
<!-- [!code classes:top-[117px],lg:top-[344px]] -->
<div class="top-[117px] lg:top-[344px]">
  <!-- ... -->
</div>
```


--------------------------------

### Configuring important flag on utilities import

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/preflight.mdx

Append important to the utilities.css import to mark all generated utility classes as important.

```css
/* [!code filename:CSS] */
@layer theme, base, components, utilities;

@import "tailwindcss/theme.css" layer(theme);
@import "tailwindcss/utilities.css" layer(utilities); /* [!code --] */
@import "tailwindcss/utilities.css" layer(utilities) important; /* [!code ++] */
```


--------------------------------

### Stacking arbitrary variants with built-in variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Arbitrary variants can be combined and stacked with built-in Tailwind variants or other arbitrary variants.

```svelte
<!-- [!code classes:[&.is-dragging]:active:cursor-grabbing] -->
<ul role="list">
  {#each items as item}
    <li class="[&.is-dragging]:active:cursor-grabbing">{item}</li>
  {/each}
</ul>
```

```css
.\[\&\.is-dragging\]\:active\:cursor-grabbing {
  &.is-dragging {
    &:active {
      cursor: grabbing;
    }
  }
}
```


--------------------------------

### Defining and using a custom utility with @utility

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/adding-custom-styles.mdx

Register a custom utility using the `@utility` directive in CSS and apply it directly or with variants in HTML. Custom utilities are automatically inserted into the `utilities` layer.

```css
/* [!code filename:CSS] */
@utility content-auto {
  content-visibility: auto;
}
```

```html
<!-- [!code filename:HTML] -->
<!-- [!code classes:content-auto] -->
<div class="content-auto">
  <!-- ... -->
</div>
```

```html
<!-- [!code filename:HTML] -->
<!-- [!code classes:hover:content-auto] -->
<div class="hover:content-auto">
  <!-- ... -->
</div>
```


--------------------------------

### Define and use custom container sizes in the theme

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/responsive-design.mdx

Configure custom `--container-*` theme variables in CSS to generate corresponding container query variants for your markup.

```css
/* [!code filename:app.css] */
@import "tailwindcss";

@theme {
  /* [!code highlight:2] */
  --container-8xl: 96rem;
}
```

```html
<!-- [!code filename:HTML] -->
<!-- [!code word:@8xl\:flex-row] -->
<div class="@container">
  <!-- prettier-ignore -->
  <div class="flex flex-col @8xl:flex-row">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Configure PostCSS with @tailwindcss/postcss in postcss.config.mjs

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/upgrade-guide.mdx

Update PostCSS configuration to use the dedicated @tailwindcss/postcss package. Remove postcss-import and autoprefixer as import handling and vendor prefixing are included automatically in v4.

```js
// [!code filename:postcss.config.mjs]
export default {
  plugins: {
    // [!code --:4]
    "postcss-import": {},
    tailwindcss: {},
    autoprefixer: {},
    // [!code ++:2]
    "@tailwindcss/postcss": {},
  },
};
```


--------------------------------

### Avoid dynamic class name interpolation in HTML

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/detecting-classes-in-source-files.mdx

Demonstrates the incorrect approach of constructing partial class strings dynamically, which prevents Tailwind from detecting the full utility classes.

```html
<!-- [!code filename:HTML] -->
<div class="text-{{ error ? 'red' : 'green' }}-600"></div>
```


--------------------------------

### Target container query ranges

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/responsive-design.mdx

Combine a standard container query variant with a max-width variant (e.g., `@sm:@max-md`) to apply styles within a specific container size range.

```html
<!-- [!code filename:HTML] -->
<!-- [!code word:@sm\:@max-md\:flex-col] -->
<div class="@container">
  <div class="flex flex-row @sm:@max-md:flex-col">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Configuring theme generation mode on theme import

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/preflight.mdx

Place theme modifiers like theme(static) or theme(inline) on the theme.css import to configure how theme variables are generated.

```css
/* [!code filename:CSS] */
@layer theme, base, components, utilities;

@import "tailwindcss/theme.css" layer(theme); /* [!code --] */
@import "tailwindcss/theme.css" layer(theme) theme(static); /* [!code ++] */
@import "tailwindcss/utilities.css" layer(utilities);
```


--------------------------------

### Resetting default border styles

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/preflight.mdx

Sets border-box sizing and a 0 solid border reset so applying the border class creates a 1px solid border using currentColor.

```css
/* [!code filename:CSS] */
*,
::after,
::before,
::backdrop,
::file-selector-button {
  box-sizing: border-box;
  border: 0 solid;
}
```


--------------------------------

### Target a breakpoint range with md:max-xl: variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/responsive-design.mdx

Stack a responsive variant with a max-* variant to restrict utilities to an active range rather than leaving them enabled on all larger screens.

```html
<!-- [!code filename:HTML]  -->
<div class="md:max-xl:flex">
  <!-- ... -->
</div>
```


--------------------------------

### Generate theme spacing with --spacing()

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/functions-and-directives.mdx

Use the --spacing() function to generate a spacing value based on your configured theme scale.

```css
/* [!code filename:Input CSS] */
.my-element {
  /* [!code highlight:2] */
  margin: --spacing(4);
}
```

```css
/* [!code filename:Compiled CSS] */
.my-element {
  margin: calc(var(--spacing) * 4);
}
```


--------------------------------

### Register positive and negative utilities with @utility

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/adding-custom-styles.mdx

To support negative values, register distinct positive and negative utilities in separate declarations.

```css
/* [!code filename:CSS] */
@utility inset-* {
  inset: --spacing(--value(integer));
  inset: --value([percentage], [length]);
}

/* [!code highlight:4] */
@utility -inset-* {
  inset: --spacing(--value(integer) * -1);
  inset: calc(--value([percentage], [length]) * -1);
}
```


--------------------------------

### Share theme variables across projects using @import

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/theme.mdx

Define theme variables in a standalone CSS file and import it into application CSS files across projects or packages.

```css
/* [!code filename:./packages/brand/theme.css] */
@theme {
  --*: initial;

  --spacing: 4px;

  --font-body: Inter, sans-serif;

  --color-lagoon: oklch(0.72 0.11 221.19);
  --color-coral: oklch(0.74 0.17 40.24);
  --color-driftwood: oklch(0.79 0.06 74.59);
  --color-tide: oklch(0.49 0.08 205.88);
  --color-dusk: oklch(0.82 0.15 72.09);
}
```

```css
/* [!code filename:./packages/admin/app.css] */
@import "tailwindcss";
/* [!code highlight:2] */
@import "../brand/theme.css";
```


--------------------------------

### Extending the default theme with @theme

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/theme.mdx

Define new theme variables within @theme in app.css to generate custom utility classes usable in HTML.

```css
/* [!code filename:app.css] */
@import "tailwindcss";

@theme {
  /* [!code highlight:2] */
  --font-script: Great Vibes, cursive;
}
```

```html
<!-- [!code filename:HTML] -->
<!-- [!code word:font-script] -->
<p class="font-script">This will use the Great Vibes font family.</p>
```


--------------------------------

### Stacking multiple variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Combines dark mode, breakpoint, and hover variants to target specific conditions simultaneously.

```html
<!-- [!code classes:dark:md:hover:bg-fuchsia-600] -->
<button class="dark:md:hover:bg-fuchsia-600 ...">Save changes</button>
```


--------------------------------

### Differentiating multiple peers with named peer classes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Assign distinct peer names using peer/{name} classes to style sibling elements based on specific peer states.

```html
<fieldset>
  <legend>Published status</legend>

  <input id="draft" class="peer/draft" type="radio" name="status" checked />
  <label for="draft" class="peer-checked/draft:text-sky-500">Draft</label>

  <input id="published" class="peer/published" type="radio" name="status" />
  <label for="published" class="peer-checked/published:text-sky-500">Published</label>
  <div class="hidden peer-checked/draft:block">Drafts are only visible to administrators.</div>
  <div class="hidden peer-checked/published:block">Your post will be publicly visible on your site.</div>
</fieldset>
```


--------------------------------

### Always generate all CSS variables using @theme static

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/theme.mdx

Use the static theme option to force all CSS variables into the final build instead of generating only used variables.

```css
/* [!code filename:app.css] */
/* [!code word:static] */
@import "tailwindcss";

@theme static {
  --color-primary: var(--color-red-500);
  --color-secondary: var(--color-blue-500);
}
```


--------------------------------

### Apply styles based on parent state using implicit in-* variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Use the in-* variant to style child elements based on parent state changes without needing to declare group on the parent element.

```html
<!-- [!code classes:in-focus:opacity-100] -->
<!-- [!code --:3] -->
<div tabindex="0" class="group">
  <div class="opacity-50 group-focus:opacity-100">
<!-- [!code ++:3] -->
<div tabindex="0">
  <div class="opacity-50 in-focus:opacity-100">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Adding custom colors with @theme

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/colors.mdx

Add new custom colors under the `--color-*` namespace using the `@theme` directive to generate matching utility classes.

```css
/* [!code filename:CSS] */
@import "tailwindcss";

/* [!code highlight:6] */
@theme {
  --color-midnight: #121063;
  --color-tahiti: #3ab7bf;
  --color-bermuda: #78dcca;
}
```


--------------------------------

### Style popovers using the open variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

The `open` variant targets the `:popover-open` pseudo-class for popovers.

```html
<!-- [!code classes:open:opacity-100] -->
<div>
  <button popovertarget="my-popover">Open Popover</button>
  <div popover id="my-popover" class="opacity-0 open:opacity-100 ...">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Registering and using a custom variant with @custom-variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Defines a reusable custom variant in CSS using the @custom-variant directive and applies it in HTML.

```css
@custom-variant theme-midnight (&:where([data-theme="midnight"] *));
```

```html
<!-- [!code classes:theme-midnight:bg-black] -->
<html data-theme="midnight">
  <button class="theme-midnight:bg-black ..."></button>
</html>
```


--------------------------------

### Adding custom base styles with @layer base

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/preflight.mdx

Add custom base styles on top of Preflight by defining rules inside the base CSS layer using @layer base.

```css
/* [!code filename:CSS] */
@layer base {
  h1 {
    font-size: var(--text-2xl);
  }
  h2 {
    font-size: var(--text-xl);
  }
  h3 {
    font-size: var(--text-lg);
  }
  a {
    color: var(--color-blue-600);
    text-decoration-line: underline;
  }
}
```


--------------------------------

### Using arbitrary variants for selector modification

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/adding-custom-styles.mdx

Apply on-the-fly selector modifications directly in HTML using square bracket variant notation.

```html
<!-- [!code filename:HTML] -->
<!-- [!code word:\[&\:nth-child(-n+3)\]] -->
<ul role="list">
  {#each items as item}
  <li class="lg:[&:nth-child(-n+3)]:hover:underline">{item}</li>
  {/each}
</ul>
```


--------------------------------

### Bundle CSS files with @import

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/compatibility.mdx

Tailwind automatically bundles external CSS files imported via @import at build time without requiring Sass or postcss-import.

```css
/* [!code filename:app.css] */
@import "tailwindcss";
@import "./typography.css";
```


--------------------------------

### Generated CSS for dark mode variant utility

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/styling-with-utility-classes.mdx

Demonstrates the CSS media query generated for utilities prefixed with `dark:`. A single class handles only dark styles using the `prefers-color-scheme: dark` media query.

```css
/* [!code filename: Generated CSS] */
.dark\:bg-gray-800 {
  @media (prefers-color-scheme: dark) {
    background-color: var(--color-gray-800);
  }
}
```


--------------------------------

### Use theme variables inside arbitrary value utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/theme.mdx

Combine CSS variables with calc() within arbitrary value utility classes to achieve concentric border radiuses.

```html
<!-- [!code filename:HTML] -->
<!-- [!code word:rounded-xl] -->
<div class="relative rounded-xl">
  <!-- [!code word:rounded-\[calc(var(--radius-xl)-1px)\]] -->
  <div class="absolute inset-px rounded-[calc(var(--radius-xl)-1px)]">
    <!-- ... -->
  </div>
  <!-- ... -->
</div>
```


--------------------------------

### Default theme definitions in node_modules/tailwindcss/theme.css

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/theme.mdx

Defines out-of-the-box theme variables for fonts, colors, and shadows using the @theme directive.

```css
/* [!code filename:node_modules/tailwindcss/theme.css] */
@theme {
  /* prettier-ignore */
  --font-sans: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", "Noto Sans", Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  --font-serif: ui-serif, Georgia, Cambria, "Times New Roman", Times, serif;
  --font-mono: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;

  --color-red-50: oklch(0.971 0.013 17.38);
  --color-red-100: oklch(0.936 0.032 17.717);
  --color-red-200: oklch(0.885 0.062 18.334);
  /* ... */

  --shadow-2xs: 0 1px rgb(0 0 0 / 0.05);
  --shadow-xs: 0 1px 2px 0 rgb(0 0 0 / 0.05);
  --shadow-sm: 0 1px 3px 0 rgb(0 0 0 / 0.1), 0 1px 2px -1px rgb(0 0 0 / 0.1);
  /* ... */
}
```


--------------------------------

### Style details and dialog elements in an open state

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Use the `open` variant to conditionally add styles when a `<details>` or `<dialog>` element is in an open state.

```html
<!-- [!code classes:open:border-black/10,open:bg-gray-100] -->
<details class="border border-transparent open:border-black/10 open:bg-gray-100 ..." open>
  <summary class="text-sm leading-6 font-semibold text-gray-900 select-none">Why do they call it Ovaltine?</summary>
  <div class="mt-3 text-sm leading-6 text-gray-600">
    <p>The mug is round. The jar is round. They should call it Roundtine.</p>
  </div>
</details>
```


--------------------------------

### Combine not- with media query variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Applies fallback styles when a specific browser feature or environment condition is not supported.

```html
<!-- [!code classes:not-supports-[display:grid]:flex] -->
<div class="not-supports-[display:grid]:flex">
  <!-- ... -->
</div>
```


--------------------------------

### Matching theme values in functional utilities with --value(--theme-key-*)

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/adding-custom-styles.mdx

Resolve utility values against `@theme` definitions by supplying the theme key pattern to `--value()`.

```css
/* [!code filename:CSS] */
@theme {
  --tab-size-2: 2;
  --tab-size-4: 4;
  --tab-size-github: 8;
}

@utility tab-* {
  /* [!code highlight:2] */
  /* prettier-ignore */
  tab-size: --value(--tab-size-*);
}
```


--------------------------------

### Migrate @layer utilities to @utility directive

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/upgrade-guide.mdx

Replace v3 @layer utilities definitions with the v4 @utility at-rule for custom utilities.

```css
/* [!code filename:CSS] */
/* [!code --:6] */
@layer utilities {
  .tab-4 {
    tab-size: 4;
  }
}
/* [!code ++:4] */
@utility tab-4 {
  tab-size: 4;
}
```


--------------------------------

### Setting dynamic CSS variables via inline styles with utility classes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/styling-with-utility-classes.mdx

Inject dynamic values into custom CSS variables using inline styles, then reference them with utility classes and variants like `bg-(--bg-color)` and `hover:bg-(--bg-color-hover)`.

```jsx
// [!code filename:branded-button.jsx]
export function BrandedButton({ buttonColor, buttonColorHover, textColor, children }) {
  return (
    <button
      style={{
        // [!code highlight:4]
        "--bg-color": buttonColor,
        "--bg-color-hover": buttonColorHover,
        "--text-color": textColor,
      }}
      // [!code classes:bg-(--bg-color),text-(--text-color),hover:bg-(--bg-color-hover)]
      className="bg-(--bg-color) text-(--text-color) hover:bg-(--bg-color-hover) ..."
    >
      {children}
    </button>
  );
}
```


--------------------------------

### Apply site-wide text selection styling

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Sets a consistent text selection highlight color across the entire site by placing the selection: variant on the body tag.

```html
<!-- [!code classes:selection:bg-pink-300] -->
<html>
  <head>
    <!-- ... -->
  </head>
  <body class="selection:bg-pink-300">
    <!-- ... -->
  </body>
</html>
```


--------------------------------

### Traditional CSS multi-state button styling

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/styling-with-utility-classes.mdx

Demonstrates the traditional CSS approach where a single class encapsulates styles across multiple interaction states.

```html
/* [!code filename:HTML] */
<button class="btn">Save changes</button>

<style>
  .btn {
    background-color: var(--color-sky-500);
    &:hover {
      background-color: var(--color-sky-700);
    }
  }
</style>
```


--------------------------------

### Override styles for dark mode with dark variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Use default utility classes for light mode and prefix utilities with dark: to apply styling overrides when prefers-color-scheme is set to dark.

```html
<!-- [!code classes:dark:bg-gray-900] -->
<!-- [!code classes:dark:text-white] -->
<!-- [!code classes:dark:text-gray-400] -->
<div class="bg-white dark:bg-gray-900 ...">
  <!-- ... -->
  <h3 class="text-gray-900 dark:text-white ...">Writes upside-down</h3>
  <p class="text-gray-500 dark:text-gray-400 ...">
    The Zero Gravity Pen can be used to write in any orientation, including upside-down. It even works in outer space.
  </p>
</div>
```


--------------------------------

### Apply hover state with hover: variant prefix

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/styling-with-utility-classes.mdx

Prefix a utility class with a state like hover to conditionally apply styles only when that state is active.

```html
<!-- [!code word:hover\:bg-sky-700] -->
<button class="bg-sky-500 hover:bg-sky-700 ...">Save changes</button>
```


--------------------------------

### Converting underscores to spaces in arbitrary values

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/adding-custom-styles.mdx

Use an underscore in arbitrary values to represent a space; Tailwind converts it at build time.

```html
<!-- [!code filename:HTML] -->
<!-- [!code classes:grid-cols-[1fr_500px_2fr]] -->
<div class="grid grid-cols-[1fr_500px_2fr]">
  <!-- ... -->
</div>
```


--------------------------------

### Define and use a custom CSS component class with theme variables

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/styling-with-utility-classes.mdx

Defines a custom `.btn-primary` class within `@layer components` using Tailwind CSS theme variables, alongside its HTML markup.

```html
<!-- [!code filename:HTML] -->
<button class="btn-primary">Save changes</button>
```

```css
/* [!code filename:CSS] */
@import "tailwindcss";

@layer components {
  .btn-primary {
    border-radius: calc(infinity * 1px);
    background-color: var(--color-violet-500);
    padding-inline: --spacing(5);
    padding-block: --spacing(2);
    font-weight: var(--font-weight-semibold);
    color: var(--color-white);
    box-shadow: var(--shadow-md);
    &:hover {
      @media (hover: hover) {
        background-color: var(--color-violet-700);
      }
    }
  }
}
```


--------------------------------

### Apply responsive viewport breakpoint variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Use responsive variants like md and lg to conditionally style elements at specific viewport breakpoints.

```html
<!-- [!code classes:md:grid-cols-4,lg:grid-cols-6] -->
<div class="grid grid-cols-3 md:grid-cols-4 lg:grid-cols-6">
  <!-- ... -->
</div>
```


--------------------------------

### Conditionally apply styles using motion-reduce

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Use the motion-reduce variant to conditionally apply styles when the user requests reduced motion via prefers-reduced-motion.

```html
<!-- [!code classes:motion-reduce:hidden] -->
<button type="button" class="bg-indigo-500 ..." disabled>
  <svg class="animate-spin motion-reduce:hidden ..." viewBox="0 0 24 24"><!-- ... --></svg>
  Processing...
</button>
```


--------------------------------

### Use full size containers with @container-size

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/responsive-design.mdx

Mark an element with `@container-size` when using container query units that depend on block size (like `cqb`) rather than just inline size.

```html
<!-- [!code filename:HTML] -->
<!-- [!code word:@container-size] -->
<!-- [!code word:h-\[50cqb\]] -->
<div class="@container-size">
  <div class="h-[50cqb]">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Displaying images inline with the inline utility

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/preflight.mdx

Use the inline utility class when an image or replaced element needs inline display behavior instead of block.

```html
<!-- [!code filename:HTML] -->
<img class="inline" src="..." alt="..." />
```


--------------------------------

### Adjust color opacity using alpha modifier syntax

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/colors.mdx

Adjust the opacity of a color utility using slash syntax such as `bg-sky-500/50`. The number after the slash specifies the alpha channel percentage from 0 to 100.

```html
<!-- [!code classes:bg-black-50/10,bg-black-100/20,bg-black-200/30,bg-black-300/40,bg-black-400/50,bg-black-500/60,bg-black-600/70,bg-black-700/80,bg-black-800/90,bg-black-900/100] -->
<div>
  <div class="bg-sky-500/10"></div>
  <div class="bg-sky-500/20"></div>
  <div class="bg-sky-500/30"></div>
  <div class="bg-sky-500/40"></div>
  <div class="bg-sky-500/50"></div>
  <div class="bg-sky-500/60"></div>
  <div class="bg-sky-500/70"></div>
  <div class="bg-sky-500/80"></div>
  <div class="bg-sky-500/90"></div>
  <div class="bg-sky-500/100"></div>
</div>
```


--------------------------------

### Apply generated utility class in HTML

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/theme.mdx

Applies the utility class generated from a theme variable to an HTML element.

```html
<!-- [!code filename:HTML] -->
<!-- [!code word:bg-mint-500] -->
<div class="bg-mint-500">
  <!-- ... -->
</div>
```


--------------------------------

### Style initial default inputs using the default variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Applies styles to an option, checkbox, or radio button that held the default value on initial page load.

```html
<!-- [!code classes:default:outline-2] -->
<input type="checkbox" class="default:outline-2 ..." />
```


--------------------------------

### Create one-off arbitrary group variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Pass custom selectors as arbitrary values inside square brackets on group-* variants to match custom parent class states.

```html
      <!-- [!code classes:group-[.is-published]:block] -->
      <div class="group is-published">
        <div class="hidden group-[.is-published]:block">
          Published
        </div>
      </div>
```

```css
      .group-\[\.is-published\]\:block {
        &:is(:where(.group):is(.is-published) *) {
          display: block;
        }
      }
```


--------------------------------

### Restore pointer cursor on buttons in Preflight

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/upgrade-guide.mdx

Restore the default cursor: pointer behavior on non-disabled buttons and button-role elements.

```css
/* [!code filename:CSS] */
@layer base {
  button:not(:disabled),
  [role="button"]:not(:disabled) {
    cursor: pointer;
  }
}
```


--------------------------------

### Configure dark mode with a data attribute selector

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/dark-mode.mdx

Override the `dark` variant in `app.css` using an attribute selector targeting `[data-theme=dark]`. In HTML, set `data-theme="dark"` on the `html` element to activate dark styles.

```css
/* [!code filename:app.css] */
@import "tailwindcss";

/* [!code highlight:2] */
@custom-variant dark (&:where([data-theme=dark], [data-theme=dark] *));
```

```html
<!-- [!code filename:HTML] -->
<!-- [!code word:dark\:bg-black] -->
<!-- [!code word:data-theme="dark"] -->
<html data-theme="dark">
  <body>
    <div class="bg-white dark:bg-black">
      <!-- ... -->
    </div>
  </body>
</html>
```


--------------------------------

### Applying color utilities to HTML elements

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/colors.mdx

Use color utility classes such as bg-white, border-pink-300, and text-gray-950 to style background, border, text, and stroke colors across light and dark variants.

```html
<!-- [!code classes:bg-white,border-pink-300,bg-pink-100,stroke-pink-700,text-gray-950,text-gray-500,outline-black/5,text-gray-700,dark:bg-gray-800,dark:border-pink-300/10,dark:bg-pink-400/10,dark:stroke-pink-500,dark:text-gray-400,dark:text-white] -->
<div class="flex items-center gap-4 rounded-lg bg-white p-6 shadow-md outline outline-black/5 dark:bg-gray-800">
  <!-- prettier-ignore -->
  <span class="inline-flex shrink-0 rounded-full border border-pink-300 bg-pink-100 p-2 dark:border-pink-300/10 dark:bg-pink-400/10">
    <svg class="size-6 stroke-pink-700 dark:stroke-pink-500"><!-- ... --></svg>
  </span>
  <div>
    <p class="text-gray-700 dark:text-gray-400">
      <span class="font-medium text-gray-950 dark:text-white">Tom Watson</span> mentioned you in
      <span class="font-medium text-gray-950 dark:text-white">Logo redesign</span>
    </p>
    <time class="mt-1 block text-gray-500" datetime="9:37">9:37am</time>
  </div>
</div>
```


--------------------------------

### Define default values for utility values with --default()

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/adding-custom-styles.mdx

Use --default() inside --value() to specify a fallback value when a custom utility is used without an explicit value. This generates rules for both explicit variants and the bare utility.

```css
/* [!code filename:CSS] */
/* [!code word:--default(4)] */
@utility tab-* {
  tab-size: --value(integer, --default(4));
}
```

```css
/* [!code filename:Compiled CSS] */
/* [!code highlight:4] */
.tab {
  tab-size: 4;
}

.tab-2 {
  tab-size: 2;
}
```


--------------------------------

### Apply styles conditionally based on browser feature support using supports-[...]

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Use the `supports-[...]` variant to apply styles when a CSS property/value pair or expression is supported by the browser.

```html
<!-- [!code classes:supports-[display:grid]:grid] -->
<div class="flex supports-[display:grid]:grid ...">
  <!-- ... -->
</div>
```


--------------------------------

### Attempting child overrides against parent * variant styles

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Demonstrates that utility classes placed directly on child elements cannot override parent `*` styles because both rules have the same specificity and children rules are generated later.

```html
<!-- [!code classes:*:bg-sky-50] -->
<!-- [!code classes:bg-red-50] -->
<ul class="*:bg-sky-50 ...">
  <li class="bg-red-50 ...">Sales</li>
  <li>Marketing</li>
  <li>SEO</li>
  <!-- ... -->
</ul>
```


--------------------------------

### Supporting arbitrary values with --value([{type}])

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/adding-custom-styles.mdx

Allow arbitrary bracketed values by enclosing the accepted data types in square brackets inside `--value()`.

```css
/* [!code filename:CSS] */
@utility tab-* {
  tab-size: --value([integer]);
}
```


--------------------------------

### Style ::after pseudo-element with after variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Use the after variant to style ::after pseudo-elements. Setting custom content requires explicit after:content-['*'] syntax.

```html
<!-- [!code classes:after:content-['*']] -->
<!-- [!code classes:after:ml-0.5] -->
<!-- [!code classes:after:text-red-500] -->
<label>
  <span class="text-gray-700 after:ml-0.5 after:text-red-500 after:content-['*'] ...">Email</span>
  <input type="email" name="email" class="..." placeholder="you@example.com" />
</label>
```


--------------------------------

### Constraining images and videos in Preflight

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/preflight.mdx

Preflight constrains images and videos to the parent width to preserve intrinsic aspect ratios and prevent overflow.

```css
/* [!code filename:CSS] */
img,
video {
  max-width: 100%;
  height: auto;
}
```


--------------------------------

### Demonstrating CSS variable scope resolution issues

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/theme.mdx

Illustrates why CSS variable resolution fails across nested parent and child scopes when variables are evaluated at definition time.

```html
<!-- [!code filename:HTML] -->
<!-- [!code word:--font-sans\: var(--font-inter, sans-serif);] -->
<div id="parent" style="--font-sans: var(--font-inter, sans-serif);">
  <!-- [!code word:--font-inter\: Inter; font-family\: var(--font-sans);] -->
  <div id="child" style="--font-inter: Inter; font-family: var(--font-sans);">
    This text will use the sans-serif font, not Inter.
  </div>
</div>
```


--------------------------------

### Update shadow utilities for Tailwind CSS v4

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/upgrade-guide.mdx

Migrates v3 shadow utilities to their v4 equivalents according to the updated scale. Replaces `shadow-sm` with `shadow-xs` and bare `shadow` with `shadow-sm`.

```html
<!-- [!code filename:HTML] -->
<!-- [!code --:2] -->
<input class="shadow-sm" />
<!-- [!code ++:2] -->
<input class="shadow-xs" />

<!-- [!code --:2] -->
<input class="shadow" />
<!-- [!code ++:2] -->
<input class="shadow-sm" />
```


--------------------------------

### Style an optional input using the optional variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Applies styling to an input field that is not marked as required.

```html
<!-- [!code classes:optional:border-red-500] -->
<input class="border optional:border-red-500 ..." />
```


--------------------------------

### Apply styles for print media

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Use the print variant to display or hide content specifically when printing the document.

```html
<!-- [!code classes:print:hidden] -->
<!-- [!code classes:print:block] -->
<div>
  <article class="print:hidden">
    <h1>My Secret Pizza Recipe</h1>
    <p>This recipe is a secret, and must not be shared with anyone</p>
    <!-- ... -->
  </article>
  <div class="hidden print:block">Are you seriously trying to print this? It's secret!</div>
</div>
```


--------------------------------

### Define default color palette variables in @theme

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/colors.mdx

Lists default color palette values using the oklch() color function inside a CSS @theme directive.

```css
/* [!code filename:CSS] */
@theme {
  --color-red-50: oklch(97.1% 0.013 17.38);
  --color-red-100: oklch(93.6% 0.032 17.717);
  --color-red-200: oklch(88.5% 0.062 18.334);
  --color-red-300: oklch(80.8% 0.114 19.571);
  --color-red-400: oklch(70.4% 0.191 22.216);
  --color-red-500: oklch(63.7% 0.237 25.331);
  --color-red-600: oklch(57.7% 0.245 27.325);
  --color-red-700: oklch(50.5% 0.213 27.518);
  --color-red-800: oklch(44.4% 0.177 26.899);
  --color-red-900: oklch(39.6% 0.141 25.723);
  --color-red-950: oklch(25.8% 0.092 26.042);

  --color-orange-50: oklch(98% 0.016 73.684);
  --color-orange-100: oklch(95.4% 0.038 75.164);
  --color-orange-200: oklch(90.1% 0.076 70.697);
  --color-orange-300: oklch(83.7% 0.128 66.29);
  --color-orange-400: oklch(75% 0.183 55.934);
  --color-orange-500: oklch(70.5% 0.213 47.604);
  --color-orange-600: oklch(64.6% 0.222 41.116);
  --color-orange-700: oklch(55.3% 0.195 38.402);
  --color-orange-800: oklch(47% 0.157 37.304);
  --color-orange-900: oklch(40.8% 0.123 38.172);
  --color-orange-950: oklch(26.6% 0.079 36.259);

  --color-amber-50: oklch(98.7% 0.022 95.277);
  --color-amber-100: oklch(96.2% 0.059 95.617);
  --color-amber-200: oklch(92.4% 0.12 95.746);
  --color-amber-300: oklch(87.9% 0.169 91.605);
  --color-amber-400: oklch(82.8% 0.189 84.429);
  --color-amber-500: oklch(76.9% 0.188 70.08);
  --color-amber-600: oklch(66.6% 0.179 58.318);
  --color-amber-700: oklch(55.5% 0.163 48.998);
  --color-amber-800: oklch(47.3% 0.137 46.201);
  --color-amber-900: oklch(41.4% 0.112 45.904);
  --color-amber-950: oklch(27.9% 0.077 45.635);

  --color-yellow-50: oklch(98.7% 0.026 102.212);
  --color-yellow-100: oklch(97.3% 0.071 103.193);
  --color-yellow-200: oklch(94.5% 0.129 101.54);
  --color-yellow-300: oklch(90.5% 0.182 98.111);
  --color-yellow-400: oklch(85.2% 0.199 91.936);
  --color-yellow-500: oklch(79.5% 0.184 86.047);
  --color-yellow-600: oklch(68.1% 0.162 75.834);
  --color-yellow-700: oklch(55.4% 0.135 66.442);
  --color-yellow-800: oklch(47.6% 0.114 61.907);
  --color-yellow-900: oklch(42.1% 0.095 57.708);
  --color-yellow-950: oklch(28.6% 0.066 53.813);

  --color-lime-50: oklch(98.6% 0.031 120.757);
  --color-lime-100: oklch(96.7% 0.067 122.328);
  --color-lime-200: oklch(93.8% 0.127 124.321);
  --color-lime-300: oklch(89.7% 0.196 126.665);
  --color-lime-400: oklch(84.1% 0.238 128.85);
  --color-lime-500: oklch(76.8% 0.233 130.85);
  --color-lime-600: oklch(64.8% 0.2 131.684);
  --color-lime-700: oklch(53.2% 0.157 131.589);
  --color-lime-800: oklch(45.3% 0.124 130.933);
  --color-lime-900: oklch(40.5% 0.101 131.063);
  --color-lime-950: oklch(27.4% 0.072 132.109);

  --color-green-50: oklch(98.2% 0.018 155.826);
  --color-green-100: oklch(96.2% 0.044 156.743);
  --color-green-200: oklch(92.5% 0.084 155.995);
  --color-green-300: oklch(87.1% 0.15 154.449);
  --color-green-400: oklch(79.2% 0.209 151.711);
  --color-green-500: oklch(72.3% 0.219 149.579);
  --color-green-600: oklch(62.7% 0.194 149.214);
  --color-green-700: oklch(52.7% 0.154 150.069);
  --color-green-800: oklch(44.8% 0.119 151.328);
  --color-green-900: oklch(39.3% 0.095 152.535);
  --color-green-950: oklch(26.6% 0.065 152.934);

  --color-emerald-50: oklch(97.9% 0.021 166.113);
  --color-emerald-100: oklch(95% 0.052 163.051);
  --color-emerald-200: oklch(90.5% 0.093 164.15);
  --color-emerald-300: oklch(84.5% 0.143 164.978);
  --color-emerald-400: oklch(76.5% 0.177 163.223);
  --color-emerald-500: oklch(69.6% 0.17 162.48);
  --color-emerald-600: oklch(59.6% 0.145 163.225);
  --color-emerald-700: oklch(50.8% 0.118 165.612);
  --color-emerald-800: oklch(43.2% 0.095 166.913);
  --color-emerald-900: oklch(37.8% 0.077 168.94);
  --color-emerald-950: oklch(26.2% 0.051 172.552);

  --color-teal-50: oklch(98.4% 0.014 180.72);
  --color-teal-100: oklch(95.3% 0.051 180.801);
  --color-teal-200: oklch(91% 0.096 180.426);
  --color-teal-300: oklch(85.5% 0.138 181.071);
  --color-teal-400: oklch(77.7% 0.152 181.912);
  --color-teal-500: oklch(70.4% 0.14 182.503);
  --color-teal-600: oklch(60% 0.118 184.704);
  --color-teal-700: oklch(51.1% 0.096 186.391);
  --color-teal-800: oklch(43.7% 0.078 188.216);
  --color-teal-900: oklch(38.6% 0.063 188.416);
  --color-teal-950: oklch(27.7% 0.046 192.524);

  --color-cyan-50: oklch(98.4% 0.019 200.873);
  --color-cyan-100: oklch(95.6% 0.045 203.388);
  --color-cyan-200: oklch(91.7% 0.08 205.041);
  --color-cyan-300: oklch(86.5% 0.127 207.078);
  --color-cyan-400: oklch(78.9% 0.154 211.53);
  --color-cyan-500: oklch(71.5% 0.143 215.221);
  --color-cyan-600: oklch(60.9% 0.126 221.723);
  --color-cyan-700: oklch(52% 0.105 223.128);
  --color-cyan-800: oklch(45% 0.085 224.283);
  --color-cyan-900: oklch(39.8% 0.07 227.392);
  --color-cyan-950: oklch(30.2% 0.056 229.695);
}
```


--------------------------------

### Explicitly registering sources with @source

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/detecting-classes-in-source-files.mdx

Explicitly registers source paths relative to the stylesheet. Use this to scan external dependencies such as UI libraries that are ignored by default in .gitignore.

```css
/* [!code filename:CSS] */
@import "tailwindcss";
/* [!code highlight:2] */
@source "../node_modules/@acmecorp/ui-lib";
```


--------------------------------

### Style file input button with file variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Applies custom styling to the button within file input elements using the file: modifier.

```html
<!-- [!code classes:file:mr-4,file:rounded-full,file:border-0,file:bg-violet-50,file:px-4,file:py-2,file:text-sm,file:font-semibold,file:text-violet-700,hover:file:bg-violet-100,dark:file:bg-violet-600,dark:file:text-violet-100,dark:hover:file:bg-violet-500] -->
<input
  type="file"
  class="file:mr-4 file:rounded-full file:border-0 file:bg-violet-50 file:px-4 file:py-2 file:text-sm file:font-semibold file:text-violet-700 hover:file:bg-violet-100 dark:file:bg-violet-600 dark:file:text-violet-100 dark:hover:file:bg-violet-500 ..."
/>
```


--------------------------------

### Resolving conflicting utility classes by stylesheet order

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/styling-with-utility-classes.mdx

Demonstrates that when conflicting utilities target the same CSS property, the rule appearing later in the stylesheet wins regardless of class attribute order.

```html
<!-- [!code filename:HTML] -->
<!-- prettier-ignore -->
<div class="grid flex">
  <!-- ... -->
</div>
```

```css
/* [!code filename: CSS] */
.flex {
  display: flex;
}
.grid {
  display: grid;
}
```


--------------------------------

### Style browser-autofilled inputs with autofill variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Applies styles to an `<input>` element when its value has been autofilled by the browser using the `autofill` variant.

```html
<!-- [!code classes:autofill:bg-yellow-200] -->
<input class="autofill:bg-yellow-200 ..." />
```


--------------------------------

### Styling based on the descendants of a peer using peer-has-*

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Marks a sibling element with the peer class and applies the peer-has-* variant to style target elements based on descendant states.

```html
<!-- [!code classes:peer-has-checked:hidden,peer] -->
<div>
  <label class="peer ...">
    <input type="checkbox" name="todo[1]" checked />
    Create a to do list
  </label>
  <svg class="peer-has-checked:hidden ..."><!-- ... --></svg>
</div>
```


--------------------------------

### Default Tailwind CSS layer imports

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/preflight.mdx

Shows the standard layer and file imports injected by the default @import "tailwindcss"; statement.

```css
/* [!code filename:CSS] */
@layer theme, base, components, utilities;

@import "tailwindcss/theme.css" layer(theme);
@import "tailwindcss/preflight.css" layer(base);
@import "tailwindcss/utilities.css" layer(utilities);
```


--------------------------------

### Style elements on hover, focus, and active states

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Use the hover, focus, and active variants to apply specific utility styles when an element is hovered, focused, or pressed.

```html
<!-- [!code classes:hover:bg-violet-600,focus:outline-2,focus:outline-offset-2,focus:outline-violet-500,active:bg-violet-700] -->
<!-- prettier-ignore -->
<button class="bg-violet-500 hover:bg-violet-600 focus:outline-2 focus:outline-offset-2 focus:outline-violet-500 active:bg-violet-700 ...">
  Save changes
</button>
```


--------------------------------

### Add viewport meta tag in index.html

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/responsive-design.mdx

Add the viewport meta tag to the document head to ensure responsive utility classes work properly across devices.

```html
<!-- [!code filename:index.html] -->
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```


--------------------------------

### Apply styles based on viewport orientation

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Use the portrait and landscape variants to conditionally show, hide, or restyle elements depending on the device orientation.

```html
<!-- [!code classes:portrait:hidden,landscape:hidden] -->
<div>
  <div class="portrait:hidden">
    <!-- ... -->
  </div>
  <div class="landscape:hidden">
    <p>This experience is designed to be viewed in landscape. Please rotate your device to view the site.</p>
  </div>
</div>
```


--------------------------------

### Matching bare data types with --value({type})

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/adding-custom-styles.mdx

Validate bare numeric inputs by passing supported data types (`number`, `integer`, `ratio`, or `percentage`) to `--value()`.

```css
/* [!code filename:CSS] */
@utility tab-* {
  tab-size: --value(integer);
}
```


--------------------------------

### Style input placeholder text with placeholder variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Style placeholder text on input or textarea elements using the placeholder variant.

```html
<!-- [!code classes:placeholder:italic,placeholder:text-gray-500] -->
<input
  class="placeholder:text-gray-500 placeholder:italic ..."
  placeholder="Search for anything..."
  type="text"
  name="search"
/>
```


--------------------------------

### Preserving accessibility on unstyled lists with role="list"

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/preflight.mdx

Add role="list" to unstyled list elements so screen readers like VoiceOver properly announce them as lists.

```html
<!-- [!code filename:HTML] -->
<ul role="list">
  <li>One</li>
  <li>Two</li>
  <li>Three</li>
</ul>
```


--------------------------------

### Style children by position using nth-* and nth-last-* variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Targets specific elements by positional index using nth-*, nth-last-*, nth-of-type-*, and nth-last-of-type-* variants. Supports numeric arguments as well as arbitrary expressions.

```html
<!-- [!code classes:nth-3:underline,nth-last-5:underline,nth-of-type-4:underline,nth-last-of-type-6:underline] -->
<div class="nth-3:underline">
  <!-- ... -->
</div>
<div class="nth-last-5:underline">
  <!-- ... -->
</div>
<div class="nth-of-type-4:underline">
  <!-- ... -->
</div>
<div class="nth-last-of-type-6:underline">
  <!-- ... -->
</div>
```


--------------------------------

### Style a valid input using the valid variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/hover-focus-and-other-states.mdx

Applies styles to an input when its content matches its validation requirements.

```html
<!-- [!code classes:valid:border-green-500] -->
<input required class="border valid:border-green-500 ..." />
```
