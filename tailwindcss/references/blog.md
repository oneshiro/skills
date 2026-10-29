# Tailwind CSS — Blog

Sourced snippets (236 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Using <script setup> with Headless UI in Vue 3

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2022-05-23-headless-ui-v1-6-tailwind-ui-team-management/index.mdx

Shows a Vue 3 single-file component using the <script setup> syntax with Headless UI components. Components imported within <script setup> are automatically available to the template without manual registration.

```html
<template>
  <Listbox as="div" v-model="selected">
    <!-- ... -->
  </Listbox>
</template>

<script setup>
  import { ref } from "vue";
  import { Listbox, ListboxButton, ListboxLabel, ListboxOption, ListboxOptions } from "@headlessui/vue";
  import { CheckIcon, SelectorIcon } from "@heroicons/vue/solid";

  const people = [
    { id: 1, name: "Wade Cooper" },
    // ...
  ];

  const selected = ref(people[3]);
</script>
```


--------------------------------

### Install and configure @tailwindcss/jit

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/just-in-time-the-next-generation-of-tailwind-css/index.mdx

Install the package along with its peer dependencies using npm and register `@tailwindcss/jit` in `postcss.config.js`.

```sh
npm install -D @tailwindcss/jit tailwindcss postcss autoprefixer
```

```js
// postcss.config.js
module.exports = {
  plugins: {
    "@tailwindcss/jit": {},
    autoprefixer: {},
  },
};
```


--------------------------------

### Install or upgrade Headless UI for React and Vue

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/headless-ui-v1-5/index.mdx

Upgrade Headless UI to version 1.5 using npm to get the Combobox component for React or Vue.

```sh
# For React
npm install @headlessui/react

# For Vue
npm install @headlessui/vue
```


--------------------------------

### Install @headlessui/react via npm

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/headless-ui-v2/index.mdx

Installs the latest version of Headless UI for React to add the library or upgrade existing projects.

```sh
npm install @headlessui/react@latest
```


--------------------------------

### Start theme from scratch without default theme

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-alpha/index.mdx

Import preflight and utilities directly instead of tailwindcss to bypass the default theme without clearing namespaces.

```css
/* [!code filename:main.css] */
@import "tailwindcss"; /* [!code --] */
@import "tailwindcss/preflight" layer(base); /* [!code ++] */
@import "tailwindcss/utilities" layer(utilities); /* [!code ++] */

@theme {
  --color-*: initial; /* [!code --] */
  --color-gray-50: #f8fafc;
  --color-gray-100: #f1f5f9;
  --color-gray-200: #e2e8f0;
  /* ... */
  --color-green-800: #3f6212;
  --color-green-900: #365314;
  --color-green-950: #1a2e05;
}
```


--------------------------------

### Install latest @headlessui/react

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2024-06-21-headless-ui-v2-1/index.mdx

Installs the latest release of Headless UI for React via npm to access new features like sibling dialog rendering.

```sh
npm i @headlessui/react@latest
```


--------------------------------

### Install and configure @tailwindcss/line-clamp

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/multi-line-truncation-with-tailwindcss-line-clamp/index.mdx

Install the plugin package via npm and register it inside the plugins array of tailwind.config.js.

```sh
npm install @tailwindcss/line-clamp
```

```js
module.exports = {
  // ...
  plugins: [
    // ...
    require("@tailwindcss/line-clamp"),
  ],
};
```


--------------------------------

### Set up and compile Tailwind CSS v4 alpha with the CLI

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-alpha/index.mdx

Install Tailwind CSS v4 and the standalone CLI package, import Tailwind in the source CSS file, and compile the stylesheet to an output destination.

```sh
npm install tailwindcss@next @tailwindcss/cli@next
```

```css
/* [!code filename:app.css] */
@import "tailwindcss";
```

```sh
npx @tailwindcss/cli@next -i app.css -o dist/app.css
```


--------------------------------

### Install and configure prettier-plugin-tailwindcss

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/automatic-class-sorting-with-prettier/index.mdx

Install the plugin and Prettier as dev dependencies, then declare the plugin inside .prettierrc. The plugin can also be loaded using the Prettier CLI --plugin flag or Prettier API plugins option.

```sh
npm install -D prettier prettier-plugin-tailwindcss
```

```json
{
  "plugins": ["prettier-plugin-tailwindcss"]
}
```


--------------------------------

### Animate Popover Entry with starting Variant and @starting-style

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4/index.mdx

Use the starting variant with transition-discrete to animate element properties when an element is first rendered or opened. This allows entry transitions on popovers without JavaScript.

```html
<!-- [!code classes:starting:open:opacity-0,transition-discrete] -->
<div>
  <button popovertarget="my-popover">Check for updates</button>
  <div popover id="my-popover" class="transition-discrete starting:open:opacity-0 ...">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Install and configure Tailwind CSS v4 with PostCSS

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4/index.mdx

Follow this three-step workflow to install Tailwind CSS v4 and its PostCSS plugin, register the plugin in PostCSS configuration, and import Tailwind in CSS without extra configuration files.

```shell
# [!code filename:1. Install Tailwind CSS]
npm i tailwindcss @tailwindcss/postcss;
```

```js
// [!code filename:2. Add the PostCSS plugin]
export default {
  plugins: ["@tailwindcss/postcss"],
};
```

```css
/* [!code filename:3. Import Tailwind in your CSS] */
@import "tailwindcss";
```


--------------------------------

### Install the latest version of prettier-plugin-tailwindcss

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2024-05-30-prettier-plugin-collapse-whitespace/index.mdx

Installs the latest release of prettier-plugin-tailwindcss using npm to enable automatic removal of duplicate classes and extra whitespace.

```sh
npm i prettier-plugin-tailwindcss@latest
```


--------------------------------

### Set up Tailwind CSS v4 alpha with PostCSS

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-alpha/index.mdx

Install Tailwind CSS v4 and the separate PostCSS plugin package, register it in postcss.config.js, and import Tailwind in the main CSS file.

```sh
npm install tailwindcss@next @tailwindcss/postcss@next
```

```js
// [!code filename:postcss.config.js]
module.exports = {
  plugins: {
    "@tailwindcss/postcss": {},
  },
};
```

```css
/* [!code filename:app.css] */
@import "tailwindcss";
```


--------------------------------

### Install Tailwind CSS v3.0 and dependencies with npm

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3/index.mdx

Installs Tailwind CSS, PostCSS, and Autoprefixer as development dependencies in an npm project.

```sh
npm install -D tailwindcss@latest postcss autoprefixer
```


--------------------------------

### Install or upgrade Tailwind CSS via npm

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Install the latest version of Tailwind CSS as a development dependency using npm.

```sh
npm install -D tailwindcss@latest

```


--------------------------------

### Set up Tailwind CSS v4 alpha with Vite

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-alpha/index.mdx

Install Tailwind CSS v4 and the official Vite plugin, add the plugin to vite.config.ts, and import Tailwind into the main CSS file.

```sh
npm install tailwindcss@next @tailwindcss/vite@next
```

```ts
// [!code filename:vite.config.ts]
import tailwindcss from "@tailwindcss/vite";
import { defineConfig } from "vite";

export default defineConfig({
  plugins: [tailwindcss()],
});
```

```css
/* [!code filename:app.css]
@import "tailwindcss";
```


--------------------------------

### Install @tailwindcss/typography plugin

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-typography-v0-5/index.mdx

Install the typography plugin from npm as a development dependency. Ensure your project is running Tailwind CSS v3.0 or later.

```sh
npm install -D @tailwindcss/typography@latest
```


--------------------------------

### Apply block-start and block-end padding and margin

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Use logical block-start (`mbs-*`, `pbs-*`) and block-end (`mbe-*`, `pbe-*`) utilities to control element spacing relative to writing direction.

```html
<!-- [!code classes:pbs-4,pbe-8,mbs-6,mbe-2] -->
<div class="mbs-6 mbe-2 pbs-4 pbe-8 ...">
  <!-- ... -->
</div>
```


--------------------------------

### Upgrade Tailwind CSS using Vite

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Installs the latest releases of tailwindcss and the official Vite plugin.

```sh
# [!code filename:Using Vite]
npm install tailwindcss@latest @tailwindcss/vite@latest
```


--------------------------------

### Manual accessible input field setup with ARIA attributes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/headless-ui-v2/index.mdx

Shows the traditional manual method for wiring accessibility attributes (id, aria-labelledby, aria-describedby) between label, input, and description elements.

```jsx
<div>
  <label id="name-label" for="name-input">
    Name
  </label>
  <input id="name-input" aria-labelledby="name-label" aria-describedby="name-description" />
  <p id="name-description">Use your real name so people will recognize you.</p>
</div>
```


--------------------------------

### Set width and height simultaneously using size-* utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-4/index.mdx

Use `size-*` utilities instead of separate `h-*` and `w-*` classes to set element width and height at the same time. This is especially convenient for sizing avatars, working with variants, or applying complex arbitrary values.

```html
<!-- [!code filename:HTML] -->
<div>
  <img class="h-10 w-10" ...> <!-- [!code --] -->
  <img class="h-12 w-12" ...> <!-- [!code --] -->
  <img class="h-14 w-14" ...> <!-- [!code --] -->
  <!-- [!code word:size-10] -->
  <img class="size-10" ...> <!-- [!code ++] -->
  <!-- [!code word:size-12] -->
  <img class="size-12" ...> <!-- [!code ++] -->
  <!-- [!code word:size-14] -->
  <img class="size-14" ...> <!-- [!code ++] -->
</div>
```


--------------------------------

### Upgrade Tailwind CSS using PostCSS

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Installs the latest releases of tailwindcss and the PostCSS plugin package.

```sh
# [!code filename:Using PostCSS]
npm install tailwindcss@latest @tailwindcss/postcss@latest
```


--------------------------------

### Upgrade Tailwind CSS to latest version with npm

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-4/index.mdx

Updates project dependencies to install the latest version of Tailwind CSS.

```bash
$ npm install tailwindcss@latest
```


--------------------------------

### Apply extended opacity scale step

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-4/index.mdx

Demonstrates using newly added opacity scale steps of 5 out of the box, such as opacity-35.

```html
<!-- [!code filename:HTML] -->
<!-- [!code word:opacity-35] -->
<div class="opacity-35">
  <!-- ... -->
</div>
```


--------------------------------

### Prevent bidirectional overflow with justify-center-safe

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-1/index.mdx

Switches alignment to start when the container starts to overflow, ensuring content only overflows in one direction.

```html
<!-- [!code filename:justify-center-safe] -->
<!-- [!code classes:justify-center-safe] -->
<ul class="flex justify-center-safe gap-2 ...">
  <li>Sales</li>
  <li>Marketing</li>
  <li>SEO</li>
  <!-- ... -->
</ul>
```


--------------------------------

### Upgrade Tailwind CSS using webpack

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Installs the latest releases of tailwindcss and the dedicated webpack plugin.

```sh
# [!code filename:Using webpack]
npm install tailwindcss@latest @tailwindcss/webpack@latest
```


--------------------------------

### Upgrade Tailwind CSS using the Tailwind CLI

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Installs the latest releases of tailwindcss and the standalone Tailwind CLI package.

```sh
# [!code filename:Using the Tailwind CLI]
npm install tailwindcss@latest @tailwindcss/cli@latest
```


--------------------------------

### Upgrade Tailwind CSS using npm

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-3/index.mdx

Install the latest version of tailwindcss as a development dependency to upgrade an existing project.

```sh
npm install -D tailwindcss@latest
```


--------------------------------

### Upgrade to Tailwind CSS v2.1 using npm

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-1/index.mdx

Installs the latest version of Tailwind CSS. This is an incremental upgrade with no breaking changes.

```bash
npm install tailwindcss@latest
```


--------------------------------

### Creating a responsive multi-column layout with columns utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3/index.mdx

Apply column count utility classes such as columns-1 and responsive variants like sm:columns-3 to format content into newspaper-style columns.

```html
<!-- [!code word:columns-1] -->
<!-- [!code word:sm\:columns-3] -->
<div class="columns-1 sm:columns-3 ...">
  <p>...</p>
  <!-- ... -->
</div>
```


--------------------------------

### Configure simple string screens in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Sets up the simple string-based screens object required for max-* and dynamic breakpoint variants to work.

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    screens: {
      sm: "640px",
      md: "768px",
      lg: "1024px",
      xl: "1280px",
      "2xl": "1536px",
    },
  },
};
```


--------------------------------

### Using theme() with opacity in arbitrary utility values

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-1/index.mdx

Combine the theme() function and slash opacity syntax within arbitrary value utility classes such as gradient definitions.

```html
<div class="bg-[image:linear-gradient(to_right,theme(colors.red.500)_75%,theme(colors.red.500/25%))]">
  <!-- ... -->
</div>
```


--------------------------------

### Authoring a Case Study in MDX

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2023-08-07-meet-studio-our-new-agency-template/index.mdx

Demonstrates the structure of an MDX case study in the Studio template, exporting metadata objects alongside standard Markdown content and custom components.

```mdx
import logo from "@/images/clients/phobia/logomark-dark.svg";
import imageHero from "./hero.jpg";
import imageJennyWilson from "./jenny-wilson.jpeg";

export const caseStudy = {
  client: "Phobia",
  title: "Overcome your fears, find your match",
  description:
    "Find love in the face of fear — Phobia is a dating app that matches users based on their mutual phobias so they can be scared together.",
  summary: [
    "Find love in the face of fear — Phobia is a dating app that matches users based on their mutual phobias so they can be scared together.",
    "We worked with Phobia to develop a new onboarding flow. A user is shown pictures of common phobias and we use the microphone to detect which ones make them scream, feeding the results into the matching algorithm.",
  ],
  logo,
  image: { src: imageHero },
  date: "2022-06",
  service: "App development",
  testimonial: {
    author: { name: "Jenny Wilson", role: "CPO of Phobia" },
    content:
      "The team at Studio went above and beyond with our onboarding, even finding a way to access the user’s microphone without triggering one of those annoying permission dialogs.",
  },
};

export const metadata = {
  title: `${caseStudy.client} Case Study`,
  description: caseStudy.description,
};

## Overview

Noticing incredibly high churn, the team at Phobia came to the conclusion that, instead of having a
fundamentally flawed business idea, they needed to improve their onboarding process.

Previously users selected their phobias manually but this led to some users selecting things they
weren’t actually afraid of to increase their matches.

To combat this, we developed a system that displays a slideshow of common phobias during
onboarding. We then use malware to surreptitiously access their microphone and detect when they
have audible reactions. We measure the pitch, volume and duration of their screams and feed that
information to the matching algorithm.

The next phase is a VR version of the onboarding flow where users are subjected to a series of
scenarios that will determine their fears. We are currently developing the first scenario, working
title: “Jumping out of a plane full of spiders”.

## What we did

<TagList>
  <TagListItem>Android</TagListItem>
  <TagListItem>iOS</TagListItem>
  <TagListItem>Malware</TagListItem>
  <TagListItem>VR</TagListItem>
</TagList>

<Blockquote author={{ name: "Jenny Wilson", role: "CPO of Phobia" }} image={{ src: imageJennyWilson }}>
  The team at Studio went above and beyond with our onboarding, even finding a way to access the user’s microphone
  without triggering one of those annoying permission dialogs.
</Blockquote>

<StatList>
  <StatListItem value="20%" label="Churn rate" />
  <StatListItem value="5x" label="Uninstalls" />
  <StatListItem value="2.3" label="App store rating" />
  <StatListItem value="8" label="Pending lawsuits" />
</StatList>
```


--------------------------------

### Structuring an abstract TeamList component in React JSX

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/building-react-and-vue-support-for-tailwind-ui/index.mdx

Illustrates a highly abstracted component pattern that enforces strict data models and prop APIs. This example demonstrates how premature componentization can make snippets less adaptable across different domain models.

```jsx
<TeamList>
  {projectMembers.map(member => (
    <TeamList.Item teamMember={member}>
  ))}
</TeamList>
```


--------------------------------

### Define Excerpt in MDX Post Using Marker Comments

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/building-the-tailwind-blog/index.mdx

Demonstrates structuring an MDX blog post with metadata and the `<!--more-->` delimiter so only preview text is bundled for page listings.

```mdx
export const meta = {
  // ...
}

This is the beginning of the post, and what we'd like to
show on the homepage.

<!--​more-->

Anything after that is not included in the bundle unless
you are actually viewing that post.
```


--------------------------------

### Using Heroicons React components

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/heroicons-v1/index.mdx

Import individual icons as React components from `@heroicons/react/solid` and apply custom styling with utility classes.

```jsx
import { BeakerIcon } from "@heroicons/react/solid";

function MyComponent() {
  return (
    <div>
      <BeakerIcon className="h-5 w-5 text-blue-500" />
      <p>...</p>
    </div>
  );
}
```


--------------------------------

### Download and prepare standalone Tailwind CLI executable

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/standalone-cli/index.mdx

Downloads the precompiled standalone CLI binary for macOS arm64 and grants it executable permissions.

```sh
# Example for macOS arm64
curl -sLO https://github.com/tailwindlabs/tailwindcss/releases/latest/download/tailwindcss-macos-arm64
chmod +x tailwindcss-macos-arm64
mv tailwindcss-macos-arm64 tailwindcss
```


--------------------------------

### Applying responsive component variants in HTML

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-5/index.mdx

Demonstrates applying responsive variants to component classes such as prose from @tailwindcss/typography.

```html
<article class="prose md:prose-lg">
  <!-- Content -->
</article>
```


--------------------------------

### Set font size and line height using the shorthand utility

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-3/index.mdx

Combine font size and line-height scale values into a single utility class like text-lg/7 instead of using separate font size and leading classes.

```html
<!-- [!code filename:index.html] -->
<!-- [!code word:leading-7] -->
<!-- [!code word:text-lg/7] -->
<!-- [!code word:text-lg] -->
<p class="text-lg leading-7 ..."><!-- [!code --] -->
<p class="text-lg/7 ..."><!-- [!code ++] -->
  So I started to walk into the water. I won't lie to you boys, I was terrified. But I pressed on, and as I made my way
  past the breakers a strange calm came over me. I don't know if it was divine intervention or the kinship of all living
  things but I tell you Jerry at that moment, I <em>was</em> a marine biologist.
</p>
```


--------------------------------

### Combine motion variants with responsive and pseudo-class variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-6/index.mdx

Stack responsive prefixes (like sm:) and pseudo-class prefixes (like hover:) together with motion-reduce variants.

```html
<!-- With responsive variants -->
<div class="sm:motion-reduce:translate-y-0"></div>

<!-- With pseudo-class variants -->
<div class="motion-reduce:hover:translate-y-0"></div>

<!-- With responsive and pseudo-class variants -->
<div class="sm:motion-reduce:hover:translate-y-0"></div>
```


--------------------------------

### Configuring variants for backgroundClip in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Demonstrates the default variant configuration enabled for the `backgroundClip` core plugin.

```javascript
// [!code filename:tailwind.config.js]
module.exports = {
  variants: {
    backgroundClip: ["responsive"],
  },
};
```


--------------------------------

### Organizing post files and assets in Next.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/building-the-tailwind-blog/index.mdx

Illustrates a Next.js pages directory layout where each post has a dedicated folder containing an index.mdx file and co-located asset files.

```text
public/
src/
├── components/
├── css/
├── img/
└── pages/
    ├── building-the-tailwindcss-blog/
    │   ├── index.mdx
    │   └── card.jpeg
    ├── introducing-linting-for-tailwindcss-intellisense/
    │   ├── index.mdx
    │   ├── css.png
    │   ├── html.png
    │   └── card.jpeg
    ├── _app.js
    ├── _document.js
    └── index.js
next.config.js
package.json
postcss.config.js
README.md
tailwind.config.js
```


--------------------------------

### Build a command preview and dialog using Tailwind Elements

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/vanilla-js-support-for-tailwind-plus/index.mdx

Uses custom HTML element primitives like <el-command-preview>, <el-command-palette>, and <el-dialog> to build interactive command palette previews without a framework. Elements manage display states using standard attributes such as 'for' and 'hidden'.

```html
            <!-- [!code highlight:2] -->
            <el-command-preview for="person-1" hidden class="h-96 w-1/2 flex-none flex-col divide-y divide-gray-100 overflow-y-auto sm:flex">
              <div class="flex-none p-6 text-center">
                <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="" class="mx-auto size-16 rounded-full" />
                <h2 class="mt-3 font-semibold text-gray-900">Leslie Alexander</h2>
                <p class="text-sm/6 text-gray-500">Co-Founder / CEO</p>
              </div>
              <div class="flex flex-auto flex-col justify-between p-6">
                <dl class="grid grid-cols-1 gap-x-6 gap-y-3 text-sm text-gray-700">
                  <dt class="col-end-1 font-semibold text-gray-900">Phone</dt>
                  <dd>1-493-747-9031</dd>
                  <dt class="col-end-1 font-semibold text-gray-900">URL</dt>
                  <dd class="truncate"><a href="https://example.com" class="text-indigo-600 underline">https://example.com</a></dd>
                  <dt class="col-end-1 font-semibold text-gray-900">Email</dt>
                  <dd class="truncate"><a href="mailto:lesliealexander@example.com" class="text-indigo-600 underline">lesliealexander@example.com</a></dd>
                </dl>
                <button type="button" class="mt-6 w-full rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-xs hover:bg-indigo-500 focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">Send message</button>
              </div>
              <!-- [!code highlight:2] -->
            </el-command-preview>
            <!-- ... -->
          </div>
          <!-- [!code highlight:3] -->
        </el-command-palette>
      </el-dialog-panel>
    </div>
  </dialog>
  <!-- [!code highlight:2] -->
</el-dialog>
```


--------------------------------

### Set logical sizing with inline-size and block-size

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Use `inline-*`, `block-*`, `min-inline-*`, `max-inline-*`, `min-block-*`, and `max-block-*` to size elements logically across writing modes.

```html
<!-- [!code classes:inline-full,min-inline-0,max-inline-lg,block-64,min-block-24,max-block-screen] -->
<div class="block-64 inline-full max-block-screen max-inline-lg min-block-24 min-inline-0 ...">
  <!-- ... -->
</div>
```


--------------------------------

### Configure Webpack resourceQuery Loader for Post Previews

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/building-the-tailwind-blog/index.mdx

Defines a custom Webpack loader matching `resourceQuery: /preview/` to trim MDX source content down to the excerpt demarcated by HTML comment tags.

```javascript
{
  resourceQuery: /preview/,
  use: [
    ...mdx,
    createLoader(function (src) {
      if (src.includes('<!--​more​-->')) {
        const [preview] = src.split('<!--​more​-->')
        return this.callback(null, preview)
      }

      const [preview] = src.split('<!--​/excerpt​-->')
      return this.callback(null, preview.replace('<!--​excerpt​-->', ''))
    }),
  ],
},
```


--------------------------------

### Configure multiple Tailwind config files using @config

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Use the `@config` directive inside a CSS file to specify a dedicated configuration file for that stylesheet. This allows projects to maintain separate Tailwind setups, such as distinct admin and client stylesheets.

```css
@config "./tailwind.admin.config.js";
@tailwind base;
@tailwind components;
@tailwind utilities;
```

```css
@config "./tailwind.client.config.js";
@tailwind base;
@tailwind components;
@tailwind utilities;
```


--------------------------------

### Create a dropdown menu using el-dropdown and el-menu

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/vanilla-js-support-for-tailwind-plus/index.mdx

Constructs an interactive dropdown component using `<el-dropdown>` and `<el-menu>`. Component state, positioning, and transitions are styled with Tailwind CSS utility classes.

```html
<!-- [!code highlight:2] -->
<el-dropdown class="relative inline-block text-left">
  <button class="inline-flex w-full justify-center gap-x-1.5 rounded-md bg-white px-3 py-2 text-sm font-semibold text-gray-900 shadow-xs ring-1 ring-gray-300 ring-inset hover:bg-gray-50">
    Options
    <svg viewBox="0 0 20 20" fill="currentColor" aria-hidden="true" class="-mr-1 size-5 text-gray-400">
      <path d="M5.22 8.22a.75.75 0 0 1 1.06 0L10 11.94l3.72-3.72a.75.75 0 1 1 1.06 1.06l-4.25 4.25a.75.75 0 0 1-1.06 0L5.22 9.28a.75.75 0 0 1 0-1.06Z" clip-rule="evenodd" fill-rule="evenodd" />
    </svg>
  </button>

  <!-- [!code highlight:2] -->
  <el-menu anchor="bottom end" popover class="w-56 origin-top-right rounded-md bg-white shadow-lg ring-1 ring-black/5 transition transition-discrete [--anchor-gap:--spacing(2)] focus:outline-hidden data-closed:scale-95 data-closed:transform data-closed:opacity-0 data-enter:duration-100 data-enter:ease-out data-leave:duration-75 data-leave:ease-in">
    <div class="py-1">
      <a href="#" class="block px-4 py-2 text-sm text-gray-700 focus:bg-gray-100 focus:text-gray-900 focus:outline-hidden">Account settings</a>
      <a href="#" class="block px-4 py-2 text-sm text-gray-700 focus:bg-gray-100 focus:text-gray-900 focus:outline-hidden">Support</a>
      <a href="#" class="block px-4 py-2 text-sm text-gray-700 focus:bg-gray-100 focus:text-gray-900 focus:outline-hidden">License</a>
      <form action="#" method="POST">
        <button type="submit" class="block w-full px-4 py-2 text-left text-sm text-gray-700 focus:bg-gray-100 focus:text-gray-900 focus:outline-hidden">Sign out</button>
      </form>
    </div>
  <!-- [!code highlight:3] -->
  </el-menu>
</el-dropdown>
```


--------------------------------

### Pause and resume CSS animations on hover using Tailwind CSS

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2024-09-12-radiant-a-beautiful-new-marketing-site-template/index.mdx

Applies infinite CSS keyframe animations that pause in place when unhovered and resume running via `group-hover:[animation-play-state:running]`. Individual logo elements specify negative `animation-delay` values to stagger starting positions along the timeline.

```jsx
// [!code filename:logo-timeline.tsx]
function Logo({
  label,
  src,
  className,
}: {
  label: string
  src: string
  className: string
}) {
  return (
    <div
      className={clsx(
        className,
        'absolute top-2 grid grid-cols-[1rem,1fr] items-center gap-2 whitespace-nowrap px-3 py-1',
        'rounded-full bg-gradient-to-t from-gray-800 from-50% to-gray-700 ring-1 ring-inset ring-white/10',
        // [!code highlight:2]
        '[--move-x-from:-100%] [--move-x-to:calc(100%+100cqw)] [animation-iteration-count:infinite] [animation-name:move-x] [animation-play-state:paused] [animation-timing-function:linear] group-hover:[animation-play-state:running]',
      )
    >
      <img alt="" src={src} className="size-4" />
      <span className="text-sm/6 font-medium text-white">{label}</span>
    </div>
  )
}

export function LogoTimeline() {
  return (
    /* ... */
    <Row>
      <Logo
        label="Loom"
        src="./logo-timeline/loom.svg"
        // [!code highlight:2]
        className="[animation-delay:-26s] [animation-duration:30s]"
      />
      <Logo
        label="Gmail"
        src="./logo-timeline/gmail.svg"
        // [!code highlight:2]
        className="[animation-delay:-8s] [animation-duration:30s]"
      />
    </Row>
    /* ... */
```


--------------------------------

### Configure custom container sizes in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Extend container query size scales by defining custom container keys under theme.extend.containers.

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      containers: {
        "2xs": "16rem",
        // etc...
      },
    },
  },
};
```


--------------------------------

### Create a SidebarLayout with Sidebar and Navbar components

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2024-05-24-catalyst-application-layouts/index.mdx

Renders a sidebar layout that moves the navigation into a collapsible mobile menu on smaller viewports. Pass the desktop menu into the sidebar prop and mobile navigation into the navbar prop.

```jsx
import { SidebarLayout } from "@/components/sidebar-layout";
import { Navbar } from "@/components/navbar";
import { Sidebar } from "@/components/sidebar";

function Example({ children }) {
  return (
    <SidebarLayout
      sidebar={<Sidebar>{/* Sidebar menu */}</Sidebar>}
      navbar={<Navbar>{/* Navbar for mobile screens */}</Navbar>}
    >
      {/* Your page content */}
    </SidebarLayout>
  );
}
```


--------------------------------

### Creating Enter/Leave Transitions in Vue.js with <transition>

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/utility-friendly-transitions-with-tailwindui-react/index.mdx

Applies utility classes to manage enter and leave transitions on an element controlled by v-show in Vue.js.

```html
<transition
  enter-active-class="transition-opacity duration-75"
  enter-from-class="opacity-0"
  enter-to-class="opacity-100"
  leave-active-class="transition-opacity duration-150"
  leave-from-class="opacity-100"
  leave-to-class="opacity-0"
>
  <div v-show="isShowing">
    <!-- Will fade in and out -->
  </div>
</transition>
```


--------------------------------

### Position elements using logical inset utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Use `inset-s-*`, `inset-e-*`, `inset-bs-*`, and `inset-be-*` to position elements relative to inline and block start/end edges.

```html
<!-- [!code classes:inset-s-0,inset-e-4,inset-bs-2,inset-be-8] -->
<div class="absolute inset-s-0 inset-e-4 inset-bs-2 inset-be-8 ...">
  <!-- ... -->
</div>
```


--------------------------------

### Reset styles across breakpoints without max-* variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Illustrates the traditional approach of setting a utility at one min-width breakpoint and explicitly resetting it at a larger breakpoint.

```html
<div class="md:sr-only xl:not-sr-only">
  <!-- ... -->
</div>
```


--------------------------------

### Create a select component using el-select and el-options

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/vanilla-js-support-for-tailwind-plus/index.mdx

Defines a custom select menu using `<el-select>`, `<el-selectedcontent>`, `<el-options>`, and `<el-option>`. Automatically manages keyboard navigation, ARIA attributes, and focus states.

```html
<label for="select" class="block text-sm/6 font-medium text-gray-900">Assigned to</label>
<!-- [!code highlight:2] -->
<el-select id="select" name="selected" value="4" class="mt-2 block">
  <button type="button" class="grid w-full cursor-default grid-cols-1 ...">
    <!-- [!code highlight:2] -->
    <el-selectedcontent></el-selectedcontent>
    <svg viewBox="0 0 16 16" fill="currentColor" aria-hidden="true" class="col-start-1 row-start-1 ...">
      <!-- ... -->
    </svg>
  </button>

  <!-- [!code highlight:2] -->
  <el-options anchor="bottom start" popover class="max-h-60 w-(--button-width) [--anchor-gap:--spacing(1)] ...">
      <!-- [!code highlight:2] -->
    <el-option value="1" class="group/option relative block focus:bg-indigo-600 ...">
      <div class="flex items-center">
        <span aria-hidden="true" class="inline-block size-2 shrink-0 ..."></span>
        <span class="ml-3 block group-aria-selected/option:font-semibold ...">
          Wade Cooper
          <span class="sr-only"> is online</span>
        </span>
      </div>
      <span class="group-not-aria-selected/option:hidden group-focus/option:text-white in-[el-selectedcontent]:hidden ...">
        <svg viewBox="0 0 20 20" fill="currentColor" aria-hidden="true" class="size-5">
            <!-- ... -->
        </svg>
      </span>
      <!-- [!code highlight:2] -->
    </el-option>
    <!-- ... -->
    <!-- [!code highlight:2] -->
  </el-options>
  <!-- [!code highlight:2] -->
</el-select>
```


--------------------------------

### Applying text-shadow size utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-1/index.mdx

Applies default theme text shadows ranging from text-shadow-2xs to text-shadow-lg to make headings or text stand out against busy backgrounds.

```html
<!-- [!code classes:text-shadow-2xs,text-shadow-xs,text-shadow-sm,text-shadow-md,text-shadow-lg,text-shadow-xl] -->
<p class="text-shadow-2xs ...">The quick brown fox...</p>
<p class="text-shadow-xs ...">The quick brown fox...</p>
<p class="text-shadow-sm ...">The quick brown fox...</p>
<p class="text-shadow-md ...">The quick brown fox...</p>
<p class="text-shadow-lg ...">The quick brown fox...</p>
```


--------------------------------

### Build a command palette using custom HTML elements

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/vanilla-js-support-for-tailwind-plus/index.mdx

Structure a command palette UI using custom elements such as el-command-list, el-defaults, el-command-group, and el-no-results without relying on a JavaScript framework.

```html
          <div class="flex transform-gpu divide-x divide-gray-100">
            <div class="max-h-96 min-w-0 flex-auto scroll-py-4 overflow-y-auto px-6 py-4">
              <!-- [!code highlight:3] -->
              <el-command-list class="-mx-2 block text-sm text-gray-700">
                <el-defaults>
                  <h2 class="mx-2 mt-2 mb-4 text-xs font-semibold text-gray-500">Recent searches</h2>
                  <div class="text-sm text-gray-700">
                    <a id="person-suggestion-6" href="#" class="group flex cursor-default items-center rounded-md p-2 select-none focus:outline-hidden aria-selected:bg-gray-100 aria-selected:text-gray-900">
                      <img src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="" class="size-6 flex-none rounded-full" />
                      <span class="ml-3 flex-auto truncate">Tom Cook</span>
                      <svg viewBox="0 0 20 20" fill="currentColor" aria-hidden="true" class="ml-3 hidden size-5 flex-none text-gray-400 group-aria-selected:block">
                        <path d="M8.22 5.22a.75.75 0 0 1 1.06 0l4.25 4.25a.75.75 0 0 1 0 1.06l-4.25 4.25a.75.75 0 0 1-1.06-1.06L11.94 10 8.22 6.28a.75.75 0 0 1 0-1.06Z" clip-rule="evenodd" fill-rule="evenodd" />
                      </svg>
                    </a>
                   <!-- ... -->
                  </div>
                  <!-- [!code highlight:2] -->
                </el-defaults>
                <!-- [!code highlight:2] -->
                <el-command-group hidden class="sm:h-96">
                  <a id="person-1" href="#" hidden class="group flex cursor-default items-center rounded-md p-2 select-none focus:outline-hidden aria-selected:bg-gray-100 aria-selected:text-gray-900">
                    <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="" class="size-6 flex-none rounded-full" />
                    <span class="ml-3 flex-auto truncate">Leslie Alexander</span>
                    <svg viewBox="0 0 20 20" fill="currentColor" aria-hidden="true" class="ml-3 hidden size-5 flex-none text-gray-400 group-aria-selected:block">
                      <path d="M8.22 5.22a.75.75 0 0 1 1.06 0l4.25 4.25a.75.75 0 0 1 0 1.06l-4.25 4.25a.75.75 0 0 1-1.06-1.06L11.94 10 8.22 6.28a.75.75 0 0 1 0-1.06Z" clip-rule="evenodd" fill-rule="evenodd" />
                    </svg>
                  </a>
                  <!-- ... -->
                  <!-- [!code highlight:4] -->
                </el-command-group>
              </el-command-list>
              <el-no-results hidden class="block px-6 py-14 text-center text-sm sm:px-14">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" aria-hidden="true" class="mx-auto size-6 text-gray-400">
                  <path d="M15 19.128a9.38 9.38 0 0 0 2.625.372 9.337 9.337 0 0 0 4.121-.952 4.125 4.125 0 0 0-7.533-2.493M15 19.128v-.003c0-1.113-.285-2.16-.786-3.07M15 19.128v.106A12.318 12.318 0 0 1 8.624 21c-2.331 0-4.512-.645-6.374-1.766l-.001-.109a6.375 6.375 0 0 1 11.964-3.07M12 6.375a3.375 3.375 0 1 1-6.75 0 3.375 3.375 0 0 1 6.75 0Zm8.25 2.25a2.625 2.625 0 1 1-5.25 0 2.625 2.625 0 0 1 5.25 0Z" stroke-linecap="round" stroke-linejoin="round" />
                </svg>
                <p class="mt-4 font-semibold text-gray-900">No people found</p>
                <p class="mt-2 text-gray-500">We couldn't find anything with that term. Please try again.</p>
                <!-- [!code highlight:2] -->
              </el-no-results>
            </div>
```


--------------------------------

### Apply logical border width utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Use `border-bs` and `border-be-*` utilities to define border widths at the logical block-start and block-end edges.

```html
<!-- [!code classes:border-bs,border-be-2] -->
<div class="border-bs border-be-2 ...">
  <!-- ... -->
</div>
```


--------------------------------

### Ordering utilities by box model and layout impact

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/automatic-class-sorting-with-prettier/index.mdx

High impact layout classes are placed at the beginning and decorative classes at the end while keeping related utilities together.

```html
<div class="text-gray-700 shadow-md p-3 border-gray-300 ml-4 h-24 flex border-2"> <!-- [!code --] -->
<div class="ml-4 flex h-24 border-2 border-gray-300 p-3 text-gray-700 shadow-md"> <!-- [!code ++] -->
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Apply focus rings using ring utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Applies a solid box-shadow ring on focus that respects border radius without impacting layout.

```html
<button class="focus:ring-opacity-50 focus:ring-2 focus:ring-blue-300 focus:outline-none ...">
  <!-- ... -->
</button>
```


--------------------------------

### Embedding React components in MDX

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/building-the-tailwind-blog/index.mdx

Demonstrates embedding a live React component inside standard Markdown content using MDX.

```md
# My first MDX post

MDX is a really cool authoring format because it lets
you embed React components right in your markdown:

<MyComponent myProp={5} />

How cool is that?
```


--------------------------------

### Defining container query ranges with stacked @min-* and @max-*

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4/index.mdx

Stack `@min-*` and `@max-*` variants together to target specific container width ranges.

```html
<!-- [!code filename:HTML] -->
<!-- [!code classes:@container,@min-md:@max-xl:hidden] -->
<div class="@container">
  <div class="flex @min-md:@max-xl:hidden">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Execute standalone Tailwind CLI commands

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/standalone-cli/index.mdx

Initialize a tailwind.config.js file, run the watcher during development, or build and minify CSS for production.

```sh
# Create a tailwind.config.js file
./tailwindcss init

# Start a watcher
./tailwindcss -i input.css -o output.css --watch

# Compile and minify your CSS for production
./tailwindcss -i input.css -o output.css --minify
```


--------------------------------

### Render a key-value list using DescriptionList

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2024-05-24-catalyst-application-layouts/index.mdx

Structure key-value data with DescriptionList, DescriptionTerm, and DescriptionDetails components. Provides responsive styling and dark mode support mirroring standard HTML definition lists.

```jsx
import { DescriptionDetails, DescriptionList, DescriptionTerm } from "@/components/description-list";

function Example() {
  return (
    <DescriptionList>
      <DescriptionTerm>Customer</DescriptionTerm>
      <DescriptionDetails>Michael Foster</DescriptionDetails>

      <DescriptionTerm>Event</DescriptionTerm>
      <DescriptionDetails>Bear Hug: Live in Concert</DescriptionDetails>

      {/* ... */}
    </DescriptionList>
  );
}
```


--------------------------------

### Apply custom @theme utilities in HTML

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-alpha/index.mdx

Reference theme-generated utility classes and variants directly in markup.

```html
<!-- [!code filename:index.html] -->
<!-- [!code word:3xl\:max-w-xl] -->
<!-- [!code word:font-display] -->
<!-- [!code word:text-neon-cyan] -->
<div class="max-w-lg 3xl:max-w-xl">
  <h1 class="font-display text-4xl">
    Data to <span class="text-neon-cyan">enrich</span> your online business
  </h1>
</div>
```


--------------------------------

### Apply colored drop shadows with drop-shadow utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-1/index.mdx

Use color utilities such as drop-shadow-cyan-500/50 or drop-shadow-indigo-500/50 alongside drop-shadow size classes to apply colored drop shadows with opacity.

```html
<!-- [!code classes:drop-shadow-cyan-500/50,drop-shadow-blue-500/50,drop-shadow-indigo-500/50] -->
<svg class="fill-cyan-500 drop-shadow-xl drop-shadow-cyan-500/50 ...">...</svg>
<svg class="fill-blue-500 drop-shadow-xl drop-shadow-blue-500/50 ...">...</svg>
<svg class="fill-indigo-500 drop-shadow-xl drop-shadow-indigo-500/50 ...">...</svg>
```


--------------------------------

### Create arbitrary grid column sizes dynamically

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4/index.mdx

Applies custom grid column counts out of the box using dynamic utilities like grid-cols-15 without defining custom arbitrary values or configuration.

```html
<!-- [!code filename:HTML] -->
<!-- [!code classes:grid-cols-15] -->
<div class="grid grid-cols-15">
  <!-- ... -->
</div>
```


--------------------------------

### Default configuration for gradient plugins in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Shows the default theme and variant definitions for the `backgroundImage` and `gradientColorStops` core plugins.

```javascript
// [!code filename:tailwind.config.js]
module.exports = {
  theme: {
    backgroundImage: {
      "gradient-to-t": "linear-gradient(to top, var(--gradient-color-stops))",
      "gradient-to-tr": "linear-gradient(to top right, var(--gradient-color-stops))",
      "gradient-to-r": "linear-gradient(to right, var(--gradient-color-stops))",
      "gradient-to-br": "linear-gradient(to bottom right, var(--gradient-color-stops))",
      "gradient-to-b": "linear-gradient(to bottom, var(--gradient-color-stops))",
      "gradient-to-bl": "linear-gradient(to bottom left, var(--gradient-color-stops))",
      "gradient-to-l": "linear-gradient(to left, var(--gradient-color-stops))",
      "gradient-to-tl": "linear-gradient(to top left, var(--gradient-color-stops))",
    },
    gradientColorStops: (theme) => theme("colors"),
  },
  variants: {
    backgroundImage: ["responsive"],
    gradientColorStops: ["responsive", "hover", "focus"],
  },
};
```


--------------------------------

### Combine responsive, dark mode, and hover variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Combines responsive prefixes, the dark variant, and state variants like `lg:dark:hover:`.

```html
<button class="lg:dark:bg-white lg:dark:hover:bg-gray-50 ...">
  <!-- ... -->
</button>
```


--------------------------------

### Applying outline-white and outline-black focus indicators

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-9/index.mdx

Use outline-white on dark backgrounds and outline-black on light backgrounds to render 2px dotted focus outlines with a 2px offset.

```html
<!-- Use `outline-white` on dark backgrounds -->
<div class="bg-gray-900">
  <button class="focus:outline-white ...">
    <!-- ... -->
  </button>
</div>

<!-- Use `outline-black` on light backgrounds -->
<div class="bg-white">
  <button class="focus:outline-black ...">
    <!-- ... -->
  </button>
</div>
```


--------------------------------

### Create a list item dropdown menu using Headless UI Menu and Transition in React

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/building-react-and-vue-support-for-tailwind-ui/index.mdx

Renders a user list where each item contains an accessible dropdown menu powered by Headless UI's Menu and Transition components. Provides fully customizable markup, transitions, and state management without rigid component abstractions.

```jsx
import { Menu, Transition } from "@headlessui/react";
import { DotsVerticalIcon } from "@heroicons/react/solid";
import { Fragment } from "react";

const people = [
  {
    name: "Calvin Hawkins",
    email: "calvin.hawkins@example.com",
    image:
      "https://images.unsplash.com/photo-1491528323818-fdd1faba62cc?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80",
  },
  {
    name: "Kristen Ramos",
    email: "kristen.ramos@example.com",
    image:
      "https://images.unsplash.com/photo-1550525811-e5869dd03032?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80",
  },
  {
    name: "Ted Fox",
    email: "ted.fox@example.com",
    image:
      "https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80",
  },
];

export default function Example() {
  return (
    <ul className="divide-y divide-gray-200">
      {people.map((person) => (
        <li key={person.email} className="flex py-4">
          <img className="h-10 w-10 rounded-full" src={person.image.src} alt="" />
          <div className="ml-3">
            <p className="text-sm font-medium text-gray-900">{person.name}</p>
            <p className="text-sm text-gray-500">{person.email}</p>
          </div>
          <Menu as="div" className="relative ml-3 inline-block text-left">
            {({ open }) => (
              <>
                <div>
                  <Menu.Button className="flex items-center rounded-full bg-gray-100 text-gray-400 hover:text-gray-600 focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 focus:ring-offset-gray-100 focus:outline-none">
                    <span className="sr-only">Open options</span>
                    <DotsVerticalIcon className="h-5 w-5" aria-hidden="true" />
                  </Menu.Button>
                </div>

                <Transition
                  show={open}
                  as={Fragment}
                  enter="transition ease-out duration-100"
                  enterFrom="transform opacity-0 scale-95"
                  enterTo="transform opacity-100 scale-100"
                  leave="transition ease-in duration-75"
                  leaveFrom="transform opacity-100 scale-100"
                  leaveTo="transform opacity-0 scale-95"
                >
                  <Menu.Items
                    static
                    className="ring-opacity-5 absolute right-0 mt-2 w-56 origin-top-right rounded-md bg-white shadow-lg ring-1 ring-black focus:outline-none"
                  >
                    <div className="py-1">
                      <Menu.Item>
                        {({ active }) => (
                          <a
                            href="#"
                            className={classNames(
                              active ? "bg-gray-100 text-gray-900" : "text-gray-700",
                              "block px-4 py-2 text-sm",
                            )}
                          >
                            View details
                          </a>
                        )}
                      </Menu.Item>
                      <Menu.Item>
                        {({ active }) => (
                          <a
                            href="#"
                            className={classNames(
                              active ? "bg-gray-100 text-gray-900" : "text-gray-700",
                              "block px-4 py-2 text-sm",
                            )}
                          >
                            Send message
                          </a>
                        )}
                      </Menu.Item>
                    </div>
                  </Menu.Items>
                </Transition>
              </>
            )}
          </Menu>
        </li>
      ))}
    </ul>
  );
}
```


--------------------------------

### Build a command palette using HTML and Elements

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/vanilla-js-support-for-tailwind-plus/index.mdx

Constructs a command palette modal using custom elements like `el-dialog` and `el-command-palette` with standard HTML dialog invocation attributes. No custom JavaScript is required to toggle the modal dialog.

```html
<button command="show-modal" commandfor="dialog" class="rounded-md bg-white/80 px-2.5 py-1.5 text-sm font-semibold text-gray-900 hover:bg-white/90">
  Open command palette
</button>

<!-- [!code highlight:2] -->
<el-dialog>
  <dialog id="dialog" class="backdrop:bg-transparent">
    <el-dialog-backdrop class="fixed inset-0 bg-gray-500/25 transition-opacity data-closed:opacity-0 data-enter:duration-300 data-enter:ease-out data-leave:duration-200 data-leave:ease-in"></div>

    <div tabindex="0" class="fixed inset-0 w-screen overflow-y-auto p-4 focus:outline-none sm:p-6 md:p-20">
      <!-- [!code highlight:3] -->
      <el-dialog-panel class="mx-auto block max-w-3xl transform overflow-hidden rounded-xl bg-white shadow-2xl ring-1 ring-black/5 transition-all data-closed:scale-95 data-closed:opacity-0 data-enter:duration-300 data-enter:ease-out data-leave:duration-200 data-leave:ease-in">
        <el-command-palette class="divide-y divide-gray-100">
          <div class="grid grid-cols-1">
            <input type="text" autofocus placeholder="Search..." class="col-start-1 row-start-1 h-12 w-full pr-4 pl-11 text-base text-gray-900 outline-hidden placeholder:text-gray-400 sm:text-sm" />
            <svg viewBox="0 0 20 20" fill="currentColor" aria-hidden="true" class="pointer-events-none col-start-1 row-start-1 ml-4 size-5 self-center text-gray-400">
              <path d="M9 3.5a5.5 5.5 0 1 0 0 11 5.5 5.5 0 0 0 0-11ZM2 9a7 7 0 1 1 12.452 4.391l3.328 3.329a.75.75 0 1 1-1.06 1.06l-3.329-3.328A7 7 0 0 1 2 9Z" clip-rule="evenodd" fill-rule="evenodd" />
            </svg>
          </div>
```


--------------------------------

### Apply arbitrary value utility classes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-1/index.mdx

Use square bracket notation to pass custom arbitrary values directly into utility classes.

```html
<!-- [!code word:top-[117px]] -->
<div class="top-[117px]">
  <!-- ... -->
</div>
```


--------------------------------

### Using arbitrary values across utility classes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Apply arbitrary values across various core Tailwind plugins using square bracket syntax.

```html
<div class="col-start-[73] object-[50%] placeholder-[#aabbcc] ..."></div>
```


--------------------------------

### Create floating labels with peer-placeholder-shown in HTML

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Combines the peer class on an input with peer-placeholder-shown and peer-focus variants on a label to dynamically adjust label position. Requires Just-in-Time mode.

```html
<div class="relative">
  <input id="name" class="peer ..." />
  <label for="name" class="peer-placeholder-shown:top-4 peer-focus:top-0 ..."> Name </label>
</div>
```


--------------------------------

### Set gradient color stop positions using arbitrary values

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-3/index.mdx

Use square bracket notation like from-[21.56%] to specify exact arbitrary stop positions when standard step values are insufficient.

```html
<!-- [!code word:from-[21.56%\]] -->
<div class="bg-gradient-to-r from-cyan-400 from-[21.56%] ...">
  <!-- ... -->
</div>
```


--------------------------------

### Merge multiple configuration presets in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-9/index.mdx

Provide multiple preset packages in the `presets` array. Presets are merged sequentially from top to bottom before project-specific theme extensions are applied.

```javascript
module.exports = {
  presets: [require("@my-company/tailwind-base"), require("@my-company/tailwind-marketing")],
  theme: {
    extend: {
      // Project specific overrides...
    },
  },
};
```


--------------------------------

### Creating 3D transforms with perspective and rotation utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4/index.mdx

Apply 3D transform utilities including `perspective-distant`, `transform-3d`, and axis-specific rotation classes like `rotate-x-51` and `rotate-z-43`.

```html
<!-- [!code classes:perspective-distant,transform-3d,rotate-x-51,rotate-z-43] -->
<div class="perspective-distant">
  <article class="rotate-x-51 rotate-z-43 transform-3d ...">
    <!-- ... -->
  </article>
</div>
```


--------------------------------

### Applying responsive variants to the container class in HTML

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-5/index.mdx

Apply a responsive prefix like md: to lock the container width at specific breakpoints and above.

```html
<!-- Only lock the width at `md` sizes and above -->
<div class="md:container">
  <!-- ... -->
</div>
```


--------------------------------

### Scaling elements with zoom-* utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Use `zoom-*` utilities to apply the CSS `zoom` property to elements with preset scaling factors.

```html
<!-- [!code classes:zoom-75,zoom-100,zoom-125] -->
<div class="zoom-75 ...">Zoomed out</div>
<div class="zoom-100 ...">Normal</div>
<div class="zoom-125 ...">Zoomed in</div>
```


--------------------------------

### Create conic and radial gradients with bg-conic-* and bg-radial-*

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4/index.mdx

Utilizes bg-conic-* and bg-radial-* utilities along with color stops and arbitrary modifiers to create conic and radial gradients.

```html
<!-- [!code classes:bg-conic/[in_hsl_longer_hue],bg-radial-[at_25%_25%]] -->
<div class="size-24 rounded-full bg-conic/[in_hsl_longer_hue] from-red-600 to-red-600"></div>
<div class="size-24 rounded-full bg-radial-[at_25%_25%] from-white to-zinc-900 to-75%"></div>
```


--------------------------------

### Fetch post preview list in getStaticProps

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/building-the-tailwind-blog/index.mdx

Loads all post previews at build time and maps them to lightweight objects containing only the title and link. These props are supplied to the page component for route matching.

```javascript
import getAllPostPreviews from "@/getAllPostPreviews";

export async function getStaticProps() {
  return {
    props: {
      posts: getAllPostPreviews().map((post) => ({
        title: post.module.meta.title,
        link: post.link.substr(1),
      })),
    },
  };
}
```


--------------------------------

### Applying default transition duration and timing function

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Uses a single transition class that inherits the configured default duration and timing function.

```html
<button class="transition ...">Count them again</button>
```


--------------------------------

### Set logical scroll margin and scroll padding

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Use `scroll-mbs-*`, `scroll-mbe-*`, `scroll-pbs-*`, and `scroll-pbe-*` to manage scroll offset snapping along logical block axes.

```html
<!-- [!code classes:scroll-pbs-12,scroll-pbe-12,scroll-mbs-4,scroll-mbe-4] -->
<div class="scroll-mbs-4 scroll-mbe-4 scroll-pbs-12 scroll-pbe-12 ...">
  <!-- ... -->
</div>
```


--------------------------------

### Using arbitrary opacity values with square bracket notation

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Specify custom opacity values directly on color utilities using square bracket notation in Just-in-Time mode.

```html
<div class="bg-red-500/[0.31]"></div>
```


--------------------------------

### Create a StackedLayout with Navbar and mobile Sidebar components

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2024-05-24-catalyst-application-layouts/index.mdx

Renders a stacked layout with top horizontal navigation and collapsible mobile sidebar support. Pass the top menu to the navbar prop and the mobile navigation to the sidebar prop.

```jsx
import { StackedLayout } from "@/components/stacked-layout";
import { Navbar } from "@/components/navbar";
import { Sidebar } from "@/components/sidebar";

function Example({ children }) {
  return (
    <StackedLayout
      navbar={<Navbar>{/* Top navigation menu */}</Navbar>}
      sidebar={<Sidebar>{/* Sidebar content for mobile menu */}</Sidebar>}
    >
      {/* Your page content */}
    </StackedLayout>
  );
}
```


--------------------------------

### Apply max-width breakpoint with max-* variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Applies utilities up to a specified configured breakpoint instead of using min-width queries.

```html
<div class="max-lg:p-8">
  <!-- Will apply `p-8` until the `lg` breakpoint kicks in -->
</div>
```


--------------------------------

### Customize underline color, style, and thickness

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3/index.mdx

Combine `underline` with `decoration-{color}`, `decoration-{style}`, and `decoration-{thickness}` utilities to style text underlines.

```html
<p>
  I’m Derek, an astro-engineer based in Tatooine. I like to build X-Wings at
  <!-- [!code word:decoration-sky-500 decoration-2] -->
  <a href="#" class="underline decoration-sky-500 decoration-2"> My Company, Inc </a>. Outside of work, I like to{" "}
  <!-- [!code word:decoration-pink-500 decoration-dotted decoration-2] -->
  <a href="#" class="underline decoration-pink-500 decoration-dotted decoration-2"> watch pod-racing </a> and have
  <!-- [!code word:decoration-indigo-500 decoration-wavy decoration-2] -->
  <a href="#" class="underline decoration-indigo-500 decoration-wavy decoration-2"> light-saber </a>{" "} fights.
</p>
```


--------------------------------

### Stack min and max-* variants for scoped breakpoint ranges

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Avoids style-resetting utilities by combining min-width and max-* variants to target a closed breakpoint window.

```html
<div class="md:max-xl:sr-only">
  <!-- ... -->
</div>
```


--------------------------------

### Applying mauve, olive, mist, and taupe palette classes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Use mauve, olive, mist, and taupe utility classes for background, text, border, and shadow styling when alternative neutral tones are preferred.

```html
<!-- [!code classes:bg-mauve-950,text-mauve-100,bg-olive-100,text-olive-950,border-mist-200,shadow-taupe-950/10] -->
<div class="bg-mauve-950 text-mauve-100 ...">Mauve</div>
<div class="bg-olive-100 text-olive-950 ...">Olive</div>
<div class="border border-mist-200 shadow-taupe-950/10 ...">Mist and taupe</div>
```


--------------------------------

### Override a theme namespace with initial

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-alpha/index.mdx

Clear an entire set of default variables by setting a namespace wildcard like --color-*: initial before assigning custom values.

```css
/* [!code filename:main.css] */
@import "tailwindcss";

@theme {
  --color-*: initial;

  --color-gray-50: #f8fafc;
  --color-gray-100: #f1f5f9;
  --color-gray-200: #e2e8f0;
  /* ... */
  --color-green-800: #3f6212;
  --color-green-900: #365314;
  --color-green-950: #1a2e05;
}
```


--------------------------------

### Creating a custom Checkbox with Field and Label

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/headless-ui-v2/index.mdx

Demonstrates building a custom checkbox using Headless UI Checkbox, Field, Label, and Description components. Checkboxes support controlled or uncontrolled modes and sync state with a hidden form input.

```jsx
import { Checkbox, Description, Field, Label } from "@headlessui/react";
import { CheckmarkIcon } from "./icons/checkmark";
import clsx from "clsx";

function Example() {
  return (
    <Field>
      // [!code highlight:11]
      <Checkbox
        defaultChecked
        className={clsx(
          "size-4 rounded border bg-white dark:bg-white/5",
          "data-[checked]:border-transparent data-[checked]:bg-blue-500",
          "focus:outline-none data-[focus]:outline-2 data-[focus]:outline-offset-2 data-[focus]:outline-blue-500",
        )}
      >
        <CheckmarkIcon className="stroke-white opacity-0 group-data-[checked]:opacity-100" />
      </Checkbox>
      <div>
        <Label>Enable beta features</Label>
        <Description>This will give you early access to any awesome new features we're developing.</Description>
      </div>
    </Field>
  );
}
```


--------------------------------

### Using shorthand color opacity syntax

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Adjust the alpha channel of a color utility directly using slash notation instead of separate opacity utility classes.

```html
<div class="bg-red-500 bg-opacity-25"> <!-- [!code --] -->
<div class="bg-red-500/25"> <!-- [!code ++] -->
</div>
```


--------------------------------

### Adding Colored Box Shadows with Utility Classes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3/index.mdx

Combine box shadow size utilities like shadow-lg with colored shadow utilities and opacity modifiers to create glow or colored shadow effects on elements.

```html
<!-- [!code word:shadow-lg shadow-cyan-500/50] -->
<button class="bg-cyan-500 shadow-lg shadow-cyan-500/50 ...">Subscribe</button>
<!-- [!code word:shadow-lg shadow-blue-500/50] -->
<button class="bg-blue-500 shadow-lg shadow-blue-500/50 ...">Subscribe</button>
<!-- [!code word:shadow-lg shadow-indigo-500/50] -->
<button class="bg-indigo-500 shadow-lg shadow-indigo-500/50 ...">Subscribe</button>
```


--------------------------------

### Configuring Tailwind CSS with CSS-based theme and imports

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2023-07-18-tailwind-connect-2023-recap/index.mdx

Preview of CSS-based configuration in the Oxide engine. Replaces JavaScript configuration files and @tailwind directives with @import "tailwindcss" and the :theme pseudo-selector.

```css
@import "tailwindcss";
@import "./fonts" layer(base);

:theme {
  --colors-neon-pink: oklch(71.7% 0.25 360);
  --colors-neon-lime: oklch(91.5% 0.258 129);
  --colors-neon-cyan: oklch(91.3% 0.139 195.8);

  --font-family-sans: "Inter", sans-serif;
  --font-family-display: "Satoshi", sans-serif;
}
```


--------------------------------

### Compile CSS using Tailwind CLI in JIT and watch mode

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Run the standalone Tailwind CLI without a configuration file by specifying output, watch mode, JIT mode, and purge file paths via CLI flags.

```sh
npx tailwindcss -o dist/tailwind.css --watch --jit --purge="./src/**/*.html"
```


--------------------------------

### Building an accessible dropdown menu with @headlessui/react

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/headless-ui-unstyled-accessible-ui-components/index.mdx

Use the Menu component from @headlessui/react to build an unstyled, fully accessible dropdown with keyboard navigation and ARIA attribute management.

```jsx
import { Menu } from "@headlessui/react";

function MyDropdown() {
  return (
    <Menu as="div" className="relative">
      <Menu.Button className="rounded bg-blue-600 px-4 py-2 text-white ...">Options</Menu.Button>
      <Menu.Items className="absolute right-0 mt-1">
        <Menu.Item>
          {({ active }) => (
            <a className={`${active && "bg-blue-500 text-white"} ...`} href="/account-settings">
              Account settings
            </a>
          )}
        </Menu.Item>
        <Menu.Item>
          {({ active }) => (
            <a className={`${active && "bg-blue-500 text-white"} ...`} href="/documentation">
              Documentation
            </a>
          )}
        </Menu.Item>
        <Menu.Item disabled>
          <span className="opacity-75 ...">Invite a friend (coming soon!)</span>
        </Menu.Item>
      </Menu.Items>
    </Menu>
  );
}
```


--------------------------------

### Using the theme() function in CSS

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-1/index.mdx

Extract design token values from the Tailwind configuration into CSS files using the theme() helper function.

```css
/* [!code filename:select2-theme.css] */
.select2-dropdown {
  border-radius: theme(borderRadius.lg);
  background-color: theme(colors.gray.100);
  color: theme(colors.gray.900);
}
/* ... */
```


--------------------------------

### Combine ring utilities with box shadows

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Renders focus rings concurrently with regular box-shadow utilities using CSS custom properties.

```html
<button class="shadow-sm focus:ring-2 ...">
  <!-- Both the shadow and ring will render together -->
</button>
```


--------------------------------

### Using container queries with @container and responsive variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4/index.mdx

Define a container using the `@container` class and apply responsive utility classes like `@sm:grid-cols-3` and `@lg:grid-cols-4` based on the container size. Container query support is included in Tailwind CSS v4 core without needing the `@tailwindcss/container-queries` plugin.

```html
<!-- [!code filename:HTML] -->
<!-- [!code classes:@container,@sm:grid-cols-3,@lg:grid-cols-4] -->
<div class="@container">
  <div class="grid grid-cols-1 @sm:grid-cols-3 @lg:grid-cols-4">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Enable extendedSpacingScale in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Activate the extended spacing scale with additional micro values, large values, and fractional percentage-based steps.

```javascript
// [!code filename:tailwind.config.js]
module.exports = {
  experimental: {
    extendedSpacingScale: true,
  },
};
```


--------------------------------

### Inject getStaticProps and Post wrapper using custom Webpack loader

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/building-the-tailwind-blog/index.mdx

Prepends the getStaticProps export and appends the default layout export to every MDX post. This avoids duplicating export code across individual files and prevents static props code from being bundled into homepage previews.

```javascript
{
  use: [
    ...mdx,
    createLoader(function (src) {
      const content = [
        'import Post from "@/components/Post"',
        'export { getStaticProps } from "@/getStaticProps"',
        src,
        'export default (props) => <Post meta={meta} {...props} />',
      ].join('\n')

      if (content.includes('<!--​more-->')) {
        return this.callback(null, content.split('<!--​more-->').join('\n'))
      }

      return this.callback(null, content.replace(/<!--​excerpt-->.*<!--\/excerpt-->/s, ''))
    }),
  ],
}
```


--------------------------------

### Set arbitrary values and CSS variables for tab-*

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Specifies custom pixel values or CSS variables for tab-size using arbitrary value syntax.

```html
<!-- [!code classes:tab-[12px],tab-(--tab-size)] -->
<pre class="tab-[12px] ...">...</pre>
<pre class="tab-(--tab-size) ...">...</pre>
```


--------------------------------

### Dynamically generate spacing utilities from the theme spacing variable

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4/index.mdx

Illustrates how spacing utilities like margin, width, and padding are dynamically computed from the --spacing root theme variable in generated CSS.

```css
/* [!code filename:Generated CSS] */
@layer theme {
  :root {
    --spacing: 0.25rem;
  }
}

@layer utilities {
  .mt-8 {
    margin-top: calc(var(--spacing) * 8);
  }
  .w-17 {
    width: calc(var(--spacing) * 17);
  }
  .pr-29 {
    padding-right: calc(var(--spacing) * 29);
  }
}
```


--------------------------------

### Author dropdown component using custom HTML elements

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/building-react-and-vue-support-for-tailwind-ui/index.mdx

Demonstrates the internal declarative HTML format containing custom elements like <x-menu>, <x-transition>, and custom attributes used to generate React, Vue, and vanilla HTML output.

```html
<x-menu as="div" id="options-menu" class="relative inline-block text-left">
  <div>
    <x-menu-button
      class="inline-flex w-full justify-center rounded-md border border-gray-300 bg-white px-4 py-2 text-sm font-medium text-gray-700 shadow-sm hover:bg-gray-50 focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 focus:ring-offset-gray-100 focus:outline-none"
    >
      Options
      <x-heroicon type="solid" name="chevron-down" class="-mr-1 ml-2 h-5 w-5" />
    </x-menu-button>
  </div>

  <x-transition
    as="x-fragment"
    enter="transition ease-out duration-100"
    enter-start="transform opacity-0 scale-95"
    enter-end="transform opacity-100 scale-100"
    leave="transition ease-in duration-75"
    leave-start="transform opacity-100 scale-100"
    leave-end="transform opacity-0 scale-95"
  >
    <x-menu-items
      class="ring-opacity-5 absolute right-0 mt-2 w-56 origin-top-right rounded-md bg-white shadow-lg ring-1 ring-black focus:outline-none"
    >
      <div class="py-1">
        <x-menu-item>
          <a
            href="#"
            class="block px-4 py-2 text-sm"
            x-active-class="bg-gray-100 text-gray-900"
            x-not-active-class="text-gray-700"
          >
            Account settings
          </a>
        </x-menu-item>
        <x-menu-item>
          <a
            href="#"
            class="block px-4 py-2 text-sm"
            x-active-class="bg-gray-100 text-gray-900"
            x-not-active-class="text-gray-700"
          >
            Support
          </a>
        </x-menu-item>
        <x-menu-item>
          <a
            href="#"
            class="block px-4 py-2 text-sm"
            x-active-class="bg-gray-100 text-gray-900"
            x-not-active-class="text-gray-700"
          >
            License
          </a>
        </x-menu-item>
      </div>
    </x-menu-items>
  </x-transition>
</x-menu>
```


--------------------------------

### Create a halo effect using ring-offset utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Adds spacing between the element border and the focus ring using ring-offset classes.

```html
<button class="focus:ring-opacity-50 focus:ring-2 focus:ring-blue-300 focus:ring-offset-2 focus:outline-none ...">
  <!-- ... -->
</button>
```


--------------------------------

### Automatic accessible input field with Field, Label, and Description

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/headless-ui-v2/index.mdx

Demonstrates using Headless UI Field, Input, Label, and Description components to automatically wire up IDs and aria-* attributes.

```jsx
import { Description, Field, Input, Label } from "@headlessui/react";

function Example() {
  return (
    <Field>
      <Label>Name</Label>
      <Input name="your_name" />
      <Description>Use your real name so people will recognize you.</Description>
    </Field>
  );
}
```


--------------------------------

### Configure Shiki syntax highlighting theme colors in CSS

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2022-12-15-protocol-api-documentation-template/index.mdx

Sets CSS custom properties for Shiki's css-variables theme using Tailwind's theme() function to customize token colors across an API reference site.

```css
:root {
  --shiki-color-text: theme("colors.white");
  --shiki-token-constant: theme("colors.emerald.300");
  --shiki-token-string: theme("colors.emerald.300");
  --shiki-token-comment: theme("colors.zinc.500");
  --shiki-token-keyword: theme("colors.sky.300");
  --shiki-token-parameter: theme("colors.pink.300");
  --shiki-token-function: theme("colors.violet.300");
  --shiki-token-string-expression: theme("colors.emerald.300");
  --shiki-token-punctuation: theme("colors.zinc.200");
}
```


--------------------------------

### Create a modal dialog in React with Dialog

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/headless-ui-v1/index.mdx

Use the Dialog component to capture page focus for traditional modal dialogs, slide-out menus, or take-over UI. Manage open/closed state with isOpen and handle closing using the onClose callback.

```jsx
import { useState } from "react";
import { Dialog } from "@headlessui/react";

function MyDialog() {
  let [isOpen, setIsOpen] = useState(true);

  return (
    <Dialog open={isOpen} onClose={setIsOpen}>
      <Dialog.Overlay />

      <Dialog.Title>Deactivate account</Dialog.Title>
      <Dialog.Description>This will permanently deactivate your account</Dialog.Description>

      <p>
        Are you sure you want to deactivate your account? All of your data will be permanently removed. This action
        cannot be undone.
      </p>

      <button onClick={() => setIsOpen(false)}>Deactivate</button>
      <button onClick={() => setIsOpen(false)}>Cancel</button>
    </Dialog>
  );
}
```


--------------------------------

### Target 1536px screens using the 2xl breakpoint

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Applies styles at 1536px and above using the default 2xl breakpoint variant.

```html
<h1 class="2xl:text-9xl ...">Godzilla</h1>
```


--------------------------------

### Apply pseudo-class variants directly to transform sub-utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Applies variant prefixes like hover: directly to sub-utilities rather than toggling transform. In JIT mode, transforms are active by default rather than dormant.

```html
<div class="scale-105 -translate-y-1 hover:transform"> <!-- [!code --] -->
<div class="hover:scale-105 hover:-translate-y-1"> <!-- [!code ++] -->
</div>
```


--------------------------------

### Build CSS with Tailwind CLI without an input file

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-6/index.mdx

Run the Tailwind CLI build command specifying only the output file destination when no custom CSS file is needed.

```bash
npx tailwindcss build -o compiled.css
```


--------------------------------

### Generate TypeScript config with npx tailwindcss init --ts

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-3/index.mdx

Explicitly initializes a new Tailwind CSS configuration file using TypeScript syntax.

```sh
npx tailwindcss init --ts
```


--------------------------------

### Using arbitrary values and CSS variables with zoom

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Apply custom zoom values or CSS custom properties using arbitrary value and variable syntax with the `zoom-*` utility.

```html
<!-- [!code classes:zoom-[1.1],zoom-(--preview-zoom)] -->
<div class="zoom-[1.1] ...">Zoomed in a little</div>
<div class="zoom-(--preview-zoom) ...">Zoomed using a variable</div>
```


--------------------------------

### Import custom CSS files with Tailwind CLI

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-1/index.mdx

Organize custom CSS into multiple files and import them using `@import` directly when compiling via the Tailwind CLI.

```css
@import "tailwindcss/base";
/* [!code highlight:2] */
@import "./select2-theme.css";
@import "tailwindcss/components";
@import "tailwindcss/utilities";
```

```css
.select2-dropdown {
  @apply rounded-b-lg shadow-md;
}
.select2-search {
  @apply rounded border border-gray-300;
}
.select2-results__group {
  @apply text-lg font-bold text-gray-900;
}
/* ... */
```


--------------------------------

### Define theme colors with closure functions

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Use a callback function in the theme colors configuration to access the opacityVariable parameter for dynamic color and opacity variable resolution.

```javascript
// [!code filename:tailwind.config.js]
module.exports = {
  theme: {
    colors: {
      primary: ({ opacityVariable }) => `rgba(var(--color-primary), var(${variable}, 1))`,
    },
  },
};
```


--------------------------------

### Generate utility ranges using brace expansion with @source inline()

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-1/index.mdx

Pass brace-expanded patterns into `@source inline()` to generate multiple utility variations and pseudo-class variants in a single directive.

```css
/* [!code filename:CSS] */
@import "tailwindcss";
/* [!code highlight:2] */
@source inline("{hover:,}bg-red-{50,{100..900..100},950}");
```

```css
/* [!code filename:Generated CSS] */
.bg-red-50 {
  background-color: var(--color-red-50);
}
.bg-red-100 {
  background-color: var(--color-red-100);
}
.bg-red-200 {
  background-color: var(--color-red-200);
}

/* ... */

.bg-red-800 {
  background-color: var(--color-red-800);
}
.bg-red-900 {
  background-color: var(--color-red-900);
}
.bg-red-950 {
  background-color: var(--color-red-950);
}
@media (hover: hover) {
  .hover\:bg-red-50:hover {
    background-color: var(--color-red-50);
  }

  /* ... */

  .hover\:bg-red-950:hover {
    background-color: var(--color-red-950);
  }
}
```


--------------------------------

### Registering component variants using the addComponents options object

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-5/index.mdx

Pass a configuration object with a variants array as the second argument to addComponents.

```js
plugin(function ({ addComponents })) {
  addComponents({
    '.card': {
      // ...
    }
  }, {
    variants: ['responsive']
  })
})
```


--------------------------------

### Generate ESM config with npx tailwindcss init --esm

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-3/index.mdx

Explicitly initializes a new Tailwind CSS configuration file using ES Module syntax.

```sh
npx tailwindcss init --esm
```


--------------------------------

### Enable all experimental features in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Opt in to all upcoming experimental Tailwind features simultaneously. Note that experimental features may introduce breaking changes, do not follow semver, and can change at any time.

```javascript
// [!code filename:tailwind.config.js]
module.exports = {
  experimental: "all",
};
```


--------------------------------

### Configuring container variants in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-5/index.mdx

Enable custom variants for the container utility in tailwind.config.js.

```js
module.exports = {
  // ...
  variants: {
    container: ["responsive", "focus", "group-hover"],
  },
};
```


--------------------------------

### Compiled native CSS variables in :root

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-alpha/index.mdx

Displays how configured theme values are output as standard CSS variables on the :root element.

```css
/* [!code filename:dist/main.css] */
:root {
  --color-gray-50: #f8fafc;
  --color-gray-100: #f1f5f9;
  --color-gray-200: #e2e8f0;
  /* ... */
  --color-green-800: #3f6212;
  --color-green-900: #365314;
  --color-green-950: #1a2e05;
}
```


--------------------------------

### Create scroll-triggered entrance animations with FadeIn and FadeInStagger

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2023-08-07-meet-studio-our-new-agency-template/index.mdx

Wrap elements in declarative FadeIn and FadeInStagger components to trigger entrance and staggered fade animations when scrolling into view.

```jsx
function Clients() {
  return (
    <div className="mt-24 rounded-4xl bg-neutral-950 py-20 sm:mt-32 sm:py-32 lg:mt-56">
      <Container>
        <FadeIn className="flex items-center gap-x-8">
          <h2 className="font-display text-center text-sm font-semibold tracking-wider text-white sm:text-left">
            We’ve worked with hundreds of amazing people
          </h2>
          <div className="h-px flex-auto bg-neutral-800" />
        </FadeIn>
        <FadeInStagger faster>
          <ul role="list" className="mt-10 grid grid-cols-2 gap-x-8 gap-y-10 lg:grid-cols-4">
            {clients.map(([client, logo]) => (
              <li key={client}>
                <FadeIn>
                  <Image src={logo} alt={client} unoptimized />
                </FadeIn>
              </li>
            ))}
          </ul>
        </FadeInStagger>
      </Container>
    </div>
  );
}
```


--------------------------------

### Import Tailwind CSS in main.css

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-alpha/index.mdx

Add Tailwind CSS v4 to your project using a standard CSS @import statement.

```css
/* [!code filename:main.css] */
@import "tailwindcss";
```


--------------------------------

### Apply container query responsive variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Mark a container element with the @container class and apply responsive variants using the @ size scale to its descendants.

```html
<div class="@container">
  <div class="block @lg:flex">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Creating a size container with @container-size

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Use `@container-size` to create a size container that exposes block-size information for container query length units like `cqb` and `cqh`. Size containers can also be named using `@container-size/{name}`.

