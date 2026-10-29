# Tailwind CSS — Utilities

Sourced snippets (256 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Start content with place-content-start

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/place-content.mdx

Packs items against the start of both the inline and block axes in a grid container.

```html
<!-- [!code classes:place-content-start] -->
<div class="grid h-48 grid-cols-2 place-content-start gap-4 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
</div>
```


--------------------------------

### Aligning and justifying grid items at the start

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/place-items.mdx

Use `place-items-start` to place grid items at the start of their grid areas on both axes simultaneously.

```html
<!-- [!code classes:place-items-start] -->
<div class="grid grid-cols-3 place-items-start gap-4 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
  <div>05</div>
  <div>06</div>
</div>
```


--------------------------------

### Align content to start with content-start

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/align-content.mdx

Use `content-start` to pack rows in a container against the start of the cross axis.

```html
<!-- [!code classes:content-start] -->
<div class="grid h-56 grid-cols-3 content-start gap-4 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
  <div>05</div>
</div>
```


--------------------------------

### Snap elements to start with snap-start

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scroll-snap-align.mdx

Use the snap-start utility on child elements to align them to the start of a scroll snap container when scrolling.

```html
<!-- [!code classes:snap-x,snap-start] -->

<div class="snap-x ...">
  <div class="snap-start ...">
    <img src="/img/vacation-01.jpg" />
  </div>
  <div class="snap-start ...">
    <img src="/img/vacation-02.jpg" />
  </div>
  <div class="snap-start ...">
    <img src="/img/vacation-03.jpg" />
  </div>
  <div class="snap-start ...">
    <img src="/img/vacation-04.jpg" />
  </div>
  <div class="snap-start ...">
    <img src="/img/vacation-05.jpg" />
  </div>
  <div class="snap-start ...">
    <img src="/img/vacation-06.jpg" />
  </div>
</div>
```


--------------------------------

### Justify grid items to the start with justify-items-start

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/justify-items.mdx

Use the justify-items-start utility to justify grid items against the start of their inline axis.

```html
<!-- [!code classes:justify-items-start] -->
<div class="grid justify-items-start ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
  <div>05</div>
  <div>06</div>
</div>
```


--------------------------------

### Align items to the start

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/align-items.mdx

Use the items-start utility to align items to the start of the container's cross axis.

```html
<!-- [!code classes:items-start] -->
<div class="flex items-start ...">
  <div class="py-4">01</div>
  <div class="py-12">02</div>
  <div class="py-8">03</div>
</div>
```


--------------------------------

### Align item to the start on both axes using place-self-start

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/place-self.mdx

Use `place-self-start` to align an individual item to the start on both axes.

```html
<!-- [!code classes:place-self-start] -->
<div class="grid grid-cols-3 gap-4 ...">
  <div>01</div>
  <div class="place-self-start ...">02</div>
  <div>03</div>
  <div>04</div>
  <div>05</div>
  <div>06</div>
</div>
```


--------------------------------

### Justify items to the start using justify-start

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/justify-content.mdx

Applies flex-start justification to align items against the start of the container's main axis.

```html
<!-- [!code classes:justify-start] -->
<div class="flex justify-start ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```


--------------------------------

### Enable transitions on discrete properties with transition-discrete

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/transition-behavior.mdx

Apply the `transition-discrete` utility to start transitions when changing properties with a discrete set of values, such as switching between `hidden` and `block`.

```html
<!-- [!code classes:transition-discrete] -->
<label class="peer ...">
  <input type="checkbox" checked />
</label>
<button class="hidden transition-all not-peer-has-checked:opacity-0 peer-has-checked:block ...">
  <!-- prettier-ignore -->
  I hide
</button>

<label class="peer ...">
  <input type="checkbox" checked />
</label>
<button class="hidden transition-all transition-discrete not-peer-has-checked:opacity-0 peer-has-checked:block ...">
  I fade out
</button>
```


--------------------------------

### Align item to the start with justify-self-start

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/justify-self.mdx

Use the `justify-self-start` utility to align a grid item to the start of its inline axis.

```html
<!-- [!code classes:justify-self-start] -->
<div class="grid justify-items-stretch ...">
  <!-- ... -->
  <div class="justify-self-start ...">02</div>
  <!-- ... -->
</div>
```


--------------------------------

### Set column width using columns-* utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/columns.mdx

Use utilities like `columns-3xs` to set the ideal column width for content inside an element. The number of columns automatically adjusts to ensure columns do not get too narrow.

```html
<!-- [!code classes:columns-3xs] -->
<div class="columns-3xs ...">
  <img class="aspect-3/2 ..." src="/img/mountains-1.jpg" />
  <img class="aspect-square ..." src="/img/mountains-2.jpg" />
  <img class="aspect-square ..." src="/img/mountains-3.jpg" />
  <!-- ... -->
</div>
```


--------------------------------

### Tab size 2 example content

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/tab-size.mdx

Indented code block rendered inside a container using the tab-2 utility.

```jsx
function indent() {
	return 'tabbed';
}
```


--------------------------------

### Set scroll margin inline start with scroll-ms-6

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scroll-margin.mdx

Applies `scroll-ms-6` to set scroll margin inline start for snap targets, automatically adjusting positioning based on LTR and RTL text direction.

```html
<!-- [!code classes:scroll-ms-6] -->
<!-- [!code word:dir="ltr"] -->
<!-- [!code word:dir="rtl"] -->
<div dir="ltr">
  <div class="snap-x ...">
    <div class="snap-start scroll-ms-6 ...">
      <img src="/img/vacation-01.jpg"/>
    </div>
    <!-- ... -->
  </div>
</div>

<div dir="rtl">
  <div class="snap-x ...">
    <div class="snap-start scroll-ms-6 ...">
      <img src="/img/vacation-01.jpg"/>
    </div>
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Setting grid start and end lines with col-start and col-end

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/grid-column.mdx

Use col-start-<number> and col-end-<number> utilities to align an element to specific grid lines. They can be combined with col-span-<number> utilities.

```html
<!-- [!code classes:col-start-1,col-start-2,col-end-3,col-end-7] -->
<div class="grid grid-cols-6 gap-4">
  <div class="col-span-4 col-start-2 ...">01</div>
  <div class="col-start-1 col-end-3 ...">02</div>
  <div class="col-span-2 col-end-7 ...">03</div>
  <div class="col-start-1 col-end-7 ...">04</div>
</div>
```


--------------------------------

### Setting flex item size using percentages

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/flex-basis.mdx

Use basis-<fraction> utilities like basis-1/3 and basis-2/3 to set proportional initial sizes for flex items.

```html
<!-- [!code classes:basis-1/3,basis-2/3] -->
<div class="flex flex-row">
  <div class="basis-1/3">01</div>
  <div class="basis-2/3">02</div>
</div>
```


--------------------------------

### Starting and ending grid lines with row-start and row-end

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/grid-row.mdx

Use row-start-<number> and row-end-<number> utilities to anchor elements to specific grid lines. They can be combined with row-span-<number> utilities to span a defined number of rows from a specific line.

```html
<!-- [!code classes:row-start-1,row-start-2,row-end-3,row-end-4] -->
<div class="grid grid-flow-col grid-rows-3 gap-4">
  <div class="row-span-2 row-start-2 ...">01</div>
  <div class="row-span-2 row-end-3 ...">02</div>
  <div class="row-start-1 row-end-4 ...">03</div>
</div>
```


--------------------------------

### Create a grid container with grid

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/display.mdx

Use the grid utility to establish a block-level grid layout container.

```html
<!-- [!code classes:grid] -->
<div class="grid grid-cols-3 grid-rows-3 gap-4">
  <!-- ... -->
</div>
```


--------------------------------

### Safely center grid items with justify-items-center-safe

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/justify-items.mdx

Use justify-items-center-safe to center grid items while aligning them to the start of the container when there is not enough available space.

```html
<!-- [!code filename:justify-items-center-safe] -->
<!-- [!code classes:justify-items-center-safe] -->
<div class="grid grid-flow-col justify-items-center-safe ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```


--------------------------------

### Creating table layouts with display utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/display.mdx

Use utilities like `table`, `table-header-group`, `table-row-group`, `table-row`, and `table-cell` to construct elements that behave like standard table markup.

```html
<!-- [!code classes:table,table-header-group,table-row-group,table-row,table-cell] -->
<div class="table w-full ...">
  <div class="table-header-group ...">
    <div class="table-row">
      <div class="table-cell text-left ...">Song</div>
      <div class="table-cell text-left ...">Artist</div>
      <div class="table-cell text-left ...">Year</div>
    </div>
  </div>
  <div class="table-row-group">
    <div class="table-row">
      <div class="table-cell ...">The Sliding Mr. Bones (Next Stop, Pottersville)</div>
      <div class="table-cell ...">Malcolm Lockyer</div>
      <div class="table-cell ...">1961</div>
    </div>
    <div class="table-row">
      <div class="table-cell ...">Witchy Woman</div>
      <div class="table-cell ...">The Eagles</div>
      <div class="table-cell ...">1972</div>
    </div>
    <div class="table-row">
      <div class="table-cell ...">Shining Star</div>
      <div class="table-cell ...">Earth, Wind, and Fire</div>
      <div class="table-cell ...">1975</div>
    </div>
  </div>
</div>
```


--------------------------------

### Set percentage-based block size with block-full and block-<fraction>

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/block-size.mdx

Use `block-full` or fractional utilities like `block-1/2` and `block-9/10` to define an element's block size as a percentage of its parent.

```html
<!-- [!code classes:block-9/10,block-3/4,block-1/2,block-1/3,block-full] -->
<div class="block-full ...">block-full</div>
<div class="block-9/10 ...">block-9/10</div>
<div class="block-3/4 ...">block-3/4</div>
<div class="block-1/2 ...">block-1/2</div>
<div class="block-1/3 ...">block-1/3</div>
```


--------------------------------

### Set block padding using logical properties

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/padding.mdx

Use pbs-<number> and pbe-<number> utilities to set padding-block-start and padding-block-end logical properties based on writing mode.

```html
<!-- [!code classes:pbs-8] -->
<div class="pbs-8 ...">pbs-8</div>
```


--------------------------------

### Set element opacity with opacity utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/opacity.mdx

Use utilities like opacity-100, opacity-75, opacity-50, and opacity-25 to configure the visual opacity level of an element.

```html
<!-- [!code classes:opacity-100,opacity-75,opacity-50,opacity-25] -->
<button class="bg-indigo-500 opacity-100 ..."></button>
<button class="bg-indigo-500 opacity-75 ..."></button>
<button class="bg-indigo-500 opacity-50 ..."></button>
<button class="bg-indigo-500 opacity-25 ..."></button>
```


--------------------------------

### Applying directional mask gradient stops with mask-x and mask-y

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/mask-image.mdx

Sets the start and end positions for horizontal and vertical linear gradient masks on an element.

```html
<!-- [!code classes:mask-x-from-70%,mask-x-to-90%,mask-y-from-70%,mask-y-to-90%] -->
<div class="mask-x-from-70% mask-x-to-90% bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-y-from-70% mask-y-to-90% bg-[url(/img/mountains.jpg)] ..."></div>
```


--------------------------------

### Set scroll margin block start with scroll-mbs-6

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scroll-margin.mdx

Sets the `scroll-margin-block-start` property to map to the top or bottom side according to the container's writing mode.

```html
<!-- [!code classes:scroll-mbs-6] -->
<div class="snap-y ...">
  <div class="snap-start scroll-mbs-6 ...">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Center an item safely using justify-self-center-safe

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/justify-self.mdx

Aligns a grid item to the center of its inline axis, falling back to align to the start of the container when there is not enough space.

```html
<!-- [!code filename:justify-self-center-safe] -->
<!-- [!code classes:justify-self-center-safe] -->
<div class="grid justify-items-stretch ...">
  <!-- ... -->
  <div class="justify-self-center-safe ...">02</div>
  <!-- ... -->
</div>
```


--------------------------------

### Center items safely using justify-center-safe

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/justify-content.mdx

Positions items along the center of the main axis, falling back to aligning items to the start when there is insufficient space.

```html
<!-- [!code filename:justify-center-safe] -->
<!-- [!code classes:justify-center-safe] -->
<div class="flex justify-center-safe ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
</div>
```


--------------------------------

### Enable hardware acceleration with transform-gpu

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/transform.mdx

Force hardware acceleration with the GPU for transitions by adding the `transform-gpu` utility. Use `transform-cpu` to revert to CPU rendering conditionally.

```html
<!-- [!code classes:transform-gpu] -->
<div class="scale-150 transform-gpu">
  <!-- ... -->
</div>
```


--------------------------------

### Setting percentage-based minimum width

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/min-width.mdx

Use min-w-full or min-w-<fraction> utilities like min-w-1/2 and min-w-3/4 to give an element a percentage-based minimum width.

```html
<!-- [!code classes:min-w-3/4] -->
<div class="flex ...">
  <div class="min-w-3/4 ...">min-w-3/4</div>
  <div class="w-full ...">w-full</div>
</div>
```


--------------------------------

### Setting a percentage-based minimum block size

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/min-block-size.mdx

Use min-block-full or min-block-<fraction> utilities to apply a percentage-based minimum block size to an element.

```html
<!-- [!code classes:min-block-9/10,min-block-3/4,min-block-1/2,min-block-1/3,min-block-full] -->
<div class="min-block-full ...">min-block-full</div>
<div class="min-block-9/10 ...">min-block-9/10</div>
<div class="min-block-3/4 ...">min-block-3/4</div>
<div class="min-block-1/2 ...">min-block-1/2</div>
<div class="min-block-1/3 ...">min-block-1/3</div>
```


--------------------------------

### Align grid item safely to end with justify-self-end-safe

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/justify-self.mdx

Aligns a grid item to the end of its inline axis. If there is insufficient space available, it aligns the item to the start instead.

```html
<!-- [!code filename:justify-self-end-safe] -->
<!-- [!code classes:justify-self-end-safe] -->
<div class="grid justify-items-stretch ...">
  <!-- ... -->
  <div class="justify-self-end-safe ...">02</div>
  <!-- ... -->
</div>
```


--------------------------------

### Justify items with overflow protection using justify-end-safe

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/justify-content.mdx

Use justify-end-safe to justify items against the end of the main axis, falling back to aligning items to the start when there is insufficient space.

```html
<!-- [!code filename:justify-end-safe] -->
<!-- [!code classes:justify-end-safe] -->
<div class="flex justify-end-safe ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
</div>
```


--------------------------------

### Justify grid items safely against the end with justify-items-end-safe

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/justify-items.mdx

Use justify-items-end-safe to justify grid items against the end of their inline axis while falling back to start alignment when insufficient space is available.

```html
<!-- [!code filename:justify-items-end-safe] -->
<!-- [!code classes:justify-items-end-safe] -->
<div class="grid grid-flow-col justify-items-end-safe ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```


--------------------------------

### Using logical properties with float-start

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/float.mdx

Use logical properties like `float-start` and `float-end` to map float positioning to either the left or right side depending on the text direction.

```html
<!-- [!code word:dir="rtl"] -->
<!-- [!code classes:float-start] -->
<article>
  <img class="float-start ..." src="/img/mountains.jpg" />
  <p>Maybe we can live without libraries, people like you and me. ...</p>
</article>

<article dir="rtl">
  <img class="float-start ..." src="/img/mountains.jpg" />
  <p>... ربما يمكننا العيش بدون مكتبات، أشخاص مثلي ومثلك. ربما. بالتأكيد</p>
</article>
```


--------------------------------

### Create an inline grid container with inline-grid

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/display.mdx

Use the inline-grid utility to establish an inline-level grid container.

```html
<!-- [!code classes:inline-grid] -->
<span class="inline-grid grid-cols-3 gap-4">
  <span>01</span>
  <span>02</span>
  <span>03</span>
  <span>04</span>
  <span>05</span>
  <span>06</span>
</span>
<span class="inline-grid grid-cols-3 gap-4">
  <span>01</span>
  <span>02</span>
  <span>03</span>
  <span>04</span>
  <span>05</span>
  <span>06</span>
</span>
```


--------------------------------

### Set maximum block size using percentage utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/max-block-size.mdx

Use `max-block-full` or `max-block-<fraction>` utilities like `max-block-1/2` and `max-block-3/4` to define percentage-based maximum constraints along the block axis.

```html
<!-- [!code classes:max-block-9/10,max-block-3/4,max-block-1/2,max-block-1/4,max-block-full] -->
<div class="block-96 ...">
  <div class="block-full max-block-9/10 ...">max-block-9/10</div>
  <div class="block-full max-block-3/4 ...">max-block-3/4</div>
  <div class="block-full max-block-1/2 ...">max-block-1/2</div>
  <div class="block-full max-block-full ...">max-block-full</div>
</div>
```


--------------------------------

### Mirror and scale an element using negative scale utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scale.mdx

Use negative scale utilities such as `-scale-x-75`, `-scale-100`, or `-scale-y-125` to mirror and scale an element by a percentage of its original size.

```html
<!-- [!code classes:-scale-x-75,-scale-100,-scale-y-125] -->
<img class="-scale-x-75 ..." src="/img/mountains.jpg" />
<img class="-scale-100 ..." src="/img/mountains.jpg" />
<img class="-scale-y-125 ..." src="/img/mountains.jpg" />
```


--------------------------------

### Applying object-fit responsively

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/object-fit.mdx

Prefix object-fit utilities with breakpoint variants like md: to apply them at specific screen sizes.

```html
<!-- [!code classes:md:object-cover] -->
<img class="object-contain md:object-cover" src="/img/mountains.jpg" />
```


--------------------------------

### Applying transition properties to an element

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/transition-property.mdx

Use transition utilities such as `transition` to control which properties smoothly animate when their state changes.

```html
<!-- [!code classes:transition] -->
<button class="bg-blue-500 transition delay-150 duration-300 ease-in-out hover:-translate-y-1 hover:scale-110 hover:bg-indigo-500 ...">
  Save Changes
</button>
```


--------------------------------

### Controlling fragment rendering with box-decoration-slice and box-decoration-clone

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/box-decoration-break.mdx

Use `box-decoration-slice` and `box-decoration-clone` to specify whether styles like background, border, and padding render as one continuous fragment or separate blocks across line breaks.

```html
<!-- [!code classes:box-decoration-slice,box-decoration-clone] -->
<span class="box-decoration-slice bg-linear-to-r from-indigo-600 to-pink-500 px-2 text-white ...">
  Hello<br />World
</span>
<span class="box-decoration-clone bg-linear-to-r from-indigo-600 to-pink-500 px-2 text-white ...">
  Hello<br />World
</span>
```


--------------------------------

### Set percentage-based height with h-full and fraction utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/height.mdx

Use h-full or h-<fraction> utilities to give an element a percentage-based height.

```html
<!-- [!code classes:h-9/10,h-3/4,h-1/2,h-1/3,h-full] -->
<div class="h-full ...">h-full</div>
<div class="h-9/10 ...">h-9/10</div>
<div class="h-3/4 ...">h-3/4</div>
<div class="h-1/2 ...">h-1/2</div>
<div class="h-1/3 ...">h-1/3</div>
```


--------------------------------

### Setting a percentage-based maximum width

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/max-width.mdx

Use max-w-full or max-w-<fraction> utilities like max-w-1/2 and max-w-2/5 to give an element a percentage-based maximum width.

```html
<!-- [!code classes:max-w-3/4,max-w-9/10,max-w-1/2,max-w-1/3] -->
<div class="w-full max-w-9/10 ...">max-w-9/10</div>
<div class="w-full max-w-3/4 ...">max-w-3/4</div>
<div class="w-full max-w-1/2 ...">max-w-1/2</div>
<div class="w-full max-w-1/3 ...">max-w-1/3</div>
```


--------------------------------

### Applying backdrop blur utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/backdrop-filter-blur.mdx

Use utilities like backdrop-blur-none, backdrop-blur-sm, and backdrop-blur-md to control an element's backdrop blur.

```html
<!-- [!code classes:backdrop-blur-none,backdrop-blur-sm,backdrop-blur-md] -->
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-blur-none ..."></div>
</div>
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-blur-sm ..."></div>
</div>
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-blur-md ..."></div>
</div>
```


--------------------------------

### Applying blur filters with blur utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/filter-blur.mdx

Use utilities like blur-none, blur-sm, blur-lg, and blur-2xl to apply different levels of blur filters to an element.

```html
<!-- [!code classes:blur-none,blur-sm,blur-lg,blur-2xl] -->
<img class="blur-none" src="/img/mountains.jpg" />
<img class="blur-sm" src="/img/mountains.jpg" />
<img class="blur-lg" src="/img/mountains.jpg" />
<img class="blur-2xl" src="/img/mountains.jpg" />
```


--------------------------------

### Applying backdrop-invert utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/backdrop-filter-invert.mdx

Use utilities like backdrop-invert, backdrop-invert-0, and backdrop-invert-65 to control the color inversion of an element's backdrop.

```html
<!-- [!code classes:backdrop-invert-0,backdrop-invert-65,backdrop-invert] -->
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-invert-0 ..."></div>
</div>
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-invert-65 ..."></div>
</div>
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-invert ..."></div>
</div>
```


--------------------------------

### Control element saturation with saturate utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/filter-saturate.mdx

Use utilities like `saturate-50` and `saturate-100` to control an element's saturation level.

```html
<!-- [!code classes:saturate-50,saturate-100,saturate-150,saturate-200] -->
<img class="saturate-50 ..." src="/img/mountains.jpg" />
<img class="saturate-100 ..." src="/img/mountains.jpg" />
<img class="saturate-150 ..." src="/img/mountains.jpg" />
<img class="saturate-200 ..." src="/img/mountains.jpg" />
```


--------------------------------

### Control stack order using z-index utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/z-index.mdx

Use utilities like z-10 and z-50 to set the three-dimensional positioning and stacking order of elements.

```html
<!-- [!code classes:z-40,z-30,z-20,z-10,z-0] -->
<div class="z-40 ...">05</div>
<div class="z-30 ...">04</div>
<div class="z-20 ...">03</div>
<div class="z-10 ...">02</div>
<div class="z-0 ...">01</div>
```


--------------------------------

### Set element color scheme with scheme-* utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/color-scheme.mdx

Use utilities like scheme-light, scheme-dark, and scheme-light-dark to control how an element should be rendered.

```html
<!-- [!code classes:scheme-light-dark,scheme-light,scheme-dark] -->
<div class="scheme-light ...">
  <input type="date" />
</div>

<div class="scheme-dark ...">
  <input type="date" />
</div>

<div class="scheme-light-dark ...">
  <input type="date" />
</div>
```


--------------------------------

### Controlling grid auto-placement with grid-flow-row-dense

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/grid-auto-flow.mdx

Use utilities like grid-flow-row-dense to control how the auto-placement algorithm works for a grid layout.

```html
<!-- [!code classes:grid-flow-row-dense] -->
<div class="grid grid-flow-row-dense grid-cols-3 grid-rows-3 ...">
  <div class="col-span-2">01</div>
  <div class="col-span-2">02</div>
  <div>03</div>
  <div>04</div>
  <div>05</div>
</div>
```


--------------------------------

### Translate elements by percentage fractions

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/translate.mdx

Use translate-<fraction> utilities like -translate-1/4, translate-1/6, and translate-1/2 to translate an element on both axes by a percentage of the element's size.

```html
<!-- [!code classes:-translate-1/4,translate-1/6,translate-1/2] -->
<img class="-translate-1/4 ..." src="/img/mountains.jpg" />
<img class="translate-1/6 ..." src="/img/mountains.jpg" />
<img class="translate-1/2 ..." src="/img/mountains.jpg" />
```


--------------------------------

### Create a block formatting context using flow-root

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/display.mdx

Use the flow-root utility to create a block-level element with its own independent block formatting context.

```html
<!-- [!code classes:flow-root] -->
<div class="p-4">
  <div class="flow-root ...">
    <div class="my-4 ...">Well, let me tell you something, ...</div>
  </div>
  <div class="flow-root ...">
    <div class="my-4 ...">Sure, go ahead, laugh if you want...</div>
  </div>
</div>
```


--------------------------------

### Setting flex item size using the container scale

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/flex-basis.mdx

Use utilities like basis-3xs, basis-2xs, basis-xs, and basis-sm to size flex items according to the container scale.

```html
<!-- [!code classes:basis-3xs,basis-2xs,basis-xs,basis-sm] -->
<div class="flex flex-row">
  <div class="basis-3xs">01</div>
  <div class="basis-2xs">02</div>
  <div class="basis-xs">03</div>
  <div class="basis-sm">04</div>
</div>
```


--------------------------------

### Applying contrast utilities to adjust element contrast

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/filter-contrast.mdx

Use utilities such as contrast-50, contrast-100, contrast-125, and contrast-200 to adjust an element's contrast.

```html
<!-- [!code classes:contrast-50,contrast-100,contrast-125,contrast-200] -->
<img class="contrast-50 ..." src="/img/mountains.jpg" />
<img class="contrast-100 ..." src="/img/mountains.jpg" />
<img class="contrast-125 ..." src="/img/mountains.jpg" />
<img class="contrast-200 ..." src="/img/mountains.jpg" />
```


--------------------------------

### Set percentage-based inline size

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/inline-size.mdx

Use inline-full or fractional utilities like inline-1/2, inline-2/5, and inline-1/3 to assign percentage-based inline sizes.

```html
<!-- [!code classes:inline-1/2,inline-2/5,inline-3/5,inline-1/3,inline-2/3,inline-full] -->
<div class="flex ...">
  <div class="inline-1/2 ...">inline-1/2</div>
  <div class="inline-1/2 ...">inline-1/2</div>
</div>
<div class="flex ...">
  <div class="inline-2/5 ...">inline-2/5</div>
  <div class="inline-3/5 ...">inline-3/5</div>
</div>
<div class="flex ...">
  <div class="inline-1/3 ...">inline-1/3</div>
  <div class="inline-2/3 ...">inline-2/3</div>
</div>
<div class="inline-full ...">inline-full</div>
```


--------------------------------

### Applying blur and grayscale filters

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/filter.mdx

Use filter utility classes like blur-xs and grayscale individually or combine them on a single element.

```html
<!-- [!code classes:blur-xs,grayscale] -->
<img class="blur-xs" src="/img/mountains.jpg" />
<img class="grayscale" src="/img/mountains.jpg" />
<img class="blur-xs grayscale" src="/img/mountains.jpg" />
```


--------------------------------

### Implementing a subgrid with grid-cols-subgrid

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/grid-template-columns.mdx

Use the grid-cols-subgrid utility to adopt the column tracks defined by the item's parent.

```html
<!-- [!code classes:grid-cols-subgrid] -->
<div class="grid grid-cols-4 gap-4">
  <div>01</div>
  <!-- ... -->
  <div>05</div>
  <div class="col-span-3 grid grid-cols-subgrid gap-4">
    <div class="col-start-2">06</div>
  </div>
</div>
```


--------------------------------

### Apply outer box shadows with size utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/box-shadow.mdx

Use utilities like shadow-md, shadow-lg, and shadow-xl to apply different sized outer box shadows to an element.

```html
<!-- [!code classes:shadow-md,shadow-lg,shadow-xl] -->
<div class="shadow-md ..."></div>
<div class="shadow-lg ..."></div>
<div class="shadow-xl ..."></div>
```


--------------------------------

### Set transition delay in milliseconds

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/transition-delay.mdx

Use utilities like `delay-150`, `delay-300`, and `delay-700` to specify the transition delay of an element.

```html
<!-- [!code classes:delay-150,delay-300,delay-700] -->
<button class="transition delay-150 duration-300 ease-in-out ...">Button A</button>
<button class="transition delay-300 duration-300 ease-in-out ...">Button B</button>
<button class="transition delay-700 duration-300 ease-in-out ...">Button C</button>
```


--------------------------------

### Allow flex items to grow and shrink ignoring initial size

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/flex.mdx

Use flex-<number> utilities such as flex-1 to allow a flex item to grow and shrink as needed while ignoring its initial size.

```html
<!-- [!code word:flex-1] -->
<div class="flex">
  <div class="w-14 flex-none ...">01</div>
  <div class="w-64 flex-1 ...">02</div>
  <div class="w-32 flex-1 ...">03</div>
</div>
```


--------------------------------

### Control backdrop saturation using backdrop-saturate utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/backdrop-filter-saturate.mdx

Use utilities like backdrop-saturate-50, backdrop-saturate-125, and backdrop-saturate-200 to control the saturation level of an element's backdrop.

```html
<!-- [!code classes:backdrop-saturate-50,backdrop-saturate-125,backdrop-saturate-200] -->
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-saturate-50 ..."></div>
</div>
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-saturate-125 ..."></div>
</div>
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-saturate-200 ..."></div>
</div>
```


--------------------------------

### Setting block border color with logical properties

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/border-color.mdx

Use utilities like border-bs-* and border-be-* to configure border-block-start-color and border-block-end-color based on writing mode.

```html
<!-- [!code classes:border-bs-indigo-500] -->
<div class="border-bs-indigo-500 ..."></div>
```


--------------------------------

### Create an inline flex container with inline-flex

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/display.mdx

Use the inline-flex utility to create an inline flex container that flows inline with text.

```html
<!-- [!code classes:inline-flex] -->
<p>
  Today I spent most of the day researching ways to ...
  <span class="inline-flex items-baseline">
    <img src="/img/kramer.jpg" class="mx-1 size-5 self-center rounded-full" />
    <span>Kramer</span>
  </span>
  keeps telling me there is no way to make it work, that ...
</p>
```


--------------------------------

### Setting the minimum block size with min-block utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/min-block-size.mdx

Use min-block-<number> utilities like min-block-24 and min-block-64 to set an element to a fixed minimum block size based on the spacing scale.

```html
<!-- [!code classes:min-block-80,min-block-64,min-block-48,min-block-40,min-block-32,min-block-24] -->
<div class="block-20 ...">
  <div class="min-block-80 ...">min-block-80</div>
  <div class="min-block-64 ...">min-block-64</div>
  <div class="min-block-48 ...">min-block-48</div>
  <div class="min-block-40 ...">min-block-40</div>
  <div class="min-block-32 ...">min-block-32</div>
</div>
```


--------------------------------

### Apply border radius sizes using rounded utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/border-radius.mdx

Use utilities like `rounded-sm`, `rounded-md`, `rounded-lg`, and `rounded-xl` to apply different border radius sizes to an element.

```html
<!-- [!code classes:rounded-sm,rounded-md,rounded-lg,rounded-xl] -->
<div class="rounded-sm ..."></div>
<div class="rounded-md ..."></div>
<div class="rounded-lg ..."></div>
<div class="rounded-xl ..."></div>
```


--------------------------------

### Set percentage-based minimum inline size

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/min-inline-size.mdx

Use min-inline-full or min-inline-<fraction> utilities to give an element a percentage-based minimum inline size.

```html
<!-- [!code classes:min-inline-3/4] -->
<div class="flex ...">
  <div class="min-inline-3/4 ...">min-inline-3/4</div>
  <div class="inline-full ...">inline-full</div>
</div>
```


--------------------------------

### Create a block-level flex container with flex

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/display.mdx

Use the flex utility to create a block-level flex container for arranging child elements.

```html
<!-- [!code classes:flex] -->
<div class="flex items-center">
  <img src="path/to/image.jpg" />
  <div>
    <strong>Andrew Alfred</strong>
    <span>Technical advisor</span>
  </div>
</div>
```


--------------------------------

### Create a phantom container with contents

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/display.mdx

Use the `contents` utility to create a phantom container whose children behave as direct children of the outer flex parent.

```html
<!-- [!code classes:contents] -->
<div class="flex ...">
  <div class="flex-1 ...">01</div>
  <div class="contents">
    <div class="flex-1 ...">02</div>
    <div class="flex-1 ...">03</div>
  </div>
  <div class="flex-1 ...">04</div>
</div>
```


--------------------------------

### Scrolling with the container using bg-local

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/background-attachment.mdx

Use the bg-local utility to scroll the background image with the container and the viewport.

```html
<!-- [!code classes:bg-local] -->
<div class="bg-[url(/img/mountains.jpg)] bg-local ...">
  <!-- ... -->
</div>
```


--------------------------------

### Setting column gap with gap utility classes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/columns.mdx

Use gap-<width> utilities like gap-8 to specify the width of gutters between columns.

```html
<!-- [!code classes:gap-8] -->
<div class="columns-3 gap-8 ...">
  <img class="aspect-3/2 ..." src="/img/mountains-1.jpg" />
  <img class="aspect-square ..." src="/img/mountains-2.jpg" />
  <img class="aspect-square ..." src="/img/mountains-3.jpg" />
  <!-- ... -->
</div>
```


--------------------------------

### Set inline padding using logical properties

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/padding.mdx

Use ps-<number> and pe-<number> utilities to set padding-inline-start and padding-inline-end based on text direction (LTR or RTL).

```html
<!-- [!code classes:ps-8,pe-8] -->
<!-- [!code word:dir="ltr"] -->
<!-- [!code word:dir="rtl"] -->
<div>
  <div dir="ltr">
    <div class="ps-8 ...">ps-8</div>
    <div class="pe-8 ...">pe-8</div>
  </div>
  <div dir="rtl">
    <div class="ps-8 ...">ps-8</div>
    <div class="pe-8 ...">pe-8</div>
  </div>
</div>
```


--------------------------------

### Control color inversion with invert utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/filter-invert.mdx

Use utilities like `invert` and `invert-20` to control the color inversion of an element.

```html
<!-- [!code classes:invert-0,invert-20,invert] -->
<img class="invert-0" src="/img/mountains.jpg" />
<img class="invert-20" src="/img/mountains.jpg" />
<img class="invert" src="/img/mountains.jpg" />
```


--------------------------------

### Setting perspective distance using perspective utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/perspective.mdx

Use utilities like perspective-normal and perspective-dramatic to control how close or far away the z-plane is from the screen.

```html
<!-- [!code classes:perspective-dramatic,perspective-normal] -->
<div class="size-20 perspective-dramatic ...">
  <div class="translate-z-12 rotate-x-0 bg-sky-300/75 ...">1</div>
  <div class="-translate-z-12 rotate-y-18 bg-sky-300/75 ...">2</div>
  <div class="translate-x-12 rotate-y-90 bg-sky-300/75 ...">3</div>
  <div class="-translate-x-12 -rotate-y-90 bg-sky-300/75 ...">4</div>
  <div class="-translate-y-12 rotate-x-90 bg-sky-300/75 ...">5</div>
  <div class="translate-y-12 -rotate-x-90 bg-sky-300/75 ...">6</div>
</div>

<div class="size-20 perspective-normal ...">
  <div class="translate-z-12 rotate-x-0 bg-sky-300/75 ...">1</div>
  <div class="-translate-z-12 rotate-y-18 bg-sky-300/75 ...">2</div>
  <div class="translate-x-12 rotate-y-90 bg-sky-300/75 ...">3</div>
  <div class="-translate-x-12 -rotate-y-90 bg-sky-300/75 ...">4</div>
  <div class="-translate-y-12 rotate-x-90 bg-sky-300/75 ...">5</div>
  <div class="translate-y-12 -rotate-x-90 bg-sky-300/75 ...">6</div>
</div>
```


--------------------------------

### Ordering items first or last

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/order.mdx

Use the `order-first` and `order-last` utilities to position specific flex and grid items at the beginning or end of the container.

```html
<!-- [!code classes:order-first,order-last] -->
<div class="flex justify-between ...">
  <div class="order-last ...">01</div>
  <div class="...">02</div>
  <div class="order-first ...">03</div>
</div>
```


--------------------------------

### Set percentage-based minimum height

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/min-height.mdx

Use min-h-full or min-h-<fraction> utilities like min-h-1/2 and min-h-2/5 to give an element a percentage-based minimum height.

```html
<!-- [!code classes:min-h-9/10,min-h-3/4,min-h-1/2,min-h-1/3,min-h-full] -->
<div class="min-h-full ...">min-h-full</div>
<div class="min-h-9/10 ...">min-h-9/10</div>
<div class="min-h-3/4 ...">min-h-3/4</div>
<div class="min-h-1/2 ...">min-h-1/2</div>
<div class="min-h-1/3 ...">min-h-1/3</div>
```


--------------------------------

### Setting logical inset properties based on text direction

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/top-right-bottom-left.mdx

Use inset-s-* or inset-e-* utilities to set inset-inline-start and inset-inline-end logical properties, automatically mapping to left or right sides according to text direction.

```html
<!-- [!code classes:inset-s-0] -->
<div dir="ltr">
  <div class="relative size-32 ...">
    <div class="absolute inset-s-0 top-0 size-14 ..."></div>
  </div>
  <div>
    <div dir="rtl">
      <div class="relative size-32 ...">
        <div class="absolute inset-s-0 top-0 size-14 ..."></div>
      </div>
      <div></div>
    </div>
  </div>
</div>
```


--------------------------------

### Setting a mask image using mask-[<value>]

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/mask-image.mdx

Use the mask-[<value>] syntax to apply an image as a mask to an element.

```html
<!-- [!code classes:mask-[url(/img/scribble.png)]] -->
<div class="mask-[url(/img/scribble.png)] bg-[url(/img/mountains.jpg)] ...">
  <!-- ... -->
</div>
```


--------------------------------

### Using negative values for top and left positioning

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/top-right-bottom-left.mdx

Prefix placement class names with a dash to convert top, right, bottom, or left offsets to negative values.

```html
<!-- [!code classes:-left-4,-top-4] -->
<div class="relative size-32 ...">
  <div class="absolute -top-4 -left-4 size-14 ..."></div>
</div>
```


--------------------------------

### Set an element's aspect ratio using aspect-<ratio>

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/aspect-ratio.mdx

Use aspect-<ratio> utilities like aspect-3/2 to give an element a specific aspect ratio.

```html
<!-- [!code classes:aspect-3/2] -->
<img class="aspect-3/2 object-cover ..." src="/img/villas.jpg" />
```


--------------------------------

### Build a scrollable schedule grid with sticky time headers

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/overflow.mdx

Constructs schedule grid rows with sticky left time indicators for multi-directional scroll containers.

```jsx
        <div className="sticky left-0 col-start-1 row-start-6 border-r border-gray-100 bg-white p-1.5 text-right text-xs font-medium text-gray-400 uppercase dark:border-gray-200/5 dark:bg-gray-800">
          9 AM
        </div>
        <div className="col-start-2 row-start-6 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-3 row-start-6 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-4 row-start-6 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-5 row-start-6 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-6 row-start-6 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-7 row-start-6 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-8 row-start-6 border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="sticky left-0 col-start-1 row-start-7 border-r border-gray-100 bg-white p-1.5 text-right text-xs font-medium text-gray-400 uppercase dark:border-gray-200/5 dark:bg-gray-800">
          10 AM
        </div>
        <div className="col-start-2 row-start-7 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-3 row-start-7 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-4 row-start-7 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-5 row-start-7 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-6 row-start-7 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-7 row-start-7 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-8 row-start-7 border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="sticky left-0 col-start-1 row-start-8 border-r border-gray-100 bg-white p-1.5 text-right text-xs font-medium text-gray-400 uppercase dark:border-gray-200/5 dark:bg-gray-800">
          11 AM
        </div>
        <div className="col-start-2 row-start-8 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-3 row-start-8 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-4 row-start-8 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-5 row-start-8 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-6 row-start-8 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-7 row-start-8 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-8 row-start-8 border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="sticky left-0 col-start-1 row-start-9 border-r border-gray-100 bg-white p-1.5 text-right text-xs font-medium text-gray-400 uppercase dark:border-gray-200/5 dark:bg-gray-800">
          12 PM
        </div>
        <div className="col-start-2 row-start-9 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-3 row-start-9 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-4 row-start-9 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-5 row-start-9 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-6 row-start-9 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-7 row-start-9 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-8 row-start-9 border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="sticky left-0 col-start-1 row-start-10 border-r border-gray-100 bg-white p-1.5 text-right text-xs font-medium text-gray-400 uppercase dark:border-gray-200/5 dark:bg-gray-800">
          1 PM
        </div>
        <div className="col-start-2 row-start-10 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-3 row-start-10 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-4 row-start-10 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-5 row-start-10 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-6 row-start-10 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-7 row-start-10 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
```


--------------------------------

### Translate on the x-axis with translate-x utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/translate.mdx

Use translate-x-<number> or translate-x-<fraction> utilities like translate-x-2, -translate-x-4, and translate-x-1/2 to translate an element horizontally.

```html
<!-- [!code classes:-translate-x-4,translate-x-2,translate-x-1/2] -->
<img class="-translate-x-4 ..." src="/img/mountains.jpg" />
<img class="translate-x-2 ..." src="/img/mountains.jpg" />
<img class="translate-x-1/2 ..." src="/img/mountains.jpg" />
```


--------------------------------

### Applying responsive column counts and gaps

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/columns.mdx

Use responsive variants like sm:columns-3 and sm:gap-8 to change the column count and gap size at specific breakpoints.

```html
<!-- [!code classes:sm:gap-8,sm:columns-3] -->
<div class="columns-2 gap-4 sm:columns-3 sm:gap-8 ...">
  <img class="aspect-3/2 ..." src="/img/mountains-1.jpg" />
  <img class="aspect-square ..." src="/img/mountains-2.jpg" />
  <img class="aspect-square ..." src="/img/mountains-3.jpg" />
  <!-- ... -->
</div>
```


--------------------------------

### Applying backdrop contrast filters

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/backdrop-filter-contrast.mdx

Use utilities like `backdrop-contrast-50` and `backdrop-contrast-200` to control an element's backdrop contrast.

```html
<!-- [!code classes:backdrop-contrast-50,backdrop-contrast-200] -->
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-contrast-50 ..."></div>
</div>
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-contrast-200 ..."></div>
</div>
```


--------------------------------

### Set block margin logical properties with mbs-* and mbe-*

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/margin.mdx

Use mbs-<number> and mbe-<number> utilities to set margin-block-start and margin-block-end according to the writing mode.

```html
<!-- [!code classes:mbs-8] -->
<div class="mbs-8 ...">mbs-8</div>
```


--------------------------------

### Setting a fixed maximum width using scale utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/max-width.mdx

Use max-w-<number> utilities like max-w-24 and max-w-64 to set an element to a fixed maximum width based on the spacing scale.

```html
<!-- [!code classes:max-w-96,max-w-80,max-w-64,max-w-48,max-w-40,max-w-32,max-w-24] -->
<div class="w-full max-w-96 ...">max-w-96</div>
<div class="w-full max-w-80 ...">max-w-80</div>
<div class="w-full max-w-64 ...">max-w-64</div>
<div class="w-full max-w-48 ...">max-w-48</div>
<div class="w-full max-w-40 ...">max-w-40</div>
<div class="w-full max-w-32 ...">max-w-32</div>
<div class="w-full max-w-24 ...">max-w-24</div>
```


--------------------------------

### Applying brightness filters to elements

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/filter-brightness.mdx

Use utilities like `brightness-50` and `brightness-100` to control an element's brightness.

```html
<!-- [!code classes:brightness-50,brightness-100,brightness-125,brightness-200] -->
<img class="brightness-50 ..." src="/img/mountains.jpg" />
<img class="brightness-100 ..." src="/img/mountains.jpg" />
<img class="brightness-125 ..." src="/img/mountains.jpg" />
<img class="brightness-200 ..." src="/img/mountains.jpg" />
```


--------------------------------

### Implement a subgrid using grid-rows-subgrid

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/grid-template-rows.mdx

Use the `grid-rows-subgrid` utility to adopt the row tracks defined by the item's parent container.

```html
<!-- [!code classes:grid-rows-subgrid] -->
<div class="grid grid-flow-col grid-rows-4 gap-4">
  <div>01</div>
  <!-- ... -->
  <div>05</div>
  <div class="row-span-3 grid grid-rows-subgrid gap-4">
    <div class="row-start-2">06</div>
  </div>
  <div>07</div>
  <!-- ... -->
  <div>10</div>
</div>
```


--------------------------------

### Aligning text using logical properties with text-end

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/text-align.mdx

Use the `text-start` and `text-end` utilities to map alignment to the left or right side based on text direction.

```html
<!-- [!code word:dir="rtl"] -->
<!-- [!code classes:text-end] -->
<div dir="rtl" lang="ar">
  <p class="text-end">فبدأت بالسير نحو الماء...</p>
</div>
```


--------------------------------

### Setting list item marker image using list-image-[<value>]

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/list-style-image.mdx

Use the list-image-[<value>] syntax to control the marker image for list items.

```html
<!-- [!code classes:list-image-[url(/img/checkmark.png)]] -->
<ul class="list-image-[url(/img/checkmark.png)]">
  <li>5 cups chopped Porcini mushrooms</li>
  <!-- ... -->
</ul>
```


--------------------------------

### Setting gradient stop positions

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/background-image.mdx

Use utilities like from-10%, via-30%, and to-90% to set more precise positions for the gradient color stops.

```html
<!-- [!code classes:from-10%,via-30%,to-90%] -->
<div class="bg-linear-to-r from-indigo-500 from-10% via-sky-500 via-30% to-emerald-500 to-90% ..."></div>
```


--------------------------------

### Setting a background image with arbitrary values

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/background-image.mdx

Use the bg-[<value>] syntax to set an arbitrary background image on an element.

```html
<!-- [!code classes:bg-[url(/img/mountains.jpg)]] -->
<div class="bg-[url(/img/mountains.jpg)] ..."></div>
```


--------------------------------

### Adding a linear gradient

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/background-image.mdx

Use utilities like bg-linear-to-r and bg-linear-<angle> combined with color stop utilities to add linear gradients.

```html
<!-- [!code classes:bg-linear-to-r,bg-linear-to-t,bg-linear-to-bl,bg-linear-65] -->
<div class="h-14 bg-linear-to-r from-cyan-500 to-blue-500"></div>
<div class="h-14 bg-linear-to-t from-sky-500 to-indigo-500"></div>
<div class="h-14 bg-linear-to-bl from-violet-500 to-fuchsia-500"></div>
<div class="h-14 bg-linear-65 from-purple-500 to-pink-500"></div>
```


--------------------------------

### Set minimum inline size using container scale

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/min-inline-size.mdx

Use utilities like min-inline-sm and min-inline-xl to set an element to a fixed minimum inline size based on the container scale.

```html
<!-- [!code classes:min-inline-lg,min-inline-md,min-inline-sm,min-inline-xs,min-inline-2xs,min-inline-3xs] -->
<div class="inline-40 ...">
  <div class="min-inline-lg ...">min-inline-lg</div>
  <div class="min-inline-md ...">min-inline-md</div>
  <div class="min-inline-sm ...">min-inline-sm</div>
  <div class="min-inline-xs ...">min-inline-xs</div>
  <div class="min-inline-2xs ...">min-inline-2xs</div>
  <div class="min-inline-3xs ...">min-inline-3xs</div>
</div>
```


--------------------------------

### Filling the container with mask-cover

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/mask-size.mdx

Use the mask-cover utility to scale the mask image until it fills the mask layer, cropping the image if needed.

```html
<!-- [!code classes:mask-cover] -->
<div class="mask-cover mask-[url(/img/scribble.png)] bg-[url(/img/mountains.jpg)] ..."></div>
```


--------------------------------

### Defining numerical tracking scale in @theme

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/letter-spacing.mdx

Customize your scale with numbered letter spacing tokens to enable negative tracking utilities.

```css
@theme {
  --tracking-1: 0em;
  --tracking-2: 0.025em;
  --tracking-3: 0.05em;
  --tracking-4: 0.1em;
}
```


--------------------------------

### Applying flex-basis conditionally with responsive variants

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/flex-basis.mdx

Prefix flex-basis utilities with responsive breakpoint modifiers such as md:basis-1/3 to apply sizes at specific screen widths.

```html
<!-- [!code classes:md:basis-1/3] -->
<div class="flex flex-row">
  <div class="basis-1/4 md:basis-1/3">01</div>
  <div class="basis-1/4 md:basis-1/3">02</div>
  <div class="basis-1/2 md:basis-1/3">03</div>
</div>
```


--------------------------------

### Setting flex item size using the spacing scale

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/flex-basis.mdx

Use basis-<number> utilities such as basis-64 and basis-128 to define the initial main size of flex items according to the spacing scale.

```html
<!-- [!code classes:basis-64,basis-128] -->
<div class="flex flex-row">
  <div class="basis-64">01</div>
  <div class="basis-64">02</div>
  <div class="basis-128">03</div>
</div>
```


--------------------------------

### Set background color using utility classes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/background-color.mdx

Use background color utilities like bg-blue-500, bg-cyan-500, and bg-pink-500 to set the background color of an element.

```html
<!-- [!code classes:bg-blue-500,bg-cyan-500,bg-pink-500] -->
<button class="bg-blue-500 ...">Button A</button>
<button class="bg-cyan-500 ...">Button B</button>
<button class="bg-pink-500 ...">Button C</button>
```


--------------------------------

### Setting minimum width using the container scale

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/min-width.mdx

Use container scale utilities such as min-w-sm and min-w-xl to set an element's minimum width based on container breakpoints.

```html
<!-- [!code classes:min-w-lg,min-w-md,min-w-sm,min-w-xs,min-w-2xs,min-w-3xs] -->
<div class="w-40 ...">
  <div class="min-w-lg ...">min-w-lg</div>
  <div class="min-w-md ...">min-w-md</div>
  <div class="min-w-sm ...">min-w-sm</div>
  <div class="min-w-xs ...">min-w-xs</div>
  <div class="min-w-2xs ...">min-w-2xs</div>
  <div class="min-w-3xs ...">min-w-3xs</div>
</div>
```


--------------------------------

### Set inline margin logical properties with ms-* and me-*

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/margin.mdx

Use ms-<number> and me-<number> utilities to set margin-inline-start and margin-inline-end based on text direction.

```html
<!-- [!code classes:ms-8,me-8] -->
<!-- [!code word:dir="ltr"] -->
<!-- [!code word:dir="rtl"] -->
<div>
  <div dir="ltr">
    <div class="ms-8 ...">ms-8</div>
    <div class="me-8 ...">me-8</div>
  </div>
  <div dir="rtl">
    <div class="ms-8 ...">ms-8</div>
    <div class="me-8 ...">me-8</div>
  </div>
</div>
```


--------------------------------

### Statically positioning elements with static

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/position.mdx

Use the static utility to position an element according to normal document flow. Offsets are ignored and the element does not serve as a position reference for absolutely positioned children.

```html
<!-- [!code classes:static] -->
<div class="static ...">
  <p>Static parent</p>
  <div class="absolute bottom-0 left-0 ...">
    <p>Absolute child</p>
  </div>
</div>
```


--------------------------------

### Set outline style with utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/outline-style.mdx

Use utilities like outline-solid, outline-dashed, outline-dotted, and outline-double to set the outline style of an element.

```html
<!-- [!code classes:outline-solid,outline-dashed,outline-dotted,outline-double] -->
<button class="outline-2 outline-offset-2 outline-solid ...">Button A</button>
<button class="outline-2 outline-offset-2 outline-dashed ...">Button B</button>
<button class="outline-2 outline-offset-2 outline-dotted ...">Button C</button>
<button class="outline-3 outline-offset-2 outline-double ...">Button D</button>
```


--------------------------------

### Set percentage-based maximum inline size

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/max-inline-size.mdx

Use max-inline-full or max-inline-<fraction> utilities such as max-inline-1/2 and max-inline-3/4 to apply a percentage-based maximum inline size to an element.

```html
<!-- [!code classes:max-inline-3/4,max-inline-9/10,max-inline-1/2,max-inline-1/3] -->
<div class="inline-full max-inline-9/10 ...">max-inline-9/10</div>
<div class="inline-full max-inline-3/4 ...">max-inline-3/4</div>
<div class="inline-full max-inline-1/2 ...">max-inline-1/2</div>
<div class="inline-full max-inline-1/3 ...">max-inline-1/3</div>
```


--------------------------------

### Allow flex items to shrink but not grow

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/flex.mdx

Use flex-initial to permit a flex item to shrink but prevent it from growing, taking its initial size into account.

```html
<!-- [!code word:flex-initial] -->
<div class="flex">
  <div class="w-14 flex-none ...">01</div>
  <div class="w-64 flex-initial ...">02</div>
  <div class="w-32 flex-initial ...">03</div>
</div>
```


--------------------------------

### Rotate elements in 3D space with rotate-x, rotate-y, and rotate-z

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/rotate.mdx

Use rotate-x-<number>, rotate-y-<number>, and rotate-z-<number> utilities together to rotate an element in 3D space.

```html
<!-- [!code classes:rotate-y-25,rotate-z-30,rotate-x-15,-rotate-y-30,rotate-x-50 rotate-z-45] -->
<img class="rotate-x-50 rotate-z-45 ..." src="/img/mountains.jpg" />
<img class="rotate-x-15 -rotate-y-30 ..." src="/img/mountains.jpg" />
<img class="rotate-y-25 rotate-z-30 ..." src="/img/mountains.jpg" />
```


--------------------------------

### Using a thin scrollbar with scrollbar-thin

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scrollbar-width.mdx

Use the scrollbar-thin utility to render a thinner scrollbar for scrollable elements.

```html
<!-- [!code classes:scrollbar-thin] -->
<div class="scrollbar-thin overflow-auto ...">
  <!-- ... -->
</div>
```


--------------------------------

### Create a new stacking context using isolate

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/isolation.mdx

Use the isolate utility to explicitly establish a new stacking context on an element.

```html
<!-- [!code classes:isolate] -->
<div class="isolate ...">
  <!-- ... -->
</div>
```


--------------------------------

### Using auto select behavior with select-auto

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/user-select.mdx

Use the select-auto utility to apply the default browser behavior for text selection.

```html
<!-- [!code classes:select-auto] -->
<div class="select-auto ...">The quick brown fox jumps over the lazy dog.</div>
```


--------------------------------

### Set fixed minimum height using spacing scale utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/min-height.mdx

Use min-h-<number> utilities like min-h-24 and min-h-64 to set an element to a fixed minimum height based on the spacing scale.

```html
<!-- [!code classes:min-h-80,min-h-64,min-h-48,min-h-40,min-h-32,min-h-24,min-h-full] -->
<div class="h-20 ...">
  <div class="min-h-80 ...">min-h-80</div>
  <div class="min-h-64 ...">min-h-64</div>
  <div class="min-h-48 ...">min-h-48</div>
  <div class="min-h-40 ...">min-h-40</div>
  <div class="min-h-32 ...">min-h-32</div>
  <div class="min-h-24 ...">min-h-24</div>
</div>
```


--------------------------------

### Using original size with object-none

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/object-fit.mdx

Use the object-none utility to display an element's content at its original size ignoring the container size.

```html
<!-- [!code classes:object-none] -->
<img class="h-48 w-96 object-none ..." src="/img/mountains.jpg" />
```


--------------------------------

### Making elements visible with visible

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/visibility.mdx

Use the `visible` utility to render an element visible, primarily useful for undoing the `invisible` utility at specific breakpoints.

```html
<!-- [!code classes:visible] -->
<div class="grid grid-cols-3 gap-4">
  <div>01</div>
  <div class="visible ...">02</div>
  <div>03</div>
</div>
```


--------------------------------

### Specifying grid columns with grid-cols-<number>

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/grid-template-columns.mdx

Use grid-cols-<number> utilities like grid-cols-2 and grid-cols-4 to create grids with n equally sized columns.

```html
<!-- [!code classes:grid-cols-4] -->
<div class="grid grid-cols-4 gap-4">
  <div>01</div>
  <!-- ... -->
  <div>09</div>
</div>
```


--------------------------------

### Apply padding to individual sides using directional utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/padding.mdx

Sets padding on a single side using `pt-*`, `pr-*`, `pb-*`, or `pl-*` utilities.

```html
<!-- [!code classes:pt-6,pr-4,pb-8,pl-2] -->
<div class="pt-6 ...">pt-6</div>
<div class="pr-4 ...">pr-4</div>
<div class="pb-8 ...">pb-8</div>
<div class="pl-2 ...">pl-2</div>
```


--------------------------------

### Set maximum height using percentage utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/max-height.mdx

Use max-h-full or fractional utilities like max-h-1/2 and max-h-3/4 to constrain an element's maximum height to a percentage of its parent.

```html
<!-- [!code classes:max-h-9/10,max-h-3/4,max-h-1/2,max-h-1/4,max-h-full] -->
<div class="h-96 ...">
  <div class="h-full max-h-9/10 ...">max-h-9/10</div>
  <div class="h-full max-h-3/4 ...">max-h-3/4</div>
  <div class="h-full max-h-1/2 ...">max-h-1/2</div>
  <div class="h-full max-h-1/4 ...">max-h-1/4</div>
  <div class="h-full max-h-full ...">max-h-full</div>
</div>
```


--------------------------------

### Set scroll-padding-block-start with scroll-pbs-6

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scroll-padding.mdx

Applies scroll-padding-block-start using logical properties that adapt to the writing mode.

```html
<!-- [!code classes:scroll-pbs-6] -->
<div class="snap-y scroll-pbs-6 ...">
  <!-- ... -->
</div>
```


--------------------------------

### Set radial gradient mask size using mask-radial utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/mask-image.mdx

Use utilities like mask-radial-closest-side, mask-radial-closest-corner, mask-radial-farthest-side, and mask-radial-farthest-corner to configure the size of radial gradient masks.

```html
<!-- [!code classes:mask-radial-farthest-corner,mask-radial-farthest-side,mask-radial-closest-corner,mask-radial-closest-side] -->
<div class="mask-radial-closest-side mask-radial-from-100% mask-radial-at-[30%_30%] bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-radial-closest-corner mask-radial-from-100% mask-radial-at-[30%_30%] bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-radial-farthest-side mask-radial-from-100% mask-radial-at-[30%_30%] bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-radial-farthest-corner mask-radial-from-100% mask-radial-at-[30%_30%] bg-[url(/img/mountains.jpg)] ..."></div>
```


--------------------------------

### Creating pill buttons with rounded-full

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/border-radius.mdx

Use the rounded-full utility to create rounded pill buttons.

```html
<!-- [!code classes:rounded-full] -->
<button class="rounded-full ...">Save Changes</button>
```


--------------------------------

### Scale elements with scale-<number> utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scale.mdx

Use scale-<number> utilities like scale-75 and scale-150 to scale an element by a percentage of its original size.

```html
<!-- [!code classes:scale-75,scale-100,scale-125] -->
<img class="scale-75 ..." src="/img/mountains.jpg" />
<img class="scale-100 ..." src="/img/mountains.jpg" />
<img class="scale-125 ..." src="/img/mountains.jpg" />
```


--------------------------------

### Applying grayscale antialiasing with antialiased

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/font-smoothing.mdx

Use the antialiased utility to render text using grayscale antialiasing.

```html
<!-- [!code classes:antialiased] -->
<p class="antialiased ...">The quick brown fox ...</p>
```


--------------------------------

### Setting letter spacing using tracking utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/letter-spacing.mdx

Use utilities like tracking-tight, tracking-normal, and tracking-wide to set the letter spacing of text elements.

```html
<!-- [!code classes:tracking-tight,tracking-normal,tracking-wide] -->
<p class="tracking-tight ...">The quick brown fox ...</p>
<p class="tracking-normal ...">The quick brown fox ...</p>
<p class="tracking-wide ...">The quick brown fox ...</p>
```


--------------------------------

### Using logical properties for border radius

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/border-radius.mdx

Set border radius using logical property utilities like rounded-s-lg to map corners dynamically based on LTR or RTL text direction.

```html
<!-- [!code classes:rounded-s-lg] -->
<!-- [!code word:dir="ltr"] -->
<!-- [!code word:dir="rtl"] -->
<div dir="ltr">
  <div class="rounded-s-lg ..."></div>
</div>

<div dir="rtl">
  <div class="rounded-s-lg ..."></div>
</div>
```


--------------------------------

### Applying subpixel antialiasing with subpixel-antialiased

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/font-smoothing.mdx

Use the subpixel-antialiased utility to render text using subpixel antialiasing.

```html
<!-- [!code classes:subpixel-antialiased] -->
<p class="subpixel-antialiased ...">The quick brown fox ...</p>
```


--------------------------------

### Set maximum width using container scale

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/max-width.mdx

Use utilities like max-w-sm or max-w-md to constrain an element to a fixed maximum width based on the container scale.

```html
<!-- [!code classes:max-w-md] -->
<div class="max-w-md ...">
  <!-- ... -->
</div>
```


--------------------------------

### Setting fixed minimum width with spacing scale

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/min-width.mdx

Use min-w-<number> utilities like min-w-24 and min-w-64 to set an element to a fixed minimum width based on the spacing scale.

```html
<!-- [!code classes:min-w-96,min-w-80,min-w-64,min-w-48,min-w-40,min-w-32,min-w-24,min-w-full] -->
<div class="w-20 ...">
  <div class="min-w-80 ...">min-w-80</div>
  <div class="min-w-64 ...">min-w-64</div>
  <div class="min-w-48 ...">min-w-48</div>
  <div class="min-w-40 ...">min-w-40</div>
  <div class="min-w-32 ...">min-w-32</div>
  <div class="min-w-24 ...">min-w-24</div>
</div>
```


--------------------------------

### Using stacked fractions

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/font-variant-numeric.mdx

Use the stacked-fractions utility to replace numbers separated by a slash with common stacked fractions in fonts that support them.

```html
<!-- [!code classes:stacked-fractions] -->
<p class="stacked-fractions ...">1/2 3/4 5/6</p>
```


--------------------------------

### Setting gradient color stops

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/background-image.mdx

Use utilities like from-indigo-500, via-purple-500, and to-pink-500 to set the colors of the gradient stops.

```html
<!-- [!code classes:from-indigo-500,via-purple-500,to-pink-500] -->
<div class="bg-linear-to-r from-indigo-500 via-purple-500 to-pink-500 ..."></div>
```


--------------------------------

### Set scroll padding using logical properties

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scroll-padding.mdx

Use logical scroll padding utilities such as `scroll-ps-*` to automatically adjust scroll offset for left-to-right and right-to-left document directions.

```html
<!-- [!code word:dir="ltr"] -->
<!-- [!code word:dir="rtl"] -->
<!-- [!code classes:scroll-ps-6] -->
<div dir="ltr">
  <div class="snap-x scroll-ps-6 ...">
    <!-- ... -->
  </div>
</div>

<div dir="rtl">
  <div class="snap-x scroll-ps-6 ...">
    <!-- ... -->
  </div>
</div>
```


--------------------------------

### Set inline size using container scale

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/inline-size.mdx

Use utilities such as inline-sm, inline-md, and inline-xl to set an element to a fixed inline size based on the container scale.

```html
<!-- [!code classes:inline-xl,inline-lg,inline-md,inline-sm,inline-xs,inline-2xs,inline-3xs] -->
<div class="inline-xl ...">inline-xl</div>
<div class="inline-lg ...">inline-lg</div>
<div class="inline-md ...">inline-md</div>
<div class="inline-sm ...">inline-sm</div>
<div class="inline-xs ...">inline-xs</div>
<div class="inline-2xs ...">inline-2xs</div>
<div class="inline-3xs ...">inline-3xs</div>
```


--------------------------------

### Setting the radial position with mask-radial-at utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/mask-image.mdx

Use mask-radial-at-* utilities such as mask-radial-at-center or mask-radial-at-bottom-right to position the origin of a radial gradient mask. This configures the gradient center rather than the overall mask image position.

```html
<!-- [!code classes:mask-radial-at-top-left,mask-radial-at-top,mask-radial-at-top-right,mask-radial-at-left,mask-radial-at-center,mask-radial-at-right,mask-radial-at-bottom,mask-radial-at-bottom-left,mask-radial-at-bottom-right] -->
<div class="mask-radial-at-top-left mask-radial-from-100% bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-radial-at-top mask-radial-from-100% bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-radial-at-top-right mask-radial-from-100% bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-radial-at-left mask-radial-from-100% bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-radial-at-center mask-radial-from-100% bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-radial-at-right mask-radial-from-100% bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-radial-at-bottom-left mask-radial-from-100% bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-radial-at-bottom mask-radial-from-100% bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-radial-at-bottom-right mask-radial-from-100% bg-[url(/img/mountains.jpg)] ..."></div>
```


--------------------------------

### Add a spin animation with animate-spin

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/animation.mdx

Use the `animate-spin` utility to add a linear spin animation to elements like loading indicators.

```html
<!-- [!code classes:animate-spin] -->
<button type="button" class="bg-indigo-500 ..." disabled>
  <svg class="mr-3 size-5 animate-spin ..." viewBox="0 0 24 24">
    <!-- ... -->
  </svg>
  Processing…
</button>
```


--------------------------------

### Center content with place-content-center

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/place-content.mdx

Packs items in the center of both the inline and block axes in a grid container.

```html
<!-- [!code classes:place-content-center] -->
<div class="grid h-48 grid-cols-2 place-content-center gap-4 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
</div>
```


--------------------------------

### Distribute items evenly using place-content-evenly

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/place-content.mdx

Use place-content-evenly to distribute grid items such that they are evenly spaced on the inline and block axes.

```html
<!-- [!code classes:place-content-evenly] -->
<div class="grid h-48 grid-cols-2 place-content-evenly gap-4 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
</div>
```


--------------------------------

### Allow flex items to grow and shrink based on initial size

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/flex.mdx

Use flex-auto to allow a flex item to both grow and shrink while respecting its initial size.

```html
<!-- [!code word:flex-auto] -->
<div class="flex ...">
  <div class="w-14 flex-none ...">01</div>
  <div class="w-64 flex-auto ...">02</div>
  <div class="w-32 flex-auto ...">03</div>
</div>
```


--------------------------------

### Specify grid rows with grid-rows-<number>

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/grid-template-rows.mdx

Use `grid-rows-<number>` utilities such as `grid-rows-4` to create grids with equally sized rows.

```html
<!-- [!code classes:grid-rows-4] -->
<div class="grid grid-flow-col grid-rows-4 gap-4">
  <div>01</div>
  <!-- ... -->
  <div>09</div>
</div>
```


--------------------------------

### Reset alignment to default using content-normal

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/align-content.mdx

Use `content-normal` to pack content items in their default position as if no `align-content` value was set.

```html
<!-- [!code classes:content-normal] -->
<div class="grid h-56 grid-cols-3 content-normal gap-4 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
  <div>05</div>
</div>
```


--------------------------------

### Displaying default size with mask-auto

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/mask-size.mdx

Use the mask-auto utility to display the mask image at its default size.

```html
<!-- [!code classes:mask-auto] -->
<div class="mask-auto mask-[url(/img/scribble.png)] bg-[url(/img/mountains.jpg)] ..."></div>
```


--------------------------------

### Distribute items with space around using place-content-around

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/place-content.mdx

Use place-content-around to distribute grid items along the inline and block axes so that there is an equal amount of space around each row and column on each axis respectively.

```html
<!-- [!code classes:place-content-around] -->
<div class="grid h-48 grid-cols-2 place-content-around gap-4 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
</div>
```


--------------------------------

### Center and pad a container element

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/max-width.mdx

Combine the container utility with mx-auto and horizontal padding utilities (px-<number>) because container does not center automatically or include padding.

```html
<!-- [!code classes:mx-auto,px-4] -->
<div class="container mx-auto px-4">
  <!-- ... -->
</div>
```


--------------------------------

### Match viewport block size using block-screen

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/block-size.mdx

Use `block-screen` to make an element span the entire block size of the viewport.

```html
<!-- [!code classes:block-screen] -->
<div class="block-screen">
  <!-- ... -->
</div>
```


--------------------------------

### Break words at any character using break-all

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/word-break.mdx

Use the break-all utility to add line breaks whenever necessary, without trying to preserve whole words.

```html
<!-- [!code classes:break-all] -->
<p class="break-all">The longest word in any of the major...</p>
```


--------------------------------

### Translate on the z-axis using translate-z utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/translate.mdx

Use translate-z-<number> utilities such as -translate-z-8 or translate-z-2 to translate an element on the z-axis. The transform-3d utility must be applied to the parent element.

```html
<!-- [!code classes:transform-3d,-translate-z-8,translate-z-2,translate-z-1/2] -->
<div class="transform-3d">
  <img class="-translate-z-8 rotate-x-50 rotate-z-45 ..." src="/img/mountains.jpg" />
  <img class="translate-z-2 rotate-x-50 rotate-z-45 ..." src="/img/mountains.jpg" />
  <img class="translate-z-1/2 rotate-x-50 rotate-z-45 ..." src="/img/mountains.jpg" />
</div>
```


--------------------------------

### Control implicit grid row sizes with auto-rows-max

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/grid-auto-rows.mdx

Use utilities like `auto-rows-min` and `auto-rows-max` to control the size of implicitly-created grid rows.

```html
<!-- [!code classes:auto-rows-max] -->
<div class="grid grid-flow-row auto-rows-max">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```


--------------------------------

### Match viewport width using w-screen

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/width.mdx

Spans an element across the entire width of the viewport using `w-screen`. You can also target large, small, or dynamic viewports with `w-lvw`, `w-svw`, and `w-dvw`.

```html
<!-- [!code classes:w-screen] -->
<div class="w-screen">
  <!-- ... -->
</div>
```


--------------------------------

### Distribute rows with space around using content-around

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/align-content.mdx

Use `content-around` to distribute rows in a container such that there is an equal amount of space around each line.

```html
<!-- [!code classes:content-around] -->
<div class="grid h-56 grid-cols-3 content-around gap-4 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
  <div>05</div>
</div>
```


--------------------------------

### Set list marker styles with list-disc, list-decimal, and list-none

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/list-style-type.mdx

Use list-disc, list-decimal, or list-none to control the marker style of unordered and ordered lists.

```html
<!-- [!code classes:list-disc] -->
<ul class="list-disc">
  <li>Now this is a story all about how, my life got flipped-turned upside down</li>
  <!-- ... -->
</ul>

<!-- [!code classes:list-decimal] -->
<ol class="list-decimal">
  <li>Now this is a story all about how, my life got flipped-turned upside down</li>
  <!-- ... -->
</ol>

<!-- [!code classes:list-none] -->
<ul class="list-none">
  <li>Now this is a story all about how, my life got flipped-turned upside down</li>
  <!-- ... -->
</ul>
```


--------------------------------

### Setting text decoration thickness with decoration-<number>

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/text-decoration-thickness.mdx

Apply decoration-<number> utilities like decoration-1, decoration-2, and decoration-4 to control the stroke thickness of text decoration lines.

```html
<!-- [!code classes:decoration-1] -->
<p class="underline decoration-1">The quick brown fox...</p>
<!-- [!code classes:decoration-2] -->
<p class="underline decoration-2">The quick brown fox...</p>
<!-- [!code classes:decoration-4] -->
<p class="underline decoration-4">The quick brown fox...</p>
```


--------------------------------

### Match the viewport inline size

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/inline-size.mdx

Use the inline-screen utility to make an element span the entire inline size of the viewport.

```html
<!-- [!code classes:inline-screen] -->
<div class="inline-screen">
  <!-- ... -->
</div>
```


--------------------------------

### Supporting reduced motion with transition duration

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/transition-duration.mdx

Conditionally apply transition durations using the motion-reduce variant when a user has specified a preference for reduced motion.

```html
<!-- [!code classes:motion-reduce:duration-0] -->
<button type="button" class="duration-300 motion-reduce:duration-0 ...">
  <!-- ... -->
</button>
```


--------------------------------

### Sizing columns automatically with table-auto

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/table-layout.mdx

Use the `table-auto` utility to automatically size table columns to fit the contents of its cells.

```html
<!-- [!code classes:table-auto] -->
<table class="table-auto">
  <thead>
    <tr>
      <th>Song</th>
      <th>Artist</th>
      <th>Year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>The Sliding Mr. Bones (Next Stop, Pottersville)</td>
      <td>Malcolm Lockyer</td>
      <td>1961</td>
    </tr>
    <tr>
      <td>Witchy Woman</td>
      <td>The Eagles</td>
      <td>1972</td>
    </tr>
    <tr>
      <td>Shining Star</td>
      <td>Earth, Wind, and Fire</td>
      <td>1975</td>
    </tr>
  </tbody>
</table>
```


--------------------------------

### Stretch items along grid areas using place-items-stretch

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/place-items.mdx

Use `place-items-stretch` to stretch items along their grid areas on both axes.

```html
<!-- [!code classes:place-items-stretch] -->
<div class="grid h-56 grid-cols-3 place-items-stretch gap-4 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
  <div>05</div>
  <div>06</div>
</div>
```


--------------------------------

### Setting text indentation using indent-8

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/text-indent.mdx

Use indent-<number> utilities such as indent-8 to set the amount of empty space shown before text in a block.

```html
<!-- [!code classes:indent-8] -->
<p class="indent-8">So I started to walk into the water...</p>
```


--------------------------------

### Snapping elements to the center using snap-center

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scroll-snap-align.mdx

Use the `snap-center` utility to snap an element to its center when being scrolled inside a snap container.

```html
<!-- [!code classes:snap-x,snap-center] -->
<div class="snap-x ...">
  <div class="snap-center ...">
    <img src="/img/vacation-01.jpg" />
  </div>
  <div class="snap-center ...">
    <img src="/img/vacation-02.jpg" />
  </div>
  <div class="snap-center ...">
    <img src="/img/vacation-03.jpg" />
  </div>
  <div class="snap-center ...">
    <img src="/img/vacation-04.jpg" />
  </div>
  <div class="snap-center ...">
    <img src="/img/vacation-05.jpg" />
  </div>
  <div class="snap-center ...">
    <img src="/img/vacation-06.jpg" />
  </div>
</div>
```


--------------------------------

### Set outline width with outline utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/outline-width.mdx

Use outline or outline-<number> utilities such as outline-2 and outline-4 to set the width of an element's outline.

```html
<!-- [!code classes:outline,outline-2,outline-4] -->
<button class="outline outline-offset-2 ...">Button A</button>
<button class="outline-2 outline-offset-2 ...">Button B</button>
<button class="outline-4 outline-offset-2 ...">Button C</button>
```


--------------------------------

### Set maximum block size using spacing scale utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/max-block-size.mdx

Use max-block-<number> utilities such as max-block-80 or max-block-32 to constrain an element's maximum block size based on the configured spacing scale.

```html
<!-- [!code classes:max-block-80,max-block-64,max-block-48,max-block-40,max-block-32,max-block-24] -->
<div class="block-96 ...">
  <div class="block-full max-block-80 ...">max-block-80</div>
  <div class="block-full max-block-64 ...">max-block-64</div>
  <div class="block-full max-block-48 ...">max-block-48</div>
  <div class="block-full max-block-40 ...">max-block-40</div>
  <div class="block-full max-block-32 ...">max-block-32</div>
</div>
```


--------------------------------

### Controlling the easing curve of an element's transition

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/transition-timing-function.mdx

Use utilities like ease-in, ease-out, and ease-in-out to control the easing curve of an element's transition.

```html
<!-- [!code classes:ease-in,ease-out,ease-in-out] -->
<button class="duration-300 ease-in ...">Button A</button>
<button class="duration-300 ease-out ...">Button B</button>
<button class="duration-300 ease-in-out ...">Button C</button>
```


--------------------------------

### Using backface-hidden and backface-visible utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/backface-visibility.mdx

Applies backface-hidden or backface-visible to show or hide the back face of rotated 3D elements.

```html
<!-- [!code classes:backface-hidden,backface-visible] -->
<div class="size-20 ...">
  <div class="translate-z-12 rotate-x-0 bg-sky-300/75 backface-hidden ...">1</div>
  <div class="-translate-z-12 rotate-y-18 bg-sky-300/75 backface-hidden ...">2</div>
  <div class="translate-x-12 rotate-y-90 bg-sky-300/75 backface-hidden ...">3</div>
  <div class="-translate-x-12 -rotate-y-90 bg-sky-300/75 backface-hidden ...">4</div>
  <div class="-translate-y-12 rotate-x-90 bg-sky-300/75 backface-hidden ...">5</div>
  <div class="translate-y-12 -rotate-x-90 bg-sky-300/75 backface-hidden ...">6</div>
</div>

<div class="size-20 ...">
  <div class="translate-z-12 rotate-x-0 bg-sky-300/75 backface-visible ...">1</div>
  <div class="-translate-z-12 rotate-y-18 bg-sky-300/75 backface-visible ...">2</div>
  <div class="translate-x-12 rotate-y-90 bg-sky-300/75 backface-visible ...">3</div>
  <div class="-translate-x-12 -rotate-y-90 bg-sky-300/75 backface-visible ...">4</div>
  <div class="-translate-y-12 rotate-x-90 bg-sky-300/75 backface-visible ...">5</div>
  <div class="translate-y-12 -rotate-x-90 bg-sky-300/75 backface-visible ...">6</div>
</div>
```


--------------------------------

### End content with place-content-end

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/place-content.mdx

Packs items against the end of both the inline and block axes in a grid container.

```html
<!-- [!code classes:place-content-end] -->
<div class="grid h-48 grid-cols-2 place-content-end gap-4 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
</div>
```


--------------------------------

### Setting element mix blend mode

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/mix-blend-mode.mdx

Use utilities like mix-blend-multiply to blend element content and background with other content in the same stacking context.

```html
<!-- [!code classes:mix-blend-multiply] -->
<div class="flex justify-center -space-x-14">
  <div class="bg-blue-500 mix-blend-multiply ..."></div>
  <div class="bg-pink-500 mix-blend-multiply ..."></div>
</div>
```


--------------------------------

### Configure custom font size with line-height, letter-spacing, and font-weight in @theme

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/font-size.mdx

Sets a custom font size variable along with default line-height, letter-spacing, and font-weight values inside the @theme directive.

```css
@theme {
  --text-tiny: 0.625rem;
  --text-tiny--line-height: 1.5rem; /* [!code highlight] */
  --text-tiny--letter-spacing: 0.125rem; /* [!code highlight] */
  --text-tiny--font-weight: 500; /* [!code highlight] */
}
```


--------------------------------

### Set background origin using bg-origin-*

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/background-origin.mdx

Use `bg-origin-border`, `bg-origin-padding`, and `bg-origin-content` to control where an element's background is rendered relative to its borders, padding, or content box.

```html
<!-- [!code classes:bg-origin-border,bg-origin-padding,bg-origin-content] -->
<div class="border-4 bg-[url(/img/mountains.jpg)] bg-origin-border p-3 ..."></div>
<div class="border-4 bg-[url(/img/mountains.jpg)] bg-origin-padding p-3 ..."></div>
<div class="border-4 bg-[url(/img/mountains.jpg)] bg-origin-content p-3 ..."></div>
```


--------------------------------

### Apply vertical padding using py-<number>

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/padding.mdx

Sets padding on both the top and bottom sides of an element simultaneously.

```html
<!-- [!code classes:py-8] -->
<div class="py-8 ...">py-8</div>
```


--------------------------------

### Adding a conic gradient

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/background-image.mdx

Use bg-conic and bg-conic-<angle> utilities with color stop utilities to add conic gradients to an element.

```html
<!-- [!code classes:bg-conic-180,bg-conic/decreasing,bg-conic] -->
<div class="size-24 rounded-full bg-conic from-blue-600 to-sky-400 to-50%"></div>
<div class="size-24 rounded-full bg-conic-180 from-indigo-600 via-indigo-50 to-indigo-600"></div>
<div class="size-24 rounded-full bg-conic/decreasing from-violet-700 via-lime-300 to-violet-700"></div>
```


--------------------------------

### Enable horizontal scrolling with overflow-x-scroll

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/overflow.mdx

Use the `overflow-x-scroll` utility to allow horizontal scrolling and always show scrollbars unless always-visible scrollbars are disabled by the operating system.

```html
<!-- [!code classes:overflow-x-scroll] -->
<div class="overflow-x-scroll ...">
  <!-- ... -->
</div>
```


--------------------------------

### Applying backdrop sepia filters to an element

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/backdrop-filter-sepia.mdx

Use utilities like backdrop-sepia and backdrop-sepia-50 to control the sepia effect applied to an element's backdrop.

```html
<!-- [!code classes:backdrop-sepia-0,backdrop-sepia-50,backdrop-sepia] -->
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-sepia-0 ..."></div>
</div>
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-sepia-50 ..."></div>
</div>
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-sepia ..."></div>
</div>
```


--------------------------------

### Use default gutter behavior with scrollbar-gutter-auto

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scrollbar-gutter.mdx

Use the `scrollbar-gutter-auto` utility to only reserve gutter space when the browser would normally show a scrollbar.

```html
<!-- [!code classes:scrollbar-gutter-auto] -->
<div class="scrollbar-gutter-auto overflow-auto ...">
  <!-- ... -->
</div>
```


--------------------------------

### Set fixed column widths using table-fixed

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/table-layout.mdx

Use `table-fixed` to ignore table cell content and apply fixed widths across columns. Widths defined in the first row dictate column widths for the entire table.

```html
<!-- [!code classes:table-fixed] -->
<table class="table-fixed">
  <thead>
    <tr>
      <th>Song</th>
      <th>Artist</th>
      <th>Year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>The Sliding Mr. Bones (Next Stop, Pottersville)</td>
      <td>Malcolm Lockyer</td>
      <td>1961</td>
    </tr>
    <tr>
      <td>Witchy Woman</td>
      <td>The Eagles</td>
      <td>1972</td>
    </tr>
    <tr>
      <td>Shining Star</td>
      <td>Earth, Wind, and Fire</td>
      <td>1975</td>
    </tr>
  </tbody>
</table>
```


--------------------------------

### Configure multi-directional scrolling grid with sticky headers in JSX

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/overflow.mdx

Use sticky positioning and coordinate classes (`top-0`, `left-0`) to keep date and time headers fixed while scrolling in all directions across a grid.

```jsx
        <div className="sticky top-0 z-10 col-start-6 row-start-1 border-b border-gray-100 bg-white bg-clip-padding py-2 text-center text-sm font-medium text-gray-900 dark:border-black/10 dark:bg-linear-to-b dark:from-gray-600 dark:to-gray-700 dark:text-gray-200">
          Thu
        </div>
        <div className="sticky top-0 z-10 col-start-7 row-start-1 border-b border-gray-100 bg-white bg-clip-padding py-2 text-center text-sm font-medium text-gray-900 dark:border-black/10 dark:bg-linear-to-b dark:from-gray-600 dark:to-gray-700 dark:text-gray-200">
          Fri
        </div>
        <div className="sticky top-0 z-10 col-start-8 row-start-1 border-b border-gray-100 bg-white bg-clip-padding py-2 text-center text-sm font-medium text-gray-900 dark:border-black/10 dark:bg-linear-to-b dark:from-gray-600 dark:to-gray-700 dark:text-gray-200">
          Sat
        </div>
        <div className="sticky left-0 col-start-1 row-start-2 border-r border-gray-100 bg-white p-1.5 text-right text-xs font-medium text-gray-400 uppercase dark:border-gray-200/5 dark:bg-gray-800">
          5 AM
        </div>
        <div className="col-start-2 row-start-2 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-3 row-start-2 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-4 row-start-2 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-5 row-start-2 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-6 row-start-2 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-7 row-start-2 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-8 row-start-2 border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="sticky left-0 col-start-1 row-start-3 border-r border-gray-100 bg-white p-1.5 text-right text-xs font-medium text-gray-400 uppercase dark:border-gray-200/5 dark:bg-gray-800">
          6 AM
        </div>
        <div className="col-start-2 row-start-3 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-3 row-start-3 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-4 row-start-3 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-5 row-start-3 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-6 row-start-3 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-7 row-start-3 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-8 row-start-3 border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="sticky left-0 col-start-1 row-start-4 border-r border-gray-100 bg-white p-1.5 text-right text-xs font-medium text-gray-400 uppercase dark:border-gray-200/5 dark:bg-gray-800">
          7 AM
        </div>
        <div className="col-start-2 row-start-4 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-3 row-start-4 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-4 row-start-4 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-5 row-start-4 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-6 row-start-4 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-7 row-start-4 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-8 row-start-4 border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="sticky left-0 col-start-1 row-start-5 border-r border-gray-100 bg-white p-1.5 text-right text-xs font-medium text-gray-400 uppercase dark:border-gray-200/5 dark:bg-gray-800">
          8 AM
        </div>
        <div className="col-start-2 row-start-5 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-3 row-start-5 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-4 row-start-5 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-5 row-start-5 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-6 row-start-5 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-7 row-start-5 border-r border-b border-gray-100 dark:border-gray-200/5"></div>
        <div className="col-start-8 row-start-5 border-b border-gray-100 dark:border-gray-200/5"></div>
```


--------------------------------

### Controlling touchscreen panning and scrolling

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/touch-action.mdx

Use utilities like touch-auto, touch-none, touch-pan-x, and touch-pan-y to configure how an element responds to scrolling and panning on touchscreens.

```html
<!-- [!code classes:overflow-auto,touch-auto,touch-none,touch-pan-x,touch-pan-y] -->
<div class="h-48 w-full touch-auto overflow-auto ...">
  <img class="h-auto w-[150%] max-w-none" src="..." />
</div>
<div class="h-48 w-full touch-none overflow-auto ...">
  <img class="h-auto w-[150%] max-w-none" src="..." />
</div>
<div class="h-48 w-full touch-pan-x overflow-auto ...">
  <img class="h-auto w-[150%] max-w-none" src="..." />
</div>
<div class="h-48 w-full touch-pan-y overflow-auto ...">
  <img class="h-auto w-[150%] max-w-none" src="..." />
</div>
```


--------------------------------

### Resizing to cover with object-cover

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/object-fit.mdx

Use the object-cover utility to resize an element's content to cover its container.

```html
<!-- [!code classes:object-cover] -->
<img class="h-48 w-96 object-cover ..." src="/img/mountains.jpg" />
```


--------------------------------

### Adding a radial gradient

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/background-image.mdx

Use bg-radial and bg-radial-[<position>] with color stop utilities to add positioned radial gradients.

```html
<!-- [!code classes:bg-radial-[at_50%_75%],bg-radial-[at_25%_25%],bg-radial] -->
<div class="size-18 rounded-full bg-radial from-pink-400 from-40% to-fuchsia-700"></div>
<div class="size-18 rounded-full bg-radial-[at_50%_75%] from-sky-200 via-blue-400 to-indigo-900 to-90%"></div>
<div class="size-18 rounded-full bg-radial-[at_25%_25%] from-white to-zinc-900 to-75%"></div>
```


--------------------------------

### Reserve scrollbar space on both sides with scrollbar-gutter-both

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scrollbar-gutter.mdx

Use the `scrollbar-gutter-both` utility to reserve matching gutter space on both sides of the element.

```html
<!-- [!code classes:scrollbar-gutter-both] -->
<div class="scrollbar-gutter-both overflow-auto ...">
  <!-- ... -->
</div>
```


--------------------------------

### Set the Perspective Origin Position

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/perspective-origin.mdx

Use utilities like `perspective-origin-top-left` and `perspective-origin-bottom-right` to control where the vanishing point of a perspective is located.

```html
<!-- [!code classes:perspective-origin-top-left,perspective-origin-bottom-right] -->
<div class="size-20 perspective-near perspective-origin-top-left ...">
  <div class="translate-z-12 rotate-x-0 bg-sky-300/75 ...">1</div>
  <div class="-translate-z-12 rotate-y-18 bg-sky-300/75 ...">2</div>
  <div class="translate-x-12 rotate-y-90 bg-sky-300/75 ...">3</div>
  <div class="-translate-x-12 -rotate-y-90 bg-sky-300/75 ...">4</div>
  <div class="-translate-y-12 rotate-x-90 bg-sky-300/75 ...">5</div>
  <div class="translate-y-12 -rotate-x-90 bg-sky-300/75 ...">6</div>
</div>

<div class="size-20 perspective-near perspective-origin-bottom-right …">
  <div class="translate-z-12 rotate-x-0 bg-sky-300/75 ...">1</div>
  <div class="-translate-z-12 rotate-y-18 bg-sky-300/75 ...">2</div>
  <div class="translate-x-12 rotate-y-90 bg-sky-300/75 ...">3</div>
  <div class="-translate-x-12 -rotate-y-90 bg-sky-300/75 ...">4</div>
  <div class="-translate-y-12 rotate-x-90 bg-sky-300/75 ...">5</div>
  <div class="translate-y-12 -rotate-x-90 bg-sky-300/75 ...">6</div>
</div>
```


--------------------------------

### Positioning elements using sticky and top-0

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/position.mdx

Use `sticky` and `top-0` to position an element relative to the normal document flow until it reaches a specified scroll threshold. Offsets are calculated relative to the element's normal position and act as a reference for absolute children.

```html
<!-- [!code classes:sticky,top-0] -->
<div>
  <div>
    <div class="sticky top-0 ...">A</div>
    <div>
      <div>
        <img src="/img/andrew.jpg" />
        <strong>Andrew Alfred</strong>
      </div>
      <div>
        <img src="/img/aisha.jpg" />
        <strong>Aisha Houston</strong>
      </div>
      <!-- ... -->
    </div>
  </div>
  <div>
    <div class="sticky top-0">B</div>
    <div>
      <div>
        <img src="/img/bob.jpg" />
        <strong>Bob Alfred</strong>
      </div>
      <!-- ... -->
    </div>
  </div>
  <!-- ... -->
</div>
```


--------------------------------

### Using negative order values

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/order.mdx

Prefix the class name with a dash to apply a negative order value to a flex or grid item.

```html
<!-- [!code classes:-order-1] -->
<div class="-order-1">
  <!-- ... -->
</div>
```


--------------------------------

### Applying drop shadows

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/filter-drop-shadow.mdx

Use utilities like `drop-shadow-md`, `drop-shadow-lg`, and `drop-shadow-xl` to apply drop shadows to elements. This is useful for irregular shapes like SVGs and text.

```html
<!-- [!code classes:drop-shadow-md,drop-shadow-lg,drop-shadow-xl] -->
<svg class="drop-shadow-md ...">
  <!-- ... -->
</svg>
<svg class="drop-shadow-lg ...">
  <!-- ... -->
</svg>
<svg class="drop-shadow-xl ...">
  <!-- ... -->
</svg>
```


--------------------------------

### Animate an element bouncing with animate-bounce

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/animation.mdx

Use the `animate-bounce` utility to make an element bounce up and down.

```html
<!-- [!code classes:animate-bounce] -->
<svg class="size-6 animate-bounce ...">
  <!-- ... -->
</svg>
```


--------------------------------

### Controlling column breaks with break-before

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/break-before.mdx

Use utilities like `break-before-column` to force a column break before an element inside multi-column layouts.

```html
<!-- [!code classes:break-before-column] -->
<div class="columns-2">
  <p>Well, let me tell you something, ...</p>
  <p class="break-before-column">Sure, go ahead, laugh...</p>
  <p>Maybe we can live without...</p>
  <p>Look. If you think this is...</p>
</div>
```


--------------------------------

### Applying backdrop filters

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/backdrop-filter.mdx

Use utilities like backdrop-blur-xs and backdrop-grayscale individually or combined to apply filter effects to an element's backdrop.

```html
<!-- [!code classes:backdrop-blur-xs,backdrop-grayscale] -->
<div class="bg-[url(/img/mountains.jpg)] ...">
  <div class="backdrop-blur-xs ..."></div>
</div>
<div class="bg-[url(/img/mountains.jpg)] ...">
  <div class="backdrop-grayscale ..."></div>
</div>
<div class="bg-[url(/img/mountains.jpg)] ...">
  <div class="backdrop-blur-xs backdrop-grayscale ..."></div>
</div>
```


--------------------------------

### Set outline offset using outline-offset utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/outline-offset.mdx

Use utilities like outline-offset-0, outline-offset-2, and outline-offset-4 to change the spacing between an element and its outline.

```html
<!-- [!code classes:outline-offset-0,outline-offset-2,outline-offset-4] -->
<button class="outline-2 outline-offset-0 ...">Button A</button>
<button class="outline-2 outline-offset-2 ...">Button B</button>
<button class="outline-2 outline-offset-4 ...">Button C</button>
```


--------------------------------

### Selecting all text in one click with select-all

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/user-select.mdx

Use the select-all utility to automatically select all text within an element when clicked.

```html
<!-- [!code classes:select-all] -->
<div class="select-all ...">The quick brown fox jumps over the lazy dog.</div>
```


--------------------------------

### Scale element on the x-axis with scale-x-<number> utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scale.mdx

Use scale-x-<number> utilities like scale-x-75 and scale-x-125 to scale an element on the x-axis by a percentage of its original width.

```html
<!-- [!code classes:scale-x-75,scale-x-100,scale-x-125] -->
<img class="scale-x-75 ..." src="/img/mountains.jpg" />
<img class="scale-x-100 ..." src="/img/mountains.jpg" />
<img class="scale-x-125 ..." src="/img/mountains.jpg" />
```


--------------------------------

### Setting fixed size for form controls using field-sizing-fixed

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/field-sizing.mdx

Use the `field-sizing-fixed` utility to make a form control use a fixed size rather than resizing with content.

```html
<!-- [!code classes:field-sizing-fixed] -->
<textarea class="field-sizing-fixed w-80 ..." rows="2">
  Latex Salesman, Vanderlay Industries
</textarea>
```


--------------------------------

### Stretching an item with place-self-stretch

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/place-self.mdx

Use `place-self-stretch` to stretch an item on both axes.

```html
<!-- [!code classes:place-self-stretch] -->
<div class="grid grid-cols-3 gap-4 ...">
  <div>01</div>
  <div class="place-self-stretch ...">02</div>
  <div>03</div>
  <div>04</div>
  <div>05</div>
  <div>06</div>
</div>
```


--------------------------------

### Enable proximity scroll snapping with snap-proximity

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scroll-snap-type.mdx

Use the snap-proximity utility to make a snap container come to rest on snap points that are close in proximity.

```html
<!-- [!code classes:snap-proximity] -->
<div class="snap-x snap-proximity ...">
  <div class="snap-center ...">
    <img src="/img/vacation-01.jpg" />
  </div>
  <div class="snap-center ...">
    <img src="/img/vacation-02.jpg" />
  </div>
  <div class="snap-center ...">
    <img src="/img/vacation-03.jpg" />
  </div>
  <div class="snap-center ...">
    <img src="/img/vacation-04.jpg" />
  </div>
  <div class="snap-center ...">
    <img src="/img/vacation-05.jpg" />
  </div>
</div>
```


--------------------------------

### Apply padding to all sides using p-<number>

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/padding.mdx

Sets uniform padding across all four sides of an element using the spacing scale.

```html
<!-- [!code classes:p-8] -->
<div class="p-8 ...">p-8</div>
```


--------------------------------

### Set a video element aspect ratio using aspect-video

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/aspect-ratio.mdx

Use the aspect-video utility to give a video element a 16 / 9 aspect ratio.

```html
<!-- [!code classes:aspect-video] -->
<iframe class="aspect-video ..." src="https://www.youtube.com/embed/dQw4w9WgXcQ"></iframe>
```


--------------------------------

### Setting column count with columns-<number>

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/columns.mdx

Use columns-<number> utilities like columns-3 to specify the number of columns for content within an element. The column width automatically adjusts to fit the configured column count.

```html
<!-- [!code classes:columns-3] -->
<div class="columns-3 ...">
  <img class="aspect-3/2 ..." src="/img/mountains-1.jpg" />
  <img class="aspect-square ..." src="/img/mountains-2.jpg" />
  <img class="aspect-square ..." src="/img/mountains-3.jpg" />
  <!-- ... -->
</div>
```


--------------------------------

### Allow flex items to shrink with shrink

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/flex-shrink.mdx

Use `shrink` to allow a flex item to shrink if needed.

```html
<!-- [!code classes:shrink] -->
<div class="flex ...">
  <div class="h-14 w-14 flex-none ...">01</div>
  <div class="h-14 w-64 shrink ...">02</div>
  <div class="h-14 w-14 flex-none ...">03</div>
</div>
```


--------------------------------

### Combining masks with mask-composite utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/mask-composite.mdx

Use utilities like `mask-add`, `mask-subtract`, `mask-intersect`, and `mask-exclude` to control how multiple mask layers are composited together on an element.

```html
<!-- [!code classes:mask-add,mask-subtract,mask-intersect,mask-exclude] -->
<div class="mask-add mask-[url(/img/circle.png),url(/img/circle.png)] mask-position-[30%_50%,70%_50%] bg-[url(/img/mountains.jpg)]"></div>
<div class="mask-subtract mask-[url(/img/circle.png),url(/img/circle.png)] mask-position-[30%_50%,70%_50%] bg-[url(/img/mountains.jpg)]"></div>
<div class="mask-intersect mask-[url(/img/circle.png),url(/img/circle.png)] mask-position-[30%_50%,70%_50%] bg-[url(/img/mountains.jpg)]"></div>
<div class="mask-exclude mask-[url(/img/circle.png),url(/img/circle.png)] mask-position-[30%_50%,70%_50%] bg-[url(/img/mountains.jpg)]"></div>
```


--------------------------------

### Scaling down content with object-scale-down

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/object-fit.mdx

Use the object-scale-down utility to display an element's content at its original size but scale it down to fit its container if necessary.

```html
<!-- [!code classes:object-scale-down] -->
<img class="h-48 w-96 object-scale-down ..." src="/img/mountains.jpg" />
```


--------------------------------

### Using tabular figures

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/font-variant-numeric.mdx

Use the tabular-nums utility to render numeric glyphs that have uniform/tabular widths in fonts that support them.

```html
<!-- [!code classes:tabular-nums] -->
<p class="tabular-nums ...">12121</p>
<p class="tabular-nums ...">90909</p>
```


--------------------------------

### Set normal word breaks using break-normal

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/word-break.mdx

Use the break-normal utility to only add line breaks at normal word break points.

```html
<!-- [!code classes:break-normal] -->
<p class="break-normal">The longest word in any of the major...</p>
```


--------------------------------

### Setting the transition duration

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/transition-duration.mdx

Use utilities like duration-150, duration-300, or duration-700 to set the duration of CSS transitions in milliseconds.

```html
<!-- [!code classes:duration-150,duration-300,duration-700] -->
<button class="transition duration-150 ease-in-out ...">Button A</button>
<button class="transition duration-300 ease-in-out ...">Button B</button>
<button class="transition duration-700 ease-in-out ...">Button C</button>
```


--------------------------------

### Stretching to fit with object-fill

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/object-fit.mdx

Use the object-fill utility to stretch an element's content to fit its container.

```html
<!-- [!code classes:object-fill] -->
<img class="h-48 w-96 object-fill ..." src="/img/mountains.jpg" />
```


--------------------------------

### Set minimum inline size using spacing scale

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/min-inline-size.mdx

Use min-inline-<number> utilities to set an element to a fixed minimum inline size based on the spacing scale.

```html
<!-- [!code classes:min-inline-80,min-inline-64,min-inline-48,min-inline-40,min-inline-32,min-inline-24] -->
<div class="inline-20 ...">
  <div class="min-inline-80 ...">min-inline-80</div>
  <div class="min-inline-64 ...">min-inline-64</div>
  <div class="min-inline-48 ...">min-inline-48</div>
  <div class="min-inline-40 ...">min-inline-40</div>
  <div class="min-inline-32 ...">min-inline-32</div>
  <div class="min-inline-24 ...">min-inline-24</div>
</div>
```


--------------------------------

### Control mask mode with mask-alpha and mask-luminance

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/mask-mode.mdx

Use mask-alpha when mask opacity determines visibility, or mask-luminance when grayscale luminance values determine visibility.

```html
<!-- [!code classes:mask-alpha,mask-luminance] -->
<div class="mask-alpha mask-r-from-black mask-r-from-50% mask-r-to-transparent bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-luminance mask-r-from-white mask-r-from-50% mask-r-to-black bg-[url(/img/mountains.jpg)] ..."></div>
```


--------------------------------

### Rotate element using rotate-<number> utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/rotate.mdx

Use rotate utilities such as rotate-45, rotate-90, and rotate-210 to rotate an element by a specific number of degrees.

```html
<!-- [!code classes:rotate-45,rotate-90,rotate-210] -->
<img class="rotate-45 ..." src="/img/mountains.jpg" />
<img class="rotate-90 ..." src="/img/mountains.jpg" />
<img class="rotate-210 ..." src="/img/mountains.jpg" />
```


--------------------------------

### Using custom scrollbar color values

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scrollbar-color.mdx

Use arbitrary value utilities like scrollbar-thumb-[<value>] and scrollbar-track-[<value>] to apply specific custom colors.

```html
<!-- [!code classes:scrollbar-thumb-[#0f766e],scrollbar-track-[#ccfbf1]] -->
<div class="scrollbar-thumb-[#0f766e] scrollbar-track-[#ccfbf1] ...">
  <!-- ... -->
</div>
```


--------------------------------

### Setting the ring color

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/box-shadow.mdx

Use ring color utilities such as ring-blue-500 to change ring color. Rings default to 100% opacity, which can be modified using opacity syntax.

```html
<!-- [!code classes:ring-blue-500,ring-blue-500/50] -->
<button class="ring-2 ring-blue-500 ...">Subscribe</button>
<button class="ring-2 ring-blue-500/50 ...">Subscribe</button>
```


--------------------------------

### Opt out of forced colors with forced-color-adjust-none

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/forced-color-adjust.mdx

Use the forced-color-adjust-none utility to opt an element out of colors enforced by forced colors mode when a limited color palette degrades usability.

```html
<!-- [!code classes:forced-color-adjust-none] -->
<form>
  <img src="/img/shirt.jpg" />
  <div>
    <h3>Basic Tee</h3>
    <h3>$35</h3>
    <fieldset>
      <legend class="sr-only">Choose a color</legend>
      <div class="forced-color-adjust-none ...">
        <label>
          <input class="sr-only" type="radio" name="color-choice" value="White" />
          <span class="sr-only">White</span>
          <span class="size-6 rounded-full border border-black/10 bg-white"></span>
        </label>
        <!-- ... -->
      </div>
    </fieldset>
  </div>
</form>
```


--------------------------------

### Distribute space between rows with content-between

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/align-content.mdx

Use `content-between` to distribute rows in a container such that there is an equal amount of space between each line.

```html
<!-- [!code classes:content-between] -->
<div class="grid h-56 grid-cols-3 content-between gap-4 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
  <div>05</div>
</div>
```


--------------------------------

### Set text decoration style using decoration-* utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/text-decoration-style.mdx

Use utilities like decoration-dotted and decoration-dashed to change the text decoration style of an element.

```html
<!-- [!code classes:decoration-solid,decoration-double,decoration-dotted,decoration-dashed,decoration-wavy] -->
<p class="underline decoration-solid">The quick brown fox...</p>
<p class="underline decoration-double">The quick brown fox...</p>
<p class="underline decoration-dotted">The quick brown fox...</p>
<p class="underline decoration-dashed">The quick brown fox...</p>
<p class="underline decoration-wavy">The quick brown fox...</p>
```


--------------------------------

### Undo line clamping with line-clamp-none

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/line-clamp.mdx

Use line-clamp-none to remove line clamping that was previously applied to an element.

```html
<!-- [!code classes:lg:line-clamp-none] -->
<p class="line-clamp-3 lg:line-clamp-none">
  <!-- ... -->
</p>
```


--------------------------------

### Enable multiple OpenType font features

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/font-feature-settings.mdx

Enable multiple OpenType features by supplying comma-separated feature tags within the arbitrary value utility.

```html
<!-- [!code classes:font-features-["smcp","onum"]] -->
<p class="font-features-['smcp','onum'] ...">This text uses small caps and oldstyle numbers.</p>
```


--------------------------------

### Distribute text evenly with text-balance

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/text-wrap.mdx

Use the text-balance utility to distribute text evenly across each line. Browsers limit text balancing to blocks that are approximately 6 lines or less, making it best suited for headings.

```html
<!-- [!code classes:text-balance] -->
<article>
  <h3 class="text-balance">Beloved Manhattan soup stand closes</h3>
  <p>New Yorkers are facing the winter chill...</p>
</article>
```


--------------------------------

### Translate elements using the spacing scale

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/translate.mdx

Use translate-<number> utilities such as translate-2, translate-8, or negative variants like -translate-6 to translate an element along both axes.

```html
<!-- [!code classes:-translate-6,translate-2,translate-8] -->
<img class="-translate-6 ..." src="/img/mountains.jpg" />
<img class="translate-2 ..." src="/img/mountains.jpg" />
<img class="translate-8 ..." src="/img/mountains.jpg" />
```


--------------------------------

### Distribute rows with space evenly using content-evenly

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/align-content.mdx

Use `content-evenly` to distribute rows in a container with equal space around each item, accounting for the doubling of space normally seen when using `content-around`.

```html
<!-- [!code classes:content-evenly] -->
<div class="grid h-56 grid-cols-3 content-evenly gap-4 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
  <div>05</div>
</div>
```


--------------------------------

### Add a ping animation with animate-ping

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/animation.mdx

Use the `animate-ping` utility to make an element scale and fade like a radar ping or ripple of water, suitable for notification badges.

```html
<!-- [!code classes:animate-ping] -->
<span class="relative flex size-3">
  <span class="absolute inline-flex h-full w-full animate-ping rounded-full bg-sky-400 opacity-75"></span>
  <span class="relative inline-flex size-3 rounded-full bg-sky-500"></span>
</span>
```


--------------------------------

### Applying negative text indentation with -indent-8

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/text-indent.mdx

Prefix the utility class with a dash (such as -indent-8) to set a negative text indent value.

```html
<!-- [!code classes:-indent-8] -->
<p class="-indent-8">So I started to walk into the water...</p>
```


--------------------------------

### Positioning children in 3D space with transform-3d and transform-flat

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/transform-style.mdx

Use `transform-3d` to position child elements in 3D space or `transform-flat` to flatten them. Without `transform-3d`, child transformations only occur in 2D space.

```html
<!-- [!code classes:transform-flat,transform-3d] -->
<div class="size-20 transform-flat ...">
  <div class="translate-z-12 rotate-x-0 bg-sky-300/75 ...">1</div>
  <div class="-translate-z-12 rotate-y-18 bg-sky-300/75 ...">2</div>
  <div class="translate-x-12 rotate-y-90 bg-sky-300/75 ...">3</div>
  <div class="-translate-x-12 -rotate-y-90 bg-sky-300/75 ...">4</div>
  <div class="-translate-y-12 rotate-x-90 bg-sky-300/75 ...">5</div>
  <div class="translate-y-12 -rotate-x-90 bg-sky-300/75 ...">6</div>
</div>

<div class="size-20 transform-3d ...">
  <div class="translate-z-12 rotate-x-0 bg-sky-300/75 ...">1</div>
  <div class="-translate-z-12 rotate-y-18 bg-sky-300/75 ...">2</div>
  <div class="translate-x-12 rotate-y-90 bg-sky-300/75 ...">3</div>
  <div class="-translate-x-12 -rotate-y-90 bg-sky-300/75 ...">4</div>
  <div class="-translate-y-12 rotate-x-90 bg-sky-300/75 ...">5</div>
  <div class="translate-y-12 -rotate-x-90 bg-sky-300/75 ...">6</div>
</div>
```


--------------------------------

### Apply horizontal padding using px-<number>

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/padding.mdx

Sets padding on both the left and right sides of an element simultaneously.

```html
<!-- [!code classes:px-8] -->
<div class="px-8 ...">px-8</div>
```


--------------------------------

### Using negative letter spacing utility

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/letter-spacing.mdx

Prefix the numerical tracking class name with a dash to apply a negative letter spacing value.

```html
<!-- [!code classes:-tracking-2] -->
<p class="-tracking-2">The quick brown fox ...</p>
```


--------------------------------

### Distribute items with space between using place-content-between

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/place-content.mdx

Use place-content-between to distribute grid items along the inline and block axes so that there is an equal amount of space between each row and column on each axis respectively.

```html
<!-- [!code classes:place-content-between] -->
<div class="grid h-48 grid-cols-2 place-content-between gap-4 ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
</div>
```


--------------------------------

### Apply backdrop grayscale filter

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/backdrop-filter-grayscale.mdx

Use utilities like `backdrop-grayscale-0`, `backdrop-grayscale-50`, and `backdrop-grayscale` to control the grayscale effect applied to an element's backdrop.

```html
<!-- [!code classes:backdrop-grayscale-0,backdrop-grayscale-50,backdrop-grayscale] -->
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-grayscale-0 ..."></div>
</div>
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-grayscale-50 ..."></div>
</div>
<div class="bg-[url(/img/mountains.jpg)]">
  <div class="bg-white/30 backdrop-grayscale-200 ..."></div>
</div>
```


--------------------------------

### Using diagonal fractions

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/font-variant-numeric.mdx

Use the diagonal-fractions utility to replace numbers separated by a slash with common diagonal fractions in fonts that support them.

```html
<!-- [!code classes:diagonal-fractions] -->
<p class="diagonal-fractions ...">1/2 3/4 5/6</p>
```


--------------------------------

### Control text flow with block and inline utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/display.mdx

Use inline, inline-block, and block to adjust how elements wrap and flow within text and parent containers.

```html
<!-- [!code classes:inline,inline-block,block] -->
<p>
  When controlling the flow of text, using the CSS property <span class="inline">display: inline</span> will cause the
  text inside the element to wrap normally.
</p>
<p>
  While using the property <span class="inline-block">display: inline-block</span> will wrap the element to prevent the
  text inside from extending beyond its parent.
</p>
<p>
  Lastly, using the property <span class="block">display: block</span> will put the element on its own line and fill its
  parent.
</p>
```


--------------------------------

### Set margin on all sides using m-<number>

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/margin.mdx

Use m-<number> utilities like m-4 and m-8 to control spacing on all four sides of an element simultaneously.

```html
<!-- [!code classes:m-8] -->
<div class="m-8 ...">m-8</div>
```


--------------------------------

### Set column and row gaps independently with gap-x-8 and gap-y-4

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/gap.mdx

Use `gap-x-<number>` or `gap-y-<number>` utilities like `gap-x-8` and `gap-y-4` to change the gap between columns and rows independently.

```html
<!-- [!code classes:gap-x-8,gap-y-4] -->
<div class="grid grid-cols-3 gap-x-8 gap-y-4">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
  <div>05</div>
  <div>06</div>
</div>
```


--------------------------------

### Customize animation theme with @theme directive

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/animation.mdx

Define a custom animation utility and corresponding keyframes inside the `@theme` directive to generate custom `animate-*` classes.

```css
@theme {
  /* [!code highlight:12] */
  --animate-wiggle: wiggle 1s ease-in-out infinite;

  @keyframes wiggle {
    0%,
    100% {
      transform: rotate(-3deg);
    }
    50% {
      transform: rotate(3deg);
    }
  }
}
```


--------------------------------

### Set background blend mode in HTML

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/background-blend-mode.mdx

Use utilities like bg-blend-multiply, bg-blend-soft-light, and bg-blend-overlay to control how an element's background image blends with its background color.

```html
<!-- [!code classes:bg-blend-multiply,bg-blend-soft-light,bg-blend-overlay] -->
<div class="bg-blue-500 bg-[url(/img/mountains.jpg)] bg-blend-multiply ..."></div>
<div class="bg-blue-500 bg-[url(/img/mountains.jpg)] bg-blend-soft-light ..."></div>
<div class="bg-blue-500 bg-[url(/img/mountains.jpg)] bg-blend-overlay ..."></div>
```


--------------------------------

### Set border width for all sides

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/border-width.mdx

Use `border` or `border-<number>` utilities like `border-2` and `border-4` to apply a border width to all sides of an element.

```html
<!-- [!code classes:border,border-2,border-4,border-8] -->
<div class="border border-indigo-600 ..."></div>
<div class="border-2 border-indigo-600 ..."></div>
<div class="border-4 border-indigo-600 ..."></div>
<div class="border-8 border-indigo-600 ..."></div>
```


--------------------------------

### Setting inline border color with logical properties

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/border-color.mdx

Use utilities like border-s-* and border-e-* to set border-inline-start-color and border-inline-end-color based on text direction.

```html
<!-- [!code classes:border-s-indigo-500,border-s-indigo-500] -->
<!-- [!code word:dir="ltr"] -->
<!-- [!code word:dir="rtl"] -->
<div dir="ltr">
  <div class="border-s-indigo-500 ..."></div>
</div>
<div dir="rtl">
  <div class="border-s-indigo-500 ..."></div>
</div>
```


--------------------------------

### Using slashed zeroes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/font-variant-numeric.mdx

Use the slashed-zero utility to force a zero with a slash in fonts that support them.

```html
<!-- [!code classes:slashed-zero] -->
<p class="slashed-zero ...">0</p>
```


--------------------------------

### Add a pulse animation with animate-pulse

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/animation.mdx

Use the `animate-pulse` utility to make an element gently fade in and out for elements like skeleton loaders.

```html
<!-- [!code classes:animate-pulse] -->
<div class="mx-auto w-full max-w-sm rounded-md border border-blue-300 p-4">
  <div class="flex animate-pulse space-x-4">
    <div class="size-10 rounded-full bg-gray-200"></div>
    <div class="flex-1 space-y-6 py-1">
      <div class="h-2 rounded bg-gray-200"></div>
      <div class="space-y-3">
        <div class="grid grid-cols-3 gap-4">
          <div class="col-span-2 h-2 rounded bg-gray-200"></div>
          <div class="col-span-1 h-2 rounded bg-gray-200"></div>
        </div>
        <div class="h-2 rounded bg-gray-200"></div>
      </div>
    </div>
  </div>
</div>
```


--------------------------------

### Prevent resizing with resize-none

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/resize.mdx

Use the `resize-none` class to disable element resizing completely and remove the resize handle.

```html
<!-- [!code classes:resize-none] -->
<textarea class="resize-none rounded-md"></textarea>
```


--------------------------------

### Scale elements along the y-axis using scale-y utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scale.mdx

Use scale-y-<number> utilities such as scale-y-75, scale-y-100, and scale-y-125 to scale an element on the y-axis by a percentage of its original height.

```html
<!-- [!code classes:scale-y-75,scale-y-100,scale-y-125] -->
<img class="scale-y-75 ..." src="/img/mountains.jpg" />
<img class="scale-y-100 ..." src="/img/mountains.jpg" />
<img class="scale-y-125 ..." src="/img/mountains.jpg" />
```


--------------------------------

### Skewing on the y-axis with skew-y-<number> utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/skew.mdx

Use utilities like skew-y-6, skew-y-12, or negative variants such as -skew-y-12 to skew an element along the y-axis.

```html
<!-- [!code classes:-skew-y-12,skew-y-12,skew-y-6] -->
<img class="-skew-y-12 ..." src="/img/mountains.jpg" />
<img class="skew-y-6 ..." src="/img/mountains.jpg" />
<img class="skew-y-12 ..." src="/img/mountains.jpg" />
```


--------------------------------

### Setting the font weight of an element

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/font-weight.mdx

Use utilities like font-light, font-normal, font-medium, font-semibold, and font-bold to apply font weights to text elements.

```html
<!-- [!code classes:font-light,font-normal,font-medium,font-semibold,font-bold] -->
<p class="font-light ...">The quick brown fox ...</p>
<p class="font-normal ...">The quick brown fox ...</p>
<p class="font-medium ...">The quick brown fox ...</p>
<p class="font-semibold ...">The quick brown fox ...</p>
<p class="font-bold ...">The quick brown fox ...</p>
```


--------------------------------

### Set fixed height using spacing scale

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/height.mdx

Use h-<number> utilities to set an element to a fixed height based on the spacing scale.

```html
<!-- [!code classes:h-96,h-80,h-64,h-48,h-40,h-32,h-24] -->
<div class="h-96 ...">h-96</div>
<div class="h-80 ...">h-80</div>
<div class="h-64 ...">h-64</div>
<div class="h-48 ...">h-48</div>
<div class="h-40 ...">h-40</div>
<div class="h-32 ...">h-32</div>
<div class="h-24 ...">h-24</div>
```


--------------------------------

### Set font stretch using percentage utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/font-stretch.mdx

Use font-stretch-<percentage> utilities such as font-stretch-50% and font-stretch-150% to adjust the width of a font face using percentage values.

```html
<!-- [!code classes:font-stretch-50%,font-stretch-100%,font-stretch-150%] -->
<p class="font-stretch-50%">The quick brown fox...</p>
<p class="font-stretch-100%">The quick brown fox...</p>
<p class="font-stretch-150%">The quick brown fox...</p>
```


--------------------------------

### Set outline color

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/outline-color.mdx

Use utilities like `outline-blue-500`, `outline-cyan-500`, and `outline-pink-500` to control the color of an element's outline.

```html
<!-- [!code classes:outline-blue-500,outline-cyan-500,outline-pink-500] -->
<button class="outline-2 outline-offset-2 outline-blue-500 ...">Button A</button>
<button class="outline-2 outline-offset-2 outline-cyan-500 ...">Button B</button>
<button class="outline-2 outline-offset-2 outline-pink-500 ...">Button C</button>
```


--------------------------------

### Set maximum width to the current breakpoint

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/max-width.mdx

Use the container utility to set an element's maximum width to match the min-width of the current breakpoint.

```html
<!-- [!code classes:container] -->
<div class="container">
  <!-- ... -->
</div>
```


--------------------------------

### Set fixed maximum inline size with spacing scale utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/max-inline-size.mdx

Use max-inline-<number> utilities like max-inline-24 and max-inline-64 to constrain an element's maximum inline size based on the spacing scale.

```html
<!-- [!code classes:max-inline-96,max-inline-80,max-inline-64,max-inline-48,max-inline-40,max-inline-32,max-inline-24] -->
<div class="inline-full max-inline-96 ...">max-inline-96</div>
<div class="inline-full max-inline-80 ...">max-inline-80</div>
<div class="inline-full max-inline-64 ...">max-inline-64</div>
<div class="inline-full max-inline-48 ...">max-inline-48</div>
<div class="inline-full max-inline-40 ...">max-inline-40</div>
<div class="inline-full max-inline-32 ...">max-inline-32</div>
```


--------------------------------

### Explicitly setting a sort order

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/order.mdx

Use `order-<number>` utilities like `order-1`, `order-2`, and `order-3` to render flex and grid items in a different order than they appear in the DOM.

```html
<!-- [!code classes:order-1,order-2,order-3] -->
<div class="flex justify-between ...">
  <div class="order-3 ...">01</div>
  <div class="order-1 ...">02</div>
  <div class="order-2 ...">03</div>
</div>
```


--------------------------------

### Enabling smooth scrolling with scroll-smooth

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/scroll-behavior.mdx

Use the `scroll-smooth` utility to enable smooth scrolling within an element. Setting `scroll-behavior` only affects scroll events triggered by the browser.

```html
<!-- [!code classes:scroll-smooth] -->
<html class="scroll-smooth">
  <!-- ... -->
</html>
```


--------------------------------

### Set mask position using mask-* utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/mask-position.mdx

Use mask position utilities like mask-top-left, mask-center, or mask-bottom-right to set the position of an element's mask image.

```html
<!-- [!code classes:mask-top-left,mask-top,mask-top-right,mask-left,mask-center,mask-right,mask-bottom-left,mask-bottom,mask-bottom-right] -->
<div class="mask-top-left mask-[url(/img/circle.png)] mask-size-[50%] bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-top mask-[url(/img/circle.png)] mask-size-[50%] bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-top-right mask-[url(/img/circle.png)] mask-size-[50%] bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-left mask-[url(/img/circle.png)] mask-size-[50%] bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-center mask-[url(/img/circle.png)] mask-size-[50%] bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-right mask-[url(/img/circle.png)] mask-size-[50%] bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-bottom-left mask-[url(/img/circle.png)] mask-size-[50%] bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-bottom mask-[url(/img/circle.png)] mask-size-[50%] bg-[url(/img/mountains.jpg)] ..."></div>
<div class="mask-bottom-right mask-[url(/img/circle.png)] mask-size-[50%] bg-[url(/img/mountains.jpg)] ..."></div>
```


--------------------------------

### Enable OpenType font features with arbitrary values

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/font-feature-settings.mdx

Use the font-features-[<value>] utility to enable OpenType features on fonts that support them.

```html
<!-- [!code classes:font-features-["smcp"]] -->
<p class="font-features-['smcp'] ...">This text uses small caps.</p>
```


--------------------------------

### Scrolling with the viewport using bg-scroll

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/background-attachment.mdx

Use the bg-scroll utility to scroll the background image with the viewport, but not with the container.

```html
<!-- [!code classes:bg-scroll] -->
<div class="bg-[url(/img/mountains.jpg)] bg-scroll ...">
  <!-- ... -->
</div>
```


--------------------------------

### Controlling text color with color utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/color.mdx

Use utilities like `text-blue-600` and `text-sky-400` to set the text color of an element across default and dark modes.

```html
<!-- [!code classes:text-blue-600,dark:text-sky-400] -->
<p class="text-blue-600 dark:text-sky-400">The quick brown fox...</p>
```


--------------------------------

### Remove an existing box shadow with shadow-none

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/box-shadow.mdx

Use the shadow-none utility to remove an existing box shadow from an element.

```html
<!-- [!code classes:shadow-none] -->
<div class="shadow-none ..."></div>
```


--------------------------------

### Match small viewport block size using block-svh

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/block-size.mdx

Use `block-svh` to set an element's block size to the smallest possible size of the viewport.

```html
<!-- [!code classes:block-svh] -->
<div class="block-svh">
  <!-- ... -->
</div>
```


--------------------------------

### Using lining figures

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/font-variant-numeric.mdx

Use the lining-nums utility to render numeric glyphs aligned to the baseline in fonts that support them.

```html
<!-- [!code classes:lining-nums] -->
<p class="lining-nums ...">1234567890</p>
```


--------------------------------

### Skew elements using negative values

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/skew.mdx

Use `-skew-<number>` utilities like `-skew-3`, `-skew-6`, or `-skew-12` to skew an element on both axes with negative angles.

```html
<!-- [!code classes:-skew-3,-skew-6,-skew-12] -->
<img class="-skew-3 ..." src="/img/mountains.jpg" />
<img class="-skew-6 ..." src="/img/mountains.jpg" />
<img class="-skew-12 ..." src="/img/mountains.jpg" />
```


--------------------------------

### Applying float conditionally at breakpoints

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/float.mdx

Prefix float utilities with breakpoint variants like `md:` to apply float styles conditionally at specific screen sizes.

```html
<!-- [!code classes:md:float-left] -->
<img class="float-right md:float-left" src="/img/mountains.jpg" />
```


--------------------------------

### Collapsing table elements with collapse

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/visibility.mdx

Use the `collapse` utility to hide table rows or columns without affecting the overall table layout.

```html
<!-- [!code classes:collapse] -->
<table>
  <thead>
    <tr>
      <th>Invoice #</th>
      <th>Client</th>
      <th>Amount</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>#100</td>
      <td>Pendant Publishing</td>
      <td>$2,000.00</td>
    </tr>
    <tr class="collapse">
      <td>#101</td>
      <td>Kruger Industrial Smoothing</td>
      <td>$545.00</td>
    </tr>
    <tr>
      <td>#102</td>
      <td>J. Peterman</td>
      <td>$10,000.25</td>
    </tr>
  </tbody>
</table>
```


--------------------------------

### Set font stretch using width keyword utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/font-stretch.mdx

Use utilities like font-stretch-condensed and font-stretch-expanded to set the width of a font face. This only applies to fonts with multiple width variations available; otherwise, the browser selects the closest match.

```html
<!-- [!code classes:font-stretch-extra-condensed,font-stretch-condensed,font-stretch-normal,font-stretch-expanded,font-stretch-extra-expanded] -->
<p class="font-stretch-extra-condensed">The quick brown fox...</p>
<p class="font-stretch-condensed">The quick brown fox...</p>
<p class="font-stretch-normal">The quick brown fox...</p>
<p class="font-stretch-expanded">The quick brown fox...</p>
<p class="font-stretch-extra-expanded">The quick brown fox...</p>
```


--------------------------------

### Preserve newlines and collapse spaces using whitespace-pre-line

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/white-space.mdx

Use the `whitespace-pre-line` utility to preserve newlines but not spaces within an element. Text will be wrapped normally.

```html
<!-- [!code classes:whitespace-pre-line] -->
<!-- prettier-ignore -->
<p class="whitespace-pre-line">Hey everyone!

It's almost 2022       and we still don't know if there             are aliens living among us, or do we? Maybe the person writing this is an alien.

You will never know.</p>
```


--------------------------------

### Adding a conic gradient mask

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/mask-image.mdx

Use mask-conic-from-<value>, mask-conic-to-<value>, and mask-conic-<angle> utilities to add a conic gradient mask to an element. Conic gradient masks default to transitioning from black to transparent.

```html
<!-- [!code classes:mask-conic-from-75%,mask-conic-to-75%] -->
<div class="flex items-center gap-5 rounded-xl bg-white p-4 shadow-lg ring-1 ring-black/5 dark:bg-gray-800">
  <div class="grid grid-cols-1 grid-rows-1">
    <div class="border-4 border-gray-100 dark:border-gray-700 ..."></div>
    <div class="border-4 border-amber-500 mask-conic-from-75% mask-conic-to-75% dark:border-amber-400 ..."></div>
  </div>
  <div class="w-0 flex-1 text-sm text-gray-950 dark:text-white">
    <p class="font-medium">Storage used: 75%</p>
    <p class="mt-1 text-gray-500 dark:text-gray-400"><span class="font-medium">0.48 GB</span> out of 2 GB remaining</p>
  </div>
</div>
```


--------------------------------

### Set margin on individual sides using mt, mr, mb, and ml

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/margin.mdx

Use mt-<number>, mr-<number>, mb-<number>, and ml-<number> utilities to apply margin specifically to the top, right, bottom, or left side of an element.

```html
<!-- [!code classes:mt-6,mr-4,mb-8,ml-2] -->
<div class="mt-6 ...">mt-6</div>
<div class="mr-4 ...">mr-4</div>
<div class="mb-8 ...">mb-8</div>
<div class="ml-2 ...">ml-2</div>
```


--------------------------------

### Set fixed inline size with spacing scale

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/inline-size.mdx

Use inline-<number> utilities such as inline-24 or inline-64 to set an element to a fixed inline size based on the spacing scale.

```html
<!-- [!code classes:inline-96,inline-80,inline-64,inline-48,inline-40,inline-32,inline-24] -->
<div class="inline-96 ...">inline-96</div>
<div class="inline-80 ...">inline-80</div>
<div class="inline-64 ...">inline-64</div>
<div class="inline-48 ...">inline-48</div>
<div class="inline-40 ...">inline-40</div>
<div class="inline-32 ...">inline-32</div>
```


--------------------------------

### Stacking multiple font-variant-numeric utilities

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/font-variant-numeric.mdx

Enables multiple numeric font variants by combining composable utility classes like slashed-zero and tabular-nums.

```html
<!-- [!code classes:slashed-zero,tabular-nums] -->
<dl class="...">
  <dt class="...">Subtotal</dt>
  <dd class="text-right slashed-zero tabular-nums ...">$100.00</dd>
  <dt class="...">Tax</dt>
  <dd class="text-right slashed-zero tabular-nums ...">$14.50</dd>
  <dt class="...">Total</dt>
  <dd class="text-right slashed-zero tabular-nums ...">$114.50</dd>
</dl>
```


--------------------------------

### Stretch grid items with justify-items-stretch

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/justify-items.mdx

Use the justify-items-stretch utility to stretch grid items across their inline axis.

```html
<!-- [!code classes:justify-items-stretch] -->
<div class="grid justify-items-stretch ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
  <div>04</div>
  <div>05</div>
  <div>06</div>
</div>
```


--------------------------------

### Set line height independently with leading-<number>

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/line-height.mdx

Use leading-<number> utilities such as leading-6, leading-7, and leading-8 to specify line height independently of font size.

```html
<!-- [!code classes:leading-6,leading-7,leading-8] -->
<p class="text-sm leading-6">So I started to walk into the water...</p>
<p class="text-sm leading-7">So I started to walk into the water...</p>
<p class="text-sm leading-8">So I started to walk into the water...</p>
```


--------------------------------

### Preserve whitespace and wrap text normally with whitespace-pre-wrap

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/white-space.mdx

Use the whitespace-pre-wrap utility to preserve newlines and multiple spaces within an element while allowing text to wrap normally.

```html
<!-- [!code classes:whitespace-pre-wrap] -->
<!-- prettier-ignore -->
<p class="whitespace-pre-wrap">Hey everyone!

It's almost 2022       and we still don't know if there             are aliens living among us, or do we? Maybe the person writing this is an alien.

You will never know.</p>
```


--------------------------------

### Justify content with justify-evenly

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/justify-content.mdx

Use justify-evenly to distribute items along the main axis with equal space around each item, accounting for the doubling of space between items in justify-around.

```html
<!-- [!code classes:justify-evenly] -->
<div class="flex justify-evenly ...">
  <div>01</div>
  <div>02</div>
  <div>03</div>
</div>
```


--------------------------------

### Set border width for horizontal and vertical axes

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/border-width.mdx

Use utilities like `border-x` and `border-y-4` to set the border width on opposing sides simultaneously.

```html
<!-- [!code classes:border-x-4,border-y-4] -->
<div class="border-x-4 border-indigo-500 ..."></div>
<div class="border-y-4 border-indigo-500 ..."></div>
```


--------------------------------

### Allow text to wrap with text-wrap

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/text-wrap.mdx

Use the text-wrap utility to wrap overflowing text onto multiple lines at logical points in the text.

```html
<!-- [!code classes:text-wrap] -->
<article class="text-wrap">
  <h3>Beloved Manhattan soup stand closes</h3>
  <p>New Yorkers are facing the winter chill...</p>
</article>
```


--------------------------------

### Removing background images with bg-none

Source: https://github.com/tailwindlabs/tailwindcss.com/blob/main/src/docs/background-image.mdx

Use the bg-none utility class to remove an existing background image from an element.

```html
<!-- [!code classes:bg-none] -->
<div class="bg-none"></div>
```