```html
<!-- [!code word:@container-size] -->
<!-- [!code word:h-\[50cqb\]] -->
<div class="@container-size">
  <div class="h-[50cqb]">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Apply radial gradient masks using mask-radial-* utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-1/index.mdx

Applies a radial gradient mask to an image using composable mask utilities like mask-radial-from-transparent, mask-radial-to-black, and mask-radial-at-right.

```html
<!-- [!code classes:mask-radial-from-transparent,mask-radial-from-15%,mask-radial-to-black,mask-radial-to-55%,mask-radial-at-right] -->
<div class="mx-auto flex items-center p-16 max-sm:p-8">
  <img
    src="/img/keyboard.png"
    class="mask-radial-from-transparent mask-radial-from-15% mask-radial-to-black mask-radial-to-55% mask-radial-at-right ..."
  />
  <div class="font-medium">
    <p class="font-mono text-xs text-blue-500 uppercase dark:text-blue-400">Speed</p>
    <p class="mt-2 text-base text-gray-700 dark:text-gray-300">Built for power users</p>
    <p class="mt-1 text-sm leading-relaxed text-balance text-gray-500">
      Work faster than ever with our keyboard shortcuts
    </p>
  </div>
</div>
```


--------------------------------

### Configure custom data attribute shortcuts in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Define reusable data attribute shortcuts under theme.data in the Tailwind configuration.

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    data: {
      checked: 'ui~="checked"',
    },
  },
  // ...
};
```


--------------------------------

### Apply custom list image with list-image-*

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-3/index.mdx

Uses an arbitrary list image utility class to display a custom image marker on a list element.

```html
<!-- [!code word:list-image-[url(/carrot.png)\]] -->
<ul class="list-image-[url(/carrot.png)] ...">
  <li>5 cups chopped Porcini mushrooms</li>
  <!-- ... -->
</ul>
```


--------------------------------

### Transitioning HTML elements with Transition component

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2024-06-21-headless-ui-v2-1/index.mdx

Use the `<Transition>` component with `data-[closed]` attributes on child HTML elements to handle enter and leave animations.

```jsx
import { Transition } from "@headlessui/react";
import { useState } from "react";

function Example() {
  const [isShowing, setIsShowing] = useState(false);

  return (
    <>
      <button onClick={() => setIsShowing((isShowing) => !isShowing)}>Toggle</button>
      // [!code highlight:6]
      <Transition show={isShowing}>
        <div className="transition duration-300 data-[closed]:opacity-0">I will fade in and out</div>
      </Transition>
    </>
  );
}
```


--------------------------------

### Retrieve entire config object in plugin API

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Invoke the config() helper with no arguments inside a plugin callback to retrieve the entire Tailwind configuration object.

```javascript
tailwind.plugin(function ({ config, addUtilities, /* ... */ })) {
  // Returns entire config object
  config()
})
```


--------------------------------

### Using transparent outline with custom shadow outline for focus styling

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-9/index.mdx

Combine focus:outline-none with box shadow focus styling. The outline-none utility renders a transparent outline by default, keeping focus indicators accessible in Windows high contrast mode.

```html
<button class="focus:shadow-outline focus:outline-none ...">
  <!-- ... -->
</button>
```


--------------------------------

### Migrate from @screen to @media screen()

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Replace deprecated or unsupported @screen directives with @media screen() syntax for better compatibility with standard CSS parsers.

```css
@screen sm { /* [!code --] */
@media screen(sm) { /* [!code ++] */
  /* ... */
}
```


--------------------------------

### Configuring custom outline utilities in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-9/index.mdx

Define custom outline styles by extending the outline theme configuration in tailwind.config.js.

```javascript
module.exports = {
  theme: {
    extend: {
      outline: {
        blue: "2px solid #0000ff",
      },
    },
  },
};
```


--------------------------------

### Use utilities with default fallback values in HTML and generated CSS

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Applies a bare utility class falling back to the configured default value alongside a parameterized utility class with an explicit argument, paired with the resulting generated CSS.

```html
<!-- [!code filename:HTML] -->
<!-- [!code classes:tab,tab-2] -->
<pre class="tab ...">...</pre>
<pre class="tab-2 ...">...</pre>
```

```css
/* [!code filename:Generated CSS] */
.tab {
  /* [!code word:4] */
  tab-size: 4;
}

.tab-2 {
  /* [!code word:2] */
  tab-size: 2;
}
```


--------------------------------

### Applying color opacity shorthand to gradients

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Change color opacity directly within gradient utilities where dedicated opacity utilities were previously unavailable.

```html
<div class="bg-gradient-to-r from-red-500/50"></div>
```


--------------------------------

### Enable uniformColorPalette in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Opt in to the Tailwind 2.0 color palette preview where every color shade has a similar perceived brightness and contrast.

```javascript
// [!code filename:tailwind.config.js]
module.exports = {
  experimental: {
    uniformColorPalette: true,
  },
};
```


--------------------------------

### Compose transforms and filters without enabling classes in JIT

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Removes the need for explicit transform, filter, and backdrop-filter classes in Just-in-Time mode. Sub-utilities now enable their respective feature sets automatically.

```html
<div class="transform scale-50 filter grayscale backdrop-filter backdrop-blur-sm"> <!-- [!code --] -->
<div class="scale-50 grayscale backdrop-blur-sm"> <!-- [!code ++] -->
</div>
```


--------------------------------

### Combine responsive breakpoints with dark variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Combines responsive prefixes such as `lg:` with `dark:` to apply dark mode styles at specific breakpoints.

```html
<div class="lg:bg-white lg:dark:bg-black ...">
  <!-- ... -->
</div>
```


--------------------------------

### Create a customizable Switch component with @headlessui/react

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwind-ui-now-with-react-and-vue-support/index.mdx

Constructs an accessible toggle switch component using Headless UI's Switch component styled with Tailwind CSS utility classes. ARIA attributes and keyboard interactions are handled automatically by Headless UI while styling remains fully customizable.

```jsx
import { useState } from "react";
import { Switch } from "@headlessui/react";

function classNames(...classes) {
  return classes.filter(Boolean).join(" ");
}

export default function Example() {
  const [enabled, setEnabled] = useState(false);

  return (
    <Switch
      checked={enabled}
      onChange={setEnabled}
      className={classNames(
        enabled ? "bg-indigo-600" : "bg-gray-200",
        "relative inline-flex h-6 w-11 flex-shrink-0 cursor-pointer rounded-full border-2 border-transparent transition-colors duration-200 ease-in-out focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 focus:outline-none",
      )}
    >
      <span className="sr-only">Use setting</span>
      <span
        aria-hidden="true"
        className={classNames(
          enabled ? "translate-x-5" : "translate-x-0",
          "pointer-events-none inline-block h-5 w-5 transform rounded-full bg-white shadow ring-0 transition duration-200 ease-in-out",
        )}
      />
    </Switch>
  );
}
```


--------------------------------

### Configuring custom outline with outline-offset in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-9/index.mdx

Specify an outline-offset value for custom outline utilities using a [outline, outlineOffset] tuple in tailwind.config.js.

```javascript
module.exports = {
  theme: {
    extend: {
      outline: {
        blue: ["2px solid #0000ff", "1px"],
      },
    },
  },
};
```


--------------------------------

### Registering component variants using the addComponents array shorthand

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-5/index.mdx

Pass an array of variant names as the second argument shorthand to addComponents.

```js
plugin(function ({ addComponents })) {
  addComponents({
    '.card': {
      // ...
    }
  }, ['responsive'])
})
```


--------------------------------

### Apply configured data attribute shortcut

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Use a custom configured data-checked variant on an HTML element matching the defined data-ui attribute pattern.

```html
<div data-ui="checked active" class="data-checked:underline">
  <!-- ... -->
</div>
```


--------------------------------

### Select a gray scale theme with prose-slate

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-typography-v0-5/index.mdx

Apply a specific gray scale theme class, such as prose-slate, to match typography colors with the rest of your site.

```html
<!-- [!code word:prose-slate] -->
<article class="prose prose-slate">{{ markdown }}</article>
```


--------------------------------

### Define default values for functional utilities with --default()

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Use --default(...) within --value(...) or --modifier(...) inside @utility definitions to provide a fallback value when a functional utility is used without an explicit value.

```css
/* [!code filename:CSS] */
/* [!code word:--default(4)] */
@utility tab-* {
  tab-size: --value(integer, --default(4));
}
```


--------------------------------

### Adapting UI styles with contrast-more variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-1/index.mdx

Modifies styles when a user requests increased contrast via operating system accessibility settings matching prefers-contrast: more. Use variants like contrast-more:border-slate-400 and contrast-more:opacity-100 to enhance visibility.

```html
<form>
  <label class="block">
    <span class="block text-sm font-medium text-slate-700">Social Security Number</span>
    <!-- [!code word:contrast-more\:border-slate-400] -->
    <!-- [!code word:contrast-more\:placeholder-slate-500] -->
    <!-- [!code word:contrast-more\:opacity-100] -->
    <input
      class="border-slate-200 placeholder-slate-400 contrast-more:border-slate-400 contrast-more:placeholder-slate-500"
    />
    <p class="mt-2 text-sm text-slate-600 opacity-10 contrast-more:opacity-100">We need this to steal your identity.</p>
  </label>
</form>
```


--------------------------------

### Enable media query dark mode in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Configures `darkMode` with the `media` strategy in `tailwind.config.js` to rely on the `prefers-color-scheme` media feature.

```javascript
module.exports = {
  darkMode: "media",
  // ...
};
```


--------------------------------

### Adding explicit transition classes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Applies explicit duration and easing classes alongside the transition property utility.

```html
<button class="transition duration-150 ease-in-out ...">Count them</button>
```


--------------------------------

### Enable extendedFontSizeScale in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Enable the 7xl, 8xl, and 9xl font size utilities along with their associated default line-heights.

```javascript
// [!code filename:tailwind.config.js]
module.exports = {
  experimental: {
    extendedFontSizeScale: true,
  },
};
```


--------------------------------

### Format post metadata and author image dynamically

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2024-09-12-radiant-a-beautiful-new-marketing-site-template/index.mdx

Displays the publication date formatted with dayjs alongside author metadata and transforms the hosted CMS author image size and dimensions on the fly.

```jsx
<div className="text-sm/5 max-sm:text-gray-700 sm:font-medium">
  {dayjs(post.publishedAt).format('dddd, MMMM D, YYYY')}
</div>
{post.author && (
  <div className="mt-2.5 flex items-center gap-3">
    {post.author.image && (
      // [!code highlight:6]
      <img
        className="aspect-square size-6 rounded-full object-cover"
        src={image(post.author.image).width(64).height(64).url()}
        alt=""
      />
    )}
    <div className="text-sm/5 text-gray-700">
      {post.author.name}
    </div>
  </div>
)}
```


--------------------------------

### Apply automatic line-height with font-size utility

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Applies a font-size utility class to automatically apply its paired default line-height.

```html
<p class="text-xl">This will have a line-height of 1.75rem automatically.</p>
```


--------------------------------

### Configure custom base preset in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-9/index.mdx

Specify a custom base configuration using the `presets` key in `tailwind.config.js`. The configured preset replaces the default Tailwind base configuration while still supporting project-specific overrides with `extend`.

```javascript
module.exports = {
  presets: [require("@my-company/tailwind-base")],
  theme: {
    extend: {
      // Project specific overrides...
    },
  },
};
```


--------------------------------

### Configure responsive variants for divideStyle

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Defines active variants such as responsive for divideStyle in tailwind.config.js.

```javascript
// [!code filename:tailwind.config.js]
module.exports = {
  variants: {
    divideStyle: ["responsive"],
  },
};
```


--------------------------------

### Styling gradient text with bg-clip-text

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Combines `bg-clip-text`, `text-transparent`, and background gradient utilities to create gradient-colored text.

```html
<h1 class="text-center text-5xl font-bold">
  <span class="bg-gradient-to-r from-teal-400 to-blue-500 bg-clip-text text-transparent">
    Greetings from Tailwind v1.7.
  </span>
</h1>
```


--------------------------------

### Standard Tailwind CSS directives input file

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-6/index.mdx

The traditional CSS entry file containing base, components, and utilities directives.

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```


--------------------------------

### Configure horizontal scroll snapping with snap-x and snap-center

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3/index.mdx

Apply `snap-x` to the container and `snap-center` to child elements to enable horizontal scroll snapping aligned to the center of each item.

```html
<!-- [!code word:snap-x] -->
<!-- [!code word:snap-center] -->
<div class="snap-x ...">
  <div class="snap-center ...">
    <img src="https://images.unsplash.com/photo-1604999565976-8913ad2ddb7c?auto=format&fit=crop&w=320&h=160&q=80" />
  </div>
  <div class="snap-center ...">
    <img src="https://images.unsplash.com/photo-1540206351-d6465b3ac5c1?auto=format&fit=crop&w=320&h=160&q=80" />
  </div>
  <div class="snap-center ...">
    <img src="https://images.unsplash.com/photo-1622890806166-111d7f6c7c97?auto=format&fit=crop&w=320&h=160&q=80" />
  </div>
  <div class="snap-center ...">
    <img src="https://images.unsplash.com/photo-1590523277543-a94d2e4eb00b?auto=format&fit=crop&w=320&h=160&q=80" />
  </div>
  <div class="snap-center ...">
    <img src="https://images.unsplash.com/photo-1575424909138-46b05e5919ec?auto=format&fit=crop&w=320&h=160&q=80" />
  </div>
  <div class="snap-center ...">
    <img src="https://images.unsplash.com/photo-1559333086-b0a56225a93c?auto=format&fit=crop&w=320&h=160&q=80" />
  </div>
</div>
```


--------------------------------

### Enable applyComplexClasses in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Enable experimental support for using @apply with variants and complex classes. This introduces breaking changes to how @apply worked previously.

```javascript
// [!code filename:tailwind.config.js]
module.exports = {
  experimental: {
    applyComplexClasses: true,
  },
};
```


--------------------------------

### Use {scheme} placeholder for dark mode Markdown images

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2025-05-14-compass-course-starter-kit/index.mdx

Use the `{scheme}` token in an image URL to dynamically resolve `light` or `dark` image variants based on the active color scheme. Omit the placeholder if an image should remain identical across themes.

```markdown
## The Myth of Free Will

![Neurological Proof](/img/neuro-proof.{scheme}.png) <!-- [!code highlight:1] -->

Your brain makes decisions before you are even aware of them.
```


--------------------------------

### Applying max-width container queries with @max-*

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4/index.mdx

Use the `@max-*` container query variant to apply styles when a container does not exceed a specified maximum width breakpoint.

```html
<!-- [!code filename:HTML] -->
<!-- [!code classes:@container,@max-md:grid-cols-1] -->
<div class="@container">
  <div class="grid grid-cols-3 @max-md:grid-cols-1">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Use arbitrary values with container queries

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Specify one-off container query thresholds using square bracket arbitrary value syntax like @[618px].

```html
<div class="@container">
  <div class="block @[618px]:flex">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Defining inline guest authors in post metadata

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/building-the-tailwind-blog/index.mdx

Shows how guest authors not in the central authors list can be defined inline within the meta object.

```js
export const meta = {
  title: "An example of a guest post by someone not on the team",
  authors: [
    {
      name: "Simon Vrachliotis",
      twitter: "@simonswiss",
      avatar: "https://pbs.twimg.com/profile_images/1160929863/n510426211_274341_6220_400x400.jpg",
    },
  ],
  // ...
};
```


--------------------------------

### Configuring default transition duration and timing function in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Specifies default transition duration and timing function values that apply automatically to any transition utility.

```javascript
module.exports = {
  // ...
  theme: {
    // ...
    transitionDuration: {
      DEFAULT: "150ms",
      // ...
    },
    transitionTimingFunction: {
      DEFAULT: "cubic-bezier(0.4, 0, 0.2, 1)",
      // ...
    },
  },
};
```


--------------------------------

### Configure Tailwind CSS v4 using the first-party Vite plugin in vite.config.ts

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4/index.mdx

Integrate Tailwind CSS v4 directly with Vite using @tailwindcss/vite for enhanced performance over PostCSS.

```js
// [!code filename:vite.config.ts]
import { defineConfig } from "vite";
// [!code highlight:2]
import tailwindcss from "@tailwindcss/vite";

export default defineConfig({
  plugins: [
    // [!code highlight:2]
    tailwindcss(),
  ],
});
```


--------------------------------

### Define theme customizations using @theme

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-alpha/index.mdx

Use the @theme directive to declare custom CSS variables for fonts, breakpoints, and colors. Tailwind generates corresponding utilities and variants automatically.

```css
/* [!code filename:main.css] */
@import "tailwindcss";

@theme {
  --font-family-display: "Satoshi", "sans-serif";

  --breakpoint-3xl: 1920px;

  --color-neon-pink: oklch(71.7% 0.25 360);
  --color-neon-lime: oklch(91.5% 0.258 129);
  --color-neon-cyan: oklch(91.3% 0.139 195.8);
}
```


--------------------------------

### Apply micro spacing value

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Applies a fractional spacing utility from the extended micro spacing scale.

```html
<span class="ml-0.5">Just a little nudge.</span>
```


--------------------------------

### Using anchor prop and CSS variables on MenuItems

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/headless-ui-v2/index.mdx

Specify anchor positioning on Headless UI MenuItems using the anchor prop and fine-tune placement with CSS variables like --anchor-gap and --anchor-padding.

```jsx
import { Menu, MenuButton, MenuItem, MenuItems } from "@headlessui/react";

function Example() {
  return (
    <Menu>
      <MenuButton>Options</MenuButton>
      <MenuItems
        // [!code highlight:3]
        anchor="bottom start"
        className="[--anchor-gap:8px] [--anchor-padding:8px]"
      >
        <MenuItem>
          <button>Edit</button>
        </MenuItem>
        <MenuItem>
          <button>Duplicate</button>
        </MenuItem>
        <hr />
        <MenuItem>
          <button>Archive</button>
        </MenuItem>
        <MenuItem>
          <button>Delete</button>
        </MenuItem>
      </MenuItems>
    </Menu>
  );
}
```


--------------------------------

### Opt-in to transitions using motion-safe variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-6/index.mdx

Explicitly apply transitions only when the user has not opted out of animations via prefers-reduced-motion.

```html
<div class="duration-150 ease-in-out motion-safe:transition ... ..."></div>
```


--------------------------------

### Specifying type hints for ambiguous arbitrary values

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Prefix an arbitrary value with a supported type name like color to clarify which CSS utility should be generated.

```html
<div class="text-[color:var(--mystery-var)]"></div>
```


--------------------------------

### Configuring postcss.config.js with built-in import support

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4/index.mdx

Remove `postcss-import` from your PostCSS configuration when using `@tailwindcss/postcss`, as CSS import inlining is handled natively.

```javascript
//  [!code filename:postcss.config.js]
export default {
  plugins: [
    "postcss-import", // [!code --]
    "@tailwindcss/postcss",
  ],
};
```


--------------------------------

### Configure custom animations and keyframes in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-6/index.mdx

Customize or add animations by extending the animation and keyframes sections in the theme configuration.

```javascript
module.exports = {
  theme: {
    extend: {
      animation: {
        wiggle: "wiggle 1s ease-in-out infinite",
      },
      keyframes: {
        wiggle: {
          "0%, 100%": { transform: "rotate(-3deg)" },
          "50%": { transform: "rotate(3deg)" },
        },
      },
    },
  },
};
```


--------------------------------

### Applying transition prop and data attributes to MenuItems

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2024-06-21-headless-ui-v2-1/index.mdx

Add the `transition` prop and data-attribute classes (`data-[closed]`, `data-[enter]`, `data-[leave]`) to style component transitions directly on the target element.

```jsx
import { Menu, MenuButton, MenuItem, MenuItems } from "@headlessui/react";

function Example() {
  return (
    <Menu>
      <MenuButton>My account</MenuButton>
      <MenuItems
        // [!code highlight:7]
        transition
        className={`
          transition ease-out
          data-[closed]:scale-95 data-[closed]:opacity-0
          data-[enter]:duration-200 data-[leave]:duration-300
        `}
      >
        {/* Menu items… */}
      </MenuItems>
    </Menu>
  );
}
```


--------------------------------

### Animating Enter and Leave Transitions in React with @tailwindui/react

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/utility-friendly-transitions-with-tailwindui-react/index.mdx

Uses the Transition component from @tailwindui/react with state to trigger utility-based enter and leave animations in React.

```jsx
import { Transition } from "@tailwindui/react";
import { useState } from "react";

function MyComponent() {
  const [isOpen, setIsOpen] = useState(false);

  return (
    <div>
      <button onClick={() => setIsOpen(!isOpen)}>Toggle</button>
      <Transition
        show={isOpen}
        enter="transition-opacity duration-75"
        enterFrom="opacity-0"
        enterTo="opacity-100"
        leave="transition-opacity duration-150"
        leaveFrom="opacity-100"
        leaveTo="opacity-0"
      >
        {/* Will fade in and out */}
      </Transition>
    </div>
  );
}
```


--------------------------------

### Styling vanilla HTML content with prose classes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-typography/index.mdx

Applies typography styles to standard HTML elements using the prose and responsive modifier classes provided by @tailwindcss/typography.

```html
<article class="prose lg:prose-xl">
  <h1>Garlic bread with cheese: What the science tells us</h1>
  <p>
    For years parents have espoused the health benefits of eating garlic bread with cheese to their children, with the
    food earning such an iconic status in our culture that kids will often dress up as warm, cheesy loaf for Halloween.
  </p>
  <p>
    But a recent study shows that the celebrated appetizer may be linked to a series of rabies cases springing up around
    the country.
  </p>
  <!-- ... -->
</article>
```


--------------------------------

### Highlighting Keys in the Keyboard Component

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2024-09-12-radiant-a-beautiful-new-marketing-site-template/index.mdx

Pass an array of key identifiers to the Keyboard component to highlight specific shortcut combinations.

```jsx
<Keyboard highlighted={["F", "M", "L"]} />
```


--------------------------------

### Apply animate-spin utility class to an element

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-6/index.mdx

Use general-purpose animation utilities like animate-spin directly on elements such as SVGs to display animations out of the box.

```html
<button type="button" class="bg-indigo-600 ..." disabled>
  <svg class="mr-3 h-5 w-5 animate-spin ..." viewBox="0 0 24 24">
    <!-- ... -->
  </svg>
  Processing
</button>
```


--------------------------------

### Check CSS property support shorthand using supports-[...]

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Specify only a CSS property name inside the `supports-[...]` variant to check if the browser supports that property. Tailwind expands the property name automatically without requiring an explicit value.

```html
<!-- [!code word:supports-[backdrop-filter\]\:bg-black/25] -->
<!-- [!code word:supports-[backdrop-filter\]\:backdrop-blur] -->
<div class="bg-black/75 supports-[backdrop-filter]:bg-black/25 supports-[backdrop-filter]:backdrop-blur ...">
  <!-- ... -->
</div>
```


--------------------------------

### Set arbitrary line-height values with font-size shorthand

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-3/index.mdx

Pass arbitrary line-height values within brackets using the font-size shorthand syntax to deviate from the configured line-height scale.

```html
<!-- [!code word:/[17px\]] -->
<p class="text-sm/[17px] ..."></p>
```


--------------------------------

### Use extended min-width spacing scale class

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-4/index.mdx

Applies a min-width utility using spacing scale values such as min-w-12.

```html
<!-- [!code filename:HTML] -->
<!-- [!code word:min-w-12] -->
<div class="min-w-12">
  <!-- ... -->
</div>
```


--------------------------------

### Target custom ranges with dynamic arbitrary min-* and max-* variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Applies styles to ad-hoc viewport ranges using arbitrary pixel values in min-[...] and max-[...] variants.

```html
<div class="min-[712px]:max-[877px]:right-16 ...">
  <!-- ... -->
</div>
```


--------------------------------

### Use @apply with responsive and pseudo-class variants in CSS

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Apply responsive variants, pseudo-class variants, and other complex utility classes directly within custom CSS rules.

```css
.btn {
  @apply bg-indigo hover:bg-indigo-700 sm:text-lg;
}
```


--------------------------------

### Use contents display utility for phantom flex containers

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Applies display: contents to make the container element act as a phantom container so child elements are treated as direct children of the outer flex parent.

```html
<div class="flex">
  <div><!-- ... --></div>
  <!-- This container will act as a phantom container, and its children will be treated as part of the parent flex container -->
  <div class="contents">
    <div><!-- ... --></div>
    <div><!-- ... --></div>
  </div>
  <div><!-- ... --></div>
</div>
```


--------------------------------

### Style based on parent ARIA state with group-aria variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Demonstrates applying styles to child elements using arbitrary group-aria variants based on the parent element's aria-sort state.

```html
<!-- [!code word:group-aria-[sort=ascending\]\:rotate-0] -->
<!-- [!code word:group-aria-[sort=descending\]\:rotate-180] -->
<table>
  <thead>
    <tr>
      <th aria-sort="ascending" class="group">
        Invoice #
        <svg
          class="group-aria-[sort=ascending]:rotate-0 group-aria-[sort=descending]:rotate-180"
        >
          <!-- ... -->
        </svg>
      </th>
      <!-- ... -->
    </tr>
  </thead>
  <!-- ... -->
</table>
```

```css
.group[aria-sort="ascending"] .group-aria-\[sort\=ascending\]\:rotate-0 {
  --tw-rotate: 0deg;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y))
    rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y))
    scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}

.group[aria-sort="descending"] .group-aria-\[sort\=descending\]\:rotate-180 {
  --tw-rotate: 180deg;
  transform: translate(var(--tw-translate-x), var(--tw-translate-y))
  rotate(var(--tw-rotate)) skewX(var(--tw-skew-x)) skewY(var(--tw-skew-y))
  scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}
```


--------------------------------

### Positioning and Animating a Logo in the Logo Cluster

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2024-09-12-radiant-a-beautiful-new-marketing-site-template/index.mdx

Configure an individual logo item with image source path, spatial coordinates, and hover transform animation properties.

```jsx
<Logo src="./logo-cluster/dribbble.svg" left={285} top={20} hover={{ x: 4, y: -5, rotate: 6, delay: 0.3 }} />
```


--------------------------------

### Create accessible tabs with Tab component

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/headless-ui-v1-4/index.mdx

Render declarative, accessible tab groups with panels using @headlessui/react or @headlessui/vue.

```jsx
import { Tab } from '@headlessui/react'

function MyTabs() {
  return (
    <Tab.Group>
      <Tab.List>
        <Tab>Tab 1</Tab>
        <Tab>Tab 2</Tab>
        <Tab>Tab 3</Tab>
      </Tab.List>
      <Tab.Panels>
        <Tab.Panel>Content 1</Tab.Panel>
        <Tab.Panel>Content 2</Tab.Panel>
        <Tab.Panel>Content 3</Tab.Panel>
      </Tab.Panels>
    </Tab.Group>
  )
}
```

```html
<template>
  <TabGroup>
    <TabList>
      <Tab>Tab 1</Tab>
      <Tab>Tab 2</Tab>
      <Tab>Tab 3</Tab>
    </TabList>
    <TabPanels>
      <TabPanel>Content 1</TabPanel>
      <TabPanel>Content 2</TabPanel>
      <TabPanel>Content 3</TabPanel>
    </TabPanels>
  </TabGroup>
</template>

<script>
  import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue'

  export default {
    components: {
      TabGroup,
      TabList,
      Tab,
      TabPanels,
      TabPanel,
    },
  }
</script>
```


--------------------------------

### Configure custom colors from tailwindcss/colors in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Imports the full `tailwindcss/colors` module to curate specific color aliases in your configuration file.

```javascript
const colors = require("tailwindcss/colors");

module.exports = {
  theme: {
    colors: {
      gray: colors.trueGray,
      indigo: colors.indigo,
      red: colors.rose,
      yellow: colors.amber,
    },
  },
};
```


--------------------------------

### Configure default letter-spacing per font size in theme

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Define font sizes as tuples with configuration objects containing default letterSpacing and lineHeight properties in tailwind.config.js.

```javascript
// [!code filename:tailwind.config.js]
module.exports = {
  theme: {
    fontSize: {
      2xl: ['24px', {
        letterSpacing: '-0.01em',
      }],
      // Or with a default line-height as well
      3xl: ['32px', {
        letterSpacing: '-0.02em',
        lineHeight: '40px',
      }],
    }
  }
}
```


--------------------------------

### Setting custom pseudo-element content with arbitrary values

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Overrides default pseudo-element content using the content utility with arbitrary string values.

```html
<div class="before:block before:content-['hello'] ..."></div>
```


--------------------------------

### Style direct child elements using the * variant

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-4/index.mdx

Apply utility classes to all direct children of an element using the `*` variant. Useful for styling elements you do not directly control or adjusting items based on parent context.

```html
<div>
  <h2>Categories:<h2>
  <!-- [!code highlight:2] -->
  <ul class="*:rounded-full *:border *:border-sky-100 *:bg-sky-50 *:px-2 *:py-0.5 dark:text-sky-300 dark:*:border-sky-500/15 dark:*:bg-sky-500/10 ...">
    <li>Sales</li>
    <li>Marketing</li>
    <li>SEO</li>
    <!-- ... -->
  </ul>
</div>
```


--------------------------------

### Sort utility classes automatically in HTML templates

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/automatic-class-sorting-with-prettier/index.mdx

Shows how classes in template attributes are reordered before and after applying the Prettier plugin. Classes are organized following Tailwind CSS's recommended class order.

```html
<!-- Before -->
<button class="text-white px-4 sm:px-8 py-2 sm:py-3 bg-sky-700 hover:bg-sky-800">...</button>

<!-- After -->
<button class="bg-sky-700 px-4 py-2 text-white hover:bg-sky-800 sm:px-8 sm:py-3">...</button>
```


--------------------------------

### Configure CSS variable colors with opacity function in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-1/index.mdx

Legacy approach in Tailwind CSS for defining colors from CSS variables using a custom opacity function.

```javascript
// [!code filename:tailwind.config.js]
function withOpacityValue(variable) {
  return ({ opacityValue }) => {
    if (opacityValue === undefined) {
      return `rgb(var(${variable}))`;
    }
    return `rgb(var(${variable}) / ${opacityValue})`;
  };
}

module.exports = {
  theme: {
    colors: {
      primary: withOpacityValue("--color-primary"),
      secondary: withOpacityValue("--color-secondary"),
      // ...
    },
  },
};
```


--------------------------------

### Position selector in dynamic peer-* variant using &

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Use the & character within square brackets to define where .peer should be placed relative to the custom selector in the generated CSS.

```html
<!-- [!code word:peer-[\:nth-of-type(3)_&\]\:block] -->
<div>
  <input type="text" class="peer" />
  <div class="peer-[:nth-of-type(3)_&]:block hidden">
    <!-- ... -->
  </div>
</div>
```

```css
:nth-of-type(3) .peer ~ .peer-\[\:nth-of-type\(3\)_\&\]\:block {
  display: block;
}
```


--------------------------------

### Require bundled plugins in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/standalone-cli/index.mdx

Enables first-party plugins such as @tailwindcss/forms and @tailwindcss/typography directly via require in tailwind.config.js without needing npm.

```js
module.exports = {
  // ...
  plugins: [require("@tailwindcss/forms"), require("@tailwindcss/typography")],
};
```


--------------------------------

### Stacking transition stage data attributes on Dialog

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2024-06-21-headless-ui-v2-1/index.mdx

Stack `data-[closed]` with `data-[enter]` and `data-[leave]` to define distinct enter and leave transition styles, such as sliding in from one side and sliding out to the other.

```jsx
import { Dialog } from "@headlessui/react";
import { useState } from "react";

function Example() {
  let [isOpen, setIsOpen] = useState(false);

  return (
    <>
      <button onClick={() => setIsOpen(true)}>Open dialog</button>
      <Dialog
        open={isOpen}
        onClose={() => setIsOpen(false)}
        // [!code highlight:8]
        transition
        className={`
          transition duration-300 ease-out
          data-[closed]:opacity-0
          data-[closed]:data-[enter]:-translate-x-8
          data-[closed]:data-[leave]:translate-x-8
        `}
      >
        {/* Dialog content… */}
      </Dialog>
    </>
  );
}
```


--------------------------------

### Enable JIT mode in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-1/index.mdx

Enables the Just-in-Time engine merged into core in Tailwind CSS v2.1. Note that this feature is in preview and not subject to semantic versioning.

```javascript
module.exports = {
  mode: "jit",
  purge: [
    // ...
  ],
  // ...
};
```


--------------------------------

### Styling a checkbox input with utility classes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Styles a native checkbox input using Tailwind utility classes made possible by the @tailwindcss/forms reset.

```html
<!-- This will be a nice rounded checkbox with an indigo focus ring and an indigo checked state -->
<input
  type="checkbox"
  class="focus:ring-opacity-50 h-4 w-4 rounded border-gray-300 text-indigo-500 focus:border-indigo-300 focus:ring-2 focus:ring-indigo-200"
/>
```


--------------------------------

### Opt-in to breaking changes in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Set future flag properties to true to adopt breaking changes early and avoid build warnings.

```javascript
// [!code filename:tailwind.config.js]
module.exports = {
  future: {
    removeDeprecatedGapUtilities: true,
  },
};
```


--------------------------------

### Configure default line-height per fontSize in theme

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Defines default line-height tuples paired with font-size definitions in the Tailwind theme configuration. Each font size utility automatically applies its corresponding line-height value.

```javascript
// Tailwind's default theme
module.exports = {
  theme: {
    // ...
    fontSize: {
      xs: ["0.75rem", { lineHeight: "1rem" }],
      sm: ["0.875rem", { lineHeight: "1.25rem" }],
      base: ["1rem", { lineHeight: "1.5rem" }],
      lg: ["1.125rem", { lineHeight: "1.75rem" }],
      xl: ["1.25rem", { lineHeight: "1.75rem" }],
      "2xl": ["1.5rem", { lineHeight: "2rem" }],
      "3xl": ["1.875rem", { lineHeight: "2.25rem" }],
      "4xl": ["2.25rem", { lineHeight: "2.5rem" }],
      "5xl": ["3rem", { lineHeight: "1" }],
      "6xl": ["3.75rem", { lineHeight: "1" }],
      "7xl": ["4.5rem", { lineHeight: "1" }],
      "8xl": ["6rem", { lineHeight: "1" }],
      "9xl": ["8rem", { lineHeight: "1" }],
    },
  },
};
```


--------------------------------

### Combine dark mode with hover state variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Combines `dark:` with pseudo-class variants like `hover:` to handle dark mode interactive states.

```html
<button class="bg-gray-900 hover:bg-gray-800 dark:bg-white dark:hover:bg-gray-50">
  <!-- ... -->
</button>
```


--------------------------------

### Apply styles conditionally based on feature support using supports-[...]

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Use the `supports-[...]` variant to conditionally apply utility classes when a browser supports a specified property/value declaration. The bracketed expression generates `@supports` rules under the hood and can include `and` and `or` expressions.

```html
<!-- [!code word:supports-[display\:grid\]\:grid] -->
<div class="flex supports-[display:grid]:grid ...">
  <!-- ... -->
</div>
```


--------------------------------

### Include @tailwindplus/elements via CDN script tag

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/vanilla-js-support-for-tailwind-plus/index.mdx

Loads the `@tailwindplus/elements` custom elements library as a module script. This allows using headless UI elements without a JavaScript framework.

```html
/* [!code filename:index.html] */
<script src="https://cdn.jsdelivr.net/npm/@tailwindplus/elements@1" type="module"></script>
```


--------------------------------

### Using the focus-visible variant in HTML

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-5/index.mdx

Apply styles that only trigger when an element receives focus via keyboard navigation.

```html
<button class="focus-visible:shadow-outline focus-visible:outline-none ...">Click me</button>
```


--------------------------------

### Apply styles conditionally with arbitrary @supports variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-1/index.mdx

Use @supports query rules inside arbitrary variants to conditionally apply utility classes when CSS features are supported.

```html
<!-- [!code word:@supports(backdrop-filter\:blur(0))\]\:bg-white/50] -->
<!-- [!code word:[@supports(backdrop-filter\:blur(0))\]\:backdrop-blur] -->
<div
  class="bg-white [@supports(backdrop-filter:blur(0))]:bg-white/50 [@supports(backdrop-filter:blur(0))]:backdrop-blur"
>
  <!-- ... -->
</div>
```


--------------------------------

### Configure OpenType font features using font-features-*

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Applies custom OpenType font-feature-settings values such as stylistic sets or tabular figures using the font-features-* arbitrary value utility.

```html
<!-- [!code classes:font-features-["tnum"]] -->
<div class='font-features-["tnum"] ...'>
  <!-- ... -->
</div>
```


--------------------------------

### Apply isolation utility

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-1/index.mdx

Applies the isolate utility to set CSS isolation, useful for scoping blend modes and managing stacking contexts.

```html
<div class="isolate ...">
  <!-- ... -->
</div>
```


--------------------------------

### Apply CSS backdrop-filter utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-1/index.mdx

Composes backdrop filters using the backdrop-filter utility alongside modifier classes like backdrop-blur and backdrop-brightness.

```html
<div class="backdrop-blur backdrop-brightness-50 backdrop-filter ...">
  <!-- ... -->
</div>
```


--------------------------------

### Migrate deprecated gap utilities in HTML

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Replace deprecated col-gap and row-gap class names with the new gap-x and gap-y utility classes.

```html
<div class="col-gap-4 row-gap-2 ..."> <!-- [!code --] -->
<div class="gap-x-4 gap-y-2 ..."> <!-- [!code ++] -->
</div>
```


--------------------------------

### Apply dark variant classes to elements

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Prefixes utility classes with `dark:` to apply styles conditionally when dark mode is active.

```html
<div class="bg-white dark:bg-black">
  <h1 class="text-gray-900 dark:text-white">Dark mode</h1>
  <p class="text-gray-500 dark:text-gray-300">The feature you've all been waiting for.</p>
</div>
```


--------------------------------

### Defining responsive component styles using the @layer directive in CSS

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-5/index.mdx

Wrap responsive component classes in @layer components so Tailwind correctly preserves them during CSS purging.

```css
@layer components {
  @responsive {
    .card {
      /* ... */
    }
  }
}
```


--------------------------------

### Control object comparisons in Listbox using by prop

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2022-09-09-new-personal-website-heroicons-2-headless-ui-v17/index.mdx

Use the `by` prop on `Listbox` (as well as `Combobox` and `RadioGroup`) to bind object values and compare them by a specific key like `id`.

```jsx
import { Listbox } from "@headlessui/react";

const departments = [
  { id: 1, name: "Marketing", contact: "Durward Reynolds" },
  { id: 2, name: "HR", contact: "Kenton Towne" },
  { id: 3, name: "Sales", contact: "Therese Wunsch" },
  { id: 4, name: "Finance", contact: "Benedict Kessler" },
  { id: 5, name: "Customer service", contact: "Katelyn Rohan" },
];

function DepartmentPicker({ selectedDepartment, onChange }) {
  return (
    <Listbox value={selectedDepartment} by="id" onChange={onChange}>
      <Listbox.Button>{selectedDepartment.name}</Listbox.Button>
      <Listbox.Options>
        {departments.map((department) => (
          <Listbox.Option key={department.id} value={department}>
            {department.name}
          </Listbox.Option>
        ))}
      </Listbox.Options>
    </Listbox>
  );
}
```


--------------------------------

### Render PortableText with custom styled components

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2024-09-12-radiant-a-beautiful-new-marketing-site-template/index.mdx

Maps Sanity structured text elements such as paragraphs, headings, blockquotes, and images to custom Tailwind CSS styled JSX components.

```jsx
<PortableText
  value={post.body}
  components={{
    block: {
      normal: ({ children }) => <p className="my-10 text-base/8 first:mt-0 last:mb-0">{children}</p>,
      h2: ({ children }) => (
        <h2 className="mt-12 mb-10 text-2xl/8 font-medium tracking-tight text-gray-950 first:mt-0 last:mb-0">
          {children}
        </h2>
      ),
      h3: ({ children }) => (
        <h3 className="mt-12 mb-10 text-xl/8 font-medium tracking-tight text-gray-950 first:mt-0 last:mb-0">
          {children}
        </h3>
      ),
      blockquote: ({ children }) => (
        <blockquote className="my-10 border-l-2 border-l-gray-300 pl-6 text-base/8 text-gray-950 first:mt-0 last:mb-0">
          {children}
        </blockquote>
      ),
    },
    types: {
      image: ({ value }) => (
        <img className="w-full rounded-2xl" src={image(value).width(2000).url()} alt={value.alt || ""} />
      ),
    },
    /* ... */
  }}
/>
```


--------------------------------

### Apply border styles to divide utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Sets the border style for elements separated by divide utilities using classes like divide-dashed.

```html
<div class="divide-y divide-dashed">
  <div><!-- ... --></div>
  <div><!-- ... --></div>
  <div><!-- ... --></div>
  <div><!-- ... --></div>
</div>
```


--------------------------------

### Structure WebVTT caption file with speaker tags in annie-king.vtt

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2025-05-14-compass-course-starter-kit/index.mdx

Defines transcript cue timing and speaker labels using standard WebVTT voice tags.

```txt
// [!code filename:annie-king.vtt]
WEBVTT

00:00.000 --> 00:20.000
<v Tom Harris>Hello fellow passengers, welcome to the Compass podcast. Today, we have a special guest, Annie King. She's the author of The Inevitable You: How to Embrace Your Path and Succeed with Relentless Precision. Annie, welcome to the show.

00:20.000 --> 00:35.000
<v Annie King>Thank you! I'm so happy to be here. And thanks for sending me the questions in advance — I'm really excited to share some of the ideas from the book with your viewers. I think we're going to have a lot of fun unpacking what it means to truly embrace your path.

00:35.000 --> 00:45.000
<v Tom Harris>Absolutely! I want to get into your book, but first I have to ask — what was it like growing up in a household that treated organization almost like...a sport?
```


--------------------------------

### Safelist utilities with @source inline()

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-1/index.mdx

Use `@source inline()` to force Tailwind to generate specific utility classes even if they are not present in your content files. This replaces the `safelist` configuration option from previous versions.

```css
/* [!code filename:CSS] */
@import "tailwindcss";
/* [!code highlight:2] */
@source inline("underline");
```

```css
/* [!code filename:Generated CSS] */
.underline {
  text-decoration: underline;
}
```


--------------------------------

### Use border-separate and border-spacing-0 for sticky table headers

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-1/index.mdx

Apply border-separate alongside border-spacing-0 to prevent borders from scrolling away under sticky table headers.

```html
<!-- [!code word:border-separate] -->
<!-- [!code word:border-spacing-0] -->
<table class="border-separate border-spacing-0">
  <thead class="bg-gray-50">
    <tr>
      <th class="sticky top-0 z-10 border-b border-gray-300 ...">Name</th>
      <th class="sticky top-0 z-10 border-b border-gray-300 ...">Email</th>
      <th class="sticky top-0 z-10 border-b border-gray-300 ...">Role</th>
    </tr>
  </thead>
  <tbody class="bg-white">
    <tr>
      <td class="border-b border-gray-200 ...">Courtney Henry</td>
      <td class="border-b border-gray-200 ...">courtney.henry@example.com</td>
      <td class="border-b border-gray-200 ...">Admin</td>
    </tr>
    <!-- ... -->
  </tbody>
</table>
```


--------------------------------

### Control tab width using tab-* utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v4-3/index.mdx

Applies tab-size utilities to adjust the rendered width of tab characters in preformatted text elements.

```jsx
function indent() {
	return 'tabbed';
}
```

```jsx
function indent() {
	return 'tabbed';
}
```

```html
<!-- [!code classes:tab-2,tab-8] -->
<pre class="tab-2 ...">function indent() {&#10;&#9;return 'tabbed'&#10;}</pre>
<pre class="tab-8 ...">function indent() {&#10;&#9;return 'tabbed'&#10;}</pre>
```


--------------------------------

### Applying a multi-stop background gradient

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Applies a linear background gradient from left to right with orange, red, and pink color stops.

```html
<div class="bg-gradient-to-r from-orange-400 via-red-500 to-pink-500">
  <!-- ... -->
</div>
```


--------------------------------

### Build console warning for upcoming breaking changes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Displayed in the console during builds when deprecations or breaking changes are available and have not been configured under the future property.

```txt
risk - There are upcoming breaking changes: removeDeprecatedGapUtilities
risk - We highly recommend opting-in to these changes now to simplify upgrading Tailwind in the future.
risk - https://tailwindcss.com/docs/upcoming-changes
```


--------------------------------

### Sorting layer order in Prettier plugin

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/automatic-class-sorting-with-prettier/index.mdx

Base layer classes are sorted first, followed by classes in the components layer, and then utilities layer classes.

```html
<!-- `container` is a component so it comes first -->
<div class="container mx-auto px-6">
  <!-- ... -->
</div>
```


--------------------------------

### Coordinate nested transitions in Vue with TransitionRoot and TransitionChild

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/headless-ui-v1/index.mdx

Use TransitionRoot and TransitionChild from @headlessui/vue to coordinate parallel nested transitions such as overlays and sidebars. The show prop on TransitionRoot controls the visibility of all nested TransitionChild elements.

```html
<template>
  <!-- This `show` prop controls all nested `Transition.Child` components. -->
  <TransitionRoot :show="isOpen">
    <!-- Background overlay -->
    <TransitionChild
      enter="transition-opacity"
      ease-linear
      duration-300"
      enter-from="opacity-0"
      enter-to="opacity-100"
      leave="transition-opacity"
      ease-linear
      duration-300"
      leave-from="opacity-100"
      leave-to="opacity-0"
    >
      <!-- … -->
    </TransitionChild>

    <!-- Sliding sidebar -->
    <TransitionChild
      enter="transition"
      ease-in-out
      duration-300
      transform"
      enter-from="-translate-x-full"
      enter-to="translate-x-0"
      leave="transition"
      ease-in-out
      duration-300
      transform"
      leave-from="translate-x-0"
      leave-to="-translate-x-full"
    >
      <!-- … -->
    </TransitionChild>
  </TransitionRoot>
</template>

<script>
import { ref } from "vue";
import { Transition, TransitionChild } from "@headlessui/vue";

export default {
  components: { TransitionRoot: Transition, TransitionChild },

  setup() {
    const isShowing = ref(true);

    return {
      isShowing,
    };
  },
};
</script>
```


--------------------------------

### Extend utility variants using variants.extend in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Add new variants like focus-visible to existing utility properties without overriding default variants.

```javascript
module.exports = {
  // ...
  variants: {
    extend: {
      backgroundColor: ["focus-visible"],
    },
  },
};
```


--------------------------------

### Control background position with bg-origin utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Positions an element's background relative to its border, padding box, or content box using bg-origin-border, bg-origin-padding, or bg-origin-content.

```html
<div class="border-4 border-dashed bg-origin-border p-4 ..." style="background-image: url(...)">
  Background is rendered under the border
</div>

<div class="border-4 border-dashed bg-origin-padding p-4 ..." style="background-image: url(...)">
  Background is rendered within the border but on top of any padding
</div>

<div class="border-4 border-dashed bg-origin-content p-4 ..." style="background-image: url(...)">
  Background is rendered within any padding and under the content
</div>
```


--------------------------------

### Configure purge extract in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Customizes the extraction logic Tailwind uses to detect class names for specific file extensions.

```javascript
module.exports = {
  purge: {
    content: ["./src/**/*.{html,md}"],
    extract: {
      pug: (content) => {
        return /[^<>"'`\s]*/.match(content);
      },
    },
  },
  // ...
};
```


--------------------------------

### Author endpoint documentation in MDX

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2022-12-15-protocol-api-documentation-template/index.mdx

Structure API endpoint documentation in MDX with layout components like Row, Col, Properties, and CodeGroup for sticky request and response details.

```jsx
// [!code filename:messages.mdx]
## Create a message {{ tag: 'POST', label: '/v1/messages' }}

<Row>
  <Col>

    Publishes a new message to a specific conversation.

    ### Required attributes

    <Properties>
      <Property name="conversation_id" type="string">
        Unique identifier for the conversation the message belongs to.
      </Property>
      <Property name="message" type="string">
        The message content.
      </Property>
    </Properties>

  </Col>
  <Col sticky>

    <CodeGroup title="Request" tag="POST" label="/v1/messages">

    ```bash {{ title: 'cURL' }}
    curl https://api.protocol.chat/v1/messages \
      -H "Authorization: Bearer {token}" \
      -d conversation_id="xgQQXg3hrtjh7AvZ" \
      -d message="You're what the French call 'les incompetents.'"
    ```

    ```js
    import ApiClient from '@example/protocol-api'
    const client = new ApiClient(token)
    await client.messages.create({
      conversation_id: 'xgQQXg3hrtjh7AvZ',
      message: 'You're what the French call 'les incompetents.'',
    })
    ```

    </CodeGroup>

    ```json {{ title: 'Response' }}
    {
      "id": "gWqY86BMFRiH5o11",
      "conversation_id": "xgQQXg3hrtjh7AvZ",
      "message": "You're what the French call 'les incompetents.'",
      "reactions": [],
      "created_at": 692233200,
    }
    ```

  </Col>
</Row>
```


--------------------------------

### Apply per-side border color utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Sets distinct border colors for individual sides of an element. This feature is only available in Just-in-Time mode.

```html
<div class="border-2 border-t-blue-500 border-r-pink-500 border-b-green-500 border-l-yellow-500">
  <!-- ... -->
</div>
```


--------------------------------

### Enable motion variants for utilities in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-6/index.mdx

Motion variants are not enabled by default; configure them under specific utility keys in the variants section.

```javascript
module.exports = {
  // ...
  variants: {
    translate: ["responsive", "hover", "focus", "motion-safe", "motion-reduce"],
  },
};
```


--------------------------------

### Replace directional variants with logical margin utility

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-3/index.mdx

Use the ms-3 logical property utility instead of separate ltr:ml-3 rtl:mr-3 classes to automatically adapt spacing based on text direction.

```html
<div class="group flex items-center">
  <img class="h-12 w-12 shrink-0 rounded-full" src="..." alt="" />
  <div class="ltr:ml-3 rtl:mr-3"><!-- [!code --] -->
    <div class="ms-3"><!-- [!code ++] -->
      <p
        class="text-sm font-medium text-slate-700 group-hover:text-slate-900"
        dark-class="text-sm font-medium text-slate-300 group-hover:text-white"
      >
        ...
      </p>
      <p
        class="text-sm font-medium text-slate-500 group-hover:text-slate-700"
        dark-class="text-sm font-medium text-slate-500 group-hover:text-slate-300"
      >
        ...
      </p>
    </div>
  </div>
</div>
```


--------------------------------

### Apply top-end spacing scale value

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Applies large padding using extended high-end spacing scale utilities.

```html
<div class="p-96">This is too much padding.</div>
```


--------------------------------

### Create dynamic group-* variant with custom selector

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Pass a custom selector inside square brackets to create custom group variants on the fly. Matches the parent group selector when the specified class is present.

```html
<!-- [!code word:group-[.is-published\]\:block] -->
<div class="group is-published">
  <div class="group-[.is-published]:block hidden">Published</div>
</div>
```

```css
.group.is-published .group-\[\.is-published\]\:block {
  display: block;
}
```


--------------------------------

### Style sibling elements using peer-* variants in HTML

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Applies styles to a sibling element when a preceding checkbox state changes using the peer class and peer-checked variant. Requires Just-in-Time mode.

```html
<label>
  <input type="checkbox" class="peer sr-only" />
  <span class="h-4 w-4 bg-gray-200 peer-checked:bg-blue-500">
    <!-- ... -->
  </span>
</label>
```


--------------------------------

### Virtualize Combobox list with virtual prop in Headless UI

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/headless-ui-v2/index.mdx

Use the virtual prop on Combobox to handle large option lists using TanStack Virtual integration. Pass filtered options to the virtual prop and render each item using the ComboboxOptions render prop.

```jsx
import { Combobox, ComboboxButton, ComboboxInput, ComboboxOption, ComboboxOptions } from "@headlessui/react";
import { ChevronDownIcon } from "@heroicons/react/20/solid";
import { useState } from "react";

const people = [
  { id: 1, name: "Rossie Abernathy" },
  { id: 2, name: "Juana Abshire" },
  { id: 3, name: "Leonel Abshire" },
  { id: 4, name: "Llewellyn Abshire" },
  { id: 5, name: "Ramon Abshire" },
  // ...up to 1000 people
];

function Example() {
  const [query, setQuery] = useState("");
  const [selected, setSelected] = useState(people[0]);

  const filteredPeople =
    query === ""
      ? people
      : people.filter((person) => {
          return person.name.toLowerCase().includes(query.toLowerCase());
        });

  return (
    <Combobox
      value={selected}
      // [!code highlight:2]
      virtual={{ options: filteredPeople }}
      onChange={(value) => setSelected(value)}
      onClose={() => setQuery("")}
    >
      <div>
        <ComboboxInput displayValue={(person) => person?.name} onChange={(event) => setQuery(event.target.value)} />
        <ComboboxButton>
          <ChevronDownIcon />
        </ComboboxButton>
      </div>
      <ComboboxOptions>
        // [!code highlight:6]
        {({ option: person }) => (
          <ComboboxOption key={person.id} value={person}>
            {person.name}
          </ComboboxOption>
        )}
      </ComboboxOptions>
    </Combobox>
  );
}
```


--------------------------------

### Enable defaultLineHeights in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-1-7/index.mdx

Enable recommended default line-heights paired with each font-size utility. This is a breaking change from the previous global default line-height of 1.5.

```javascript
// [!code filename:tailwind.config.js]
module.exports = {
  experimental: {
    defaultLineHeights: true,
  },
};
```


--------------------------------

### Conditional styling with arbitrary data attribute variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Conditionally apply styles using data-[size=large] attribute variants and view the resulting CSS output.

```html
<!-- Will apply -->
<div data-size="large" class="data-[size=large]:p-8">
  <!-- ... -->
</div>

<!-- Will not apply -->
<div data-size="medium" class="data-[size=large]:p-8">
  <!-- ... -->
</div>

<!-- Generated CSS -->
<style>
  .data-\[size\=large\]\:p-8[data-size="large"] {
    padding: 2rem;
  }
</style>
```


--------------------------------

### Ordering utility overrides

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/automatic-class-sorting-with-prettier/index.mdx

Utilities are sorted in the same order as in CSS, ensuring classes that override other classes appear later in the class list.

```html
<div class="pt-2 p-4"> <!-- [!code --] -->
<div class="p-4 pt-2"> <!-- [!code ++] -->
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Pass props to headings using mdx-annotations

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/2022-12-15-protocol-api-documentation-template/index.mdx

Annotate Markdown headings with an object to pass props directly into rendered JSX components via mdx-annotations.

```mdx
## Create a message { tag: 'POST', label: '/v1/messages' }
```

```jsx
<Heading level={2} tag="POST" label="/v1/messages">
  Create a message
</Heading>
```


--------------------------------

### Apply complex and responsive utility variants with @apply

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v2/index.mdx

Apply hover, focus, ring, and opacity utility variants directly within CSS rules using the @apply directive.

```css
.btn {
  @apply focus:ring-opacity-50 bg-indigo-500 hover:bg-indigo-600 focus:ring-2 focus:ring-indigo-200;
}
```


--------------------------------

### Generated CSS output for peer sibling selector variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-2-2/index.mdx

Illustrates the generated CSS that uses the general sibling combinator (~). Sibling targeting only works on elements following the peer in DOM order.

```css
.peer:checked ~ .peer-checked\:bg-blue-500 {
  background-color: #3b82f6;
}
```


--------------------------------

### Configure custom aria modifiers in tailwind.config.js

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/blog/tailwindcss-v3-2/index.mdx

Customizes available aria-* modifiers by configuring theme.extend.aria in tailwind.config.js.

```javascript
// [!code filename:tailwind.config.js]
module.exports = {
  theme: {
    extend: {
      aria: {
        asc: 'sort="ascending"',
        desc: 'sort="descending"',
      },
    },
  },
};
```
