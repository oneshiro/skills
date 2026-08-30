\### Install Sass



Source: https://getbootstrap.com/docs/5.3/getting-started/vite



Install Sass to handle Bootstrap CSS compilation.



```bash

npm i --save-dev sass

```



\--------------------------------



\### Install Vite



Source: https://getbootstrap.com/docs/5.3/getting-started/vite



Install Vite as a development dependency.



```bash

npm i --save-dev vite

```



\--------------------------------



\### Install Bootstrap with NuGet



Source: https://getbootstrap.com/docs/5.3/getting-started/download



Install Bootstrap CSS or Sass packages for .NET Framework projects.



```powershell

Install-Package bootstrap

```



```powershell

Install-Package bootstrap.sass

```



\--------------------------------



\### Install Bootstrap and Popper



Source: https://getbootstrap.com/docs/5.3/getting-started/parcel



Installs Bootstrap and the required Popper dependency for positioning components.



```bash

npm i --save bootstrap @popperjs/core

```



\--------------------------------



\### Install mini-css-extract-plugin



Source: https://getbootstrap.com/docs/5.3/getting-started/webpack



Install the plugin required to extract CSS into separate files.



```bash

npm install --save-dev mini-css-extract-plugin

```



\--------------------------------



\### Start Vite development server



Source: https://getbootstrap.com/docs/5.3/getting-started/vite



Execute the npm script to launch the local development server.



```bash

npm start



```



\--------------------------------



\### Install Bootstrap with npm



Source: https://getbootstrap.com/docs/5.3/getting-started/download



Use the npm CLI to add Bootstrap to a Node.js project.



```bash

npm install bootstrap@5.3.8

```



\--------------------------------



\### Install build loaders and tools



Source: https://getbootstrap.com/docs/5.3/getting-started/webpack



Install Sass, loaders, and Autoprefixer required for processing Bootstrap assets.



```bash

npm i --save-dev autoprefixer css-loader postcss-loader sass sass-loader style-loader

```



\--------------------------------



\### Add npm start script



Source: https://getbootstrap.com/docs/5.3/getting-started/vite



Update the package.json file to include a script for starting the Vite development server.



```json

{

&#x20; // ...

&#x20; "scripts": {

&#x20;   "start": "vite",

&#x20;   "test": "echo \\"Error: no test specified\\" \&\& exit 1"

&#x20; },

&#x20; // ...

}



```



\--------------------------------



\### Install Bootstrap with Bun



Source: https://getbootstrap.com/docs/5.3/getting-started/download



Use the Bun CLI to add Bootstrap to a Bun or Node.js project.



```bash

bun add bootstrap@5.3.8

```



\--------------------------------



\### Install Bootstrap with Composer



Source: https://getbootstrap.com/docs/5.3/getting-started/download



Manage Bootstrap assets in PHP projects using Composer.



```bash

composer require twbs/bootstrap:5.3.8

```



\--------------------------------



\### Link element examples



Source: https://getbootstrap.com/docs/5.3/content/reboot



Examples of standard links, links with opacity overrides, and placeholder links without href attributes.



```html

<a href="#">This is an example link</a>

```



```html

<a href="#" style="--bs-link-opacity: .5">This is an example link</a>

```



```html

<a>This is a placeholder link</a>

```



\--------------------------------



\### Install Webpack dependencies



Source: https://getbootstrap.com/docs/5.3/getting-started/webpack



Install core Webpack packages and the HTML plugin as development dependencies.



```bash

npm i --save-dev webpack webpack-cli webpack-dev-server html-webpack-plugin

```



\--------------------------------



\### Basic Icon Link Examples



Source: https://getbootstrap.com/docs/5.3/helpers/icon-link



Examples of placing an icon to the left or right of link text using the .icon-link class.



```html

<a class="icon-link" href="#">

&#x20; <svg xmlns="http://www.w3.org/2000/svg" class="bi" viewBox="0 0 16 16" aria-hidden="true">

&#x20;   <path d="M8.186 1.113a.5.5 0 0 0-.372 0L1.846 3.5l2.404.961L10.404 2l-2.218-.887zm3.564 1.426L5.596 5 8 5.961 14.154 3.5l-2.404-.961zm3.25 1.7-6.5 2.6v7.922l6.5-2.6V4.24zM7.5 14.762V6.838L1 4.239v7.923l6.5 2.6zM7.443.184a1.5 1.5 0 0 1 1.114 0l7.129 2.852A.5.5 0 0 1 16 3.5v8.662a1 1 0 0 1-.629.928l-7.185 2.874a.5.5 0 0 1-.372 0L.63 13.09a1 1 0 0 1-.63-.928V3.5a.5.5 0 0 1 .314-.464L7.443.184z"/>

&#x20; </svg>

&#x20; Icon link

</a>

```



```html

<a class="icon-link" href="#">

&#x20; Icon link

&#x20; <svg xmlns="http://www.w3.org/2000/svg" class="bi" viewBox="0 0 16 16" aria-hidden="true">

&#x20;   <path d="M1 8a.5.5 0 0 1 .5-.5h11.793l-3.147-3.146a.5.5 0 0 1 .708-.708l4 4a.5.5 0 0 1 0 .708l-4 4a.5.5 0 0 1-.708-.708L13.293 8.5H1.5A.5.5 0 0 1 1 8z"/>

&#x20; </svg>

</a>

```



\--------------------------------



\### Basic Input Group Examples



Source: https://getbootstrap.com/docs/5.3/forms/input-group



Demonstrates various configurations including single add-ons, dual add-ons, URL inputs, and textarea integration.



```html

<div class="input-group mb-3">

&#x20; <span class="input-group-text" id="basic-addon1">@</span>

&#x20; <input type="text" class="form-control" placeholder="Username" aria-label="Username" aria-describedby="basic-addon1">

</div>



<div class="input-group mb-3">

&#x20; <input type="text" class="form-control" placeholder="Recipient’s username" aria-label="Recipient’s username" aria-describedby="basic-addon2">

&#x20; <span class="input-group-text" id="basic-addon2">@example.com</span>

</div>



<div class="mb-3">

&#x20; <label for="basic-url" class="form-label">Your vanity URL</label>

&#x20; <div class="input-group">

&#x20;   <span class="input-group-text" id="basic-addon3">https://example.com/users/</span>

&#x20;   <input type="text" class="form-control" id="basic-url" aria-describedby="basic-addon3 basic-addon4">

&#x20; </div>

&#x20; <div class="form-text" id="basic-addon4">Example help text goes outside the input group.</div>

</div>



<div class="input-group mb-3">

&#x20; <span class="input-group-text">$</span>

&#x20; <input type="text" class="form-control" aria-label="Amount (to the nearest dollar)">

&#x20; <span class="input-group-text">.00</span>

</div>



<div class="input-group mb-3">

&#x20; <input type="text" class="form-control" placeholder="Username" aria-label="Username">

&#x20; <span class="input-group-text">@</span>

&#x20; <input type="text" class="form-control" placeholder="Server" aria-label="Server">

</div>



<div class="input-group">

&#x20; <span class="input-group-text">With textarea</span>

&#x20; <textarea class="form-control" aria-label="With textarea"></textarea>

</div>

```



\--------------------------------



\### Clearfix Usage Example



Source: https://getbootstrap.com/docs/5.3/helpers/clearfix



A practical example showing a container with floated buttons using the .clearfix class to maintain layout integrity.



```html

<div class="bg-info clearfix">

&#x20; <button type="button" class="btn btn-secondary float-start">Example Button floated left</button>

&#x20; <button type="button" class="btn btn-secondary float-end">Example Button floated right</button>

</div>

```



\--------------------------------



\### Basic Progress Bar Examples



Source: https://getbootstrap.com/docs/5.3/components/progress



Demonstrates standard progress bars at various completion percentages using the .progress and .progress-bar classes.



```html

<div class="progress" role="progressbar" aria-label="Basic example" aria-valuenow="0" aria-valuemin="0" aria-valuemax="100">

&#x20; <div class="progress-bar" style="width: 0%"></div>

</div>

<div class="progress" role="progressbar" aria-label="Basic example" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">

&#x20; <div class="progress-bar" style="width: 25%"></div>

</div>

<div class="progress" role="progressbar" aria-label="Basic example" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100">

&#x20; <div class="progress-bar" style="width: 50%"></div>

</div>

<div class="progress" role="progressbar" aria-label="Basic example" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100">

&#x20; <div class="progress-bar" style="width: 75%"></div>

</div>

<div class="progress" role="progressbar" aria-label="Basic example" aria-valuenow="100" aria-valuemin="0" aria-valuemax="100">

&#x20; <div class="progress-bar" style="width: 100%"></div>

</div>

```



\--------------------------------



\### Install Bootstrap with RubyGems



Source: https://getbootstrap.com/docs/5.3/getting-started/download



Add Bootstrap to Ruby projects via Gemfile or direct command line installation.



```ruby

gem 'bootstrap', '\~> 5.3.8'

```



```bash

gem install bootstrap -v 5.3.8

```



\--------------------------------



\### Start Parcel server



Source: https://getbootstrap.com/docs/5.3/getting-started/parcel



Command to launch the Parcel development server using the configured npm script.



```bash

npm start

```



\--------------------------------



\### Install Bootstrap with yarn



Source: https://getbootstrap.com/docs/5.3/getting-started/download



Use the yarn CLI to add Bootstrap to a Node.js project.



```bash

yarn add bootstrap@5.3.8

```



\--------------------------------



\### Sass Spacing Utility Examples



Source: https://getbootstrap.com/docs/5.3/utilities/spacing



Representative examples of how spacing utility classes are defined in Sass.



```scss

.mt-0 {

&#x20; margin-top: 0 !important;

}



.ms-1 {

&#x20; margin-left: ($spacer \* .25) !important;

}



.px-2 {

&#x20; padding-left: ($spacer \* .5) !important;

&#x20; padding-right: ($spacer \* .5) !important;

}



.p-3 {

&#x20; padding: $spacer !important;

}

```



\--------------------------------



\### Install Parcel



Source: https://getbootstrap.com/docs/5.3/getting-started/parcel



Adds Parcel as a development dependency to the project.



```bash

npm i --save-dev parcel

```



\--------------------------------



\### Grid Start Classes



Source: https://getbootstrap.com/docs/5.3/layout/css-grid



Uses start classes to position grid items at specific column indices, replacing traditional offset classes.



```html

<div class="grid text-center">

&#x20; <div class="g-col-3 g-start-2">.g-col-3 .g-start-2</div>

&#x20; <div class="g-col-4 g-start-6">.g-col-4 .g-start-6</div>

</div>

```



\--------------------------------



\### Responsive Navbar with Sub-components



Source: https://getbootstrap.com/docs/5.3/components/navbar



A complete responsive navbar example featuring a brand, toggler, navigation links, dropdowns, and a search form.



```html

<nav class="navbar navbar-expand-lg bg-body-tertiary">

&#x20; <div class="container-fluid">

&#x20;   <a class="navbar-brand" href="#">Navbar</a>

&#x20;   <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">

&#x20;     <span class="navbar-toggler-icon"></span>

&#x20;   </button>

&#x20;   <div class="collapse navbar-collapse" id="navbarSupportedContent">

&#x20;     <ul class="navbar-nav me-auto mb-2 mb-lg-0">

&#x20;       <li class="nav-item">

&#x20;         <a class="nav-link active" aria-current="page" href="#">Home</a>

&#x20;       </li>

&#x20;       <li class="nav-item">

&#x20;         <a class="nav-link" href="#">Link</a>

&#x20;       </li>

&#x20;       <li class="nav-item dropdown">

&#x20;         <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;           Dropdown

&#x20;         </a>

&#x20;         <ul class="dropdown-menu">

&#x20;           <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;           <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;           <li><hr class="dropdown-divider"></li>

&#x20;           <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;         </ul>

&#x20;       </li>

&#x20;       <li class="nav-item">

&#x20;         <a class="nav-link disabled" aria-disabled="true">Disabled</a>

&#x20;       </li>

&#x20;     </ul>

&#x20;     <form class="d-flex" role="search">

&#x20;       <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search"/>

&#x20;       <button class="btn btn-outline-success" type="submit">Search</button>

&#x20;     </form>

&#x20;   </div>

&#x20; </div>

</nav>

```



\--------------------------------



\### Live Toast Example with Trigger



Source: https://getbootstrap.com/docs/5.3/components/toasts



A button-triggered toast positioned in the bottom-right corner using utility classes.



```html

<button type="button" class="btn btn-primary" id="liveToastBtn">Show live toast</button>



<div class="toast-container position-fixed bottom-0 end-0 p-3">

&#x20; <div id="liveToast" class="toast" role="alert" aria-live="assertive" aria-atomic="true">

&#x20;   <div class="toast-header">

&#x20;     <img src="..." class="rounded me-2" alt="...">

&#x20;     <strong class="me-auto">Bootstrap</strong>

&#x20;     <small>11 mins ago</small>

&#x20;     <button type="button" class="btn-close" data-bs-dismiss="toast" aria-label="Close"></button>

&#x20;   </div>

&#x20;   <div class="toast-body">

&#x20;     Hello, world! This is a toast message.

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Basic Form Example



Source: https://getbootstrap.com/docs/5.3/forms/overview



A standard form layout using Bootstrap's form-control and form-check classes.



```html

<form>

&#x20; <div class="mb-3">

&#x20;   <label for="exampleInputEmail1" class="form-label">Email address</label>

&#x20;   <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">

&#x20;   <div id="emailHelp" class="form-text">We'll never share your email with anyone else.</div>

&#x20; </div>

&#x20; <div class="mb-3">

&#x20;   <label for="exampleInputPassword1" class="form-label">Password</label>

&#x20;   <input type="password" class="form-control" id="exampleInputPassword1">

&#x20; </div>

&#x20; <div class="mb-3 form-check">

&#x20;   <input type="checkbox" class="form-check-input" id="exampleCheck1">

&#x20;   <label class="form-check-label" for="exampleCheck1">Check me out</label>

&#x20; </div>

&#x20; <button type="submit" class="btn btn-primary">Submit</button>

</form>

```



\--------------------------------



\### Create input groups with button addons



Source: https://getbootstrap.com/docs/5.3/forms/input-group



Use these examples to place buttons on either side of an input field or group multiple buttons together.



```html

<div class="input-group mb-3">

&#x20; <button class="btn btn-outline-secondary" type="button" id="button-addon1">Button</button>

&#x20; <input type="text" class="form-control" placeholder="" aria-label="Example text with button addon" aria-describedby="button-addon1">

</div>



<div class="input-group mb-3">

&#x20; <input type="text" class="form-control" placeholder="Recipient’s username" aria-label="Recipient’s username" aria-describedby="button-addon2">

&#x20; <button class="btn btn-outline-secondary" type="button" id="button-addon2">Button</button>

</div>



<div class="input-group mb-3">

&#x20; <button class="btn btn-outline-secondary" type="button">Button</button>

&#x20; <button class="btn btn-outline-secondary" type="button">Button</button>

&#x20; <input type="text" class="form-control" placeholder="" aria-label="Example text with two button addons">

</div>



<div class="input-group">

&#x20; <input type="text" class="form-control" placeholder="Recipient’s username" aria-label="Recipient’s username with two button addons">

&#x20; <button class="btn btn-outline-secondary" type="button">Button</button>

&#x20; <button class="btn btn-outline-secondary" type="button">Button</button>

</div>

```



\--------------------------------



\### Example Code Block



Source: https://getbootstrap.com/docs/5.3/examples/blog



A basic example of a code block. This is often used for displaying code snippets or commands.



```plaintext

Example code block

```



\--------------------------------



\### Create a Media Object with Flex Utilities



Source: https://getbootstrap.com/docs/5.3/utilities/flex



Use flexbox utilities to replicate the media object component. The second example demonstrates how to vertically center content relative to the image.



```html

<div class="d-flex">

&#x20; <div class="flex-shrink-0">

&#x20;   <img src="..." alt="...">

&#x20; </div>

&#x20; <div class="flex-grow-1 ms-3">

&#x20;   This is some content from a media component. You can replace this with any content and adjust it as needed.

&#x20; </div>

</div>

```



```html

<div class="d-flex align-items-center">

&#x20; <div class="flex-shrink-0">

&#x20;   <img src="..." alt="...">

&#x20; </div>

&#x20; <div class="flex-grow-1 ms-3">

&#x20;   This is some content from a media component. You can replace this with any content and adjust it as needed.

&#x20; </div>

</div>

```



\--------------------------------



\### Applying color manipulation functions



Source: https://getbootstrap.com/docs/5.3/customize/sass



Examples of calling tint, shade, and shift functions with specific color variables and weights.



```scss

.custom-element {

&#x20; color: tint-color($primary, 10%);

}



.custom-element-2 {

&#x20; color: shade-color($danger, 30%);

}



.custom-element-3 {

&#x20; color: shift-color($success, 40%);

&#x20; background-color: shift-color($success, -60%);

}



```



\--------------------------------



\### Basic Breadcrumb Examples



Source: https://getbootstrap.com/docs/5.3/components/breadcrumb



Standard breadcrumb implementations using ordered lists with active and linked items.



```html

<nav aria-label="breadcrumb">

&#x20; <ol class="breadcrumb">

&#x20;   <li class="breadcrumb-item active" aria-current="page">Home</li>

&#x20; </ol>

</nav>



<nav aria-label="breadcrumb">

&#x20; <ol class="breadcrumb">

&#x20;   <li class="breadcrumb-item"><a href="#">Home</a></li>

&#x20;   <li class="breadcrumb-item active" aria-current="page">Library</li>

&#x20; </ol>

</nav>



<nav aria-label="breadcrumb">

&#x20; <ol class="breadcrumb">

&#x20;   <li class="breadcrumb-item"><a href="#">Home</a></li>

&#x20;   <li class="breadcrumb-item"><a href="#">Library</a></li>

&#x20;   <li class="breadcrumb-item active" aria-current="page">Data</li>

&#x20; </ol>

</nav>

```



\--------------------------------



\### Stack buttons and forms



Source: https://getbootstrap.com/docs/5.3/helpers/stacks



Examples of using stacks for common UI components like button groups and inline forms.



```html

<div class="vstack gap-2 col-md-5 mx-auto">

&#x20; <button type="button" class="btn btn-secondary">Save changes</button>

&#x20; <button type="button" class="btn btn-outline-secondary">Cancel</button>

</div>

```



```html

<div class="hstack gap-3">

&#x20; <input class="form-control me-auto" type="text" placeholder="Add your item here..." aria-label="Add your item here...">

&#x20; <button type="button" class="btn btn-secondary">Submit</button>

&#x20; <div class="vr"></div>

&#x20; <button type="button" class="btn btn-outline-danger">Reset</button>

</div>

```



\--------------------------------



\### Collapse Component Example



Source: https://getbootstrap.com/docs/5.3/components/collapse



Demonstrates using a button and an anchor tag to toggle the visibility of a card element.



```html

<p class="d-inline-flex gap-1">

&#x20; <a class="btn btn-primary" data-bs-toggle="collapse" href="#collapseExample" role="button" aria-expanded="false" aria-controls="collapseExample">

&#x20;   Link with href

&#x20; </a>

&#x20; <button class="btn btn-primary" type="button" data-bs-toggle="collapse" data-bs-target="#collapseExample" aria-expanded="false" aria-controls="collapseExample">

&#x20;   Button with data-bs-target

&#x20; </button>

</p>

<div class="collapse" id="collapseExample">

&#x20; <div class="card card-body">

&#x20;   Some placeholder content for the collapse component. This panel is hidden by default but revealed when the user activates the relevant trigger.

&#x20; </div>

</div>

```



\--------------------------------



\### Handle module resolution errors



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Example of a console error when module specifiers cannot be resolved.



```text

Uncaught TypeError: Failed to resolve module specifier "@popperjs/core". Relative references must start with either "/", "./", or "../".

```



\--------------------------------



\### Initialize project folder and npm



Source: https://getbootstrap.com/docs/5.3/getting-started/parcel



Creates a new directory and initializes a package.json file with default settings.



```bash

mkdir my-project \&\& cd my-project

npm init -y

```



\--------------------------------



\### Paragraph element example



Source: https://getbootstrap.com/docs/5.3/content/reboot



Standard paragraph element with default Bootstrap spacing.



```html

<p>This is an example paragraph.</p>

```



\--------------------------------



\### Add npm scripts to package.json



Source: https://getbootstrap.com/docs/5.3/getting-started/webpack



Configuration for start and build scripts to manage the Webpack development server and production builds.



```json

{

&#x20; // ...

&#x20; "scripts": {

&#x20;   "start": "webpack serve",

&#x20;   "build": "webpack build --mode=production",

&#x20;   "test": "echo \\"Error: no test specified\\" \&\& exit 1"

&#x20; },

&#x20; // ...

}

```



\--------------------------------



\### Initialize project structure



Source: https://getbootstrap.com/docs/5.3/getting-started/parcel



Commands to create the necessary directory and file structure for a new project.



```bash

mkdir {src,src/js,src/scss}

touch src/index.html src/js/main.js src/scss/styles.scss

```



\--------------------------------



\### Customizing columns and gaps



Source: https://getbootstrap.com/docs/5.3/layout/css-grid



Examples of adjusting column counts and gap sizes using CSS variables.



```html

<div class="grid text-center" style="--bs-columns: 4; --bs-gap: 5rem;">

&#x20; <div class="g-col-2">.g-col-2</div>

&#x20; <div class="g-col-2">.g-col-2</div>

</div>

```



```html

<div class="grid text-center" style="--bs-columns: 10; --bs-gap: 1rem;">

&#x20; <div class="g-col-6">.g-col-6</div>

&#x20; <div class="g-col-4">.g-col-4</div>

</div>

```



\--------------------------------



\### Initialize project structure



Source: https://getbootstrap.com/docs/5.3/getting-started/vite



Create the necessary directories and files for a Vite project using terminal commands.



```bash

mkdir {src,src/js,src/scss}

touch src/index.html src/js/main.js src/scss/styles.scss vite.config.js



```



\--------------------------------



\### Apply responsive float utilities



Source: https://getbootstrap.com/docs/5.3/utilities/float



Use responsive classes to apply float properties starting from specific viewport breakpoints.



```html

<div class="float-sm-end">Float end on viewports sized SM (small) or wider</div><br>

<div class="float-md-end">Float end on viewports sized MD (medium) or wider</div><br>

<div class="float-lg-end">Float end on viewports sized LG (large) or wider</div><br>

<div class="float-xl-end">Float end on viewports sized XL (extra large) or wider</div><br>

<div class="float-xxl-end">Float end on viewports sized XXL (extra extra large) or wider</div><br>

```



\--------------------------------



\### Define CSS custom properties



Source: https://getbootstrap.com/docs/5.3/docsref



Example of defining a CSS class with a custom property.



```css

.test {

&#x20; --color: blue;

}



```



\--------------------------------



\### Apply first and last order classes



Source: https://getbootstrap.com/docs/5.3/layout/columns



Use .order-first and .order-last to force elements to the start or end of the visual sequence.



```html

<div class="container text-center">

&#x20; <div class="row">

&#x20;   <div class="col order-last">

&#x20;     First in DOM, ordered last

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     Second in DOM, unordered

&#x20;   </div>

&#x20;   <div class="col order-first">

&#x20;     Third in DOM, ordered first

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Create a grid with all breakpoints



Source: https://getbootstrap.com/docs/5.3/layout/grid



Use .col and .col-\* classes to maintain consistent column sizing across all device sizes.



```html

<div class="container text-center">

&#x20; <div class="row">

&#x20;   <div class="col">col</div>

&#x20;   <div class="col">col</div>

&#x20;   <div class="col">col</div>

&#x20;   <div class="col">col</div>

&#x20; </div>

&#x20; <div class="row">

&#x20;   <div class="col-8">col-8</div>

&#x20;   <div class="col-4">col-4</div>

&#x20; </div>

</div>

```



\--------------------------------



\### Create a loading card with placeholders



Source: https://getbootstrap.com/docs/5.3/components/placeholders



Demonstrates a standard card component alongside a version using placeholders to simulate a loading state.



```html

<div class="card">

&#x20; <img src="..." class="card-img-top" alt="...">



&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20;   <a href="#" class="btn btn-primary">Go somewhere</a>

&#x20; </div>

</div>



<div class="card" aria-hidden="true">

&#x20; <img src="..." class="card-img-top" alt="...">

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title placeholder-glow">

&#x20;     <span class="placeholder col-6"></span>

&#x20;   </h5>

&#x20;   <p class="card-text placeholder-glow">

&#x20;     <span class="placeholder col-7"></span>

&#x20;     <span class="placeholder col-4"></span>

&#x20;     <span class="placeholder col-4"></span>

&#x20;     <span class="placeholder col-6"></span>

&#x20;     <span class="placeholder col-8"></span>

&#x20;   </p>

&#x20;   <a class="btn btn-primary disabled placeholder col-6" aria-disabled="true"></a>

&#x20; </div>

</div>

```



\--------------------------------



\### Align Content Flexbox Utilities



Source: https://getbootstrap.com/docs/5.3/utilities/flex



Examples of applying different align-content classes to a flex container with wrapping enabled.



```html

<div class="d-flex align-content-start flex-wrap">

&#x20; ...

</div>

```



```html

<div class="d-flex align-content-end flex-wrap">...</div>

```



```html

<div class="d-flex align-content-center flex-wrap">...</div>

```



```html

<div class="d-flex align-content-between flex-wrap">...</div>

```



```html

<div class="d-flex align-content-around flex-wrap">...</div>

```



```html

<div class="d-flex align-content-stretch flex-wrap">...</div>

```



\--------------------------------



\### View project file structure



Source: https://getbootstrap.com/docs/5.3/getting-started/vite



The expected file hierarchy for the initialized project.



```text

my-project/

├── src/

│   ├── js/

│   │   └── main.js

│   └── scss/

│   |   └── styles.scss

|   └── index.html

├── package-lock.json

├── package.json

└── vite.config.js



```



\--------------------------------



\### Add Parcel npm scripts



Source: https://getbootstrap.com/docs/5.3/getting-started/parcel



Configuration for the package.json file to include the start script for the Parcel development server.



```json

{

&#x20;  // ...

&#x20;  "scripts": {

&#x20;    "start": "parcel serve src/index.html --public-url / --dist-dir dist",

&#x20;    "test": "echo \\"Error: no test specified\\" \&\& exit 1"

&#x20;  },

&#x20;  // ...

}

```



\--------------------------------



\### Create Collapse Instance with Options



Source: https://getbootstrap.com/docs/5.3/components/collapse



Initialize a specific collapse instance with custom configuration options.



```javascript

const bsCollapse = new bootstrap.Collapse('#myCollapse', {

&#x20; toggle: false

})

```



\--------------------------------



\### Using opacity utility classes



Source: https://getbootstrap.com/docs/5.3/utilities/colors



Apply predefined opacity levels using the .text-opacity-\* utility classes.



```html

<div class="text-primary">This is default primary text</div>

<div class="text-primary text-opacity-75">This is 75% opacity primary text</div>

<div class="text-primary text-opacity-50">This is 50% opacity primary text</div>

<div class="text-primary text-opacity-25">This is 25% opacity primary text</div>

```



\--------------------------------



\### Create responsive grid layouts



Source: https://getbootstrap.com/docs/5.3/layout/css-grid



Demonstrates using responsive classes to adjust column counts based on viewport size.



```html

<div class="grid text-center">

&#x20; <div class="g-col-6 g-col-md-4">.g-col-6 .g-col-md-4</div>

&#x20; <div class="g-col-6 g-col-md-4">.g-col-6 .g-col-md-4</div>

&#x20; <div class="g-col-6 g-col-md-4">.g-col-6 .g-col-md-4</div>

</div>

```



```html

<div class="grid text-center">

&#x20; <div class="g-col-6">.g-col-6</div>

&#x20; <div class="g-col-6">.g-col-6</div>

</div>

```



\--------------------------------



\### Initializing plugins with the Programmatic API



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Constructors accept an optional configuration object or default to standard behavior.



```javascript

const myModalEl = document.querySelector('#myModal')

const modal = new bootstrap.Modal(myModalEl) // initialized with defaults



const configObject = { keyboard: false }

const modal1 = new bootstrap.Modal(myModalEl, configObject) // initialized with no keyboard

```



\--------------------------------



\### Define SCSS gradient variable



Source: https://getbootstrap.com/docs/5.3/docsref



Example of a SCSS variable definition using a linear gradient.



```scss

$gradient: linear-gradient(180deg, rgba($white, .15), rgba($white, 0));



```



\--------------------------------



\### Manage Tooltip Instances and Content



Source: https://getbootstrap.com/docs/5.3/components/tooltips



Demonstrates retrieving an existing tooltip instance and updating its content dynamically.



```javascript

const tooltip = bootstrap.Tooltip.getInstance('#example') // Returns a Bootstrap tooltip instance



// setContent example

tooltip.setContent({ '.tooltip-inner': 'another title' })

```



\--------------------------------



\### HTML5 Doctype Declaration



Source: https://getbootstrap.com/docs/5.3/getting-started/introduction



Required at the start of the document to ensure consistent styling across browsers.



```html

<!doctype html>

<html lang="en">

&#x20; ...

</html>

```



\--------------------------------



\### Disabled Checkboxes



Source: https://getbootstrap.com/docs/5.3/forms/checks



Examples of checkboxes in various states with the disabled attribute applied.



```html

<div class="form-check">

&#x20; <input class="form-check-input" type="checkbox" value="" id="checkIndeterminateDisabled" disabled>

&#x20; <label class="form-check-label" for="checkIndeterminateDisabled">

&#x20;   Disabled indeterminate checkbox

&#x20; </label>

</div>

<div class="form-check">

&#x20; <input class="form-check-input" type="checkbox" value="" id="checkDisabled" disabled>

&#x20; <label class="form-check-label" for="checkDisabled">

&#x20;   Disabled checkbox

&#x20; </label>

</div>

<div class="form-check">

&#x20; <input class="form-check-input" type="checkbox" value="" id="checkCheckedDisabled" checked disabled>

&#x20; <label class="form-check-label" for="checkCheckedDisabled">

&#x20;   Disabled checked checkbox

&#x20; </label>

</div>

```



\--------------------------------



\### Apply background opacity utilities



Source: https://getbootstrap.com/docs/5.3/utilities/background



Demonstrates using predefined .bg-opacity-\* classes to adjust background transparency.



```html

<div class="bg-success p-2 text-white">This is default success background</div>

<div class="bg-success p-2 text-white bg-opacity-75">This is 75% opacity success background</div>

<div class="bg-success p-2 text-dark bg-opacity-50">This is 50% opacity success background</div>

<div class="bg-success p-2 text-dark bg-opacity-25">This is 25% opacity success background</div>

<div class="bg-success p-2 text-dark bg-opacity-10">This is 10% opacity success background</div>

```



\--------------------------------



\### Compile Sass via CLI



Source: https://getbootstrap.com/docs/5.3/customize/sass



Install the Sass compiler globally and use the watch command to automatically compile custom Sass files into CSS.



```bash

\# Install Sass globally

npm install -g sass



\# Watch your custom Sass for changes and compile it to CSS

sass --watch ./scss/custom.scss ./css/custom.css

```



\--------------------------------



\### Compiled RTL CSS Output



Source: https://getbootstrap.com/docs/5.3/getting-started/rtl



Example of how RTLCSS directives transform standard CSS into RTL-specific CSS.



```css

/\* bootstrap.css \*/

dt {

&#x20; font-weight: 700 /\* rtl:600 \*/;

}



/\* bootstrap.rtl.css \*/

dt {

&#x20; font-weight: 600;

}

```



\--------------------------------



\### Using Color Variables in Sass



Source: https://getbootstrap.com/docs/5.3/customize/color



Example of applying color variables directly within custom Sass rules.



```scss

.alpha { color: $purple; }

.beta {

&#x20; color: $yellow-300;

&#x20; background-color: $indigo-900;

}

```



\--------------------------------



\### Apply text alignment utilities



Source: https://getbootstrap.com/docs/5.3/utilities/text



Use these classes to align text to the start, center, or end of a container, with support for responsive breakpoints.



```html

<p class="text-start">Start aligned text on all viewport sizes.</p>

<p class="text-center">Center aligned text on all viewport sizes.</p>

<p class="text-end">End aligned text on all viewport sizes.</p>



<p class="text-sm-end">End aligned text on viewports sized SM (small) or wider.</p>

<p class="text-md-end">End aligned text on viewports sized MD (medium) or wider.</p>

<p class="text-lg-end">End aligned text on viewports sized LG (large) or wider.</p>

<p class="text-xl-end">End aligned text on viewports sized XL (extra large) or wider.</p>

<p class="text-xxl-end">End aligned text on viewports sized XXL (extra extra large) or wider.</p>

```



\--------------------------------



\### RTL starter template



Source: https://getbootstrap.com/docs/5.3/getting-started/rtl



A complete HTML template configured for RTL, including the required dir and lang attributes and the RTL CSS stylesheet.



```html

<!doctype html>

<html lang="ar" dir="rtl">

&#x20; <head>

&#x20;   <!-- Required meta tags -->

&#x20;   <meta charset="utf-8">

&#x20;   <meta name="viewport" content="width=device-width, initial-scale=1">



&#x20;   <!-- Bootstrap CSS -->

&#x20;   <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.rtl.min.css" integrity="sha384-CfCrinSRH2IR6a4e6fy2q6ioOX7O6Mtm1L9vRvFZ1trBncWmMePhzvafv7oIcWiW" crossorigin="anonymous">



&#x20;   <title>مرحبًا بالعالم!</title>

&#x20; </head>

&#x20; <body>

&#x20;   <h1>مرحبًا بالعالم!</h1>



&#x20;   <!-- Optional JavaScript; choose one of the two! -->



&#x20;   <!-- Option 1: Bootstrap Bundle with Popper -->

&#x20;   <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js" integrity="sha384-FKyoEForCGlyvwx9Hj09JcYn3nv7wiPVlz7YYwJrWVcXK/BmnVDxM+D2scQbITxI" crossorigin="anonymous"></script>



&#x20;   <!-- Option 2: Separate Popper and Bootstrap JS -->

&#x20;   <!--

&#x20;   <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.8/dist/umd/popper.min.js" integrity="sha384-I7E8VVD/ismYTF4hNIPjVp/Zjvgyol6VFvRkX/vR+Vc4jQkC+hVqc2pM8ODewa9r" crossorigin="anonymous"></script>

&#x20;   <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.min.js" integrity="sha384-G/EV+4j2dNv+tEPo3++6LCgdCROaejBqfUeNjuKAiuXbjrxilcCdDz6ZAVfHWe1Y" crossorigin="anonymous"></script>

&#x20;   -->

&#x20; </body>

</html>

```



\--------------------------------



\### Project File Structure without Package Manager



Source: https://getbootstrap.com/docs/5.3/customize/sass



Recommended directory layout when manually managing Bootstrap source files.



```text

your-project/

├── scss/

│   └── custom.scss

└── bootstrap/

│   ├── js/

│   └── scss/

└── index.html

```



\--------------------------------



\### Custom Button Modifier Class



Source: https://getbootstrap.com/docs/5.3/components/buttons



Example of creating a custom button variant by overriding Bootstrap's CSS variables.



```scss

.btn-bd-primary {

&#x20; --bs-btn-font-weight: 600;

&#x20; --bs-btn-color: var(--bs-white);

&#x20; --bs-btn-bg: var(--bd-violet-bg);

&#x20; --bs-btn-border-color: var(--bd-violet-bg);

&#x20; --bs-btn-hover-color: var(--bs-white);

&#x20; --bs-btn-hover-bg: #{shade-color($bd-violet, 10%)};

&#x20; --bs-btn-hover-border-color: #{shade-color($bd-violet, 10%)};

&#x20; --bs-btn-focus-shadow-rgb: var(--bd-violet-rgb);

&#x20; --bs-btn-active-color: var(--bs-btn-hover-color);

&#x20; --bs-btn-active-bg: #{shade-color($bd-violet, 20%)};

&#x20; --bs-btn-active-border-color: #{shade-color($bd-violet, 20%)};

}

```



\--------------------------------



\### Initialize Tooltip via JavaScript



Source: https://getbootstrap.com/docs/5.3/components/tooltips



Standard initialization of a tooltip instance using a DOM element and optional configuration.



```javascript

const exampleEl = document.getElementById('example')

const tooltip = new bootstrap.Tooltip(exampleEl, options)

```



\--------------------------------



\### Retrieving plugin instances



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Use getInstance to retrieve an existing instance or getOrCreateInstance to retrieve or initialize one.



```javascript

bootstrap.Popover.getInstance(myPopoverEl)

```



```javascript

bootstrap.Popover.getOrCreateInstance(myPopoverEl, configObject)

```



\--------------------------------



\### Create Non-Autohiding Toast with Dismiss Button



Source: https://getbootstrap.com/docs/5.3/components/toasts



Example of a toast that remains visible until manually dismissed by the user, requiring a close button.



```html

<div role="alert" aria-live="assertive" aria-atomic="true" class="toast" data-bs-autohide="false">

&#x20; <div class="toast-header">

&#x20;   <img src="..." class="rounded me-2" alt="...">

&#x20;   <strong class="me-auto">Bootstrap</strong>

&#x20;   <small>11 mins ago</small>

&#x20;   <button type="button" class="btn-close" data-bs-dismiss="toast" aria-label="Close"></button>

&#x20; </div>

&#x20; <div class="toast-body">

&#x20;   Hello, world! This is a toast message.

&#x20; </div>

</div>

```



\--------------------------------



\### Initialize Carousel with Options



Source: https://getbootstrap.com/docs/5.3/components/carousel



Create a carousel instance with custom configuration options such as interval and touch support.



```javascript

const myCarouselElement = document.querySelector('#myCarousel')



const carousel = new bootstrap.Carousel(myCarouselElement, {

&#x20; interval: 2000,

&#x20; touch: false

})

```



\--------------------------------



\### Define Root CSS Variables in Sass



Source: https://getbootstrap.com/docs/5.3/content/reboot



Example of how Bootstrap defines :root CSS variables from Sass variables for body styles.



```scss

@if $font-size-root != null {

&#x20; --#{$prefix}root-font-size: #{$font-size-root};

}

\--#{$prefix}body-font-family: #{inspect($font-family-base)};

@include rfs($font-size-base, --#{$prefix}body-font-size);

\--#{$prefix}body-font-weight: #{$font-weight-base};

\--#{$prefix}body-line-height: #{$line-height-base};

@if $body-text-align != null {

&#x20; --#{$prefix}body-text-align: #{$body-text-align};

}



\--#{$prefix}body-color: #{$body-color};

\--#{$prefix}body-color-rgb: #{to-rgb($body-color)};

\--#{$prefix}body-bg: #{$body-bg};

\--#{$prefix}body-bg-rgb: #{to-rgb($body-bg)};



\--#{$prefix}emphasis-color: #{$body-emphasis-color};

\--#{$prefix}emphasis-color-rgb: #{to-rgb($body-emphasis-color)};



\--#{$prefix}secondary-color: #{$body-secondary-color};

\--#{$prefix}secondary-color-rgb: #{to-rgb($body-secondary-color)};

\--#{$prefix}secondary-bg: #{$body-secondary-bg};

\--#{$prefix}secondary-bg-rgb: #{to-rgb($body-secondary-bg)};



\--#{$prefix}tertiary-color: #{$body-tertiary-color};

\--#{$prefix}tertiary-color-rgb: #{to-rgb($body-tertiary-color)};

\--#{$prefix}tertiary-bg: #{$body-tertiary-bg};

\--#{$prefix}tertiary-bg-rgb: #{to-rgb($body-tertiary-bg)};

```



\--------------------------------



\### Configure position utilities in the API



Source: https://getbootstrap.com/docs/5.3/utilities/position



The utilities API maps properties like position, top, bottom, start, end, and translate-middle to their respective CSS values.



```scss

"position": (

&#x20; property: position,

&#x20; values: static relative absolute fixed sticky

),

"top": (

&#x20; property: top,

&#x20; values: $position-values

),

"bottom": (

&#x20; property: bottom,

&#x20; values: $position-values

),

"start": (

&#x20; property: left,

&#x20; class: start,

&#x20; values: $position-values

),

"end": (

&#x20; property: right,

&#x20; class: end,

&#x20; values: $position-values

),

"translate-middle": (

&#x20; property: transform,

&#x20; class: translate-middle,

&#x20; values: (

&#x20;   null: translate(-50%, -50%),

&#x20;   x: translateX(-50%),

&#x20;   y: translateY(-50%),

&#x20; )

),

```



\--------------------------------



\### Resetting styles with CSS variables



Source: https://getbootstrap.com/docs/5.3/customize/css-variables



Example of overriding default body font and link colors using Bootstrap's CSS variables.



```css

body {

&#x20; font: 1rem/1.5 var(--bs-font-sans-serif);

}

a {

&#x20; color: var(--bs-blue);

}

```



\--------------------------------



\### Handle Tooltip Lifecycle Events



Source: https://getbootstrap.com/docs/5.3/components/tooltips



Shows how to initialize a tooltip instance and listen for the hidden event.



```javascript

const myTooltipEl = document.getElementById('myTooltip')

const tooltip = bootstrap.Tooltip.getOrCreateInstance(myTooltipEl)



myTooltipEl.addEventListener('hidden.bs.tooltip', () => {

&#x20; // do something...

})



tooltip.hide()

```



\--------------------------------



\### Preventing default event behavior



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Use preventDefault() within an event handler to stop an action before it starts.



```javascript

const myModal = document.querySelector('#myModal')



myModal.addEventListener('show.bs.modal', event => {

&#x20; return event.preventDefault() // stops modal from being shown

})

```



\--------------------------------



\### Basic placeholder usage



Source: https://getbootstrap.com/docs/5.3/components/placeholders



Shows how to apply the placeholder class to elements and buttons.



```html

<p aria-hidden="true">

&#x20; <span class="placeholder col-6"></span>

</p>



<a class="btn btn-primary disabled placeholder col-4" aria-disabled="true"></a>

```



\--------------------------------



\### Customizing Breadcrumb Dividers



Source: https://getbootstrap.com/docs/5.3/components/breadcrumb



Examples of modifying the breadcrumb divider using CSS custom properties and Sass variables.



```html

<nav style="--bs-breadcrumb-divider: '>';" aria-label="breadcrumb">

&#x20; <ol class="breadcrumb">

&#x20;   <li class="breadcrumb-item"><a href="#">Home</a></li>

&#x20;   <li class="breadcrumb-item active" aria-current="page">Library</li>

&#x20; </ol>

</nav>

```



```scss

$breadcrumb-divider: quote(">");

```



```html

<nav style="--bs-breadcrumb-divider: url(\&#34;data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='8' height='8'%3E%3Cpath d='M2.5 0L1 1.5 3.5 4 1 6.5 2.5 8l4-4-4-4z' fill='%236c757d'/%3E%3C/svg%3E\&#34;);" aria-label="breadcrumb">

&#x20; <ol class="breadcrumb">

&#x20;   <li class="breadcrumb-item"><a href="#">Home</a></li>

&#x20;   <li class="breadcrumb-item active" aria-current="page">Library</li>

&#x20; </ol>

</nav>

```



```scss

$breadcrumb-divider: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' width='8' height='8'><path d='M2.5 0L1 1.5 3.5 4 1 6.5 2.5 8l4-4-4-4z' fill='#{$breadcrumb-divider-color}'/></svg>");

```



```html

<nav style="--bs-breadcrumb-divider: '';" aria-label="breadcrumb">

&#x20; <ol class="breadcrumb">

&#x20;   <li class="breadcrumb-item"><a href="#">Home</a></li>

&#x20;   <li class="breadcrumb-item active" aria-current="page">Library</li>

&#x20; </ol>

</nav>

```



```scss

$breadcrumb-divider: none;

```



\--------------------------------



\### Sass Min-width Breakpoint Mixins



Source: https://getbootstrap.com/docs/5.3/layout/breakpoints



Use these mixins in Sass to apply styles starting from a specific breakpoint and scaling up.



```scss

// Source mixins



// No media query necessary for xs breakpoint as it’s effectively `@media (min-width: 0) { ... }`

@include media-breakpoint-up(sm) { ... }

@include media-breakpoint-up(md) { ... }

@include media-breakpoint-up(lg) { ... }

@include media-breakpoint-up(xl) { ... }

@include media-breakpoint-up(xxl) { ... }



// Usage



// Example: Hide starting at `min-width: 0`, and then show at the `sm` breakpoint

.custom-class {

&#x20; display: none;

}

@include media-breakpoint-up(sm) {

&#x20; .custom-class {

&#x20;   display: block;

&#x20; }

}

```



\--------------------------------



\### Indicate sample output



Source: https://getbootstrap.com/docs/5.3/content/reboot



Use the <samp> tag to represent output from a computer program.



```html

<samp>This text is meant to be treated as sample output from a computer program.</samp>

```



\--------------------------------



\### Project File Structure with Package Manager



Source: https://getbootstrap.com/docs/5.3/customize/sass



Recommended directory layout when using a package manager like npm to manage Bootstrap dependencies.



```text

your-project/

├── scss/

│   └── custom.scss

└── node\_modules/

│   └── bootstrap/

│       ├── js/

│       └── scss/

└── index.html

```



\--------------------------------



\### new bootstrap.Tooltip(element, options)



Source: https://getbootstrap.com/docs/5.3/components/tooltips



Initializes a new tooltip instance on the specified element with optional configuration.



```APIDOC

\## new bootstrap.Tooltip(element, options)



\### Description

Initializes a tooltip instance for a given DOM element or selector.



\### Parameters

\- \*\*element\*\* (HTMLElement|string) - Required - The target element or CSS selector string.

\- \*\*options\*\* (object) - Optional - Configuration object for the tooltip.



\### Example

```javascript

const exampleEl = document.getElementById('example');

const tooltip = new bootstrap.Tooltip(exampleEl, {

&#x20; boundary: document.body

});

```

```



\--------------------------------



\### Initialize Modal with Options



Source: https://getbootstrap.com/docs/5.3/components/modal



Pass an optional configuration object to the constructor to customize modal behavior, such as disabling keyboard interaction.



```javascript

const myModal = new bootstrap.Modal('#myModal', {

&#x20; keyboard: false

})

```



\--------------------------------



\### Configure src/index.html



Source: https://getbootstrap.com/docs/5.3/getting-started/parcel



Basic HTML template including links to the project's Sass and JavaScript files.



```html

<!doctype html>

<html lang="en">

&#x20; <head>

&#x20;   <meta charset="utf-8">

&#x20;   <meta name="viewport" content="width=device-width, initial-scale=1">

&#x20;   <title>Bootstrap w/ Parcel</title>

&#x20;   <link rel="stylesheet" href="scss/styles.scss">

&#x20;   <script type="module" src="js/main.js"></script>

&#x20; </head>

&#x20; <body>

&#x20;   <div class="container py-4 px-3 mx-auto">

&#x20;     <h1>Hello, Bootstrap and Parcel!</h1>

&#x20;     <button class="btn btn-primary">Primary button</button>

&#x20;   </div>

&#x20; </body>

</html>

```



\--------------------------------



\### Define negative margin CSS class



Source: https://getbootstrap.com/docs/5.3/utilities/spacing



Example of a negative margin utility class that can be enabled via the $enable-negative-margins Sass variable.



```css

.mt-n1 {

&#x20; margin-top: -0.25rem !important;

}

```



\--------------------------------



\### Initialize tooltips with JavaScript



Source: https://getbootstrap.com/docs/5.3/components/tooltips



Select all elements with the data-bs-toggle attribute and initialize them as Bootstrap Tooltip instances.



```javascript

const tooltipTriggerList = document.querySelectorAll('\[data-bs-toggle="tooltip"]')

const tooltipList = \[...tooltipTriggerList].map(tooltipTriggerEl => new bootstrap.Tooltip(tooltipTriggerEl))

```



\--------------------------------



\### Implement custom component structure



Source: https://getbootstrap.com/docs/5.3/customize/components



Demonstrates the HTML structure for a custom component using a base class.



```html

<div class="callout">...</div>

```



\--------------------------------



\### Initialize Button Instance with JavaScript



Source: https://getbootstrap.com/docs/5.3/components/buttons



Create a new button instance by passing a selector to the bootstrap.Button constructor.



```javascript

const bsButton = new bootstrap.Button('#myButton')

```



\--------------------------------



\### Initialize Toasts with JavaScript



Source: https://getbootstrap.com/docs/5.3/components/toasts



Use this pattern to initialize all toast elements on a page.



```javascript

const toastElList = document.querySelectorAll('.toast')

const toastList = \[...toastElList].map(toastEl => new bootstrap.Toast(toastEl, option))

```



\--------------------------------



\### Create a basic equal-width grid layout



Source: https://getbootstrap.com/docs/5.3/layout/grid



Uses a container and row to distribute three columns equally across all viewports.



```html

<div class="container text-center">

&#x20; <div class="row">

&#x20;   <div class="col">

&#x20;     Column

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     Column

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     Column

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Initializing Bootstrap components with default exports



Source: https://getbootstrap.com/docs/5.3/customize/optimize



Import the component class and instantiate it by passing the target DOM element.



```javascript

import Modal from 'bootstrap/js/dist/modal'

const modal = new Modal(document.getElementById('myModal'))

```



\--------------------------------



\### Segmented dropdown buttons in input groups



Source: https://getbootstrap.com/docs/5.3/forms/input-group



Examples of placing segmented dropdown buttons on either the left or right side of an input field.



```html

<div class="input-group mb-3">

&#x20; <button type="button" class="btn btn-outline-secondary">Action</button>

&#x20; <button type="button" class="btn btn-outline-secondary dropdown-toggle dropdown-toggle-split" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   <span class="visually-hidden">Toggle Dropdown</span>

&#x20; </button>

&#x20; <ul class="dropdown-menu">

&#x20;   <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;   <li><hr class="dropdown-divider"></li>

&#x20;   <li><a class="dropdown-item" href="#">Separated link</a></li>

&#x20; </ul>

&#x20; <input type="text" class="form-control" aria-label="Text input with segmented dropdown button">

</div>



<div class="input-group">

&#x20; <input type="text" class="form-control" aria-label="Text input with segmented dropdown button">

&#x20; <button type="button" class="btn btn-outline-secondary">Action</button>

&#x20; <button type="button" class="btn btn-outline-secondary dropdown-toggle dropdown-toggle-split" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   <span class="visually-hidden">Toggle Dropdown</span>

&#x20; </button>

&#x20; <ul class="dropdown-menu dropdown-menu-end">

&#x20;   <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;   <li><hr class="dropdown-divider"></li>

&#x20;   <li><a class="dropdown-item" href="#">Separated link</a></li>

&#x20; </ul>

</div>

```



\--------------------------------



\### Configure vite.config.js



Source: https://getbootstrap.com/docs/5.3/getting-started/vite



Define the root directory, build output, server port, and Sass preprocessor options for Vite.



```javascript

import { resolve } from 'path'



export default {

&#x20; root: resolve(\_\_dirname, 'src'),

&#x20; build: {

&#x20;   outDir: '../dist'

&#x20; },

&#x20; server: {

&#x20;   port: 8080

&#x20; },

&#x20; // Optional: Silence Sass deprecation warnings. See note below.

&#x20; css: {

&#x20;    preprocessorOptions: {

&#x20;       scss: {

&#x20;         silenceDeprecations: \[

&#x20;           'import',

&#x20;           'mixed-decls',

&#x20;           'color-functions',

&#x20;           'global-builtin',

&#x20;         ],

&#x20;       },

&#x20;    },

&#x20; },

}



```



\--------------------------------



\### Manage Popover Instances and Content



Source: https://getbootstrap.com/docs/5.3/components/popovers



Demonstrates retrieving a popover instance and updating its content dynamically using the setContent method.



```javascript

// getOrCreateInstance example

const popover = bootstrap.Popover.getOrCreateInstance('#example') // Returns a Bootstrap popover instance



// setContent example

popover.setContent({

&#x20; '.popover-header': 'another title',

&#x20; '.popover-body': 'another content'

})

```



\--------------------------------



\### new bootstrap.Toast(element, options)



Source: https://getbootstrap.com/docs/5.3/components/toasts



Initializes a new toast instance for a given DOM element with optional configuration.



```APIDOC

\## new bootstrap.Toast(element, options)



\### Description

Initializes a new toast instance for a given DOM element.



\### Parameters

\- \*\*element\*\* (HTMLElement) - Required - The DOM element to initialize as a toast.

\- \*\*options\*\* (Object) - Optional - Configuration object for the toast.



\### Options

\- \*\*animation\*\* (boolean) - Default: true - Apply a CSS fade transition to the toast.

\- \*\*autohide\*\* (boolean) - Default: true - Automatically hide the toast after the delay.

\- \*\*delay\*\* (number) - Default: 5000 - Delay in milliseconds before hiding the toast.

```



\--------------------------------



\### File Input Variants



Source: https://getbootstrap.com/docs/5.3/forms/form-control



Demonstrates default, multiple, disabled, small, and large file input configurations.



```html

<div class="mb-3">

&#x20; <label for="formFile" class="form-label">Default file input example</label>

&#x20; <input class="form-control" type="file" id="formFile">

</div>

<div class="mb-3">

&#x20; <label for="formFileMultiple" class="form-label">Multiple files input example</label>

&#x20; <input class="form-control" type="file" id="formFileMultiple" multiple>

</div>

<div class="mb-3">

&#x20; <label for="formFileDisabled" class="form-label">Disabled file input example</label>

&#x20; <input class="form-control" type="file" id="formFileDisabled" disabled>

</div>

<div class="mb-3">

&#x20; <label for="formFileSm" class="form-label">Small file input example</label>

&#x20; <input class="form-control form-control-sm" id="formFileSm" type="file">

</div>

<div>

&#x20; <label for="formFileLg" class="form-label">Large file input example</label>

&#x20; <input class="form-control form-control-lg" id="formFileLg" type="file">

</div>

```



\--------------------------------



\### Create a basic HTML5 boilerplate



Source: https://getbootstrap.com/docs/5.3/getting-started/introduction



The initial structure for a Bootstrap project, including the required viewport meta tag for responsive design.



```html

<!doctype html>

<html lang="en">

&#x20; <head>

&#x20;   <meta charset="utf-8">

&#x20;   <meta name="viewport" content="width=device-width, initial-scale=1">

&#x20;   <title>Bootstrap demo</title>

&#x20; </head>

&#x20; <body>

&#x20;   <h1>Hello, world!</h1>

&#x20; </body>

</html>

```



\--------------------------------



\### Implement Stack and Vertical Rule Helpers



Source: https://getbootstrap.com/docs/5.3/migration



Utilize hstack and vstack for flexbox layouts and .vr for vertical dividers.



```html

.hstack

.vstack

.vr

```



\--------------------------------



\### Create a basic card with HTML



Source: https://getbootstrap.com/docs/5.3/components/card



A standard card implementation featuring an image, body content, and a call-to-action button.



```html

<div class="card" style="width: 18rem;">

&#x20; <img src="..." class="card-img-top" alt="...">

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20;   <a href="#" class="btn btn-primary">Go somewhere</a>

&#x20; </div>

</div>

```



\--------------------------------



\### Implement column wrapping



Source: https://getbootstrap.com/docs/5.3/layout/columns



Demonstrates how columns wrap to a new line when the total width exceeds 12 units.



```html

<div class="container">

&#x20; <div class="row">

&#x20;   <div class="col-9">.col-9</div>

&#x20;   <div class="col-4">.col-4<br>Since 9 + 4 = 13 \&gt; 12, this 4-column-wide div gets wrapped onto a new line as one contiguous unit.</div>

&#x20;   <div class="col-6">.col-6<br>Subsequent columns continue along the new line.</div>

&#x20; </div>

</div>

```



\--------------------------------



\### Applying colors to placeholders



Source: https://getbootstrap.com/docs/5.3/components/placeholders



Shows how to override the default color using background utility classes.



```html

<span class="placeholder col-12"></span>



<span class="placeholder col-12 bg-primary"></span>

<span class="placeholder col-12 bg-secondary"></span>

<span class="placeholder col-12 bg-success"></span>

<span class="placeholder col-12 bg-danger"></span>

<span class="placeholder col-12 bg-warning"></span>

<span class="placeholder col-12 bg-info"></span>

<span class="placeholder col-12 bg-light"></span>

<span class="placeholder col-12 bg-dark"></span>

```



\--------------------------------



\### Adding rows and placement



Source: https://getbootstrap.com/docs/5.3/layout/css-grid



Configuring grid rows and using placement classes to position items.



```html

<div class="grid text-center" style="--bs-rows: 3; --bs-columns: 3;">

&#x20; <div>Auto-column</div>

&#x20; <div class="g-start-2" style="grid-row: 2">Auto-column</div>

&#x20; <div class="g-start-3" style="grid-row: 3">Auto-column</div>

</div>

```



\--------------------------------



\### Configure Custom Bootstrap CSS Builds



Source: https://getbootstrap.com/docs/5.3/migration



Shows the required import order and map merging syntax for custom Bootstrap builds using the new \_maps.scss file.



```scss

&#x20; // Functions come first

&#x20; @import "functions";



&#x20; // Optional variable overrides here

\+ $custom-color: #df711b;

\+ $custom-theme-colors: (

\+   "custom": $custom-color

\+ );



&#x20; // Variables come next

&#x20; @import "variables";



\+ // Optional Sass map overrides here

\+ $theme-colors: map-merge($theme-colors, $custom-theme-colors);

\+

\+ // Followed by our default maps

\+ @import "maps";

\+

&#x20; // Rest of our imports

&#x20; @import "mixins";

&#x20; @import "utilities";

&#x20; @import "root";

&#x20; @import "reboot";

&#x20; // etc

```



\--------------------------------



\### Initialize a tab instance



Source: https://getbootstrap.com/docs/5.3/components/list-group



Create a new tab instance using the Bootstrap Tab constructor.



```javascript

const bsTab = new bootstrap.Tab('#myTab')

```



\--------------------------------



\### Implement a default container



Source: https://getbootstrap.com/docs/5.3/layout/containers



Use the .container class for a responsive, fixed-width container that adjusts its max-width at each breakpoint.



```html

<div class="container">

&#x20; <!-- Content here -->

</div>

```



\--------------------------------



\### Stacking Multiple Toasts



Source: https://getbootstrap.com/docs/5.3/components/toasts



Demonstrates how to use a toast-container to automatically stack multiple toast notifications.



```html

<div aria-live="polite" aria-atomic="true" class="position-relative">

&#x20; <!-- Position it: -->

&#x20; <!-- - `.toast-container` for spacing between toasts -->

&#x20; <!-- - `top-0` \& `end-0` to position the toasts in the upper right corner -->

&#x20; <!-- - `.p-3` to prevent the toasts from sticking to the edge of the container  -->

&#x20; <div class="toast-container top-0 end-0 p-3">



&#x20;   <!-- Then put toasts within -->

&#x20;   <div class="toast" role="alert" aria-live="assertive" aria-atomic="true">

&#x20;     <div class="toast-header">

&#x20;       <img src="..." class="rounded me-2" alt="...">

&#x20;       <strong class="me-auto">Bootstrap</strong>

&#x20;       <small class="text-body-secondary">just now</small>

&#x20;       <button type="button" class="btn-close" data-bs-dismiss="toast" aria-label="Close"></button>

&#x20;     </div>

&#x20;     <div class="toast-body">

&#x20;       See? Just like this.

&#x20;     </div>

&#x20;   </div>



&#x20;   <div class="toast" role="alert" aria-live="assertive" aria-atomic="true">

&#x20;     <div class="toast-header">

&#x20;       <img src="..." class="rounded me-2" alt="...">

&#x20;       <strong class="me-auto">Bootstrap</strong>

&#x20;       <small class="text-body-secondary">2 seconds ago</small>

&#x20;       <button type="button" class="btn-close" data-bs-dismiss="toast" aria-label="Close"></button>

&#x20;     </div>

&#x20;     <div class="toast-body">

&#x20;       Heads up, toasts will stack automatically

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Plugin Constructor



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Initializes a Bootstrap plugin instance on a DOM element or via a CSS selector, optionally accepting a configuration object.



```APIDOC

\## new bootstrap.Plugin(element, options?)



\### Description

Initializes a new instance of a Bootstrap plugin. The first argument can be a DOM element or a CSS selector string. The second argument is an optional configuration object.



\### Parameters

\- \*\*element\*\* (HTMLElement|string) - Required - The DOM element or CSS selector to initialize the plugin on.

\- \*\*options\*\* (Object) - Optional - Configuration object to override default settings.

```



\--------------------------------



\### Configure component with data-bs-config



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Use the experimental data-bs-config attribute to pass a JSON string for component configuration.



```html

data-bs-config='{"delay":0, "title":123}'

```



\--------------------------------



\### Configure importmap for Bootstrap and Popper



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Use an importmap to resolve module names to full paths, ensuring compatibility with dependencies.



```html

<!doctype html>

<html lang="en">

&#x20; <head>

&#x20;   <meta charset="utf-8">

&#x20;   <meta name="viewport" content="width=device-width, initial-scale=1">

&#x20;   <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB" crossorigin="anonymous">

&#x20;   <title>Hello, modularity!</title>

&#x20; </head>

&#x20; <body>

&#x20;   <h1>Hello, modularity!</h1>

&#x20;   <button id="popoverButton" type="button" class="btn btn-primary btn-lg" data-bs-toggle="popover" title="ESM in Browser" data-bs-content="Bang!">Custom popover</button>



&#x20;   <script async src="https://cdn.jsdelivr.net/npm/es-module-shims@1/dist/es-module-shims.min.js" crossorigin="anonymous"></script>

&#x20;   <script type="importmap">

&#x20;   {

&#x20;     "imports": {

&#x20;       "@popperjs/core": "https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.8/dist/esm/popper.min.js",

&#x20;       "bootstrap": "https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.esm.min.js"

&#x20;     }

&#x20;   }

&#x20;   </script>

&#x20;   <script type="module">

&#x20;     import \* as bootstrap from 'bootstrap'



&#x20;     new bootstrap.Popover(document.getElementById('popoverButton'))

&#x20;   </script>

&#x20; </body>

</html>

```



\--------------------------------



\### Initialize Bootstrap components as an ES module



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Use the ESM build of Bootstrap directly in the browser with a module script tag.



```html

<script type="module">

&#x20; import { Toast } from 'bootstrap.esm.min.js'



&#x20; Array.from(document.querySelectorAll('.toast'))

&#x20;   .forEach(toastNode => new Toast(toastNode))

</script>

```



\--------------------------------



\### Create src/index.html



Source: https://getbootstrap.com/docs/5.3/getting-started/webpack



The base HTML file that Webpack will load in the browser.



```html

<!doctype html>

<html lang="en">

&#x20; <head>

&#x20;   <meta charset="utf-8">

&#x20;   <meta name="viewport" content="width=device-width, initial-scale=1">

&#x20;   <title>Bootstrap w/ Webpack</title>

&#x20; </head>

&#x20; <body>

&#x20;   <div class="container py-4 px-3 mx-auto">

&#x20;     <h1>Hello, Bootstrap and Webpack!</h1>

&#x20;     <button class="btn btn-primary">Primary button</button>

&#x20;   </div>

&#x20; </body>

</html>



```



\--------------------------------



\### Create a stacked to horizontal grid



Source: https://getbootstrap.com/docs/5.3/layout/grid



Apply .col-sm-\* classes to stack columns on extra small devices and transition to horizontal layouts at the small breakpoint.



```html

<div class="container text-center">

&#x20; <div class="row">

&#x20;   <div class="col-sm-8">col-sm-8</div>

&#x20;   <div class="col-sm-4">col-sm-4</div>

&#x20; </div>

&#x20; <div class="row">

&#x20;   <div class="col-sm">col-sm</div>

&#x20;   <div class="col-sm">col-sm</div>

&#x20;   <div class="col-sm">col-sm</div>

&#x20; </div>

</div>

```



\--------------------------------



\### Create src/index.html



Source: https://getbootstrap.com/docs/5.3/getting-started/vite



The entry HTML file that loads the main JavaScript module and includes basic Bootstrap classes.



```html

<!doctype html>

<html lang="en">

&#x20; <head>

&#x20;   <meta charset="utf-8">

&#x20;   <meta name="viewport" content="width=device-width, initial-scale=1">

&#x20;   <title>Bootstrap w/ Vite</title>

&#x20;   <script type="module" src="./js/main.js"></script>

&#x20; </head>

&#x20; <body>

&#x20;   <div class="container py-4 px-3 mx-auto">

&#x20;     <h1>Hello, Bootstrap and Vite!</h1>

&#x20;     <button class="btn btn-primary">Primary button</button>

&#x20;   </div>

&#x20; </body>

</html>



```



\--------------------------------



\### Create responsive images



Source: https://getbootstrap.com/docs/5.3/content/images



Apply the .img-fluid class to make images scale with their parent width.



```html

<img src="..." class="img-fluid" alt="...">

```



\--------------------------------



\### Create a basic accordion with HTML



Source: https://getbootstrap.com/docs/5.3/components/accordion



Uses the .accordion class to group multiple .accordion-item elements. Each item requires a header with a button and a corresponding collapse body.



```html

<div class="accordion" id="accordionExample">

&#x20; <div class="accordion-item">

&#x20;   <h2 class="accordion-header">

&#x20;     <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">

&#x20;       Accordion Item #1

&#x20;     </button>

&#x20;   </h2>

&#x20;   <div id="collapseOne" class="accordion-collapse collapse show" data-bs-parent="#accordionExample">

&#x20;     <div class="accordion-body">

&#x20;       <strong>This is the first item’s accordion body.</strong> It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It’s also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="accordion-item">

&#x20;   <h2 class="accordion-header">

&#x20;     <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseTwo" aria-expanded="false" aria-controls="collapseTwo">

&#x20;       Accordion Item #2

&#x20;     </button>

&#x20;   </h2>

&#x20;   <div id="collapseTwo" class="accordion-collapse collapse" data-bs-parent="#accordionExample">

&#x20;     <div class="accordion-body">

&#x20;       <strong>This is the second item’s accordion body.</strong> It is hidden by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It’s also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="accordion-item">

&#x20;   <h2 class="accordion-header">

&#x20;     <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseThree" aria-expanded="false" aria-controls="collapseThree">

&#x20;       Accordion Item #3

&#x20;     </button>

&#x20;   </h2>

&#x20;   <div id="collapseThree" class="accordion-collapse collapse" data-bs-parent="#accordionExample">

&#x20;     <div class="accordion-body">

&#x20;       <strong>This is the third item’s accordion body.</strong> It is hidden by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It’s also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Animating placeholders



Source: https://getbootstrap.com/docs/5.3/components/placeholders



Shows how to add glow or wave animations to placeholders.



```html

<p class="placeholder-glow">

&#x20; <span class="placeholder col-12"></span>

</p>



<p class="placeholder-wave">

&#x20; <span class="placeholder col-12"></span>

</p>

```



\--------------------------------



\### Single Breakpoint Mixins and Output



Source: https://getbootstrap.com/docs/5.3/layout/breakpoints



Target a specific screen size segment using min and max width constraints.



```scss

@include media-breakpoint-only(xs) { ... }

@include media-breakpoint-only(sm) { ... }

@include media-breakpoint-only(md) { ... }

@include media-breakpoint-only(lg) { ... }

@include media-breakpoint-only(xl) { ... }

@include media-breakpoint-only(xxl) { ... }

```



```css

@media (min-width: 768px) and (max-width: 991.98px) { ... }

```



\--------------------------------



\### Initialize Bootstrap components with jQuery



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Use these methods to enable or configure Bootstrap components when jQuery is detected in the window object.



```javascript

// to enable tooltips with the default configuration

$('\[data-bs-toggle="tooltip"]').tooltip()



// to initialize tooltips with given configuration

$('\[data-bs-toggle="tooltip"]').tooltip({

&#x20; boundary: 'clippingParents',

&#x20; customClass: 'myClass'

})



// to trigger the `show` method

$('#myTooltip').tooltip('show')

```



\--------------------------------



\### new bootstrap.Modal(target, options)



Source: https://getbootstrap.com/docs/5.3/components/modal



Initializes a modal instance for a given DOM element or selector.



```APIDOC

\## new bootstrap.Modal(target, options)



\### Description

Activates your content as a modal. Accepts an optional options object.



\### Parameters

\- \*\*target\*\* (string|Element) - Required - The DOM element or selector string for the modal.

\- \*\*options\*\* (object) - Optional - Configuration object for the modal.



\### Options

\- \*\*backdrop\*\* (boolean|string) - Default: true - Includes a modal-backdrop element. Use 'static' for a backdrop that doesn't close the modal when clicked.

\- \*\*focus\*\* (boolean) - Default: true - Puts the focus on the modal when initialized.

\- \*\*keyboard\*\* (boolean) - Default: true - Closes the modal when the escape key is pressed.

```



\--------------------------------



\### Create responsive stacked buttons



Source: https://getbootstrap.com/docs/5.3/components/buttons



Uses the d-md-block utility to switch from a grid stack to block layout at the md breakpoint.



```html

<div class="d-grid gap-2 d-md-block">

&#x20; <button class="btn btn-primary" type="button">Button</button>

&#x20; <button class="btn btn-primary" type="button">Button</button>

</div>

```



\--------------------------------



\### Project directory layout



Source: https://getbootstrap.com/docs/5.3/getting-started/parcel



Visual representation of the expected project file structure.



```text

my-project/

├── src/

│   ├── js/

│   │   └── main.js

│   ├── scss/

│   │   └── styles.scss

│   └── index.html

├── package-lock.json

└── package.json

```



\--------------------------------



\### Create a basic button group



Source: https://getbootstrap.com/docs/5.3/components/button-group



Wrap a series of buttons with the .btn class inside a .btn-group container.



```html

<div class="btn-group" role="group" aria-label="Basic example">

&#x20; <button type="button" class="btn btn-primary">Left</button>

&#x20; <button type="button" class="btn btn-primary">Middle</button>

&#x20; <button type="button" class="btn btn-primary">Right</button>

</div>

```



\--------------------------------



\### Enable responsive utility classes



Source: https://getbootstrap.com/docs/5.3/utilities/api



Set the responsive property to true within a utility map to generate breakpoint-specific variations.



```scss

@import "bootstrap/scss/functions";

@import "bootstrap/scss/variables";

@import "bootstrap/scss/variables-dark";

@import "bootstrap/scss/maps";

@import "bootstrap/scss/mixins";

@import "bootstrap/scss/utilities";



$utilities: map-merge(

&#x20; $utilities,

&#x20; (

&#x20;   "border": map-merge(

&#x20;     map-get($utilities, "border"),

&#x20;     ( responsive: true ),

&#x20;   ),

&#x20; )

);



@import "bootstrap/scss/utilities/api";

```



```css

.border { ... }

.border-0 { ... }



@media (min-width: 576px) {

&#x20; .border-sm { ... }

&#x20; .border-sm-0 { ... }

}



@media (min-width: 768px) {

&#x20; .border-md { ... }

&#x20; .border-md-0 { ... }

}



@media (min-width: 992px) {

&#x20; .border-lg { ... }

&#x20; .border-lg-0 { ... }

}



@media (min-width: 1200px) {

&#x20; .border-xl { ... }

&#x20; .border-xl-0 { ... }

}



@media (min-width: 1400px) {

&#x20; .border-xxl { ... }

&#x20; .border-xxl-0 { ... }

}

```



\--------------------------------



\### new bootstrap.Popover(element, options)



Source: https://getbootstrap.com/docs/5.3/components/popovers



Initializes a new popover instance for a given DOM element with optional configuration.



```APIDOC

\## new bootstrap.Popover(element, options)



\### Description

Initializes a popover instance for the specified DOM element. The `options` parameter is an object that configures the behavior and appearance of the popover.



\### Parameters

\- \*\*element\*\* (HTMLElement) - Required - The DOM element to attach the popover to.

\- \*\*options\*\* (Object) - Optional - Configuration object containing settings like `animation`, `delay`, `html`, etc.

```



\--------------------------------



\### bootstrap.Button Constructor



Source: https://getbootstrap.com/docs/5.3/components/buttons



Initializes a new button instance for a given DOM element.



```APIDOC

\## new bootstrap.Button(element)



\### Description

Creates a new button instance associated with the provided DOM element or selector.



\### Usage

```javascript

const bsButton = new bootstrap.Button('#myButton')

```

```



\--------------------------------



\### Implement Card Image Caps



Source: https://getbootstrap.com/docs/5.3/components/card



Use .card-img-top or .card-img-bottom to place images at the top or bottom of a card.



```html

<div class="card mb-3">

&#x20; <img src="..." class="card-img-top" alt="...">

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Card title</h5>

&#x20;   <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>

&#x20;   <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>

&#x20; </div>

</div>

<div class="card">

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Card title</h5>

&#x20;   <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>

&#x20;   <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>

&#x20; </div>

&#x20; <img src="..." class="card-img-bottom" alt="...">

</div>

```



\--------------------------------



\### Initialize Dropdowns via JavaScript



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



Select elements with the dropdown-toggle class and instantiate them using the bootstrap.Dropdown constructor.



```javascript

const dropdownElementList = document.querySelectorAll('.dropdown-toggle')

const dropdownList = \[...dropdownElementList].map(dropdownToggleEl => new bootstrap.Dropdown(dropdownToggleEl))

```



\--------------------------------



\### Apply Z-index Utilities



Source: https://getbootstrap.com/docs/5.3/utilities/z-index



Demonstrates applying z-index classes to elements with absolute positioning.



```html

<div class="z-3 position-absolute p-5 rounded-3"><span>z-3</span></div>

<div class="z-2 position-absolute p-5 rounded-3"><span>z-2</span></div>

<div class="z-1 position-absolute p-5 rounded-3"><span>z-1</span></div>

<div class="z-0 position-absolute p-5 rounded-3"><span>z-0</span></div>

<div class="z-n1 position-absolute p-5 rounded-3"><span>z-n1</span></div>

```



\--------------------------------



\### Implement static backdrop for offcanvas



Source: https://getbootstrap.com/docs/5.3/components/offcanvas



Set the backdrop to static to prevent the offcanvas from closing when clicking outside of it.



```html

<button class="btn btn-primary" type="button" data-bs-toggle="offcanvas" data-bs-target="#staticBackdrop" aria-controls="staticBackdrop">

&#x20; Toggle static offcanvas

</button>



<div class="offcanvas offcanvas-start" data-bs-backdrop="static" tabindex="-1" id="staticBackdrop" aria-labelledby="staticBackdropLabel">

&#x20; <div class="offcanvas-header">

&#x20;   <h5 class="offcanvas-title" id="staticBackdropLabel">Offcanvas</h5>

&#x20;   <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>

&#x20; </div>

&#x20; <div class="offcanvas-body">

&#x20;   <div>

&#x20;     I will not close if you click outside of me.

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Create compact tables



Source: https://getbootstrap.com/docs/5.3/content/tables



Use .table-sm to reduce cell padding by half for a more compact layout.



```html

<table class="table table-sm">

&#x20; ...

</table>

```



```html

<table class="table table-dark table-sm">

&#x20; ...

</table>

```



\--------------------------------



\### Apply font weight and style utilities



Source: https://getbootstrap.com/docs/5.3/utilities/text



Use .fw-\* classes for font weight and .fst-\* classes for font style.



```html

<p class="fw-bold">Bold text.</p>

<p class="fw-bolder">Bolder weight text (relative to the parent element).</p>

<p class="fw-semibold">Semibold weight text.</p>

<p class="fw-medium">Medium weight text.</p>

<p class="fw-normal">Normal weight text.</p>

<p class="fw-light">Light weight text.</p>

<p class="fw-lighter">Lighter weight text (relative to the parent element).</p>

<p class="fst-italic">Italic text.</p>

<p class="fst-normal">Text with normal font style</p>

```



\--------------------------------



\### Apply color variants to growing spinners



Source: https://getbootstrap.com/docs/5.3/components/spinners



Demonstrates applying Bootstrap text color utilities to change the appearance of growing spinners.



```html

<div class="spinner-grow text-primary" role="status">

&#x20; <span class="visually-hidden">Loading...</span>

</div>

<div class="spinner-grow text-secondary" role="status">

&#x20; <span class="visually-hidden">Loading...</span>

</div>

<div class="spinner-grow text-success" role="status">

&#x20; <span class="visually-hidden">Loading...</span>

</div>

<div class="spinner-grow text-danger" role="status">

&#x20; <span class="visually-hidden">Loading...</span>

</div>

<div class="spinner-grow text-warning" role="status">

&#x20; <span class="visually-hidden">Loading...</span>

</div>

<div class="spinner-grow text-info" role="status">

&#x20; <span class="visually-hidden">Loading...</span>

</div>

<div class="spinner-grow text-light" role="status">

&#x20; <span class="visually-hidden">Loading...</span>

</div>

<div class="spinner-grow text-dark" role="status">

&#x20; <span class="visually-hidden">Loading...</span>

</div>

```



\--------------------------------



\### Apply horizontal and vertical gutters with .g-\*



Source: https://getbootstrap.com/docs/5.3/layout/gutters



Use .g-\* classes to set both horizontal and vertical gutters simultaneously.



```html

<div class="container text-center">

&#x20; <div class="row g-2">

&#x20;   <div class="col-6">

&#x20;     <div class="p-3">Custom column padding</div>

&#x20;   </div>

&#x20;   <div class="col-6">

&#x20;     <div class="p-3">Custom column padding</div>

&#x20;   </div>

&#x20;   <div class="col-6">

&#x20;     <div class="p-3">Custom column padding</div>

&#x20;   </div>

&#x20;   <div class="col-6">

&#x20;     <div class="p-3">Custom column padding</div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Responsive Object Fit Classes



Source: https://getbootstrap.com/docs/5.3/utilities/object-fit



Use breakpoint-specific classes to change object-fit behavior based on screen size.



```html

<img src="..." class="object-fit-sm-contain border rounded" alt="...">

<img src="..." class="object-fit-md-contain border rounded" alt="...">

<img src="..." class="object-fit-lg-contain border rounded" alt="...">

<img src="..." class="object-fit-xl-contain border rounded" alt="...">

<img src="..." class="object-fit-xxl-contain border rounded" alt="...">

```



\--------------------------------



\### Implement abbreviations with HTML



Source: https://getbootstrap.com/docs/5.3/content/typography



Use the <abbr> element to provide expanded text on hover. Add the .initialism class for a smaller font size.



```html

<p><abbr title="attribute">attr</abbr></p>

<p><abbr title="HyperText Markup Language" class="initialism">HTML</abbr></p>

```



\--------------------------------



\### Apply basic float utilities



Source: https://getbootstrap.com/docs/5.3/utilities/float



Use these classes to set the float property on elements across all viewport sizes.



```html

<div class="float-start">Float start on all viewport sizes</div><br>

<div class="float-end">Float end on all viewport sizes</div><br>

<div class="float-none">Don’t float on all viewport sizes</div>

```



\--------------------------------



\### Adjusting horizontal gutters with padding utilities



Source: https://getbootstrap.com/docs/5.3/layout/gutters



Use .gx-\* classes for gutter width and apply padding utilities like .px-4 to the container to prevent overflow.



```html

<div class="container px-4 text-center">

&#x20; <div class="row gx-5">

&#x20;   <div class="col">

&#x20;     <div class="p-3">Custom column padding</div>

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     <div class="p-3">Custom column padding</div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Create a standard link



Source: https://getbootstrap.com/docs/5.3/content



Basic anchor tag with default Bootstrap link styling.



```html

<a href="#">This is an example link</a>

```



\--------------------------------



\### Responsive Nav with Flexbox Utilities



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



Uses flexbox utilities to create a navigation component that stacks vertically on small screens and expands horizontally on larger viewports.



```html

<nav class="nav nav-pills flex-column flex-sm-row">

&#x20; <a class="flex-sm-fill text-sm-center nav-link active" aria-current="page" href="#">Active</a>

&#x20; <a class="flex-sm-fill text-sm-center nav-link" href="#">Longer nav link</a>

&#x20; <a class="flex-sm-fill text-sm-center nav-link" href="#">Link</a>

&#x20; <a class="flex-sm-fill text-sm-center nav-link disabled" aria-disabled="true">Disabled</a>

</nav>

```



\--------------------------------



\### Between Breakpoints Mixins and Output



Source: https://getbootstrap.com/docs/5.3/layout/breakpoints



Target a range of screen sizes spanning multiple breakpoints.



```scss

@include media-breakpoint-between(md, xl) { ... }

```



```css

// Example

// Apply styles starting from medium devices and up to extra large devices

@media (min-width: 768px) and (max-width: 1199.98px) { ... }

```



\--------------------------------



\### Apply Shadow Utility Classes



Source: https://getbootstrap.com/docs/5.3/utilities/shadows



Use these classes to apply different shadow sizes or remove shadows from elements.



```html

<div class="shadow-none p-3 mb-5 bg-body-tertiary rounded">No shadow</div>

<div class="shadow-sm p-3 mb-5 bg-body-tertiary rounded">Small shadow</div>

<div class="shadow p-3 mb-5 bg-body-tertiary rounded">Regular shadow</div>

<div class="shadow-lg p-3 mb-5 bg-body-tertiary rounded">Larger shadow</div>

```



\--------------------------------



\### Configure background utilities API



Source: https://getbootstrap.com/docs/5.3/utilities/background



Defines background color and opacity utilities within the Bootstrap utilities API map.



```scss

"background-color": (

&#x20; property: background-color,

&#x20; class: bg,

&#x20; local-vars: (

&#x20;   "bg-opacity": 1

&#x20; ),

&#x20; values: map-merge(

&#x20;   $utilities-bg-colors,

&#x20;   (

&#x20;     "transparent": transparent,

&#x20;     "body-secondary": rgba(var(--#{$prefix}secondary-bg-rgb), var(--#{$prefix}bg-opacity)),

&#x20;     "body-tertiary": rgba(var(--#{$prefix}tertiary-bg-rgb), var(--#{$prefix}bg-opacity)),

&#x20;   )

&#x20; )

),

"bg-opacity": (

&#x20; css-var: true,

&#x20; class: bg-opacity,

&#x20; values: (

&#x20;   10: .1,

&#x20;   25: .25,

&#x20;   50: .5,

&#x20;   75: .75,

&#x20;   100: 1

&#x20; )

),

"subtle-background-color": (

&#x20; property: background-color,

&#x20; class: bg,

&#x20; values: $utilities-bg-subtle

),

```



\--------------------------------



\### Create a horizontal card with grid utilities



Source: https://getbootstrap.com/docs/5.3/components/card



Uses the grid system with .g-0 and .col-md-\* classes to create a responsive horizontal layout.



```html

<div class="card mb-3" style="max-width: 540px;">

&#x20; <div class="row g-0">

&#x20;   <div class="col-md-4">

&#x20;     <img src="..." class="img-fluid rounded-start" alt="...">

&#x20;   </div>

&#x20;   <div class="col-md-8">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>

&#x20;       <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Create image thumbnails



Source: https://getbootstrap.com/docs/5.3/content/images



Use the .img-thumbnail class to add a rounded 1px border to an image.



```html

<img src="..." class="img-thumbnail" alt="...">

```



\--------------------------------



\### bootstrap.Collapse Constructor



Source: https://getbootstrap.com/docs/5.3/components/collapse



Initializes a new collapse instance for a given element with optional configuration.



```APIDOC

\## new bootstrap.Collapse(element, options?)



\### Description

Activates content as a collapsible element.



\### Parameters

\- \*\*element\*\* (string | Element) - Required - A CSS selector or DOM element to initialize.

\- \*\*options\*\* (object) - Optional - Configuration object.



\### Options

\- \*\*parent\*\* (selector | DOM element) - Default: null - If provided, all collapsible elements under the specified parent will be closed when this item is shown.

\- \*\*toggle\*\* (boolean) - Default: true - Toggles the collapsible element on invocation.

```



\--------------------------------



\### Sanitizer Configuration



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



How to customize the allowList or provide a custom sanitize function for tooltips and popovers.



```APIDOC

\## Sanitizer Configuration



\### Modifying the allowList

You can extend the default `allowList` to permit additional tags or attributes.



```javascript

const myDefaultAllowList = bootstrap.Tooltip.Default.allowList

myDefaultAllowList.table = \[]

myDefaultAllowList.td = \['data-bs-option']

myDefaultAllowList\['\*'].push(/^data-my-app-\[\\w-]+/)

```



\### Custom sanitizeFn

You can replace the default sanitizer with a custom function, such as DOMPurify.



```javascript

const tooltip = new bootstrap.Tooltip(element, {

&#x20; sanitizeFn(content) {

&#x20;   return DOMPurify.sanitize(content)

&#x20; }

})

```



\--------------------------------



\### Apply the base button class



Source: https://getbootstrap.com/docs/5.3/components/buttons



The .btn class provides foundational padding and alignment. Custom focus and hover styles should be added when using this class alone.



```html

<button type="button" class="btn">Base class</button>

```



\--------------------------------



\### Import Individual Bootstrap Plugins



Source: https://getbootstrap.com/docs/5.3/getting-started/parcel



Import specific plugins or components to reduce the final bundle size.



```javascript

import Alert from 'bootstrap/js/dist/alert'



// or, specify which plugins you need:

import { Tooltip, Toast, Popover } from 'bootstrap'

```



\--------------------------------



\### Implement responsive containers



Source: https://getbootstrap.com/docs/5.3/layout/containers



Responsive containers remain 100% wide until the specified breakpoint is reached, after which they apply max-widths.



```html

<div class="container-sm">100% wide until small breakpoint</div>

<div class="container-md">100% wide until medium breakpoint</div>

<div class="container-lg">100% wide until large breakpoint</div>

<div class="container-xl">100% wide until extra large breakpoint</div>

<div class="container-xxl">100% wide until extra extra large breakpoint</div>

```



\--------------------------------



\### Implement standard pagination



Source: https://getbootstrap.com/docs/5.3/components/pagination



A basic pagination structure using a nav element and an unordered list of page links.



```html

<nav aria-label="Page navigation example">

&#x20; <ul class="pagination">

&#x20;   <li class="page-item"><a class="page-link" href="#">Previous</a></li>

&#x20;   <li class="page-item"><a class="page-link" href="#">1</a></li>

&#x20;   <li class="page-item"><a class="page-link" href="#">2</a></li>

&#x20;   <li class="page-item"><a class="page-link" href="#">3</a></li>

&#x20;   <li class="page-item"><a class="page-link" href="#">Next</a></li>

&#x20; </ul>

</nav>

```



\--------------------------------



\### Create a basic button toolbar



Source: https://getbootstrap.com/docs/5.3/components/button-group



Combine multiple button groups into a single toolbar using the btn-toolbar class.



```html

<div class="btn-toolbar" role="toolbar" aria-label="Toolbar with button groups">

&#x20; <div class="btn-group me-2" role="group" aria-label="First group">

&#x20;   <button type="button" class="btn btn-primary">1</button>

&#x20;   <button type="button" class="btn btn-primary">2</button>

&#x20;   <button type="button" class="btn btn-primary">3</button>

&#x20;   <button type="button" class="btn btn-primary">4</button>

&#x20; </div>

&#x20; <div class="btn-group me-2" role="group" aria-label="Second group">

&#x20;   <button type="button" class="btn btn-secondary">5</button>

&#x20;   <button type="button" class="btn btn-secondary">6</button>

&#x20;   <button type="button" class="btn btn-secondary">7</button>

&#x20; </div>

&#x20; <div class="btn-group" role="group" aria-label="Third group">

&#x20;   <button type="button" class="btn btn-info">8</button>

&#x20; </div>

</div>

```



\--------------------------------



\### Implement live alert trigger



Source: https://getbootstrap.com/docs/5.3/components/alerts



HTML markup required to host and trigger dynamic alerts.



```html

<div id="liveAlertPlaceholder"></div>

<button type="button" class="btn btn-primary" id="liveAlertBtn">Show live alert</button>

```



\--------------------------------



\### Apply Opacity Utilities



Source: https://getbootstrap.com/docs/5.3/utilities/opacity



Use these classes to set the transparency level of an element.



```html

<div class="opacity-100">...</div>

<div class="opacity-75">...</div>

<div class="opacity-50">...</div>

<div class="opacity-25">...</div>

<div class="opacity-0">...</div>

```



\--------------------------------



\### Sizing placeholders



Source: https://getbootstrap.com/docs/5.3/components/placeholders



Demonstrates using sizing modifiers to match parent typographic styles.



```html

<span class="placeholder col-12 placeholder-lg"></span>

<span class="placeholder col-12"></span>

<span class="placeholder col-12 placeholder-sm"></span>

<span class="placeholder col-12 placeholder-xs"></span>

```



\--------------------------------



\### Programmatically Activate List Items



Source: https://getbootstrap.com/docs/5.3/components/list-group



Demonstrates how to trigger specific tabs using the bootstrap.Tab instance methods.



```javascript

const triggerEl = document.querySelector('#myTab a\[href="#profile"]')

bootstrap.Tab.getInstance(triggerEl).show() // Select tab by name



const triggerFirstTabEl = document.querySelector('#myTab li:first-child a')

bootstrap.Tab.getInstance(triggerFirstTabEl).show() // Select first tab

```



\--------------------------------



\### Load CSS and Bootstrap JS



Source: https://getbootstrap.com/docs/5.3/getting-started/vite



Configure the main JavaScript file to import the compiled styles and the full Bootstrap library.



```javascript

// Import our custom CSS

import '../scss/styles.scss'



// Import all of Bootstrap’s JS

import \* as bootstrap from 'bootstrap'

```



\--------------------------------



\### Implement a responsive offcanvas



Source: https://getbootstrap.com/docs/5.3/components/offcanvas



Uses responsive classes like .offcanvas-lg to control visibility based on viewport breakpoints. Requires a toggle button with matching data-bs-target.



```html

<button class="btn btn-primary d-lg-none" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasResponsive" aria-controls="offcanvasResponsive">Toggle offcanvas</button>



<div class="alert alert-info d-none d-lg-block">Resize your browser to show the responsive offcanvas toggle.</div>



<div class="offcanvas-lg offcanvas-end" tabindex="-1" id="offcanvasResponsive" aria-labelledby="offcanvasResponsiveLabel">

&#x20; <div class="offcanvas-header">

&#x20;   <h5 class="offcanvas-title" id="offcanvasResponsiveLabel">Responsive offcanvas</h5>

&#x20;   <button type="button" class="btn-close" data-bs-dismiss="offcanvas" data-bs-target="#offcanvasResponsive" aria-label="Close"></button>

&#x20; </div>

&#x20; <div class="offcanvas-body">

&#x20;   <p class="mb-0">This is content within an <code>.offcanvas-lg</code>.</p>

&#x20; </div>

</div>

```



\--------------------------------



\### Apply font size utilities



Source: https://getbootstrap.com/docs/5.3/utilities/text



Use .fs-\* classes to set font sizes matching HTML heading elements.



```html

<p class="fs-1">.fs-1 text</p>

<p class="fs-2">.fs-2 text</p>

<p class="fs-3">.fs-3 text</p>

<p class="fs-4">.fs-4 text</p>

<p class="fs-5">.fs-5 text</p>

<p class="fs-6">.fs-6 text</p>

```



\--------------------------------



\### Generate Responsive Utility Classes



Source: https://getbootstrap.com/docs/5.3/utilities/api



Set the responsive boolean to true to generate utility classes across all defined breakpoints.



```scss

$utilities: (

&#x20; "opacity": (

&#x20;   property: opacity,

&#x20;   responsive: true,

&#x20;   values: (

&#x20;     0: 0,

&#x20;     25: .25,

&#x20;     50: .5,

&#x20;     75: .75,

&#x20;     100: 1,

&#x20;   )

&#x20; )

);

```



```css

.opacity-0 { opacity: 0 !important; }

.opacity-25 { opacity: .25 !important; }

.opacity-50 { opacity: .5 !important; }

.opacity-75 { opacity: .75 !important; }

.opacity-100 { opacity: 1 !important; }



@media (min-width: 576px) {

&#x20; .opacity-sm-0 { opacity: 0 !important; }

&#x20; .opacity-sm-25 { opacity: .25 !important; }

&#x20; .opacity-sm-50 { opacity: .5 !important; }

&#x20; .opacity-sm-75 { opacity: .75 !important; }

&#x20; .opacity-sm-100 { opacity: 1 !important; }

}



@media (min-width: 768px) {

&#x20; .opacity-md-0 { opacity: 0 !important; }

&#x20; .opacity-md-25 { opacity: .25 !important; }

&#x20; .opacity-md-50 { opacity: .5 !important; }

&#x20; .opacity-md-75 { opacity: .75 !important; }

&#x20; .opacity-md-100 { opacity: 1 !important; }

}



@media (min-width: 992px) {

&#x20; .opacity-lg-0 { opacity: 0 !important; }

&#x20; .opacity-lg-25 { opacity: .25 !important; }

&#x20; .opacity-lg-50 { opacity: .5 !important; }

&#x20; .opacity-lg-75 { opacity: .75 !important; }

&#x20; .opacity-lg-100 { opacity: 1 !important; }

}



@media (min-width: 1200px) {

&#x20; .opacity-xl-0 { opacity: 0 !important; }

&#x20; .opacity-xl-25 { opacity: .25 !important; }

&#x20; .opacity-xl-50 { opacity: .5 !important; }

&#x20; .opacity-xl-75 { opacity: .75 !important; }

&#x20; .opacity-xl-100 { opacity: 1 !important; }

}



@media (min-width: 1400px) {

&#x20; .opacity-xxl-0 { opacity: 0 !important; }

&#x20; .opacity-xxl-25 { opacity: .25 !important; }

&#x20; .opacity-xxl-50 { opacity: .5 !important; }

&#x20; .opacity-xxl-75 { opacity: .75 !important; }

&#x20; .opacity-xxl-100 { opacity: 1 !important; }

}

```



\--------------------------------



\### Apply font-size with RFS mixin



Source: https://getbootstrap.com/docs/5.3/getting-started/rfs



Demonstrates the source Sass and the resulting compiled CSS for a responsive font-size.



```scss

.title {

&#x20; @include font-size(4rem);

}

```



```css

.title {

&#x20; font-size: calc(1.525rem + 3.3vw);

}



@media (min-width: 1200px) {

&#x20; .title {

&#x20;   font-size: 4rem;

&#x20; }

}

```



\--------------------------------



\### Create standard form controls



Source: https://getbootstrap.com/docs/5.3/forms/form-control



Basic implementation of email input and textarea fields using the form-control class.



```html

<div class="mb-3">

&#x20; <label for="exampleFormControlInput1" class="form-label">Email address</label>

&#x20; <input type="email" class="form-control" id="exampleFormControlInput1" placeholder="name@example.com">

</div>

<div class="mb-3">

&#x20; <label for="exampleFormControlTextarea1" class="form-label">Example textarea</label>

&#x20; <textarea class="form-control" id="exampleFormControlTextarea1" rows="3"></textarea>

</div>

```



\--------------------------------



\### Configure CSS Grid Variables



Source: https://getbootstrap.com/docs/5.3/layout/css-grid



Customize column counts and gutter sizes using CSS variables on the grid container.



```css

\--bs-columns: 12;

\--bs-gap: 1.5rem;

```



\--------------------------------



\### Apply background and contrasting text colors



Source: https://getbootstrap.com/docs/5.3/helpers/color-background



Use .text-bg-\* classes to set a background color and an automatically calculated contrasting foreground color.



```html

<div class="text-bg-primary p-3">Primary with contrasting color</div>

<div class="text-bg-secondary p-3">Secondary with contrasting color</div>

<div class="text-bg-success p-3">Success with contrasting color</div>

<div class="text-bg-danger p-3">Danger with contrasting color</div>

<div class="text-bg-warning p-3">Warning with contrasting color</div>

<div class="text-bg-info p-3">Info with contrasting color</div>

<div class="text-bg-light p-3">Light with contrasting color</div>

<div class="text-bg-dark p-3">Dark with contrasting color</div>

```



\--------------------------------



\### Configure webpack.config.js



Source: https://getbootstrap.com/docs/5.3/getting-started/webpack



Boilerplate configuration for Webpack, including entry points, output paths, and development server settings.



```javascript

'use strict'



const path = require('path')

const HtmlWebpackPlugin = require('html-webpack-plugin')



module.exports = {

&#x20; mode: 'development',

&#x20; entry: './src/js/main.js',

&#x20; output: {

&#x20;   filename: 'main.js',

&#x20;   path: path.resolve(\_\_dirname, 'dist')

&#x20; },

&#x20; devServer: {

&#x20;   static: path.resolve(\_\_dirname, 'dist'),

&#x20;   port: 8080,

&#x20;   hot: true

&#x20; },

&#x20; plugins: \[

&#x20;   new HtmlWebpackPlugin({ template: './src/index.html' })

&#x20; ]

}

```



\--------------------------------



\### Creating an Offcanvas Instance



Source: https://getbootstrap.com/docs/5.3/components/offcanvas



Create a new offcanvas instance using the constructor with a CSS selector.



```javascript

const bsOffcanvas = new bootstrap.Offcanvas('#myOffcanvas')

```



\--------------------------------



\### Create a basic table with a group divider



Source: https://getbootstrap.com/docs/5.3/content/tables



Uses the table class for base styling and table-group-divider to visually separate the header from the body.



```html

<table class="table">

&#x20; <thead>

&#x20;   <tr>

&#x20;     <th scope="col">#</th>

&#x20;     <th scope="col">First</th>

&#x20;     <th scope="col">Last</th>

&#x20;     <th scope="col">Handle</th>

&#x20;   </tr>

&#x20; </thead>

&#x20; <tbody class="table-group-divider">

&#x20;   <tr>

&#x20;     <th scope="row">1</th>

&#x20;     <td>Mark</td>

&#x20;     <td>Otto</td>

&#x20;     <td>@mdo</td>

&#x20;   </tr>

&#x20;   <tr>

&#x20;     <th scope="row">2</th>

&#x20;     <td>Jacob</td>

&#x20;     <td>Thornton</td>

&#x20;     <td>@fat</td>

&#x20;   </tr>

&#x20;   <tr>

&#x20;     <th scope="row">3</th>

&#x20;     <td>John</td>

&#x20;     <td>Doe</td>

&#x20;     <td>@social</td>

&#x20;   </tr>

&#x20; </tbody>

</table>

```



\--------------------------------



\### Enable Flexbox Containers



Source: https://getbootstrap.com/docs/5.3/utilities/flex



Apply display utilities to transform elements into flexbox or inline-flexbox containers.



```html

<div class="d-flex p-2">I'm a flexbox container!</div>

```



```html

<div class="d-inline-flex p-2">I'm an inline flexbox container!</div>

```



\--------------------------------



\### Popover directions



Source: https://getbootstrap.com/docs/5.3/components/popovers



Demonstrates popovers positioned at the top, right, bottom, and left using the data-bs-placement attribute.



```html

<button type="button" class="btn btn-secondary" data-bs-container="body" data-bs-toggle="popover" data-bs-placement="top" data-bs-content="Top popover">

&#x20; Popover on top

</button>

<button type="button" class="btn btn-secondary" data-bs-container="body" data-bs-toggle="popover" data-bs-placement="right" data-bs-content="Right popover">

&#x20; Popover on right

</button>

<button type="button" class="btn btn-secondary" data-bs-container="body" data-bs-toggle="popover" data-bs-placement="bottom" data-bs-content="Bottom popover">

&#x20; Popover on bottom

</button>

<button type="button" class="btn btn-secondary" data-bs-container="body" data-bs-toggle="popover" data-bs-placement="left" data-bs-content="Left popover">

&#x20; Popover on left

</button>

```



\--------------------------------



\### Initialize all popovers



Source: https://getbootstrap.com/docs/5.3/components/popovers



Selects all elements with the data-bs-toggle attribute and initializes them as Bootstrap popovers.



```javascript

const popoverTriggerList = document.querySelectorAll('\[data-bs-toggle="popover"]')

const popoverList = \[...popoverTriggerList].map(popoverTriggerEl => new bootstrap.Popover(popoverTriggerEl))

```



\--------------------------------



\### Create a basic form grid



Source: https://getbootstrap.com/docs/5.3/forms/layout



Uses grid classes for multi-column form layouts. Requires the $enable-grid-classes Sass variable.



```html

<div class="row">

&#x20; <div class="col">

&#x20;   <input type="text" class="form-control" placeholder="First name" aria-label="First name">

&#x20; </div>

&#x20; <div class="col">

&#x20;   <input type="text" class="form-control" placeholder="Last name" aria-label="Last name">

&#x20; </div>

</div>

```



\--------------------------------



\### Popover Configuration Options



Source: https://getbootstrap.com/docs/5.3/components/popovers



A list of available options that can be passed to the Popover constructor or defined via data attributes.



```APIDOC

\## Popover Options



\### Parameters

\- \*\*offset\*\* (number, string, function) - Optional - Offset of the popover relative to its target.

\- \*\*placement\*\* (string, function) - Optional - How to position the popover (auto, top, bottom, left, right).

\- \*\*popperConfig\*\* (null, object, function) - Optional - Custom configuration for Popper.js.

\- \*\*sanitize\*\* (boolean) - Optional - Enable or disable content sanitization.

\- \*\*sanitizeFn\*\* (null, function) - Optional - Custom function for content sanitization.

\- \*\*selector\*\* (string, false) - Optional - Delegate popover objects to specified targets.

\- \*\*template\*\* (string) - Optional - Base HTML template for the popover.

\- \*\*title\*\* (string, element, function) - Optional - The popover title.

\- \*\*trigger\*\* (string) - Optional - How the popover is triggered (click, hover, focus, manual).

```



\--------------------------------



\### Adjusting placeholder width



Source: https://getbootstrap.com/docs/5.3/components/placeholders



Demonstrates controlling width using grid columns, width utilities, or inline styles.



```html

<span class="placeholder col-6"></span>

<span class="placeholder w-75"></span>

<span class="placeholder" style="width: 25%;"></span>

```



\--------------------------------



\### Initialize Alert elements with JavaScript



Source: https://getbootstrap.com/docs/5.3/components/alerts



Manually initialize all alert elements on the page using the Bootstrap Alert constructor.



```javascript

const alertList = document.querySelectorAll('.alert')

const alerts = \[...alertList].map(element => new bootstrap.Alert(element))

```



\--------------------------------



\### Configure color utilities in API



Source: https://getbootstrap.com/docs/5.3/utilities/colors



Defines color and opacity utilities within the Bootstrap utilities API.



```scss

"color": (

&#x20; property: color,

&#x20; class: text,

&#x20; local-vars: (

&#x20;   "text-opacity": 1

&#x20; ),

&#x20; values: map-merge(

&#x20;   $utilities-text-colors,

&#x20;   (

&#x20;     "muted": var(--#{$prefix}secondary-color), // deprecated

&#x20;     "black-50": rgba($black, .5), // deprecated

&#x20;     "white-50": rgba($white, .5), // deprecated

&#x20;     "body-secondary": var(--#{$prefix}secondary-color),

&#x20;     "body-tertiary": var(--#{$prefix}tertiary-color),

&#x20;     "body-emphasis": var(--#{$prefix}emphasis-color),

&#x20;     "reset": inherit,

&#x20;   )

&#x20; )

),

"text-opacity": (

&#x20; css-var: true,

&#x20; class: text-opacity,

&#x20; values: (

&#x20;   25: .25,

&#x20;   50: .5,

&#x20;   75: .75,

&#x20;   100: 1

&#x20; )

),

"text-color": (

&#x20; property: color,

&#x20; class: text,

&#x20; values: $utilities-text-emphasis-colors

),

```



\--------------------------------



\### Initialize Modal via JavaScript



Source: https://getbootstrap.com/docs/5.3/components/modal



Create a modal instance by passing a DOM element or selector string to the bootstrap.Modal constructor.



```javascript

const myModal = new bootstrap.Modal(document.getElementById('myModal'), options)

// or

const myModalAlternative = new bootstrap.Modal('#myModal', options)

```



\--------------------------------



\### bootstrap.Alert



Source: https://getbootstrap.com/docs/5.3/components/alerts



The Alert constructor allows manual initialization of alert components. It listens for click events on descendant elements with the data-bs-dismiss="alert" attribute.



```APIDOC

\## bootstrap.Alert



\### Description

Creates an alert instance for a given DOM element.



\### Constructor

`new bootstrap.Alert(element)`



\### Methods

\- \*\*close()\*\*: Closes an alert by removing it from the DOM. If the .fade and .show classes are present, the alert fades out before removal.

\- \*\*dispose()\*\*: Destroys an element's alert and removes stored data on the DOM element.

\- \*\*static getInstance(element)\*\*: Returns the alert instance associated with a DOM element.

\- \*\*static getOrCreateInstance(element)\*\*: Returns the alert instance associated with a DOM element or creates a new one if it wasn't initialized.



\### Events

\- \*\*close.bs.alert\*\*: Fires immediately when the close instance method is called.

\- \*\*closed.bs.alert\*\*: Fired when the alert has been closed and CSS transitions have completed.

```



\--------------------------------



\### Plugin Methods and Properties



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Standard methods and static properties available on Bootstrap plugins.



```APIDOC

\## Plugin Methods



\### dispose()

Destroys an element’s modal and removes stored data on the DOM element.



\### getInstance(element)

Static method to get the modal instance associated with a DOM element.



\### getOrCreateInstance(element)

Static method to get the modal instance associated with a DOM element, or create a new one if it wasn’t initialized.



\## Static Properties



\### NAME

Returns the plugin name (e.g., `bootstrap.Tooltip.NAME`).



\### VERSION

Returns the version of the plugin (e.g., `bootstrap.Tooltip.VERSION`).

```



\--------------------------------



\### Responsive Sticky Top Helpers



Source: https://getbootstrap.com/docs/5.3/helpers/position



Apply sticky top positioning based on specific viewport breakpoints.



```html

<div class="sticky-sm-top">Stick to the top on viewports sized SM (small) or wider</div>

<div class="sticky-md-top">Stick to the top on viewports sized MD (medium) or wider</div>

<div class="sticky-lg-top">Stick to the top on viewports sized LG (large) or wider</div>

<div class="sticky-xl-top">Stick to the top on viewports sized XL (extra-large) or wider</div>

<div class="sticky-xxl-top">Stick to the top on viewports sized XXL (extra-extra-large) or wider</div>

```



\--------------------------------



\### bootstrap.Offcanvas Constructor



Source: https://getbootstrap.com/docs/5.3/components/offcanvas



Initializes a new Offcanvas instance for a given DOM element or selector.



```APIDOC

\## new bootstrap.Offcanvas(element, options?)



\### Description

Activates your content as an offcanvas element. Accepts an optional options object.



\### Parameters

\- \*\*element\*\* (string|Element) - Required - A CSS selector or DOM element to initialize as an offcanvas.

\- \*\*options\*\* (object) - Optional - Configuration object for the offcanvas instance.



\### Example

```javascript

const bsOffcanvas = new bootstrap.Offcanvas('#myOffcanvas')

```

```



\--------------------------------



\### Create a base navigation list



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



Uses a <ul> structure to define a navigation list with active and disabled states.



```html

<ul class="nav">

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link active" aria-current="page" href="#">Active</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link" href="#">Link</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link" href="#">Link</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link disabled" aria-disabled="true">Disabled</a>

&#x20; </li>

</ul>

```



\--------------------------------



\### Apply Color Utilities to Elements



Source: https://getbootstrap.com/docs/5.3/customize/color



Use utility classes to apply theme-specific colors, backgrounds, and borders that automatically adapt to color modes.



```html

<div class="p-3 text-primary-emphasis bg-primary-subtle border border-primary-subtle rounded-3">

&#x20; Example element with utilities

</div>

```



\--------------------------------



\### Create an offcanvas navbar



Source: https://getbootstrap.com/docs/5.3/components/navbar



Transforms a standard navbar into an offcanvas drawer. Omit .navbar-expand-\* classes to keep it collapsed across all breakpoints.



```html

<nav class="navbar bg-body-tertiary fixed-top">

&#x20; <div class="container-fluid">

&#x20;   <a class="navbar-brand" href="#">Offcanvas navbar</a>

&#x20;   <button class="navbar-toggler" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasNavbar" aria-controls="offcanvasNavbar" aria-label="Toggle navigation">

&#x20;     <span class="navbar-toggler-icon"></span>

&#x20;   </button>

&#x20;   <div class="offcanvas offcanvas-end" tabindex="-1" id="offcanvasNavbar" aria-labelledby="offcanvasNavbarLabel">

&#x20;     <div class="offcanvas-header">

&#x20;       <h5 class="offcanvas-title" id="offcanvasNavbarLabel">Offcanvas</h5>

&#x20;       <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>

&#x20;     </div>

&#x20;     <div class="offcanvas-body">

&#x20;       <ul class="navbar-nav justify-content-end flex-grow-1 pe-3">

&#x20;         <li class="nav-item">

&#x20;           <a class="nav-link active" aria-current="page" href="#">Home</a>

&#x20;         </li>

&#x20;         <li class="nav-item">

&#x20;           <a class="nav-link" href="#">Link</a>

&#x20;         </li>

&#x20;         <li class="nav-item dropdown">

&#x20;           <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;             Dropdown

&#x20;           </a>

&#x20;           <ul class="dropdown-menu">

&#x20;             <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;             <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;             <li>

&#x20;               <hr class="dropdown-divider">

&#x20;             </li>

&#x20;             <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;           </ul>

&#x20;         </li>

&#x20;       </ul>

&#x20;       <form class="d-flex mt-3" role="search">

&#x20;         <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search"/>

&#x20;         <button class="btn btn-outline-success" type="submit">Search</button>

&#x20;       </form>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</nav>

```



\--------------------------------



\### Create Alert instance



Source: https://getbootstrap.com/docs/5.3/components/alerts



Instantiate an alert component for a specific DOM element.



```javascript

const bsAlert = new bootstrap.Alert('#myAlert')

```



\--------------------------------



\### Create a dynamic modal with HTML



Source: https://getbootstrap.com/docs/5.3/components/modal



Uses data-bs-whatever attributes on buttons to pass data to the modal, which is then retrieved via JavaScript.



```html

<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal" data-bs-whatever="@mdo">Open modal for @mdo</button>

<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal" data-bs-whatever="@fat">Open modal for @fat</button>

<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal" data-bs-whatever="@getbootstrap">Open modal for @getbootstrap</button>



<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">

&#x20; <div class="modal-dialog">

&#x20;   <div class="modal-content">

&#x20;     <div class="modal-header">

&#x20;       <h1 class="modal-title fs-5" id="exampleModalLabel">New message</h1>

&#x20;       <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>

&#x20;     </div>

&#x20;     <div class="modal-body">

&#x20;       <form>

&#x20;         <div class="mb-3">

&#x20;           <label for="recipient-name" class="col-form-label">Recipient:</label>

&#x20;           <input type="text" class="form-control" id="recipient-name">

&#x20;         </div>

&#x20;         <div class="mb-3">

&#x20;           <label for="message-text" class="col-form-label">Message:</label>

&#x20;           <textarea class="form-control" id="message-text"></textarea>

&#x20;         </div>

&#x20;       </form>

&#x20;     </div>

&#x20;     <div class="modal-footer">

&#x20;       <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>

&#x20;       <button type="button" class="btn btn-primary">Send message</button>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### bootstrap.Tab Constructor



Source: https://getbootstrap.com/docs/5.3/components/list-group



Creates a new tab instance for a given DOM element.



```APIDOC

\## bootstrap.Tab(element)



\### Description

Activates your content as a tab element.



\### Usage

```javascript

const bsTab = new bootstrap.Tab('#myTab')

```

```



\--------------------------------



\### Range Input with Steps



Source: https://getbootstrap.com/docs/5.3/forms/range



Defining snap intervals for the range input using the step attribute.



```html

<label for="range3" class="form-label">Example range</label>

<input type="range" class="form-range" min="0" max="5" step="0.5" id="range3">

```



\--------------------------------



\### Applying Toast Color Schemes



Source: https://getbootstrap.com/docs/5.3/components/toasts



Use background and text utilities to create colored toasts, ensuring close buttons are adjusted for visibility.



```html

<div class="toast align-items-center text-bg-primary border-0" role="alert" aria-live="assertive" aria-atomic="true">

&#x20; <div class="d-flex">

&#x20;   <div class="toast-body">

&#x20;     Hello, world! This is a toast message.

&#x20;   </div>

&#x20;   <button type="button" class="btn-close btn-close-white me-2 m-auto" data-bs-dismiss="toast" aria-label="Close"></button>

&#x20; </div>

</div>

```



\--------------------------------



\### Implement Small Spinners



Source: https://getbootstrap.com/docs/5.3/components/spinners



Use the spinner-border-sm or spinner-grow-sm classes to create compact spinners suitable for inline use.



```html

<div class="spinner-border spinner-border-sm" role="status">

&#x20; <span class="visually-hidden">Loading...</span>

</div>

<div class="spinner-grow spinner-grow-sm" role="status">

&#x20; <span class="visually-hidden">Loading...</span>

</div>

```



\--------------------------------



\### Dropdown Alignment and Directional Variations



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



A collection of dropdown configurations demonstrating standard, right-aligned, responsive, and directional (dropstart, dropend, dropup) menus.



```html

<div class="btn-group">

&#x20; <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   Dropdown

&#x20; </button>

&#x20; <ul class="dropdown-menu">

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20; </ul>

</div>



<div class="btn-group">

&#x20; <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   Right-aligned menu

&#x20; </button>

&#x20; <ul class="dropdown-menu dropdown-menu-end">

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20; </ul>

</div>



<div class="btn-group">

&#x20; <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" data-bs-display="static" aria-expanded="false">

&#x20;   Left-aligned, right-aligned lg

&#x20; </button>

&#x20; <ul class="dropdown-menu dropdown-menu-lg-end">

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20; </ul>

</div>



<div class="btn-group">

&#x20; <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" data-bs-display="static" aria-expanded="false">

&#x20;   Right-aligned, left-aligned lg

&#x20; </button>

&#x20; <ul class="dropdown-menu dropdown-menu-end dropdown-menu-lg-start">

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20; </ul>

</div>



<div class="btn-group dropstart">

&#x20; <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   Dropstart

&#x20; </button>

&#x20; <ul class="dropdown-menu">

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20; </ul>

</div>



<div class="btn-group dropend">

&#x20; <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   Dropend

&#x20; </button>

&#x20; <ul class="dropdown-menu">

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20; </ul>

</div>



<div class="btn-group dropup">

&#x20; <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   Dropup

&#x20; </button>

&#x20; <ul class="dropdown-menu">

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Menu item</a></li>

&#x20; </ul>

</div>

```



\--------------------------------



\### Create full-width block buttons



Source: https://getbootstrap.com/docs/5.3/components/buttons



Uses the d-grid and gap utilities to create a stack of full-width buttons.



```html

<div class="d-grid gap-2">

&#x20; <button class="btn btn-primary" type="button">Button</button>

&#x20; <button class="btn btn-primary" type="button">Button</button>

</div>

```



\--------------------------------



\### Use color helpers on cards



Source: https://getbootstrap.com/docs/5.3/helpers/color-background



Apply .text-bg-\* classes to card components to set the background and text color for the entire card.



```html

<div class="card text-bg-primary mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body">

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

<div class="card text-bg-info mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body">

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

```



\--------------------------------



\### Create a base navigation with nav element



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



Uses a <nav> element to create a navigation component without requiring list markup.



```html

<nav class="nav">

&#x20; <a class="nav-link active" aria-current="page" href="#">Active</a>

&#x20; <a class="nav-link" href="#">Link</a>

&#x20; <a class="nav-link" href="#">Link</a>

&#x20; <a class="nav-link disabled" aria-disabled="true">Disabled</a>

</nav>

```



\--------------------------------



\### Sizing cards with utilities



Source: https://getbootstrap.com/docs/5.3/components/card



Apply Bootstrap sizing utility classes directly to the card element to quickly set specific widths.



```html

<div class="card w-75 mb-3">

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Card title</h5>

&#x20;   <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>

&#x20;   <a href="#" class="btn btn-primary">Button</a>

&#x20; </div>

</div>



<div class="card w-50">

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Card title</h5>

&#x20;   <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>

&#x20;   <a href="#" class="btn btn-primary">Button</a>

&#x20; </div>

</div>

```



\--------------------------------



\### Toast Methods



Source: https://getbootstrap.com/docs/5.3/components/toasts



Methods available on the toast instance to control visibility and state.



```APIDOC

\## Toast Methods



\### Methods

\- \*\*show()\*\* - Reveals the toast.

\- \*\*hide()\*\* - Hides the toast.

\- \*\*dispose()\*\* - Destroys the toast instance.

\- \*\*isShown()\*\* - Returns a boolean indicating the toast's visibility state.

\- \*\*getInstance(element)\*\* (Static) - Returns the toast instance associated with a DOM element.

\- \*\*getOrCreateInstance(element)\*\* (Static) - Returns the toast instance associated with a DOM element, or creates a new one if it doesn't exist.

```



\--------------------------------



\### Use color helpers on badges



Source: https://getbootstrap.com/docs/5.3/helpers/color-background



Apply .text-bg-\* classes to badges to replace manual combinations of .text-\* and .bg-\* utilities.



```html

<span class="badge text-bg-primary">Primary</span>

<span class="badge text-bg-info">Info</span>

```



\--------------------------------



\### Generate Print Utility Classes



Source: https://getbootstrap.com/docs/5.3/utilities/api



Enable the print option to generate utility classes that are applied only within the @media print media query.



```scss

$utilities: (

&#x20; "opacity": (

&#x20;   property: opacity,

&#x20;   print: true,

&#x20;   values: (

&#x20;     0: 0,

&#x20;     25: .25,

&#x20;     50: .5,

&#x20;     75: .75,

&#x20;     100: 1,

&#x20;   )

&#x20; )

);

```



```css

.opacity-0 { opacity: 0 !important; }

.opacity-25 { opacity: .25 !important; }

.opacity-50 { opacity: .5 !important; }

.opacity-75 { opacity: .75 !important; }

.opacity-100 { opacity: 1 !important; }



@media print {

&#x20; .opacity-print-0 { opacity: 0 !important; }

&#x20; .opacity-print-25 { opacity: .25 !important; }

&#x20; .opacity-print-50 { opacity: .5 !important; }

&#x20; .opacity-print-75 { opacity: .75 !important; }

&#x20; .opacity-print-100 { opacity: 1 !important; }

}

```



\--------------------------------



\### Implement a basic border spinner



Source: https://getbootstrap.com/docs/5.3/components/spinners



Use the border spinner class for a standard lightweight loading indicator.



```html

<div class="spinner-border" role="status">

&#x20; <span class="visually-hidden">Loading...</span>

</div>

```



\--------------------------------



\### Create Pills with Dropdowns



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



Use the nav-pills class to create pill-style navigation that supports dropdown menus.



```html

<ul class="nav nav-pills">

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link active" aria-current="page" href="#">Active</a>

&#x20; </li>

&#x20; <li class="nav-item dropdown">

&#x20;   <a class="nav-link dropdown-toggle" data-bs-toggle="dropdown" href="#" role="button" aria-expanded="false">Dropdown</a>

&#x20;   <ul class="dropdown-menu">

&#x20;     <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;     <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;     <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;     <li><hr class="dropdown-divider"></li>

&#x20;     <li><a class="dropdown-item" href="#">Separated link</a></li>

&#x20;   </ul>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link" href="#">Link</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link disabled" aria-disabled="true">Disabled</a>

&#x20; </li>

</ul>

```



\--------------------------------



\### Positioning Progress Steps



Source: https://getbootstrap.com/docs/5.3/utilities/position



Shows how to align buttons along a progress bar using absolute positioning.



```html

<div class="position-relative m-4">

&#x20; <div class="progress" role="progressbar" aria-label="Progress" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100" style="height: 1px;">

&#x20;   <div class="progress-bar" style="width: 50%"></div>

&#x20; </div>

&#x20; <button type="button" class="position-absolute top-0 start-0 translate-middle btn btn-sm btn-primary rounded-pill" style="width: 2rem; height:2rem;">1</button>

&#x20; <button type="button" class="position-absolute top-0 start-50 translate-middle btn btn-sm btn-primary rounded-pill" style="width: 2rem; height:2rem;">2</button>

&#x20; <button type="button" class="position-absolute top-0 start-100 translate-middle btn btn-sm btn-secondary rounded-pill" style="width: 2rem; height:2rem;">3</button>

</div>

```



\--------------------------------



\### Implement a static backdrop modal



Source: https://getbootstrap.com/docs/5.3/components/modal



Configures a modal that does not close when clicking outside or pressing the escape key by setting data-bs-backdrop to static and data-bs-keyboard to false.



```html

<!-- Button trigger modal -->

<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#staticBackdrop">

&#x20; Launch static backdrop modal

</button>



<!-- Modal -->

<div class="modal fade" id="staticBackdrop" data-bs-backdrop="static" data-bs-keyboard="false" tabindex="-1" aria-labelledby="staticBackdropLabel" aria-hidden="true">

&#x20; <div class="modal-dialog">

&#x20;   <div class="modal-content">

&#x20;     <div class="modal-header">

&#x20;       <h1 class="modal-title fs-5" id="staticBackdropLabel">Modal title</h1>

&#x20;       <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>

&#x20;     </div>

&#x20;     <div class="modal-body">

&#x20;       ...

&#x20;     </div>

&#x20;     <div class="modal-footer">

&#x20;       <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>

&#x20;       <button type="button" class="btn btn-primary">Understood</button>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Include Masonry via CDN



Source: https://getbootstrap.com/docs/5.3/examples/masonry



Add the Masonry JavaScript plugin to your project using the official CDN link.



```html

<script src="https://cdn.jsdelivr.net/npm/masonry-layout@4.2.2/dist/masonry.pkgd.min.js" integrity="sha384-GNFwBvfVxBkLMJpYMOABq3c+d3KnQxudP/mGPkzpZSTYykLBNsZEnG2D9G/X/+7D" crossorigin="anonymous" async></script>

```



\--------------------------------



\### Create a link-based navbar



Source: https://getbootstrap.com/docs/5.3/components/navbar



An alternative approach that avoids list elements by using a container with the .navbar-nav class directly.



```html

<nav class="navbar navbar-expand-lg bg-body-tertiary">

&#x20; <div class="container-fluid">

&#x20;   <a class="navbar-brand" href="#">Navbar</a>

&#x20;   <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">

&#x20;     <span class="navbar-toggler-icon"></span>

&#x20;   </button>

&#x20;   <div class="collapse navbar-collapse" id="navbarNavAltMarkup">

&#x20;     <div class="navbar-nav">

&#x20;       <a class="nav-link active" aria-current="page" href="#">Home</a>

&#x20;       <a class="nav-link" href="#">Features</a>

&#x20;       <a class="nav-link" href="#">Pricing</a>

&#x20;       <a class="nav-link disabled" aria-disabled="true">Disabled</a>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</nav>

```



\--------------------------------



\### Positioning Badges and Markers



Source: https://getbootstrap.com/docs/5.3/utilities/position



Demonstrates using position-relative and position-absolute classes to place badges and SVG markers on components.



```html

<button type="button" class="btn btn-primary position-relative">

&#x20; Mails <span class="position-absolute top-0 start-100 translate-middle badge rounded-pill text-bg-secondary">+99 <span class="visually-hidden">unread messages</span></span>

</button>



<div class="position-relative py-2 px-4 text-bg-secondary border border-secondary rounded-pill">

&#x20; Marker <svg width="1em" height="1em" viewBox="0 0 16 16" class="position-absolute top-100 start-50 translate-middle mt-1" fill="var(--bs-secondary)" xmlns="http://www.w3.org/2000/svg" aria-hidden="true"><path d="M7.247 11.14L2.451 5.658C1.885 5.013 2.345 4 3.204 4h9.592a1 1 0 0 1 .753 1.659l-4.796 5.48a1 1 0 0 1-1.506 0z"/></svg>

</div>



<button type="button" class="btn btn-primary position-relative">

&#x20; Alerts <span class="position-absolute top-0 start-100 translate-middle badge border border-light rounded-circle bg-danger p-2"><span class="visually-hidden">unread messages</span></span>

</button>

```



\--------------------------------



\### Generate responsive dropdown alignment with Sass



Source: https://getbootstrap.com/docs/5.3/customize/components



Uses an @each loop over $grid-breakpoints and media query includes to create responsive dropdown positioning classes.



```scss

// We deliberately hardcode the `bs-` prefix because we check

// this custom property in JS to determine Popper's positioning



@each $breakpoint in map-keys($grid-breakpoints) {

&#x20; @include media-breakpoint-up($breakpoint) {

&#x20;   $infix: breakpoint-infix($breakpoint, $grid-breakpoints);



&#x20;   .dropdown-menu#{$infix}-start {

&#x20;     --bs-position: start;



&#x20;     \&\[data-bs-popper] {

&#x20;       right: auto;

&#x20;       left: 0;

&#x20;     }

&#x20;   }



&#x20;   .dropdown-menu#{$infix}-end {

&#x20;     --bs-position: end;



&#x20;     \&\[data-bs-popper] {

&#x20;       right: 0;

&#x20;       left: auto;

&#x20;     }

&#x20;   }

&#x20; }

}

```



\--------------------------------



\### Grid Item Wrapping



Source: https://getbootstrap.com/docs/5.3/layout/css-grid



Demonstrates how grid items automatically wrap to the next line when horizontal space is exhausted.



```html

<div class="grid text-center">

&#x20; <div class="g-col-6">.g-col-6</div>

&#x20; <div class="g-col-6">.g-col-6</div>



&#x20; <div class="g-col-6">.g-col-6</div>

&#x20; <div class="g-col-6">.g-col-6</div>

</div>

```



\--------------------------------



\### JavaScript Toast Initialization



Source: https://getbootstrap.com/docs/5.3/components/toasts



JavaScript logic to initialize and show a toast instance when a trigger button is clicked.



```javascript

const toastTrigger = document.getElementById('liveToastBtn')

const toastLiveExample = document.getElementById('liveToast')



if (toastTrigger) {

&#x20; const toastBootstrap = bootstrap.Toast.getOrCreateInstance(toastLiveExample)

&#x20; toastTrigger.addEventListener('click', () => {

&#x20;   toastBootstrap.show()

&#x20; })

}

```



\--------------------------------



\### Basic Figure Component



Source: https://getbootstrap.com/docs/5.3/content/figures



Use the .figure, .figure-img, and .figure-caption classes to style images and captions. Ensure .img-fluid is applied to the image for responsiveness.



```html

<figure class="figure">

&#x20; <img src="..." class="figure-img img-fluid rounded" alt="...">

&#x20; <figcaption class="figure-caption">A caption for the above image.</figcaption>

</figure>

```



\--------------------------------



\### Create a Bootstrap Accordion



Source: https://getbootstrap.com/docs/5.3/components/accordion



A standard accordion structure using the .accordion class with multiple .accordion-item elements.



```html

<div class="accordion" id="accordionPanelsStayOpenExample">

&#x20; <div class="accordion-item">

&#x20;   <h2 class="accordion-header">

&#x20;     <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#panelsStayOpen-collapseOne" aria-expanded="true" aria-controls="panelsStayOpen-collapseOne">

&#x20;       Accordion Item #1

&#x20;     </button>

&#x20;   </h2>

&#x20;   <div id="panelsStayOpen-collapseOne" class="accordion-collapse collapse show">

&#x20;     <div class="accordion-body">

&#x20;       <strong>This is the first item’s accordion body.</strong> It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It’s also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="accordion-item">

&#x20;   <h2 class="accordion-header">

&#x20;     <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#panelsStayOpen-collapseTwo" aria-expanded="false" aria-controls="panelsStayOpen-collapseTwo">

&#x20;       Accordion Item #2

&#x20;     </button>

&#x20;   </h2>

&#x20;   <div id="panelsStayOpen-collapseTwo" class="accordion-collapse collapse">

&#x20;     <div class="accordion-body">

&#x20;       <strong>This is the second item’s accordion body.</strong> It is hidden by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It’s also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="accordion-item">

&#x20;   <h2 class="accordion-header">

&#x20;     <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#panelsStayOpen-collapseThree" aria-expanded="false" aria-controls="panelsStayOpen-collapseThree">

&#x20;       Accordion Item #3

&#x20;     </button>

&#x20;   </h2>

&#x20;   <div id="panelsStayOpen-collapseThree" class="accordion-collapse collapse">

&#x20;     <div class="accordion-body">

&#x20;       <strong>This is the third item’s accordion body.</strong> It is hidden by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It’s also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Implement pagination with icons



Source: https://getbootstrap.com/docs/5.3/components/pagination



Use icons instead of text for navigation links while maintaining accessibility with aria-label and aria-hidden attributes.



```html

<nav aria-label="Page navigation example">

&#x20; <ul class="pagination">

&#x20;   <li class="page-item">

&#x20;     <a class="page-link" href="#" aria-label="Previous">

&#x20;       <span aria-hidden="true">\&laquo;</span>

&#x20;     </a>

&#x20;   </li>

&#x20;   <li class="page-item"><a class="page-link" href="#">1</a></li>

&#x20;   <li class="page-item"><a class="page-link" href="#">2</a></li>

&#x20;   <li class="page-item"><a class="page-link" href="#">3</a></li>

&#x20;   <li class="page-item">

&#x20;     <a class="page-link" href="#" aria-label="Next">

&#x20;       <span aria-hidden="true">\&raquo;</span>

&#x20;     </a>

&#x20;   </li>

&#x20; </ul>

</nav>

```



\--------------------------------



\### Apply a custom theme to HTML



Source: https://getbootstrap.com/docs/5.3/customize/color-modes



Wrap content in an element with the data-bs-theme attribute set to the custom theme name.



```html

<div data-bs-theme="blue">

&#x20; ...

</div>

```



\--------------------------------



\### Icon Link with Utilities



Source: https://getbootstrap.com/docs/5.3/helpers/icon-link



Applying link utility classes to customize appearance.



```html

<a class="icon-link icon-link-hover link-success link-underline-success link-underline-opacity-25" href="#">

&#x20; Icon link

&#x20; <svg xmlns="http://www.w3.org/2000/svg" class="bi" viewBox="0 0 16 16" aria-hidden="true">

&#x20;   <path d="M1 8a.5.5 0 0 1 .5-.5h11.793l-3.147-3.146a.5.5 0 0 1 .708-.708l4 4a.5.5 0 0 1 0 .708l-4 4a.5.5 0 0 1-.708-.708L13.293 8.5H1.5A.5.5 0 0 1 1 8z"/>

&#x20; </svg>

</a>

```



\--------------------------------



\### Implement column sizing in forms



Source: https://getbootstrap.com/docs/5.3/forms/layout



Uses specific column classes like .col-sm-7 to define widths while allowing other columns to split remaining space.



```html

<div class="row g-3">

&#x20; <div class="col-sm-7">

&#x20;   <input type="text" class="form-control" placeholder="City" aria-label="City">

&#x20; </div>

&#x20; <div class="col-sm">

&#x20;   <input type="text" class="form-control" placeholder="State" aria-label="State">

&#x20; </div>

&#x20; <div class="col-sm">

&#x20;   <input type="text" class="form-control" placeholder="Zip" aria-label="Zip">

&#x20; </div>

</div>

```



\--------------------------------



\### Include Bootstrap CSS and JS via CDN



Source: https://getbootstrap.com/docs/5.3/getting-started/introduction



Integrate Bootstrap's production-ready CSS and JS bundle into the HTML boilerplate.



```html

<!doctype html>

<html lang="en">

&#x20; <head>

&#x20;   <meta charset="utf-8">

&#x20;   <meta name="viewport" content="width=device-width, initial-scale=1">

&#x20;   <title>Bootstrap demo</title>

&#x20;   <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB" crossorigin="anonymous">

&#x20; </head>

&#x20; <body>

&#x20;   <h1>Hello, world!</h1>

&#x20;   <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js" integrity="sha384-FKyoEForCGlyvwx9Hj09JcYn3nv7wiPVlz7YYwJrWVcXK/BmnVDxM+D2scQbITxI" crossorigin="anonymous"></script>

&#x20; </body>

</html>

```



\--------------------------------



\### Apply lead paragraph class



Source: https://getbootstrap.com/docs/5.3/content/typography



Add the .lead class to a paragraph to make it stand out from regular text.



```html

<p class="lead">

&#x20; This is a lead paragraph. It stands out from regular paragraphs.

</p>

```



\--------------------------------



\### Using CSS selectors in constructors



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Plugin constructors and instance methods accept CSS selectors as the first argument.



```javascript

const modal = new bootstrap.Modal('#myModal')

const dropdown = new bootstrap.Dropdown('\[data-bs-toggle="dropdown"]')

const offcanvas = bootstrap.Offcanvas.getInstance('#myOffcanvas')

const alert = bootstrap.Alert.getOrCreateInstance('#myAlert')

```



\--------------------------------



\### Create a card group with footers



Source: https://getbootstrap.com/docs/5.3/components/card



Demonstrates how card footers automatically align when used within a card group.



```html

<div class="card-group">

&#x20; <div class="card">

&#x20;   <img src="..." class="card-img-top" alt="...">

&#x20;   <div class="card-body">

&#x20;     <h5 class="card-title">Card title</h5>

&#x20;     <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>

&#x20;   </div>

&#x20;   <div class="card-footer">

&#x20;     <small class="text-body-secondary">Last updated 3 mins ago</small>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="card">

&#x20;   <img src="..." class="card-img-top" alt="...">

&#x20;   <div class="card-body">

&#x20;     <h5 class="card-title">Card title</h5>

&#x20;     <p class="card-text">This card has supporting text below as a natural lead-in to additional content.</p>

&#x20;   </div>

&#x20;   <div class="card-footer">

&#x20;     <small class="text-body-secondary">Last updated 3 mins ago</small>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="card">

&#x20;   <img src="..." class="card-img-top" alt="...">

&#x20;   <div class="card-body">

&#x20;     <h5 class="card-title">Card title</h5>

&#x20;     <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.</p>

&#x20;   </div>

&#x20;   <div class="card-footer">

&#x20;     <small class="text-body-secondary">Last updated 3 mins ago</small>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Implement a fluid container



Source: https://getbootstrap.com/docs/5.3/layout/containers



The .container-fluid class creates a full-width container that spans the entire width of the viewport.



```html

<div class="container-fluid">

&#x20; ...

</div>

```



\--------------------------------



\### Apply contextual classes to links and buttons



Source: https://getbootstrap.com/docs/5.3/components/list-group



Combine contextual classes with .list-group-item-action to enable hover states on interactive list items.



```html

<div class="list-group">

&#x20; <a href="#" class="list-group-item list-group-item-action">A simple default list group item</a>

&#x20; 

&#x20; <a href="#" class="list-group-item list-group-item-action list-group-item-primary">A simple primary list group item</a>

&#x20; <a href="#" class="list-group-item list-group-item-action list-group-item-secondary">A simple secondary list group item</a>

&#x20; <a href="#" class="list-group-item list-group-item-action list-group-item-success">A simple success list group item</a>

&#x20; <a href="#" class="list-group-item list-group-item-action list-group-item-danger">A simple danger list group item</a>

&#x20; <a href="#" class="list-group-item list-group-item-action list-group-item-warning">A simple warning list group item</a>

&#x20; <a href="#" class="list-group-item list-group-item-action list-group-item-info">A simple info list group item</a>

&#x20; <a href="#" class="list-group-item list-group-item-action list-group-item-light">A simple light list group item</a>

&#x20; <a href="#" class="list-group-item list-group-item-action list-group-item-dark">A simple dark list group item</a>

</div>

```



\--------------------------------



\### Implement size-specific column layouts



Source: https://getbootstrap.com/docs/5.3/forms/layout



Combines specific column classes with auto-sizing utilities for complex form layouts.



```html

<form class="row gx-3 gy-2 align-items-center">

&#x20; <div class="col-sm-3">

&#x20;   <label class="visually-hidden" for="specificSizeInputName">Name</label>

&#x20;   <input type="text" class="form-control" id="specificSizeInputName" placeholder="Jane Doe">

&#x20; </div>

&#x20; <div class="col-sm-3">

&#x20;   <label class="visually-hidden" for="specificSizeInputGroupUsername">Username</label>

&#x20;   <div class="input-group">

&#x20;     <div class="input-group-text">@</div>

&#x20;     <input type="text" class="form-control" id="specificSizeInputGroupUsername" placeholder="Username">

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col-sm-3">

&#x20;   <label class="visually-hidden" for="specificSizeSelect">Preference</label>

&#x20;   <select class="form-select" id="specificSizeSelect">

&#x20;     <option selected>Choose...</option>

&#x20;     <option value="1">One</option>

&#x20;     <option value="2">Two</option>

&#x20;     <option value="3">Three</option>

&#x20;   </select>

&#x20; </div>

&#x20; <div class="col-auto">

&#x20;   <div class="form-check">

&#x20;     <input class="form-check-input" type="checkbox" id="autoSizingCheck2">

&#x20;     <label class="form-check-label" for="autoSizingCheck2">

&#x20;       Remember me

&#x20;     </label>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col-auto">

&#x20;   <button type="submit" class="btn btn-primary">Submit</button>

&#x20; </div>

</form>

```



\--------------------------------



\### Apply Text Decoration



Source: https://getbootstrap.com/docs/5.3/utilities/text



Use utility classes to add underlines, line-throughs, or remove text decoration.



```html

<p class="text-decoration-underline">This text has a line underneath it.</p>

<p class="text-decoration-line-through">This text has a line going through it.</p>

<a href="#" class="text-decoration-none">This link has its text decoration removed</a>

```



\--------------------------------



\### getInstance



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Retrieves an existing plugin instance associated with a specific DOM element.



```APIDOC

\## bootstrap.Plugin.getInstance(element)



\### Description

Retrieves the plugin instance associated with the provided DOM element or CSS selector. Returns null if no instance is initialized.



\### Parameters

\- \*\*element\*\* (HTMLElement|string) - Required - The DOM element or CSS selector to query.

```



\--------------------------------



\### Apply default aspect ratio classes



Source: https://getbootstrap.com/docs/5.3/helpers/ratio



Use modifier classes like .ratio-1x1, .ratio-4x3, .ratio-16x9, or .ratio-21x9 to set specific aspect ratios.



```html

<div class="ratio ratio-1x1">

&#x20; <div>1x1</div>

</div>

<div class="ratio ratio-4x3">

&#x20; <div>4x3</div>

</div>

<div class="ratio ratio-16x9">

&#x20; <div>16x9</div>

</div>

<div class="ratio ratio-21x9">

&#x20; <div>21x9</div>

</div>

```



\--------------------------------



\### Create equal-width columns



Source: https://getbootstrap.com/docs/5.3/layout/grid



Use unit-less .col classes to create columns that share width equally across all breakpoints.



```html

<div class="container text-center">

&#x20; <div class="row">

&#x20;   <div class="col">

&#x20;     1 of 2

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     2 of 2

&#x20;   </div>

&#x20; </div>

&#x20; <div class="row">

&#x20;   <div class="col">

&#x20;     1 of 3

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     2 of 3

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     3 of 3

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Create three equal-width columns



Source: https://getbootstrap.com/docs/5.3/layout/css-grid



Uses .g-col-4 classes to distribute three columns equally across all viewports.



```html

<div class="grid text-center">

&#x20; <div class="g-col-4">.g-col-4</div>

&#x20; <div class="g-col-4">.g-col-4</div>

&#x20; <div class="g-col-4">.g-col-4</div>

</div>

```



\--------------------------------



\### Responsive dropdown alignment (Left on large screens)



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



Combine .dropdown-menu-end and .dropdown-menu-lg-start to force a right-aligned menu to align to the left on large screens and up.



```html

<div class="btn-group">

&#x20; <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" data-bs-display="static" aria-expanded="false">

&#x20;   Right-aligned but left aligned when large screen

&#x20; </button>

&#x20; <ul class="dropdown-menu dropdown-menu-end dropdown-menu-lg-start">

&#x20;   <li><button class="dropdown-item" type="button">Action</button></li>

&#x20;   <li><button class="dropdown-item" type="button">Another action</button></li>

&#x20;   <li><button class="dropdown-item" type="button">Something else here</button></li>

&#x20; </ul>

</div>

```



\--------------------------------



\### Initializing Offcanvas via JavaScript



Source: https://getbootstrap.com/docs/5.3/components/offcanvas



Manually initialize all offcanvas elements on the page using the Bootstrap JavaScript API.



```javascript

const offcanvasElementList = document.querySelectorAll('.offcanvas')

const offcanvasList = \[...offcanvasElementList].map(offcanvasEl => new bootstrap.Offcanvas(offcanvasEl))

```



\--------------------------------



\### Configure Webpack loaders for Bootstrap



Source: https://getbootstrap.com/docs/5.3/getting-started/webpack



Set up the module rules in webpack.config.js to handle SCSS, CSS, and PostCSS processing.



```javascript

'use strict'



const path = require('path')

const autoprefixer = require('autoprefixer')

const HtmlWebpackPlugin = require('html-webpack-plugin')



module.exports = {

&#x20; mode: 'development',

&#x20; entry: './src/js/main.js',

&#x20; output: {

&#x20;   filename: 'main.js',

&#x20;   path: path.resolve(\_\_dirname, 'dist')

&#x20; },

&#x20; devServer: {

&#x20;   static: path.resolve(\_\_dirname, 'dist'),

&#x20;   port: 8080,

&#x20;   hot: true

&#x20; },

&#x20; plugins: \[

&#x20;   new HtmlWebpackPlugin({ template: './src/index.html' })

&#x20; ],

&#x20; module: {

&#x20;   rules: \[

&#x20;     {

&#x20;       test: /\\.(scss)$/,

&#x20;       use: \[

&#x20;         {

&#x20;           // Adds CSS to the DOM by injecting a `<style>` tag

&#x20;           loader: 'style-loader'

&#x20;         },

&#x20;         {

&#x20;           // Interprets `@import` and `url()` like `import/require()` and will resolve them

&#x20;           loader: 'css-loader'

&#x20;         },

&#x20;         {

&#x20;           // Loader for webpack to process CSS with PostCSS

&#x20;           loader: 'postcss-loader',

&#x20;           options: {

&#x20;             postcssOptions: {

&#x20;               plugins: \[

&#x20;                 autoprefixer

&#x20;               ]

&#x20;             }

&#x20;           }

&#x20;         },

&#x20;         {

&#x20;           // Loads a SASS/SCSS file and compiles it to CSS

&#x20;           loader: 'sass-loader',

&#x20;           options: {

&#x20;             sassOptions: {

&#x20;               // Optional: Silence Sass deprecation warnings. See note below.

&#x20;               silenceDeprecations: \[

&#x20;                 'mixed-decls',

&#x20;                 'color-functions',

&#x20;                 'global-builtin',

&#x20;                 'import'

&#x20;               ]

&#x20;             }

&#x20;           }

&#x20;         }

&#x20;       ]

&#x20;     }

&#x20;   ]

&#x20; }

}

```



\--------------------------------



\### Apply link colors



Source: https://getbootstrap.com/docs/5.3/helpers/colored-links



Use .link-\* classes to apply specific colors to links. Note that some light colors require a dark background for sufficient contrast.



```html

<p><a href="#" class="link-primary">Primary link</a></p>

<p><a href="#" class="link-secondary">Secondary link</a></p>

<p><a href="#" class="link-success">Success link</a></p>

<p><a href="#" class="link-danger">Danger link</a></p>

<p><a href="#" class="link-warning">Warning link</a></p>

<p><a href="#" class="link-info">Info link</a></p>

<p><a href="#" class="link-light">Light link</a></p>

<p><a href="#" class="link-dark">Dark link</a></p>

<p><a href="#" class="link-body-emphasis">Emphasis link</a></p>

```



\--------------------------------



\### Initialize Accordion via JavaScript



Source: https://getbootstrap.com/docs/5.3/components/accordion



Manually initialize multiple collapse elements within an accordion container.



```javascript

const accordionCollapseElementList = document.querySelectorAll('#myAccordion .collapse')

const accordionCollapseList = \[...accordionCollapseElementList].map(accordionCollapseEl => new bootstrap.Collapse(accordionCollapseEl))

```



\--------------------------------



\### Import Bootstrap JavaScript



Source: https://getbootstrap.com/docs/5.3/getting-started/parcel



Import the full Bootstrap JavaScript bundle into your main entry file. Popper is included automatically.



```javascript

// Import all of Bootstrap’s JS

import \* as bootstrap from 'bootstrap'

```



\--------------------------------



\### Implementing LTR and RTL Simultaneously



Source: https://getbootstrap.com/docs/5.3/getting-started/rtl



Use RTLCSS String Maps to wrap imports and automatically rename selectors for both directions.



```scss

/\* rtl:begin:options: {

&#x20; "autoRename": true,

&#x20; "stringMap":\[ {

&#x20;   "name": "ltr-rtl",

&#x20;   "priority": 100,

&#x20;   "search": \["ltr"],

&#x20;   "replace": \["rtl"],

&#x20;   "options": {

&#x20;     "scope": "\*",

&#x20;     "ignoreCase": false

&#x20;   }

&#x20; } ]

} \*/

.ltr {

&#x20; @import "../node\_modules/bootstrap/scss/bootstrap";

}

/\*rtl:end:options\*/

```



\--------------------------------



\### Implement auto-sizing form controls



Source: https://getbootstrap.com/docs/5.3/forms/layout



Uses .col-auto to size columns based on content and flexbox utilities for alignment.



```html

<form class="row gy-2 gx-3 align-items-center">

&#x20; <div class="col-auto">

&#x20;   <label class="visually-hidden" for="autoSizingInput">Name</label>

&#x20;   <input type="text" class="form-control" id="autoSizingInput" placeholder="Jane Doe">

&#x20; </div>

&#x20; <div class="col-auto">

&#x20;   <label class="visually-hidden" for="autoSizingInputGroup">Username</label>

&#x20;   <div class="input-group">

&#x20;     <div class="input-group-text">@</div>

&#x20;     <input type="text" class="form-control" id="autoSizingInputGroup" placeholder="Username">

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col-auto">

&#x20;   <label class="visually-hidden" for="autoSizingSelect">Preference</label>

&#x20;   <select class="form-select" id="autoSizingSelect">

&#x20;     <option selected>Choose...</option>

&#x20;     <option value="1">One</option>

&#x20;     <option value="2">Two</option>

&#x20;     <option value="3">Three</option>

&#x20;   </select>

&#x20; </div>

&#x20; <div class="col-auto">

&#x20;   <div class="form-check">

&#x20;     <input class="form-check-input" type="checkbox" id="autoSizingCheck">

&#x20;     <label class="form-check-label" for="autoSizingCheck">

&#x20;       Remember me

&#x20;     </label>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col-auto">

&#x20;   <button type="submit" class="btn btn-primary">Submit</button>

&#x20; </div>

</form>

```



\--------------------------------



\### Apply responsive gutters to row columns



Source: https://getbootstrap.com/docs/5.3/layout/gutters



Uses responsive row column classes combined with responsive gutter classes to control spacing across different breakpoints.



```html

<div class="container text-center">

&#x20; <div class="row row-cols-2 row-cols-lg-5 g-2 g-lg-3">

&#x20;   <div class="col">

&#x20;     <div class="p-3">Row column</div>

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     <div class="p-3">Row column</div>

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     <div class="p-3">Row column</div>

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     <div class="p-3">Row column</div>

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     <div class="p-3">Row column</div>

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     <div class="p-3">Row column</div>

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     <div class="p-3">Row column</div>

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     <div class="p-3">Row column</div>

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     <div class="p-3">Row column</div>

&#x20;   </div>

&#x20;   <div class="col">

&#x20;     <div class="p-3">Row column</div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Responsive Sticky Bottom Helpers



Source: https://getbootstrap.com/docs/5.3/helpers/position



Apply sticky bottom positioning based on specific viewport breakpoints.



```html

<div class="sticky-sm-bottom">Stick to the bottom on viewports sized SM (small) or wider</div>

<div class="sticky-md-bottom">Stick to the bottom on viewports sized MD (medium) or wider</div>

<div class="sticky-lg-bottom">Stick to the bottom on viewports sized LG (large) or wider</div>

<div class="sticky-xl-bottom">Stick to the bottom on viewports sized XL (extra-large) or wider</div>

<div class="sticky-xxl-bottom">Stick to the bottom on viewports sized XXL (extra-extra-large) or wider</div>

```



\--------------------------------



\### Border Opacity Utility Classes



Source: https://getbootstrap.com/docs/5.3/utilities/borders



Applies predefined border-opacity utility classes to control transparency levels.



```html

<div class="border border-success p-2 mb-2">This is default success border</div>

<div class="border border-success p-2 mb-2 border-opacity-75">This is 75% opacity success border</div>

<div class="border border-success p-2 mb-2 border-opacity-50">This is 50% opacity success border</div>

<div class="border border-success p-2 mb-2 border-opacity-25">This is 25% opacity success border</div>

<div class="border border-success p-2 border-opacity-10">This is 10% opacity success border</div>

```



\--------------------------------



\### Create a card with header and body



Source: https://getbootstrap.com/docs/5.3/components/card



Use the card-header class to add a header section above the card-body.



```html

<div class="card">

&#x20; <div class="card-header">

&#x20;   Featured

&#x20; </div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Special title treatment</h5>

&#x20;   <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>

&#x20;   <a href="#" class="btn btn-primary">Go somewhere</a>

&#x20; </div>

</div>

```



\--------------------------------



\### Create custom layout with mixins



Source: https://getbootstrap.com/docs/5.3/layout/grid



Implement a custom two-column layout using Sass mixins and media breakpoints.



```scss

.example-container {

&#x20; @include make-container();

&#x20; // Make sure to define this width after the mixin to override

&#x20; // `width: 100%` generated by `make-container()`

&#x20; width: 800px;

}



.example-row {

&#x20; @include make-row();

}



.example-content-main {

&#x20; @include make-col-ready();



&#x20; @include media-breakpoint-up(sm) {

&#x20;   @include make-col(6);

&#x20; }

&#x20; @include media-breakpoint-up(lg) {

&#x20;   @include make-col(8);

&#x20; }

}



.example-content-secondary {

&#x20; @include make-col-ready();



&#x20; @include media-breakpoint-up(sm) {

&#x20;   @include make-col(6);

&#x20; }

&#x20; @include media-breakpoint-up(lg) {

&#x20;   @include make-col(4);

&#x20; }

}

```



\--------------------------------



\### Mix and match column classes



Source: https://getbootstrap.com/docs/5.3/layout/grid



Combine different column classes to achieve complex responsive behaviors across multiple grid tiers.



```html

<div class="container text-center">

&#x20; <!-- Stack the columns on mobile by making one full-width and the other half-width -->

&#x20; <div class="row">

&#x20;   <div class="col-md-8">.col-md-8</div>

&#x20;   <div class="col-6 col-md-4">.col-6 .col-md-4</div>

&#x20; </div>



&#x20; <!-- Columns start at 50% wide on mobile and bump up to 33.3% wide on desktop -->

&#x20; <div class="row">

&#x20;   <div class="col-6 col-md-4">.col-6 .col-md-4</div>

&#x20;   <div class="col-6 col-md-4">.col-6 .col-md-4</div>

&#x20;   <div class="col-6 col-md-4">.col-6 .col-md-4</div>

&#x20; </div>



&#x20; <!-- Columns are always 50% wide, on mobile and desktop -->

&#x20; <div class="row">

&#x20;   <div class="col-6">.col-6</div>

&#x20;   <div class="col-6">.col-6</div>

&#x20; </div>

</div>

```



\--------------------------------



\### Border Success CSS Implementation



Source: https://getbootstrap.com/docs/5.3/utilities/borders



Shows the underlying CSS structure for the border-success utility using RGB variables and border-opacity.



```css

.border-success {

&#x20; --bs-border-opacity: 1;

&#x20; border-color: rgba(var(--bs-success-rgb), var(--bs-border-opacity)) !important;

}

```



\--------------------------------



\### Create a standard list-based navbar



Source: https://getbootstrap.com/docs/5.3/components/navbar



Uses an unordered list structure for navigation items. Requires the .active class and aria-current="page" attribute for the current page indicator.



```html

<nav class="navbar navbar-expand-lg bg-body-tertiary">

&#x20; <div class="container-fluid">

&#x20;   <a class="navbar-brand" href="#">Navbar</a>

&#x20;   <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">

&#x20;     <span class="navbar-toggler-icon"></span>

&#x20;   </button>

&#x20;   <div class="collapse navbar-collapse" id="navbarNav">

&#x20;     <ul class="navbar-nav">

&#x20;       <li class="nav-item">

&#x20;         <a class="nav-link active" aria-current="page" href="#">Home</a>

&#x20;       </li>

&#x20;       <li class="nav-item">

&#x20;         <a class="nav-link" href="#">Features</a>

&#x20;       </li>

&#x20;       <li class="nav-item">

&#x20;         <a class="nav-link" href="#">Pricing</a>

&#x20;       </li>

&#x20;       <li class="nav-item">

&#x20;         <a class="nav-link disabled" aria-disabled="true">Disabled</a>

&#x20;       </li>

&#x20;     </ul>

&#x20;   </div>

&#x20; </div>

</nav>

```



\--------------------------------



\### Implement a growing spinner



Source: https://getbootstrap.com/docs/5.3/components/spinners



A basic growing spinner component that uses the .spinner-grow class.



```html

<div class="spinner-grow" role="status">

&#x20; <span class="visually-hidden">Loading...</span>

</div>

```



\--------------------------------



\### Initialize Collapse via JavaScript



Source: https://getbootstrap.com/docs/5.3/components/collapse



Manually initialize all elements with the collapse class using the Bootstrap Collapse constructor.



```javascript

const collapseElementList = document.querySelectorAll('.collapse')

const collapseList = \[...collapseElementList].map(collapseEl => new bootstrap.Collapse(collapseEl))

```



\--------------------------------



\### Apply background utility classes to progress bars



Source: https://getbootstrap.com/docs/5.3/components/progress



Use background utility classes to change the appearance of individual progress bars.



```html

<div class="progress" role="progressbar" aria-label="Success example" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">

&#x20; <div class="progress-bar bg-success" style="width: 25%"></div>

</div>

<div class="progress" role="progressbar" aria-label="Info example" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100">

&#x20; <div class="progress-bar bg-info" style="width: 50%"></div>

</div>

<div class="progress" role="progressbar" aria-label="Warning example" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100">

&#x20; <div class="progress-bar bg-warning" style="width: 75%"></div>

</div>

<div class="progress" role="progressbar" aria-label="Danger example" aria-valuenow="100" aria-valuemin="0" aria-valuemax="100">

&#x20; <div class="progress-bar bg-danger" style="width: 100%"></div>

</div>

```



\--------------------------------



\### Implement semantic button variants



Source: https://getbootstrap.com/docs/5.3/components/buttons



Use these classes to apply predefined semantic color schemes to buttons. Ensure button content remains accessible to screen readers by providing sufficient context beyond color.



```html

<button type="button" class="btn btn-primary">Primary</button>

<button type="button" class="btn btn-secondary">Secondary</button>

<button type="button" class="btn btn-success">Success</button>

<button type="button" class="btn btn-danger">Danger</button>

<button type="button" class="btn btn-warning">Warning</button>

<button type="button" class="btn btn-info">Info</button>

<button type="button" class="btn btn-light">Light</button>

<button type="button" class="btn btn-dark">Dark</button>



<button type="button" class="btn btn-link">Link</button>

```



\--------------------------------



\### Initialize Tabs via JavaScript



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



Manually initialize tab triggers and handle click events using the Bootstrap Tab API.



```javascript

const triggerTabList = document.querySelectorAll('#myTab button')

triggerTabList.forEach(triggerEl => {

&#x20; const tabTrigger = new bootstrap.Tab(triggerEl)



&#x20; triggerEl.addEventListener('click', event => {

&#x20;   event.preventDefault()

&#x20;   tabTrigger.show()

&#x20; })

})

```



\--------------------------------



\### Create Card Image Overlays



Source: https://getbootstrap.com/docs/5.3/components/card



Apply .card-img-overlay to position content over an image background. Ensure content height does not exceed the image height to avoid overflow.



```html

<div class="card text-bg-dark">

&#x20; <img src="..." class="card-img" alt="...">

&#x20; <div class="card-img-overlay">

&#x20;   <h5 class="card-title">Card title</h5>

&#x20;   <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>

&#x20;   <p class="card-text"><small>Last updated 3 mins ago</small></p>

&#x20; </div>

</div>

```



\--------------------------------



\### Apply Nav Variants



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



Use specific classes to transform basic navs into tabs, pills, or underlined navigation.



```html

<ul class="nav nav-tabs">

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link active" aria-current="page" href="#">Active</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link" href="#">Link</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link" href="#">Link</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link disabled" aria-disabled="true">Disabled</a>

&#x20; </li>

</ul>

```



```html

<ul class="nav nav-pills">

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link active" aria-current="page" href="#">Active</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link" href="#">Link</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link" href="#">Link</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link disabled" aria-disabled="true">Disabled</a>

&#x20; </li>

</ul>

```



```html

<ul class="nav nav-underline">

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link active" aria-current="page" href="#">Active</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link" href="#">Link</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link" href="#">Link</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link disabled" aria-disabled="true">Disabled</a>

&#x20; </li>

</ul>

```



\--------------------------------



\### Validating calc() with add and subtract



Source: https://getbootstrap.com/docs/5.3/customize/sass



Demonstrates how the subtract function handles valid calculations compared to native CSS calc().



```scss

$border-radius: .25rem;

$border-width: 1px;



.element {

&#x20; // Output calc(.25rem - 1px) is valid

&#x20; border-radius: calc($border-radius - $border-width);

}



.element {

&#x20; // Output the same calc(.25rem - 1px) as above

&#x20; border-radius: subtract($border-radius, $border-width);

}



```



\--------------------------------



\### Customize card header and footer with mixins



Source: https://getbootstrap.com/docs/5.3/components/card



Use .bg-transparent and border utilities to customize the header and footer sections of a card.



```html

<div class="card border-success mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header bg-transparent border-success">Header</div>

&#x20; <div class="card-body text-success">

&#x20;   <h5 class="card-title">Success card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

&#x20; <div class="card-footer bg-transparent border-success">Footer</div>

</div>

```



\--------------------------------



\### Implement variable width content



Source: https://getbootstrap.com/docs/5.3/layout/grid



Use .col-{breakpoint}-auto classes to size columns based on the natural width of their content.



```html

<div class="container text-center">

&#x20; <div class="row justify-content-md-center">

&#x20;   <div class="col col-lg-2">

&#x20;     1 of 3

&#x20;   </div>

&#x20;   <div class="col-md-auto">

&#x20;     Variable width content

&#x20;   </div>

&#x20;   <div class="col col-lg-2">

&#x20;     3 of 3

&#x20;   </div>

&#x20; </div>

&#x20; <div class="row">

&#x20;   <div class="col">

&#x20;     1 of 3

&#x20;   </div>

&#x20;   <div class="col-md-auto">

&#x20;     Variable width content

&#x20;   </div>

&#x20;   <div class="col col-lg-2">

&#x20;     3 of 3

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Combine brand and search form



Source: https://getbootstrap.com/docs/5.3/components/navbar



Demonstrates placing a brand link alongside a search form, utilizing default flex space-between behavior.



```html

<nav class="navbar bg-body-tertiary">

&#x20; <div class="container-fluid">

&#x20;   <a class="navbar-brand">Navbar</a>

&#x20;   <form class="d-flex" role="search">

&#x20;     <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search"/>

&#x20;     <button class="btn btn-outline-success" type="submit">Search</button>

&#x20;   </form>

&#x20; </div>

</nav>

```



\--------------------------------



\### Create vertical layouts with vstack



Source: https://getbootstrap.com/docs/5.3/helpers/stacks



Use the vstack class to stack items vertically. Items are full-width by default.



```html

<div class="vstack gap-3">

&#x20; <div class="p-2">First item</div>

&#x20; <div class="p-2">Second item</div>

&#x20; <div class="p-2">Third item</div>

</div>

```



\--------------------------------



\### Handling unitless zero in calc()



Source: https://getbootstrap.com/docs/5.3/customize/sass



Demonstrates how the subtract function prevents errors when a unitless zero is passed to a calculation.



```scss

$border-radius: .25rem;

$border-width: 0;



.element {

&#x20; // Output calc(.25rem - 0) is invalid

&#x20; border-radius: calc($border-radius - $border-width);

}



.element {

&#x20; // Output .25rem

&#x20; border-radius: subtract($border-radius, $border-width);

}



```



\--------------------------------



\### Define button-size mixin



Source: https://getbootstrap.com/docs/5.3/components/buttons



Sets padding, font size, and border radius for button sizing.



```scss

@mixin button-size($padding-y, $padding-x, $font-size, $border-radius) {

&#x20; --#{$prefix}btn-padding-y: #{$padding-y};

&#x20; --#{$prefix}btn-padding-x: #{$padding-x};

&#x20; @include rfs($font-size, --#{$prefix}btn-font-size);

&#x20; --#{$prefix}btn-border-radius: #{$border-radius};

}

```



\--------------------------------



\### Initialize Bootstrap Plugins with CSS Selectors



Source: https://getbootstrap.com/docs/5.3/migration



Bootstrap 5.3 plugins now accept CSS selectors as the first argument for initialization, replacing the requirement for direct DOM element references.



```javascript

const modal = new bootstrap.Modal('#myModal')

const dropdown = new bootstrap.Dropdown('\[data-bs-toggle="dropdown"]')

```



\--------------------------------



\### CSS implementation of stacks



Source: https://getbootstrap.com/docs/5.3/helpers/stacks



The underlying SCSS definitions for the hstack and vstack helpers.



```scss

.hstack {

&#x20; display: flex;

&#x20; flex-direction: row;

&#x20; align-items: center;

&#x20; align-self: stretch;

}



.vstack {

&#x20; display: flex;

&#x20; flex: 1 1 auto;

&#x20; flex-direction: column;

&#x20; align-self: stretch;

}

```



\--------------------------------



\### Add labels to progress bars with background colors



Source: https://getbootstrap.com/docs/5.3/components/progress



Use text-bg utility classes to ensure labels have sufficient contrast against the background color.



```html

<div class="progress" role="progressbar" aria-label="Success example" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">

&#x20; <div class="progress-bar text-bg-success" style="width: 25%">25%</div>

</div>

<div class="progress" role="progressbar" aria-label="Info example" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100">

&#x20; <div class="progress-bar text-bg-info" style="width: 50%">50%</div>

</div>

<div class="progress" role="progressbar" aria-label="Warning example" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100">

&#x20; <div class="progress-bar text-bg-warning" style="width: 75%">75%</div>

</div>

<div class="progress" role="progressbar" aria-label="Danger example" aria-valuenow="100" aria-valuemin="0" aria-valuemax="100">

&#x20; <div class="progress-bar text-bg-danger" style="width: 100%">100%</div>

</div>

```



\--------------------------------



\### Apply background color utilities



Source: https://getbootstrap.com/docs/5.3/utilities/background



Use these classes to set the background color of an element. Pair with text color utilities to ensure readability.



```html

<div class="p-3 mb-2 bg-primary text-white">.bg-primary</div>

<div class="p-3 mb-2 bg-primary-subtle text-primary-emphasis">.bg-primary-subtle</div>

<div class="p-3 mb-2 bg-secondary text-white">.bg-secondary</div>

<div class="p-3 mb-2 bg-secondary-subtle text-secondary-emphasis">.bg-secondary-subtle</div>

<div class="p-3 mb-2 bg-success text-white">.bg-success</div>

<div class="p-3 mb-2 bg-success-subtle text-success-emphasis">.bg-success-subtle</div>

<div class="p-3 mb-2 bg-danger text-white">.bg-danger</div>

<div class="p-3 mb-2 bg-danger-subtle text-danger-emphasis">.bg-danger-subtle</div>

<div class="p-3 mb-2 bg-warning text-dark">.bg-warning</div>

<div class="p-3 mb-2 bg-warning-subtle text-warning-emphasis">.bg-warning-subtle</div>

<div class="p-3 mb-2 bg-info text-dark">.bg-info</div>

<div class="p-3 mb-2 bg-info-subtle text-info-emphasis">.bg-info-subtle</div>

<div class="p-3 mb-2 bg-light text-dark">.bg-light</div>

<div class="p-3 mb-2 bg-light-subtle text-light-emphasis">.bg-light-subtle</div>

<div class="p-3 mb-2 bg-dark text-white">.bg-dark</div>

<div class="p-3 mb-2 bg-dark-subtle text-dark-emphasis">.bg-dark-subtle</div>

<div class="p-3 mb-2 bg-body-secondary">.bg-body-secondary</div>

<div class="p-3 mb-2 bg-body-tertiary">.bg-body-tertiary</div>

<div class="p-3 mb-2 bg-body text-body">.bg-body</div>

<div class="p-3 mb-2 bg-black text-white">.bg-black</div>

<div class="p-3 mb-2 bg-white text-dark">.bg-white</div>

<div class="p-3 mb-2 bg-transparent text-body">.bg-transparent</div>

```



\--------------------------------



\### Create a basic blockquote



Source: https://getbootstrap.com/docs/5.3/content/typography



Wrap content in a blockquote element with the .blockquote class.



```html

<blockquote class="blockquote">

&#x20; <p>A well-known quote, contained in a blockquote element.</p>

</blockquote>

```



\--------------------------------



\### Generate button classes with loops



Source: https://getbootstrap.com/docs/5.3/components/buttons



Iterates over the theme-colors map to generate standard and outline button classes.



```scss

@each $color, $value in $theme-colors {

&#x20; .btn-#{$color} {

&#x20;   @if $color == "light" {

&#x20;     @include button-variant(

&#x20;       $value,

&#x20;       $value,

&#x20;       $hover-background: shade-color($value, $btn-hover-bg-shade-amount),

&#x20;       $hover-border: shade-color($value, $btn-hover-border-shade-amount),

&#x20;       $active-background: shade-color($value, $btn-active-bg-shade-amount),

&#x20;       $active-border: shade-color($value, $btn-active-border-shade-amount)

&#x20;     );

&#x20;   } @else if $color == "dark" {

&#x20;     @include button-variant(

&#x20;       $value,

&#x20;       $value,

&#x20;       $hover-background: tint-color($value, $btn-hover-bg-tint-amount),

&#x20;       $hover-border: tint-color($value, $btn-hover-border-tint-amount),

&#x20;       $active-background: tint-color($value, $btn-active-bg-tint-amount),

&#x20;       $active-border: tint-color($value, $btn-active-border-tint-amount)

&#x20;     );

&#x20;   } @else {

&#x20;     @include button-variant($value, $value);

&#x20;   }

&#x20; }

}



@each $color, $value in $theme-colors {

&#x20; .btn-outline-#{$color} {

&#x20;   @include button-outline-variant($value);

&#x20; }

}

```



\--------------------------------



\### Use margin utilities for column alignment



Source: https://getbootstrap.com/docs/5.3/layout/columns



Apply margin utilities like .ms-auto or .me-auto to force spacing between sibling columns.



```html

<div class="container text-center">

&#x20; <div class="row">

&#x20;   <div class="col-md-4">.col-md-4</div>

&#x20;   <div class="col-md-4 ms-auto">.col-md-4 .ms-auto</div>

&#x20; </div>

&#x20; <div class="row">

&#x20;   <div class="col-md-3 ms-md-auto">.col-md-3 .ms-md-auto</div>

&#x20;   <div class="col-md-3 ms-md-auto">.col-md-3 .ms-md-auto</div>

&#x20; </div>

&#x20; <div class="row">

&#x20;   <div class="col-auto me-auto">.col-auto .me-auto</div>

&#x20;   <div class="col-auto">.col-auto</div>

&#x20; </div>

</div>

```



\--------------------------------



\### Create a basic card body



Source: https://getbootstrap.com/docs/5.3/components/card



Use the .card-body class to provide a padded section within a card container.



```html

<div class="card">

&#x20; <div class="card-body">

&#x20;   This is some text within a card body.

&#x20; </div>

</div>

```



\--------------------------------



\### Implement custom file input in input groups



Source: https://getbootstrap.com/docs/5.3/forms/input-group



Use the form-control class with type="file" inside an input-group to create custom file upload components.



```html

<div class="input-group mb-3">

&#x20; <label class="input-group-text" for="inputGroupFile01">Upload</label>

&#x20; <input type="file" class="form-control" id="inputGroupFile01">

</div>



<div class="input-group mb-3">

&#x20; <input type="file" class="form-control" id="inputGroupFile02">

&#x20; <label class="input-group-text" for="inputGroupFile02">Upload</label>

</div>



<div class="input-group mb-3">

&#x20; <button class="btn btn-outline-secondary" type="button" id="inputGroupFileAddon03">Button</button>

&#x20; <input type="file" class="form-control" id="inputGroupFile03" aria-describedby="inputGroupFileAddon03" aria-label="Upload">

</div>



<div class="input-group">

&#x20; <input type="file" class="form-control" id="inputGroupFile04" aria-describedby="inputGroupFileAddon04" aria-label="Upload">

&#x20; <button class="btn btn-outline-secondary" type="button" id="inputGroupFileAddon04">Button</button>

</div>

```



\--------------------------------



\### Managing transitioning components



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Method calls on a component currently in transition are ignored.



```javascript

const myCarouselEl = document.querySelector('#myCarousel')

const carousel = bootstrap.Carousel.getInstance(myCarouselEl) // Retrieve a Carousel instance



myCarouselEl.addEventListener('slid.bs.carousel', event => {

&#x20; carousel.to('2') // Will slide to the slide 2 as soon as the transition to slide 1 is finished

})



carousel.to('1') // Will start sliding to the slide 1 and returns to the caller

carousel.to('2') // !! Will be ignored, as the transition to the slide 1 is not finished !!

```



\--------------------------------



\### Include Bootstrap with separate Popper



Source: https://getbootstrap.com/docs/5.3/getting-started/download



Use this configuration if you prefer to load Popper separately before the Bootstrap JavaScript file.



```html

<script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.8/dist/umd/popper.min.js" integrity="sha384-I7E8VVD/ismYTF4hNIPjVp/Zjvgyol6VFvRkX/vR+Vc4jQkC+hVqc2pM8ODewa9r" crossorigin="anonymous"></script>

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.min.js" integrity="sha384-G/EV+4j2dNv+tEPo3++6LCgdCROaejBqfUeNjuKAiuXbjrxilcCdDz6ZAVfHWe1Y" crossorigin="anonymous"></script>

```



\--------------------------------



\### Generate Responsive Fullscreen Modals



Source: https://getbootstrap.com/docs/5.3/components/modal



Sass loop that iterates over grid breakpoints to generate responsive fullscreen modal classes.



```scss

@each $breakpoint in map-keys($grid-breakpoints) {

&#x20; $infix: breakpoint-infix($breakpoint, $grid-breakpoints);

&#x20; $postfix: if($infix != "", $infix + "-down", "");



&#x20; @include media-breakpoint-down($breakpoint) {

&#x20;   .modal-fullscreen#{$postfix} {

&#x20;     width: 100vw;

&#x20;     max-width: none;

&#x20;     height: 100%;

&#x20;     margin: 0;



&#x20;     .modal-content {

&#x20;       height: 100%;

&#x20;       border: 0;

&#x20;       @include border-radius(0);

&#x20;     }



&#x20;     .modal-header,

&#x20;     .modal-footer {

&#x20;       @include border-radius(0);

&#x20;     }



&#x20;     .modal-body {

&#x20;       overflow-y: auto;

&#x20;     }

&#x20;   }

&#x20; }

}

```



\--------------------------------



\### Enable body scrolling with backdrop



Source: https://getbootstrap.com/docs/5.3/components/offcanvas



Configure the offcanvas to allow body scrolling while maintaining a visible backdrop.



```html

<button class="btn btn-primary" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasWithBothOptions" aria-controls="offcanvasWithBothOptions">Enable both scrolling \& backdrop</button>



<div class="offcanvas offcanvas-start" data-bs-scroll="true" tabindex="-1" id="offcanvasWithBothOptions" aria-labelledby="offcanvasWithBothOptionsLabel">

&#x20; <div class="offcanvas-header">

&#x20;   <h5 class="offcanvas-title" id="offcanvasWithBothOptionsLabel">Backdrop with scrolling</h5>

&#x20;   <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>

&#x20; </div>

&#x20; <div class="offcanvas-body">

&#x20;   <p>Try scrolling the rest of the page to see this option in action.</p>

&#x20; </div>

</div>

```



\--------------------------------



\### Configure Yarn 2+ for Bootstrap



Source: https://getbootstrap.com/docs/5.3/getting-started/download



Adjustments required for Yarn Berry to support the node\_modules directory structure used by Bootstrap.



```bash

yarn config set nodeLinker node-modules # Use the node\_modules linker

touch yarn.lock # Create an empty yarn.lock file

yarn install # Install the dependencies

yarn start # Start the project

```



\--------------------------------



\### Tooltip Methods



Source: https://getbootstrap.com/docs/5.3/components/tooltips



Methods available on the Bootstrap Tooltip instance to control visibility, state, and content.



```APIDOC

\## Tooltip Methods



\### Description

Methods to manage tooltip behavior, including enabling, disabling, showing, hiding, and updating content.



\### Methods

\- \*\*disable()\*\*: Removes the ability for an element’s tooltip to be shown.

\- \*\*dispose()\*\*: Hides and destroys an element’s tooltip.

\- \*\*enable()\*\*: Gives an element’s tooltip the ability to be shown.

\- \*\*getInstance(element)\*\*: Static method to get the tooltip instance associated with a DOM element.

\- \*\*getOrCreateInstance(element)\*\*: Static method to get or create a tooltip instance for a DOM element.

\- \*\*hide()\*\*: Manually hides the tooltip.

\- \*\*setContent(object)\*\*: Updates the tooltip content after initialization.

\- \*\*show()\*\*: Manually reveals the tooltip.

\- \*\*toggle()\*\*: Toggles the tooltip visibility.

\- \*\*toggleEnabled()\*\*: Toggles the enabled state of the tooltip.

\- \*\*update()\*\*: Updates the position of the tooltip.

```



\--------------------------------



\### Create custom button sizes



Source: https://getbootstrap.com/docs/5.3/components/buttons



Override padding and font size using inline CSS variables.



```html

<button type="button" class="btn btn-primary"

&#x20;       style="--bs-btn-padding-y: .25rem; --bs-btn-padding-x: .5rem; --bs-btn-font-size: .75rem;">

&#x20; Custom button

</button>

```



\--------------------------------



\### Apply viewport-relative sizing utilities



Source: https://getbootstrap.com/docs/5.3/utilities/sizing



Sets width and height relative to the browser viewport dimensions.



```html

<div class="min-vw-100">Min-width 100vw</div>

<div class="min-vh-100">Min-height 100vh</div>

<div class="vw-100">Width 100vw</div>

<div class="vh-100">Height 100vh</div>

```



\--------------------------------



\### Use Responsive Containers in Navbar



Source: https://getbootstrap.com/docs/5.3/components/navbar



Apply responsive container classes like container-md to control the width of navbar content.



```html

<nav class="navbar navbar-expand-lg bg-body-tertiary">

&#x20; <div class="container-md">

&#x20;   <a class="navbar-brand" href="#">Navbar</a>

&#x20; </div>

</nav>

```



\--------------------------------



\### Enable CSS Grid via Sass



Source: https://getbootstrap.com/docs/5.3/layout/css-grid



Configure Sass variables to disable the default grid system and enable the CSS Grid implementation.



```scss

$enable-grid-classes: false;

$enable-cssgrid: true;

```



\--------------------------------



\### Programmatically Toggle Buttons with JavaScript



Source: https://getbootstrap.com/docs/5.3/components/buttons



Use getOrCreateInstance to retrieve or initialize button instances and trigger the toggle method.



```javascript

document.querySelectorAll('.btn').forEach(buttonElement => {

&#x20; const button = bootstrap.Button.getOrCreateInstance(buttonElement)

&#x20; button.toggle()

})

```



\--------------------------------



\### Create a grid of equal height cards



Source: https://getbootstrap.com/docs/5.3/components/card



Uses the row-cols utility classes to create a responsive grid where all cards maintain equal height.



```html

<div class="row row-cols-1 row-cols-md-3 g-4">

&#x20; <div class="col">

&#x20;   <div class="card h-100">

&#x20;     <img src="..." class="card-img-top" alt="...">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col">

&#x20;   <div class="card h-100">

&#x20;     <img src="..." class="card-img-top" alt="...">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This is a short card.</p>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col">

&#x20;   <div class="card h-100">

&#x20;     <img src="..." class="card-img-top" alt="...">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content.</p>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col">

&#x20;   <div class="card h-100">

&#x20;     <img src="..." class="card-img-top" alt="...">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Sizing Select Menus



Source: https://getbootstrap.com/docs/5.3/forms/select



Use .form-select-lg or .form-select-sm classes to adjust the size of the select menu.



```html

<select class="form-select form-select-lg mb-3" aria-label="Large select example">

&#x20; <option selected>Open this select menu</option>

&#x20; <option value="1">One</option>

&#x20; <option value="2">Two</option>

&#x20; <option value="3">Three</option>

</select>



<select class="form-select form-select-sm" aria-label="Small select example">

&#x20; <option selected>Open this select menu</option>

&#x20; <option value="1">One</option>

&#x20; <option value="2">Two</option>

&#x20; <option value="3">Three</option>

</select>

```



\--------------------------------



\### Create an outlined button group



Source: https://getbootstrap.com/docs/5.3/components/button-group



Uses the btn-outline-primary class to create a group of buttons with an outlined appearance.



```html

<div class="btn-group" role="group" aria-label="Basic outlined example">

&#x20; <button type="button" class="btn btn-outline-primary">Left</button>

&#x20; <button type="button" class="btn btn-outline-primary">Middle</button>

&#x20; <button type="button" class="btn btn-outline-primary">Right</button>

</div>

```



\--------------------------------



\### Define Browser Support in .browserslistrc



Source: https://getbootstrap.com/docs/5.3/getting-started/browsers-devices



Configuration file used to specify the range of supported browsers and versions for Autoprefixer.



```text

\# https://github.com/browserslist/browserslist#readme



>= 0.5%

last 2 major versions

not dead

Chrome >= 60

Firefox >= 60

Firefox ESR

iOS >= 12

Safari >= 12

not Explorer <= 11

not kaios <= 2.5 # fix floating label issues in Firefox (see https://github.com/postcss/autoprefixer/issues/1533)

```



\--------------------------------



\### Apply background and text color to cards



Source: https://getbootstrap.com/docs/5.3/components/card



Use these classes to set a background color with a contrasting foreground color on card components.



```html

<div class="card text-bg-primary mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Primary card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

<div class="card text-bg-secondary mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Secondary card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

<div class="card text-bg-success mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Success card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

<div class="card text-bg-danger mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Danger card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

<div class="card text-bg-warning mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Warning card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

<div class="card text-bg-info mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Info card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

<div class="card text-bg-light mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Light card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

<div class="card text-bg-dark mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Dark card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

```



\--------------------------------



\### Live popover demo



Source: https://getbootstrap.com/docs/5.3/components/popovers



A button element configured to trigger a popover with a title and body content.



```html

<button type="button" class="btn btn-lg btn-danger" data-bs-toggle="popover" data-bs-title="Popover title" data-bs-content="And here’s some amazing content. It’s very engaging. Right?">Click to toggle popover</button>

```



\--------------------------------



\### Enable HTML in tooltips



Source: https://getbootstrap.com/docs/5.3/components/tooltips



Set data-bs-html to true to allow rendering HTML tags within the tooltip content.



```html

<button type="button" class="btn btn-secondary" data-bs-toggle="tooltip" data-bs-html="true" data-bs-title="<em>Tooltip</em> <u>with</u> <b>HTML</b>">

&#x20; Tooltip with HTML

</button>

```



\--------------------------------



\### Configure Utility Class Prefix



Source: https://getbootstrap.com/docs/5.3/utilities/api



Use the class option to override the default class prefix. Setting class to null generates classes directly from the values keys.



```scss

$utilities: (

&#x20; "opacity": (

&#x20;   property: opacity,

&#x20;   class: o,

&#x20;   values: (

&#x20;     0: 0,

&#x20;     25: .25,

&#x20;     50: .5,

&#x20;     75: .75,

&#x20;     100: 1,

&#x20;   )

&#x20; )

);

```



```css

.o-0 { opacity: 0 !important; }

.o-25 { opacity: .25 !important; }

.o-50 { opacity: .5 !important; }

.o-75 { opacity: .75 !important; }

.o-100 { opacity: 1 !important; }

```



```scss

$utilities: (

&#x20; "visibility": (

&#x20;   property: visibility,

&#x20;   class: null,

&#x20;   values: (

&#x20;     visible: visible,

&#x20;     invisible: hidden,

&#x20;   )

&#x20; )

);

```



```css

.visible { visibility: visible !important; }

.invisible { visibility: hidden !important; }

```



\--------------------------------



\### Create a static modal component



Source: https://getbootstrap.com/docs/5.3/components/modal



Defines the basic structure of a modal including header, body, and footer components.



```html

<div class="modal" tabindex="-1">

&#x20; <div class="modal-dialog">

&#x20;   <div class="modal-content">

&#x20;     <div class="modal-header">

&#x20;       <h5 class="modal-title">Modal title</h5>

&#x20;       <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>

&#x20;     </div>

&#x20;     <div class="modal-body">

&#x20;       <p>Modal body text goes here.</p>

&#x20;     </div>

&#x20;     <div class="modal-footer">

&#x20;       <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>

&#x20;       <button type="button" class="btn btn-primary">Save changes</button>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Define background opacity utility



Source: https://getbootstrap.com/docs/5.3/utilities/background



Shows the internal structure of a background utility using CSS variables for opacity control.



```css

.bg-success {

&#x20; --bs-bg-opacity: 1;

&#x20; background-color: rgba(var(--bs-success-rgb), var(--bs-bg-opacity)) !important;

}

```



\--------------------------------



\### Implement Grid System in Modals



Source: https://getbootstrap.com/docs/5.3/components/modal



Nest a .container-fluid within the .modal-body to enable standard Bootstrap grid layouts.



```html

<div class="modal-body">

&#x20; <div class="container-fluid">

&#x20;   <div class="row">

&#x20;     <div class="col-md-4">.col-md-4</div>

&#x20;     <div class="col-md-4 ms-auto">.col-md-4 .ms-auto</div>

&#x20;   </div>

&#x20;   <div class="row">

&#x20;     <div class="col-md-3 ms-auto">.col-md-3 .ms-auto</div>

&#x20;     <div class="col-md-2 ms-auto">.col-md-2 .ms-auto</div>

&#x20;   </div>

&#x20;   <div class="row">

&#x20;     <div class="col-md-6 ms-auto">.col-md-6 .ms-auto</div>

&#x20;   </div>

&#x20;   <div class="row">

&#x20;     <div class="col-sm-9">

&#x20;       Level 1: .col-sm-9

&#x20;       <div class="row">

&#x20;         <div class="col-8 col-sm-6">

&#x20;           Level 2: .col-8 .col-sm-6

&#x20;         </div>

&#x20;         <div class="col-4 col-sm-6">

&#x20;           Level 2: .col-4 .col-sm-6

&#x20;         </div>

&#x20;       </div>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Small Button Dropdown Sizing



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



Implementation of small button dropdowns and split button dropdowns using the btn-sm class.



```html

<div class="btn-group">

&#x20; <button class="btn btn-secondary btn-sm dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   Small button

&#x20; </button>

&#x20; <ul class="dropdown-menu">

&#x20;   ...

&#x20; </ul>

</div>

<div class="btn-group">

&#x20; <button class="btn btn-secondary btn-sm" type="button">

&#x20;   Small split button

&#x20; </button>

&#x20; <button type="button" class="btn btn-sm btn-secondary dropdown-toggle dropdown-toggle-split" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   <span class="visually-hidden">Toggle Dropdown</span>

&#x20; </button>

&#x20; <ul class="dropdown-menu">

&#x20;   ...

&#x20; </ul>

</div>

```



\--------------------------------



\### Indicate keyboard input



Source: https://getbootstrap.com/docs/5.3/content/reboot



Use the <kbd> tag to represent user keyboard input.



```html

To switch directories, type <kbd>cd</kbd> followed by the name of the directory.<br>

To edit settings, press <kbd><kbd>Ctrl</kbd> + <kbd>,</kbd></kbd>

```



\--------------------------------



\### Initialize Carousel via JavaScript



Source: https://getbootstrap.com/docs/5.3/components/carousel



Manually initialize a carousel instance by passing a selector to the constructor.



```javascript

const carousel = new bootstrap.Carousel('#myCarousel')

```



\--------------------------------



\### Implement Nav Pills with Tab Content



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



Uses data-bs-toggle="pill" to link navigation buttons to their respective tab-pane content containers.



```html

<ul class="nav nav-pills mb-3" id="pills-tab" role="tablist">

&#x20; <li class="nav-item" role="presentation">

&#x20;   <button class="nav-link active" id="pills-home-tab" data-bs-toggle="pill" data-bs-target="#pills-home" type="button" role="tab" aria-controls="pills-home" aria-selected="true">Home</button>

&#x20; </li>

&#x20; <li class="nav-item" role="presentation">

&#x20;   <button class="nav-link" id="pills-profile-tab" data-bs-toggle="pill" data-bs-target="#pills-profile" type="button" role="tab" aria-controls="pills-profile" aria-selected="false">Profile</button>

&#x20; </li>

&#x20; <li class="nav-item" role="presentation">

&#x20;   <button class="nav-link" id="pills-contact-tab" data-bs-toggle="pill" data-bs-target="#pills-contact" type="button" role="tab" aria-controls="pills-contact" aria-selected="false">Contact</button>

&#x20; </li>

&#x20; <li class="nav-item" role="presentation">

&#x20;   <button class="nav-link" id="pills-disabled-tab" data-bs-toggle="pill" data-bs-target="#pills-disabled" type="button" role="tab" aria-controls="pills-disabled" aria-selected="false" disabled>Disabled</button>

&#x20; </li>

</ul>

<div class="tab-content" id="pills-tabContent">

&#x20; <div class="tab-pane fade show active" id="pills-home" role="tabpanel" aria-labelledby="pills-home-tab" tabindex="0">...</div>

&#x20; <div class="tab-pane fade" id="pills-profile" role="tabpanel" aria-labelledby="pills-profile-tab" tabindex="0">...</div>

&#x20; <div class="tab-pane fade" id="pills-contact" role="tabpanel" aria-labelledby="pills-contact-tab" tabindex="0">...</div>

&#x20; <div class="tab-pane fade" id="pills-disabled" role="tabpanel" aria-labelledby="pills-disabled-tab" tabindex="0">...</div>

</div>

```



\--------------------------------



\### Dropstart Variations



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



Use .dropstart on the parent element to trigger menus to the left of the toggle.



```html

<!-- Default dropstart button -->

<div class="btn-group dropstart">

&#x20; <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   Dropstart

&#x20; </button>

&#x20; <ul class="dropdown-menu">

&#x20;   <!-- Dropdown menu links -->

&#x20; </ul>

</div>



<!-- Split dropstart button -->

<div class="btn-group dropstart">

&#x20; <button type="button" class="btn btn-secondary dropdown-toggle dropdown-toggle-split" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   <span class="visually-hidden">Toggle Dropstart</span>

&#x20; </button>

&#x20; <ul class="dropdown-menu">

&#x20;   <!-- Dropdown menu links -->

&#x20; </ul>

&#x20; <button type="button" class="btn btn-secondary">

&#x20;   Split dropstart

&#x20; </button>

</div>

```



\--------------------------------



\### Generating color contrast swatches



Source: https://getbootstrap.com/docs/5.3/customize/sass



Use the color-contrast function within an @each loop to generate accessible text colors for theme swatches.



```scss

@each $color, $value in $theme-colors {

&#x20; .swatch-#{$color} {

&#x20;   color: color-contrast($value);

&#x20; }

}



```



\--------------------------------



\### Align images with helper classes



Source: https://getbootstrap.com/docs/5.3/content/images



Use float or margin utility classes to align images horizontally.



```html

<img src="..." class="rounded float-start" alt="...">

<img src="..." class="rounded float-end" alt="...">

```



```html

<img src="..." class="rounded mx-auto d-block" alt="...">

```



```html

<div class="text-center">

&#x20; <img src="..." class="rounded" alt="...">

</div>

```



\--------------------------------



\### Tab Methods



Source: https://getbootstrap.com/docs/5.3/components/navs



Methods available on the Tab instance or as static methods on the bootstrap.Tab class.



```APIDOC

\## Tab Methods



\### dispose()

Destroys an element’s tab.



\### static getInstance(element)

Static method which allows you to get the tab instance associated with a DOM element.



\### static getOrCreateInstance(element)

Static method which returns a tab instance associated to a DOM element or creates a new one if it wasn’t initialized.



\### show()

Selects the given tab and shows its associated pane. Returns to the caller before the tab pane has actually been shown.

```



\--------------------------------



\### Enable dark mode globally



Source: https://getbootstrap.com/docs/5.3/customize/color-modes



Apply the dark color mode to the entire project by adding the data-bs-theme attribute to the html element.



```html

<!doctype html>

<html lang="en" data-bs-theme="dark">

&#x20; <head>

&#x20;   <meta charset="utf-8">

&#x20;   <meta name="viewport" content="width=device-width, initial-scale=1">

&#x20;   <title>Bootstrap demo</title>

&#x20;   <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB" crossorigin="anonymous">

&#x20; </head>

&#x20; <body>

&#x20;   <h1>Hello, world!</h1>

&#x20;   <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js" integrity="sha384-FKyoEForCGlyvwx9Hj09JcYn3nv7wiPVlz7YYwJrWVcXK/BmnVDxM+D2scQbITxI" crossorigin="anonymous"></script>

&#x20; </body>

</html>

```



\--------------------------------



\### Initialize Tabbable List Items via JavaScript



Source: https://getbootstrap.com/docs/5.3/components/list-group



Manually enables tab functionality for list items using the Bootstrap Tab constructor.



```javascript

const triggerTabList = document.querySelectorAll('#myTab a')

triggerTabList.forEach(triggerEl => {

&#x20; const tabTrigger = new bootstrap.Tab(triggerEl)



&#x20; triggerEl.addEventListener('click', event => {

&#x20;   event.preventDefault()

&#x20;   tabTrigger.show()

&#x20; })

})

```



\--------------------------------



\### Importing specific Bootstrap components



Source: https://getbootstrap.com/docs/5.3/customize/optimize



Use this pattern to import only the required JavaScript modules from the distribution folder.



```javascript

// Import just what we need



// import 'bootstrap/js/dist/alert';

// import 'bootstrap/js/dist/button';

// import 'bootstrap/js/dist/carousel';

// import 'bootstrap/js/dist/collapse';

// import 'bootstrap/js/dist/dropdown';

import 'bootstrap/js/dist/modal';

// import 'bootstrap/js/dist/offcanvas';

// import 'bootstrap/js/dist/popover';

// import 'bootstrap/js/dist/scrollspy';

// import 'bootstrap/js/dist/tab';

// import 'bootstrap/js/dist/toast';

// import 'bootstrap/js/dist/tooltip';

```



\--------------------------------



\### Handling asynchronous transitions



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Listen for completion events to execute actions after an asynchronous transition finishes.



```javascript

const myCollapseEl = document.querySelector('#myCollapse')



myCollapseEl.addEventListener('shown.bs.collapse', event => {

&#x20; // Action to execute once the collapsible area is expanded

})

```



\--------------------------------



\### Configure Dropdown Positioning



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



Use data-bs-offset to adjust the menu position and data-bs-reference to define the reference element for the dropdown.



```html

<div class="d-flex">

&#x20; <div class="dropdown me-1">

&#x20;   <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false" data-bs-offset="10,20">

&#x20;     Offset

&#x20;   </button>

&#x20;   <ul class="dropdown-menu">

&#x20;     <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;     <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;     <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;   </ul>

&#x20; </div>

&#x20; <div class="btn-group">

&#x20;   <button type="button" class="btn btn-secondary">Reference</button>

&#x20;   <button type="button" class="btn btn-secondary dropdown-toggle dropdown-toggle-split" data-bs-toggle="dropdown" aria-expanded="false" data-bs-reference="parent">

&#x20;     <span class="visually-hidden">Toggle Dropdown</span>

&#x20;   </button>

&#x20;   <ul class="dropdown-menu">

&#x20;     <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;     <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;     <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;     <li><hr class="dropdown-divider"></li>

&#x20;     <li><a class="dropdown-item" href="#">Separated link</a></li>

&#x20;   </ul>

&#x20; </div>

</div>

```



\--------------------------------



\### Utilities API Configuration



Source: https://getbootstrap.com/docs/5.3/helpers/focus-ring



The configuration used in the utilities API to generate focus ring color classes.



```scss

"focus-ring": (

&#x20; css-var: true,

&#x20; css-variable-name: focus-ring-color,

&#x20; class: focus-ring,

&#x20; values: map-loop($theme-colors-rgb, rgba-css-var, "$key", "focus-ring")

),

```



\--------------------------------



\### Apply button group sizing



Source: https://getbootstrap.com/docs/5.3/components/button-group



Use .btn-group-lg, .btn-group, or .btn-group-sm on the container to size all buttons within the group simultaneously.



```html

<div class="btn-group btn-group-lg" role="group" aria-label="Large button group">

&#x20; <button type="button" class="btn btn-outline-primary">Left</button>

&#x20; <button type="button" class="btn btn-outline-primary">Middle</button>

&#x20; <button type="button" class="btn btn-outline-primary">Right</button>

</div>

<br>

<div class="btn-group" role="group" aria-label="Default button group">

&#x20; <button type="button" class="btn btn-outline-primary">Left</button>

&#x20; <button type="button" class="btn btn-outline-primary">Middle</button>

&#x20; <button type="button" class="btn btn-outline-primary">Right</button>

</div>

<br>

<div class="btn-group btn-group-sm" role="group" aria-label="Small button group">

&#x20; <button type="button" class="btn btn-outline-primary">Left</button>

&#x20; <button type="button" class="btn btn-outline-primary">Middle</button>

&#x20; <button type="button" class="btn btn-outline-primary">Right</button>

</div>

```



\--------------------------------



\### Nesting CSS Grids



Source: https://getbootstrap.com/docs/5.3/layout/css-grid



Demonstrates nesting grids where child grids inherit or override column counts using CSS variables.



```html

<div class="grid text-center overflow-x-auto" style="--bs-columns: 3;">

&#x20; <div>

&#x20;   First auto-column

&#x20;   <div class="grid">

&#x20;     <div>Auto-column</div>

&#x20;     <div>Auto-column</div>

&#x20;   </div>

&#x20; </div>

&#x20; <div>

&#x20;   Second auto-column

&#x20;   <div class="grid" style="--bs-columns: 12;">

&#x20;     <div class="g-col-6">6 of 12</div>

&#x20;     <div class="g-col-4">4 of 12</div>

&#x20;     <div class="g-col-2">2 of 12</div>

&#x20;   </div>

&#x20; </div>

&#x20; <div>Third auto-column</div>

</div>

```



\--------------------------------



\### Multiple Addons



Source: https://getbootstrap.com/docs/5.3/forms/input-group



Combine multiple text or symbol addons within an input group, placed either before or after the input field.



```html

<div class="input-group mb-3">

&#x20; <span class="input-group-text">$</span>

&#x20; <span class="input-group-text">0.00</span>

&#x20; <input type="text" class="form-control" aria-label="Dollar amount (with dot and two decimal places)">

</div>



<div class="input-group">

&#x20; <input type="text" class="form-control" aria-label="Dollar amount (with dot and two decimal places)">

&#x20; <span class="input-group-text">$</span>

&#x20; <span class="input-group-text">0.00</span>

</div>

```



\--------------------------------



\### Create a button group with mixed styles



Source: https://getbootstrap.com/docs/5.3/components/button-group



Combine different button contextual classes within a single group.



```html

<div class="btn-group" role="group" aria-label="Basic mixed styles example">

&#x20; <button type="button" class="btn btn-danger">Left</button>

&#x20; <button type="button" class="btn btn-warning">Middle</button>

&#x20; <button type="button" class="btn btn-success">Right</button>

</div>

```



\--------------------------------



\### Basic Table Structure



Source: https://getbootstrap.com/docs/5.3/content/tables



Standard HTML table structure using Bootstrap's .table class.



```html

<table class="table">

&#x20; <thead>

&#x20;   ...

&#x20; </thead>

&#x20; <tbody>

&#x20;   ...

&#x20; </tbody>

&#x20; <tfoot>

&#x20;   ...

&#x20; </tfoot>

</table>

```



\--------------------------------



\### Configure image thumbnail Sass variables



Source: https://getbootstrap.com/docs/5.3/content/images



Customize thumbnail appearance using these Sass variables.



```scss

$thumbnail-padding:                 .25rem;

$thumbnail-bg:                      var(--#{$prefix}body-bg);

$thumbnail-border-width:            var(--#{$prefix}border-width);

$thumbnail-border-color:            var(--#{$prefix}border-color);

$thumbnail-border-radius:           var(--#{$prefix}border-radius);

$thumbnail-box-shadow:              var(--#{$prefix}box-shadow-sm);

```



\--------------------------------



\### Implement a standard Bootstrap modal



Source: https://getbootstrap.com/docs/5.3/components/modal



Uses a button trigger with data-bs-toggle and data-bs-target attributes to display a modal dialog.



```html

<!-- Button trigger modal -->

<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">

&#x20; Launch demo modal

</button>



<!-- Modal -->

<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">

&#x20; <div class="modal-dialog">

&#x20;   <div class="modal-content">

&#x20;     <div class="modal-header">

&#x20;       <h1 class="modal-title fs-5" id="exampleModalLabel">Modal title</h1>

&#x20;       <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>

&#x20;     </div>

&#x20;     <div class="modal-body">

&#x20;       ...

&#x20;     </div>

&#x20;     <div class="modal-footer">

&#x20;       <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>

&#x20;       <button type="button" class="btn btn-primary">Save changes</button>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Create a placeholder link



Source: https://getbootstrap.com/docs/5.3/content



Anchor tag without an href attribute, which resets color and text-decoration to default values.



```html

<a>This is a placeholder link</a>

```



\--------------------------------



\### Create a responsive card grid



Source: https://getbootstrap.com/docs/5.3/components/card



Uses row-cols-1 and row-cols-md-2 to define a grid that adjusts from single-column to two-column layout on medium screens.



```html

<div class="row row-cols-1 row-cols-md-2 g-4">

&#x20; <div class="col">

&#x20;   <div class="card">

&#x20;     <img src="..." class="card-img-top" alt="...">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col">

&#x20;   <div class="card">

&#x20;     <img src="..." class="card-img-top" alt="...">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col">

&#x20;   <div class="card">

&#x20;     <img src="..." class="card-img-top" alt="...">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content.</p>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col">

&#x20;   <div class="card">

&#x20;     <img src="..." class="card-img-top" alt="...">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Create a list group with custom content



Source: https://getbootstrap.com/docs/5.3/components/list-group



Incorporate complex HTML structures inside list group items by leveraging flexbox utilities for layout control.



```html

<div class="list-group">

&#x20; <a href="#" class="list-group-item list-group-item-action active" aria-current="true">

&#x20;   <div class="d-flex w-100 justify-content-between">

&#x20;     <h5 class="mb-1">List group item heading</h5>

&#x20;     <small>3 days ago</small>

&#x20;   </div>

&#x20;   <p class="mb-1">Some placeholder content in a paragraph.</p>

&#x20;   <small>And some small print.</small>

&#x20; </a>

&#x20; <a href="#" class="list-group-item list-group-item-action">

&#x20;   <div class="d-flex w-100 justify-content-between">

&#x20;     <h5 class="mb-1">List group item heading</h5>

&#x20;     <small class="text-body-secondary">3 days ago</small>

&#x20;   </div>

&#x20;   <p class="mb-1">Some placeholder content in a paragraph.</p>

&#x20;   <small class="text-body-secondary">And some muted small print.</small>

&#x20; </a>

&#x20; <a href="#" class="list-group-item list-group-item-action">

&#x20;   <div class="d-flex w-100 justify-content-between">

&#x20;     <h5 class="mb-1">List group item heading</h5>

&#x20;     <small class="text-body-secondary">3 days ago</small>

&#x20;   </div>

&#x20;   <p class="mb-1">Some placeholder content in a paragraph.</p>

&#x20;   <small class="text-body-secondary">And some muted small print.</small>

&#x20; </a>

</div>

```



\--------------------------------



\### Customize grid tiers and container widths



Source: https://getbootstrap.com/docs/5.3/layout/grid



Update the grid breakpoints and container maximum widths to define custom responsive tiers.



```scss

$grid-breakpoints: (

&#x20; xs: 0,

&#x20; sm: 480px,

&#x20; md: 768px,

&#x20; lg: 1024px

);



$container-max-widths: (

&#x20; sm: 420px,

&#x20; md: 720px,

&#x20; lg: 960px

);

```



\--------------------------------



\### Dropdown Methods



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



Programmatic methods to control the state and lifecycle of a dropdown instance.



```APIDOC

\## Dropdown Methods



\### Description

Methods available on the Dropdown instance to manipulate the component programmatically.



\### Methods

\- \*\*dispose()\*\* - Destroys an element’s dropdown and removes stored data.

\- \*\*getInstance(element)\*\* - Static method to get the dropdown instance associated with a DOM element.

\- \*\*getOrCreateInstance(element)\*\* - Static method to get an existing instance or create a new one.

\- \*\*hide()\*\* - Hides the dropdown menu.

\- \*\*show()\*\* - Shows the dropdown menu.

\- \*\*toggle()\*\* - Toggles the dropdown menu visibility.

\- \*\*update()\*\* - Updates the position of the dropdown.

```



\--------------------------------



\### Apply border colors



Source: https://getbootstrap.com/docs/5.3/utilities/borders



Change border colors using theme-based utility classes.



```html

<span class="border border-primary"></span>

<span class="border border-primary-subtle"></span>

<span class="border border-secondary"></span>

<span class="border border-secondary-subtle"></span>

<span class="border border-success"></span>

<span class="border border-success-subtle"></span>

<span class="border border-danger"></span>

<span class="border border-danger-subtle"></span>

<span class="border border-warning"></span>

<span class="border border-warning-subtle"></span>

<span class="border border-info"></span>

<span class="border border-info-subtle"></span>

<span class="border border-light"></span>

<span class="border border-light-subtle"></span>

<span class="border border-dark"></span>

<span class="border border-dark-subtle"></span>

<span class="border border-black"></span>

<span class="border border-white"></span>

```



\--------------------------------



\### Link Hover Variant Utilities



Source: https://getbootstrap.com/docs/5.3/utilities/link



Combine offset and opacity utilities with hover variants to create interactive link styles.



```html

<a class="link-offset-2 link-offset-3-hover link-underline link-underline-opacity-0 link-underline-opacity-75-hover" href="#">

&#x20; Underline opacity 0

</a>

```



\--------------------------------



\### Configure multiple toggles and targets



Source: https://getbootstrap.com/docs/5.3/components/collapse



Reference multiple elements in data-bs-target or href to control several collapse components simultaneously.



```html

<p class="d-inline-flex gap-1">

&#x20; <a class="btn btn-primary" data-bs-toggle="collapse" href="#multiCollapseExample1" role="button" aria-expanded="false" aria-controls="multiCollapseExample1">Toggle first element</a>

&#x20; <button class="btn btn-primary" type="button" data-bs-toggle="collapse" data-bs-target="#multiCollapseExample2" aria-expanded="false" aria-controls="multiCollapseExample2">Toggle second element</button>

&#x20; <button class="btn btn-primary" type="button" data-bs-toggle="collapse" data-bs-target=".multi-collapse" aria-expanded="false" aria-controls="multiCollapseExample1 multiCollapseExample2">Toggle both elements</button>

</p>

<div class="row">

&#x20; <div class="col">

&#x20;   <div class="collapse multi-collapse" id="multiCollapseExample1">

&#x20;     <div class="card card-body">

&#x20;       Some placeholder content for the first collapse component of this multi-collapse example. This panel is hidden by default but revealed when the user activates the relevant trigger.

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col">

&#x20;   <div class="collapse multi-collapse" id="multiCollapseExample2">

&#x20;     <div class="card card-body">

&#x20;       Some placeholder content for the second collapse component of this multi-collapse example. This panel is hidden by default but revealed when the user activates the relevant trigger.

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### bootstrap.Carousel Constructor



Source: https://getbootstrap.com/docs/5.3/components/carousel



Initializes a new carousel instance on a DOM element with optional configuration.



```APIDOC

\## new bootstrap.Carousel(element, options)



\### Description

Creates a new carousel instance. The constructor accepts a DOM element or selector and an optional configuration object.



\### Parameters

\- \*\*element\*\* (string|Element) - Required - The DOM element or selector to initialize the carousel on.

\- \*\*options\*\* (object) - Optional - Configuration object for the carousel.



\### Options

\- \*\*interval\*\* (number) - Default: 5000 - Time to delay between automatically cycling items.

\- \*\*keyboard\*\* (boolean) - Default: true - Whether the carousel should react to keyboard events.

\- \*\*pause\*\* (string|boolean) - Default: "hover" - Pauses cycling on mouseenter and resumes on mouseleave.

\- \*\*ride\*\* (string|boolean) - Default: false - Autoplay behavior.

\- \*\*touch\*\* (boolean) - Default: true - Whether to support swipe interactions.

\- \*\*wrap\*\* (boolean) - Default: true - Whether the carousel should cycle continuously.

```



\--------------------------------



\### Implement top-positioned offcanvas



Source: https://getbootstrap.com/docs/5.3/components/offcanvas



Uses the .offcanvas-top class to anchor the component to the top of the viewport.



```html

<button class="btn btn-primary" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasTop" aria-controls="offcanvasTop">Toggle top offcanvas</button>



<div class="offcanvas offcanvas-top" tabindex="-1" id="offcanvasTop" aria-labelledby="offcanvasTopLabel">

&#x20; <div class="offcanvas-header">

&#x20;   <h5 class="offcanvas-title" id="offcanvasTopLabel">Offcanvas top</h5>

&#x20;   <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>

&#x20; </div>

&#x20; <div class="offcanvas-body">

&#x20;   ...

&#x20; </div>

</div>

```



\--------------------------------



\### Create stacked progress bars



Source: https://getbootstrap.com/docs/5.3/components/progress



Use the .progress-stacked container to group multiple progress bars. Apply width styles directly to the .progress elements instead of the .progress-bar elements.



```html

<div class="progress-stacked">

&#x20; <div class="progress" role="progressbar" aria-label="Segment one" aria-valuenow="15" aria-valuemin="0" aria-valuemax="100" style="width: 15%">

&#x20;   <div class="progress-bar"></div>

&#x20; </div>

&#x20; <div class="progress" role="progressbar" aria-label="Segment two" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100" style="width: 30%">

&#x20;   <div class="progress-bar bg-success"></div>

&#x20; </div>

&#x20; <div class="progress" role="progressbar" aria-label="Segment three" aria-valuenow="20" aria-valuemin="0" aria-valuemax="100" style="width: 20%">

&#x20;   <div class="progress-bar bg-info"></div>

&#x20; </div>

</div>

```



\--------------------------------



\### getOrCreateInstance



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Retrieves an existing plugin instance or creates a new one if it does not exist.



```APIDOC

\## bootstrap.Plugin.getOrCreateInstance(element, options?)



\### Description

Retrieves the instance associated with a DOM element, or initializes a new one if it wasn't already initialized. Accepts an optional configuration object if a new instance is created.



\### Parameters

\- \*\*element\*\* (HTMLElement|string) - Required - The DOM element or CSS selector.

\- \*\*options\*\* (Object) - Optional - Configuration object used only if a new instance is created.

```



\--------------------------------



\### Perform Real-time Customization



Source: https://getbootstrap.com/docs/5.3/content/reboot



Shows how to override Bootstrap CSS variables directly on an HTML element.



```html

<body style="--bs-body-color: #333;">

&#x20; <!-- ... -->

</body>

```



\--------------------------------



\### Create an unstyled list



Source: https://getbootstrap.com/docs/5.3/content/typography



Use the .list-unstyled class to remove default list-style and left margin from immediate children.



```html

<ul class="list-unstyled">

&#x20; <li>This is a list.</li>

&#x20; <li>It appears completely unstyled.</li>

&#x20; <li>Structurally, it’s still a list.</li>

&#x20; <li>However, this style only applies to immediate child elements.</li>

&#x20; <li>Nested lists:

&#x20;   <ul>

&#x20;     <li>are unaffected by this style</li>

&#x20;     <li>will still show a bullet</li>

&#x20;     <li>and have appropriate left margin</li>

&#x20;   </ul>

&#x20; </li>

&#x20; <li>This may still come in handy in some situations.</li>

</ul>

```



\--------------------------------



\### Configure Navbar Sass Variables



Source: https://getbootstrap.com/docs/5.3/components/navbar



Global variables for controlling padding, font sizes, and toggler styles in the navbar.



```scss

$navbar-padding-y:                  $spacer \* .5;

$navbar-padding-x:                  null;



$navbar-nav-link-padding-x:         .5rem;



$navbar-brand-font-size:            $font-size-lg;

// Compute the navbar-brand padding-y so the navbar-brand will have the same height as navbar-text and nav-link

$nav-link-height:                   $font-size-base \* $line-height-base + $nav-link-padding-y \* 2;

$navbar-brand-height:               $navbar-brand-font-size \* $line-height-base;

$navbar-brand-padding-y:            ($nav-link-height - $navbar-brand-height) \* .5;

$navbar-brand-margin-end:           1rem;



$navbar-toggler-padding-y:          .25rem;

$navbar-toggler-padding-x:          .75rem;

$navbar-toggler-font-size:          $font-size-lg;

$navbar-toggler-border-radius:      $btn-border-radius;

$navbar-toggler-focus-width:        $btn-focus-width;

$navbar-toggler-transition:         box-shadow .15s ease-in-out;



$navbar-light-color:                rgba(var(--#{$prefix}emphasis-color-rgb), .65);

$navbar-light-hover-color:          rgba(var(--#{$prefix}emphasis-color-rgb), .8);

$navbar-light-active-color:         rgba(var(--#{$prefix}emphasis-color-rgb), 1);

$navbar-light-disabled-color:       rgba(var(--#{$prefix}emphasis-color-rgb), .3);

$navbar-light-icon-color:           rgba($body-color, .75);

$navbar-light-toggler-icon-bg:      url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 30 30'><path stroke='#{$navbar-light-icon-color}' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/></svg>");

$navbar-light-toggler-border-color: rgba(var(--#{$prefix}emphasis-color-rgb), .15);

$navbar-light-brand-color:          $navbar-light-active-color;

$navbar-light-brand-hover-color:    $navbar-light-active-color;

```



```scss

$navbar-dark-color:                 rgba($white, .55);

$navbar-dark-hover-color:           rgba($white, .75);

$navbar-dark-active-color:          $white;

$navbar-dark-disabled-color:        rgba($white, .25);

$navbar-dark-icon-color:            $navbar-dark-color;

$navbar-dark-toggler-icon-bg:       url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 30 30'><path stroke='#{$navbar-dark-icon-color}' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/></svg>");

$navbar-dark-toggler-border-color:  rgba($white, .1);

$navbar-dark-brand-color:           $navbar-dark-active-color;

$navbar-dark-brand-hover-color:     $navbar-dark-active-color;

```



\--------------------------------



\### Create borderless tables



Source: https://getbootstrap.com/docs/5.3/content/tables



Use .table-borderless to remove all borders from the table.



```html

<table class="table table-borderless">

&#x20; ...

</table>

```



```html

<table class="table table-dark table-borderless">

&#x20; ...

</table>

```



\--------------------------------



\### Responsive Viewport Meta Tag



Source: https://getbootstrap.com/docs/5.3/getting-started/introduction



Essential for mobile-first rendering and touch zooming on all devices.



```html

<meta name="viewport" content="width=device-width, initial-scale=1">

```



\--------------------------------



\### Implement a fullscreen modal



Source: https://getbootstrap.com/docs/5.3/components/modal



Apply the .modal-fullscreen-sm-down class to the .modal-dialog element to create a modal that covers the viewport below the small breakpoint.



```html

<!-- Full screen modal -->

<div class="modal-dialog modal-fullscreen-sm-down">

&#x20; ...

</div>

```



\--------------------------------



\### Integrate input groups with button toolbars



Source: https://getbootstrap.com/docs/5.3/components/button-group



Combine input groups and button groups within a toolbar, using utility classes for spacing and alignment.



```html

<div class="btn-toolbar mb-3" role="toolbar" aria-label="Toolbar with button groups">

&#x20; <div class="btn-group me-2" role="group" aria-label="First group">

&#x20;   <button type="button" class="btn btn-outline-secondary">1</button>

&#x20;   <button type="button" class="btn btn-outline-secondary">2</button>

&#x20;   <button type="button" class="btn btn-outline-secondary">3</button>

&#x20;   <button type="button" class="btn btn-outline-secondary">4</button>

&#x20; </div>

&#x20; <div class="input-group">

&#x20;   <div class="input-group-text" id="btnGroupAddon">@</div>

&#x20;   <input type="text" class="form-control" placeholder="Input group example" aria-label="Input group example" aria-describedby="btnGroupAddon">

&#x20; </div>

</div>



<div class="btn-toolbar justify-content-between" role="toolbar" aria-label="Toolbar with button groups">

&#x20; <div class="btn-group" role="group" aria-label="First group">

&#x20;   <button type="button" class="btn btn-outline-secondary">1</button>

&#x20;   <button type="button" class="btn btn-outline-secondary">2</button>

&#x20;   <button type="button" class="btn btn-outline-secondary">3</button>

&#x20;   <button type="button" class="btn btn-outline-secondary">4</button>

&#x20; </div>

&#x20; <div class="input-group">

&#x20;   <div class="input-group-text" id="btnGroupAddon2">@</div>

&#x20;   <input type="text" class="form-control" placeholder="Input group example" aria-label="Input group example" aria-describedby="btnGroupAddon2">

&#x20; </div>

</div>

```



\--------------------------------



\### Link Hover Opacity Utilities



Source: https://getbootstrap.com/docs/5.3/utilities/link



Apply opacity changes specifically when the user hovers over the link.



```html

<p><a class="link-opacity-10-hover" href="#">Link hover opacity 10</a></p>

<p><a class="link-opacity-25-hover" href="#">Link hover opacity 25</a></p>

<p><a class="link-opacity-50-hover" href="#">Link hover opacity 50</a></p>

<p><a class="link-opacity-75-hover" href="#">Link hover opacity 75</a></p>

<p><a class="link-opacity-100-hover" href="#">Link hover opacity 100</a></p>

```



\--------------------------------



\### Link Opacity Utilities



Source: https://getbootstrap.com/docs/5.3/utilities/link



Adjust the alpha opacity of link colors. Ensure contrast remains sufficient when applying these classes.



```html

<p><a class="link-opacity-10" href="#">Link opacity 10</a></p>

<p><a class="link-opacity-25" href="#">Link opacity 25</a></p>

<p><a class="link-opacity-50" href="#">Link opacity 50</a></p>

<p><a class="link-opacity-75" href="#">Link opacity 75</a></p>

<p><a class="link-opacity-100" href="#">Link opacity 100</a></p>

```



\--------------------------------



\### Apply display heading classes



Source: https://getbootstrap.com/docs/5.3/content/typography



Use these classes on heading elements to create larger, more opinionated heading styles.



```html

<h1 class="display-1">Display 1</h1>

<h1 class="display-2">Display 2</h1>

<h1 class="display-3">Display 3</h1>

<h1 class="display-4">Display 4</h1>

<h1 class="display-5">Display 5</h1>

<h1 class="display-6">Display 6</h1>

```



\--------------------------------



\### Implement a dark dropdown menu



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



Applies the .dropdown-menu-dark class to a standard dropdown menu structure.



```html

<div class="dropdown">

&#x20; <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   Dropdown button

&#x20; </button>

&#x20; <ul class="dropdown-menu dropdown-menu-dark">

&#x20;   <li><a class="dropdown-item active" href="#">Action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;   <li><hr class="dropdown-divider"></li>

&#x20;   <li><a class="dropdown-item" href="#">Separated link</a></li>

&#x20; </ul>

</div>

```



\--------------------------------



\### Generate Responsive Navbar Expand Classes



Source: https://getbootstrap.com/docs/5.3/components/navbar



Sass loop that iterates over grid breakpoints to generate responsive navbar expansion classes.



```scss

// Generate series of `.navbar-expand-\*` responsive classes for configuring

// where your navbar collapses.

.navbar-expand {

&#x20; @each $breakpoint in map-keys($grid-breakpoints) {

&#x20;   $next: breakpoint-next($breakpoint, $grid-breakpoints);

&#x20;   $infix: breakpoint-infix($next, $grid-breakpoints);



&#x20;   // stylelint-disable-next-line scss/selector-no-union-class-name

&#x20;   \&#{$infix} {

&#x20;     @include media-breakpoint-up($next) {

&#x20;       flex-wrap: nowrap;

&#x20;       justify-content: flex-start;



&#x20;       .navbar-nav {

&#x20;         flex-direction: row;



&#x20;         .dropdown-menu {

&#x20;           position: absolute;

&#x20;         }



&#x20;         .nav-link {

&#x20;           padding-right: var(--#{$prefix}navbar-nav-link-padding-x);

&#x20;           padding-left: var(--#{$prefix}navbar-nav-link-padding-x);

&#x20;         }

&#x20;       }



&#x20;       .navbar-nav-scroll {

&#x20;         overflow: visible;

&#x20;       }



&#x20;       .navbar-collapse {

&#x20;         display: flex !important; // stylelint-disable-line declaration-no-important

&#x20;         flex-basis: auto;

&#x20;       }



&#x20;       .navbar-toggler {

&#x20;         display: none;

&#x20;       }



&#x20;       .offcanvas {

&#x20;         // stylelint-disable declaration-no-important

&#x20;         position: static;

&#x20;         z-index: auto;

&#x20;         flex-grow: 1;

&#x20;         width: auto !important;

&#x20;         height: auto !important;

&#x20;         visibility: visible !important;

&#x20;         background-color: transparent !important;

&#x20;         border: 0 !important;

&#x20;         transform: none !important;

&#x20;         @include box-shadow(none);

&#x20;         @include transition(none);

&#x20;         // stylelint-enable declaration-no-important



&#x20;         .offcanvas-header {

&#x20;           display: none;

&#x20;         }



&#x20;         .offcanvas-body {

&#x20;           display: flex;

&#x20;           flex-grow: 0;

&#x20;           padding: 0;

&#x20;           overflow-y: visible;

&#x20;         }

&#x20;       }

&#x20;     }

&#x20;   }

&#x20; }

}

```



\--------------------------------



\### Create a list group with checkboxes



Source: https://getbootstrap.com/docs/5.3/components/list-group



Integrates standard checkboxes into list group items using form-check-input classes.



```html

<ul class="list-group">

&#x20; <li class="list-group-item">

&#x20;   <input class="form-check-input me-1" type="checkbox" value="" id="firstCheckbox">

&#x20;   <label class="form-check-label" for="firstCheckbox">First checkbox</label>

&#x20; </li>

&#x20; <li class="list-group-item">

&#x20;   <input class="form-check-input me-1" type="checkbox" value="" id="secondCheckbox">

&#x20;   <label class="form-check-label" for="secondCheckbox">Second checkbox</label>

&#x20; </li>

&#x20; <li class="list-group-item">

&#x20;   <input class="form-check-input me-1" type="checkbox" value="" id="thirdCheckbox">

&#x20;   <label class="form-check-label" for="thirdCheckbox">Third checkbox</label>

&#x20; </li>

</ul>

```



\--------------------------------



\### Placeholder Sass variables



Source: https://getbootstrap.com/docs/5.3/components/placeholders



Lists the Sass variables used to configure placeholder opacity.



```scss

$placeholder-opacity-max:           .5;

$placeholder-opacity-min:           .2;

```



\--------------------------------



\### Button Methods



Source: https://getbootstrap.com/docs/5.3/components/buttons



Methods available on the button instance to control its state and lifecycle.



```APIDOC

\## Button Instance Methods



\### toggle()

\- \*\*Description\*\*: Toggles the push state of the button, giving it the appearance of being activated.



\### dispose()

\- \*\*Description\*\*: Destroys the button instance and removes stored data from the DOM element.



\### static getInstance(element)

\- \*\*Description\*\*: Static method to retrieve the existing button instance associated with a DOM element.



\### static getOrCreateInstance(element)

\- \*\*Description\*\*: Static method to retrieve an existing button instance or create a new one if it has not been initialized.

```



\--------------------------------



\### Include Bootstrap via jsDelivr CDN



Source: https://getbootstrap.com/docs/5.3/getting-started/download



Use these tags to load the compiled Bootstrap CSS and JS bundles directly from the jsDelivr CDN.



```html

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB" crossorigin="anonymous">

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js" integrity="sha384-FKyoEForCGlyvwx9Hj09JcYn3nv7wiPVlz7YYwJrWVcXK/BmnVDxM+D2scQbITxI" crossorigin="anonymous"></script>

```



\--------------------------------



\### Implement bottom-positioned offcanvas



Source: https://getbootstrap.com/docs/5.3/components/offcanvas



Uses the .offcanvas-bottom class to anchor the component to the bottom of the viewport.



```html

<button class="btn btn-primary" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasBottom" aria-controls="offcanvasBottom">Toggle bottom offcanvas</button>



<div class="offcanvas offcanvas-bottom" tabindex="-1" id="offcanvasBottom" aria-labelledby="offcanvasBottomLabel">

&#x20; <div class="offcanvas-header">

&#x20;   <h5 class="offcanvas-title" id="offcanvasBottomLabel">Offcanvas bottom</h5>

&#x20;   <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>

&#x20; </div>

&#x20; <div class="offcanvas-body small">

&#x20;   ...

&#x20; </div>

</div>

```



\--------------------------------



\### Implement horizontal collapse



Source: https://getbootstrap.com/docs/5.3/components/collapse



Use the .collapse-horizontal class to transition width instead of height. Ensure the immediate child element has a defined width.



```html

<p>

&#x20; <button class="btn btn-primary" type="button" data-bs-toggle="collapse" data-bs-target="#collapseWidthExample" aria-expanded="false" aria-controls="collapseWidthExample">

&#x20;   Toggle width collapse

&#x20; </button>

</p>

<div style="min-height: 120px;">

&#x20; <div class="collapse collapse-horizontal" id="collapseWidthExample">

&#x20;   <div class="card card-body" style="width: 300px;">

&#x20;     This is some placeholder content for a horizontal collapse. It’s hidden by default and shown when triggered.

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Actionable List Group Items



Source: https://getbootstrap.com/docs/5.3/components/list-group



Create interactive list groups using anchor tags or buttons with the .list-group-item-action class.



```html

<div class="list-group">

&#x20; <a href="#" class="list-group-item list-group-item-action active" aria-current="true">

&#x20;   The current link item

&#x20; </a>

&#x20; <a href="#" class="list-group-item list-group-item-action">A second link item</a>

&#x20; <a href="#" class="list-group-item list-group-item-action">A third link item</a>

&#x20; <a href="#" class="list-group-item list-group-item-action">A fourth link item</a>

&#x20; <a href="#" class="list-group-item list-group-item-action disabled" aria-disabled="true">A disabled link item</a>

</div>

```



```html

<div class="list-group">

&#x20; <button type="button" class="list-group-item list-group-item-action active" aria-current="true">

&#x20;   The current button

&#x20; </button>

&#x20; <button type="button" class="list-group-item list-group-item-action">A second button item</button>

&#x20; <button type="button" class="list-group-item list-group-item-action">A third button item</button>

&#x20; <button type="button" class="list-group-item list-group-item-action">A fourth button item</button>

&#x20; <button type="button" class="list-group-item list-group-item-action" disabled>A disabled button item</button>

</div>

```



\--------------------------------



\### Collapse Methods



Source: https://getbootstrap.com/docs/5.3/components/collapse



Methods available on the Collapse instance to control visibility and lifecycle.



```APIDOC

\## Collapse Methods



\### show()

Shows the collapsible element.



\### hide()

Hides the collapsible element.



\### toggle()

Toggles the collapsible element between shown and hidden.



\### dispose()

Destroys the collapse instance and removes stored data from the DOM element.



\### getInstance(element)

Static method to retrieve the collapse instance associated with a DOM element.



\### getOrCreateInstance(element)

Static method to retrieve an existing collapse instance or create a new one if it does not exist.

```



\--------------------------------



\### Horizontal Rule Styling



Source: https://getbootstrap.com/docs/5.3/content/reboot



Demonstrates default horizontal rule styling and the use of border and opacity utilities to customize appearance.



```html

<hr>



<div class="text-success">

&#x20; <hr>

</div>



<hr class="border border-danger border-2 opacity-50">

<hr class="border border-primary border-3 opacity-75">

```



\--------------------------------



\### Listen for dropdown show event



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



Attaches an event listener to a dropdown element to execute logic when the show event is triggered.



```javascript

const myDropdown = document.getElementById('myDropdown')

myDropdown.addEventListener('show.bs.dropdown', event => {

&#x20; // do something...

})

```



\--------------------------------



\### Create a vertical button group



Source: https://getbootstrap.com/docs/5.3/components/button-group



Use the .btn-group-vertical class to stack buttons vertically.



```html

<div class="btn-group-vertical" role="group" aria-label="Vertical button group">

&#x20; <button type="button" class="btn btn-primary">Button</button>

&#x20; <button type="button" class="btn btn-primary">Button</button>

&#x20; <button type="button" class="btn btn-primary">Button</button>

&#x20; <button type="button" class="btn btn-primary">Button</button>

</div>

```



\--------------------------------



\### Modify links with utilities



Source: https://getbootstrap.com/docs/5.3/helpers/colored-links



Combine link color classes with link utilities to control underline offset and opacity.



```html

<p><a href="#" class="link-primary link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Primary link</a></p>

<p><a href="#" class="link-secondary link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Secondary link</a></p>

<p><a href="#" class="link-success link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Success link</a></p>

<p><a href="#" class="link-danger link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Danger link</a></p>

<p><a href="#" class="link-warning link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Warning link</a></p>

<p><a href="#" class="link-info link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Info link</a></p>

<p><a href="#" class="link-light link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Light link</a></p>

<p><a href="#" class="link-dark link-offset-2 link-underline-opacity-25 link-underline-opacity-100-hover">Dark link</a></p>

<p><a href="#" class="link-body-emphasis link-offset-2 link-underline-opacity-25 link-underline-opacity-75-hover">Emphasis link</a></p>

```



\--------------------------------



\### Applying Object Fit to Video Elements



Source: https://getbootstrap.com/docs/5.3/utilities/object-fit



Object-fit utilities are compatible with video elements to manage how video content fits its container.



```html

<video src="..." class="object-fit-contain" autoplay></video>

<video src="..." class="object-fit-cover" autoplay></video>

<video src="..." class="object-fit-fill" autoplay></video>

<video src="..." class="object-fit-scale" autoplay></video>

<video src="..." class="object-fit-none" autoplay></video>

```



\--------------------------------



\### new bootstrap.ScrollSpy(element, options)



Source: https://getbootstrap.com/docs/5.3/components/scrollspy



Initializes a new ScrollSpy instance on a target element with optional configuration.



```APIDOC

\## new bootstrap.ScrollSpy(element, options)



\### Description

Initializes a new ScrollSpy instance on the specified DOM element.



\### Parameters

\- \*\*element\*\* (DOM element) - Required - The element to apply Scrollspy to.

\- \*\*options\*\* (object) - Optional - Configuration object containing properties like `rootMargin`, `smoothScroll`, `target`, and `threshold`.

```



\--------------------------------



\### Dropdown Configuration Options



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



Configuration options for the Dropdown component, which can be passed via data attributes or JavaScript objects.



```APIDOC

\## Dropdown Options



\### Description

Configure the behavior of the dropdown component using data attributes (e.g., `data-bs-auto-close`) or a JavaScript configuration object.



\### Options

\- \*\*autoClose\*\* (boolean, string) - Default: `true` - Configure the auto close behavior (true, false, 'inside', 'outside').

\- \*\*boundary\*\* (string, element) - Default: `'clippingParents'` - Overflow constraint boundary of the dropdown menu.

\- \*\*display\*\* (string) - Default: `'dynamic'` - Positioning mode, use 'static' to disable Popper.

\- \*\*offset\*\* (array, string, function) - Default: `\[0, 2]` - Offset of the dropdown relative to its target.

\- \*\*popperConfig\*\* (null, object, function) - Default: `null` - Custom Popper configuration.

\- \*\*reference\*\* (string, element, object) - Default: `'toggle'` - Reference element for the dropdown menu.

```



\--------------------------------



\### Create styled tables



Source: https://getbootstrap.com/docs/5.3/content/reboot



Use the <table> element with <caption>, <thead>, and <tbody> for structured data presentation.



```html

<table>

&#x20; <caption>

&#x20;   This is an example table, and this is its caption to describe the contents.

&#x20; </caption>

&#x20; <thead>

&#x20;   <tr>

&#x20;     <th>Table heading</th>

&#x20;     <th>Table heading</th>

&#x20;     <th>Table heading</th>

&#x20;     <th>Table heading</th>

&#x20;   </tr>

&#x20; </thead>

&#x20; <tbody>

&#x20;   <tr>

&#x20;     <td>Table cell</td>

&#x20;     <td>Table cell</td>

&#x20;     <td>Table cell</td>

&#x20;     <td>Table cell</td>

&#x20;   </tr>

&#x20;   <tr>

&#x20;     <td>Table cell</td>

&#x20;     <td>Table cell</td>

&#x20;     <td>Table cell</td>

&#x20;     <td>Table cell</td>

&#x20;   </tr>

&#x20;   <tr>

&#x20;     <td>Table cell</td>

&#x20;     <td>Table cell</td>

&#x20;     <td>Table cell</td>

&#x20;     <td>Table cell</td>

&#x20;   </tr>

&#x20; </tbody>

</table>

```



\--------------------------------



\### Add Popovers and Tooltips to Modals



Source: https://getbootstrap.com/docs/5.3/components/modal



Integrate popovers and tooltips within a modal body using data attributes.



```html

<div class="modal-body">

&#x20; <h2 class="fs-5">Popover in a modal</h2>

&#x20; <p>This <button class="btn btn-secondary" data-bs-toggle="popover" title="Popover title" data-bs-content="Popover body content is set in this attribute.">button</button> triggers a popover on click.</p>

&#x20; <hr>

&#x20; <h2 class="fs-5">Tooltips in a modal</h2>

&#x20; <p><a href="#" data-bs-toggle="tooltip" title="Tooltip">This link</a> and <a href="#" data-bs-toggle="tooltip" title="Tooltip">that link</a> have tooltips on hover.</p>

</div>

```



\--------------------------------



\### Configure Input Sass Variables



Source: https://getbootstrap.com/docs/5.3/forms/form-control



Variables defining padding, font, border, and focus states for form inputs.



```scss

$input-padding-y:                       $input-btn-padding-y;

$input-padding-x:                       $input-btn-padding-x;

$input-font-family:                     $input-btn-font-family;

$input-font-size:                       $input-btn-font-size;

$input-font-weight:                     $font-weight-base;

$input-line-height:                     $input-btn-line-height;



$input-padding-y-sm:                    $input-btn-padding-y-sm;

$input-padding-x-sm:                    $input-btn-padding-x-sm;

$input-font-size-sm:                    $input-btn-font-size-sm;



$input-padding-y-lg:                    $input-btn-padding-y-lg;

$input-padding-x-lg:                    $input-btn-padding-x-lg;

$input-font-size-lg:                    $input-btn-font-size-lg;



$input-bg:                              var(--#{$prefix}body-bg);

$input-disabled-color:                  null;

$input-disabled-bg:                     var(--#{$prefix}secondary-bg);

$input-disabled-border-color:           null;



$input-color:                           var(--#{$prefix}body-color);

$input-border-color:                    var(--#{$prefix}border-color);

$input-border-width:                    $input-btn-border-width;

$input-box-shadow:                      var(--#{$prefix}box-shadow-inset);



$input-border-radius:                   var(--#{$prefix}border-radius);

$input-border-radius-sm:                var(--#{$prefix}border-radius-sm);

$input-border-radius-lg:                var(--#{$prefix}border-radius-lg);



$input-focus-bg:                        $input-bg;

$input-focus-border-color:              tint-color($component-active-bg, 50%);

$input-focus-color:                     $input-color;

$input-focus-width:                     $input-btn-focus-width;

$input-focus-box-shadow:                $input-btn-focus-box-shadow;



$input-placeholder-color:               var(--#{$prefix}secondary-color);

$input-plaintext-color:                 var(--#{$prefix}body-color);



$input-height-border:                   calc(#{$input-border-width} \* 2); // stylelint-disable-line function-disallowed-list



$input-height-inner:                    add($input-line-height \* 1em, $input-padding-y \* 2);

$input-height-inner-half:               add($input-line-height \* .5em, $input-padding-y);

$input-height-inner-quarter:            add($input-line-height \* .25em, $input-padding-y \* .5);



$input-height:                          add($input-line-height \* 1em, add($input-padding-y \* 2, $input-height-border, false));

$input-height-sm:                       add($input-line-height \* 1em, add($input-padding-y-sm \* 2, $input-height-border, false));

$input-height-lg:                       add($input-line-height \* 1em, add($input-padding-y-lg \* 2, $input-height-border, false));



$input-transition:                      border-color .15s ease-in-out, box-shadow .15s ease-in-out;



$form-color-width:                      3rem;

```



\--------------------------------



\### Apply gap utilities to a grid container



Source: https://getbootstrap.com/docs/5.3/utilities/spacing



Uses the d-grid and gap-3 classes to manage spacing between grid items.



```html

<div style="grid-template-columns: 1fr 1fr;" class="d-grid gap-3">

&#x20; <div class="p-2">Grid item 1</div>

&#x20; <div class="p-2">Grid item 2</div>

&#x20; <div class="p-2">Grid item 3</div>

&#x20; <div class="p-2">Grid item 4</div>

</div>

```



\--------------------------------



\### Popover Methods



Source: https://getbootstrap.com/docs/5.3/components/popovers



Methods available on the Popover instance to control visibility, state, and content.



```APIDOC

\## Popover Methods



\### disable()

Removes the ability for an element’s popover to be shown.



\### dispose()

Hides and destroys an element’s popover.



\### enable()

Gives an element’s popover the ability to be shown.



\### getInstance(element)

Static method to get the popover instance associated with a DOM element.



\### getOrCreateInstance(element)

Static method to get the popover instance associated with a DOM element, or create a new one.



\### hide()

Hides an element’s popover.



\### setContent(object)

Updates the popover content. Accepts an object where keys are selectors and values are string, element, function, or null.



\### show()

Reveals an element’s popover.



\### toggle()

Toggles an element’s popover visibility.



\### toggleEnabled()

Toggles the ability for an element’s popover to be shown or hidden.



\### update()

Updates the position of an element’s popover.

```



\--------------------------------



\### Apply CSS Variables in Reboot



Source: https://getbootstrap.com/docs/5.3/content/reboot



Demonstrates how the defined CSS variables are applied to the body element within the Reboot stylesheet.



```scss

body {

&#x20; margin: 0; // 1

&#x20; font-family: var(--#{$prefix}body-font-family);

&#x20; @include font-size(var(--#{$prefix}body-font-size));

&#x20; font-weight: var(--#{$prefix}body-font-weight);

&#x20; line-height: var(--#{$prefix}body-line-height);

&#x20; color: var(--#{$prefix}body-color);

&#x20; text-align: var(--#{$prefix}body-text-align);

&#x20; background-color: var(--#{$prefix}body-bg); // 2

&#x20; -webkit-text-size-adjust: 100%; // 3

&#x20; -webkit-tap-highlight-color: rgba($black, 0); // 4

}

```



\--------------------------------



\### Import Popper dependency



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



Bootstrap's internal dependency on Popper requires resolution when using ESM.



```javascript

import \* as Popper from "@popperjs/core"

```



\--------------------------------



\### Configure miscellaneous typography variables



Source: https://getbootstrap.com/docs/5.3/content/typography



Variables for styling elements like lead text, small text, blockquotes, horizontal rules, and lists.



```scss

$lead-font-size:              $font-size-base \* 1.25;

$lead-font-weight:            300;



$small-font-size:             .875em;



$sub-sup-font-size:           .75em;



// fusv-disable

$text-muted:                  var(--#{$prefix}secondary-color); // Deprecated in 5.3.0

// fusv-enable



$initialism-font-size:        $small-font-size;



$blockquote-margin-y:         $spacer;

$blockquote-font-size:        $font-size-base \* 1.25;

$blockquote-footer-color:     $gray-600;

$blockquote-footer-font-size: $small-font-size;



$hr-margin-y:                 $spacer;

$hr-color:                    inherit;



// fusv-disable

$hr-bg-color:                 null; // Deprecated in v5.2.0

$hr-height:                   null; // Deprecated in v5.2.0

// fusv-enable



$hr-border-color:             null; // Allows for inherited colors

$hr-border-width:             var(--#{$prefix}border-width);

$hr-opacity:                  .25;



// scss-docs-start vr-variables

$vr-border-width:             var(--#{$prefix}border-width);

// scss-docs-end vr-variables



$legend-margin-bottom:        .5rem;

$legend-font-size:            1.5rem;

$legend-font-weight:          null;



$dt-font-weight:              $font-weight-bold;



$list-inline-padding:         .5rem;



$mark-padding:                .1875em;

$mark-color:                  $body-color;

$mark-bg:                     $yellow-100;

```



\--------------------------------



\### Apply small button sizes



Source: https://getbootstrap.com/docs/5.3/components/buttons



Use the .btn-sm class to decrease the size of button elements.



```html

<button type="button" class="btn btn-primary btn-sm">Small button</button>

<button type="button" class="btn btn-secondary btn-sm">Small button</button>

```



\--------------------------------



\### Focus Ring Utility Classes



Source: https://getbootstrap.com/docs/5.3/helpers/focus-ring



Use theme-specific utility classes to quickly change the color of the focus ring.



```html

<p><a href="#" class="d-inline-flex focus-ring focus-ring-primary py-1 px-2 text-decoration-none border rounded-2">Primary focus</a></p>

<p><a href="#" class="d-inline-flex focus-ring focus-ring-secondary py-1 px-2 text-decoration-none border rounded-2">Secondary focus</a></p>

<p><a href="#" class="d-inline-flex focus-ring focus-ring-success py-1 px-2 text-decoration-none border rounded-2">Success focus</a></p>

<p><a href="#" class="d-inline-flex focus-ring focus-ring-danger py-1 px-2 text-decoration-none border rounded-2">Danger focus</a></p>

<p><a href="#" class="d-inline-flex focus-ring focus-ring-warning py-1 px-2 text-decoration-none border rounded-2">Warning focus</a></p>

<p><a href="#" class="d-inline-flex focus-ring focus-ring-info py-1 px-2 text-decoration-none border rounded-2">Info focus</a></p>

<p><a href="#" class="d-inline-flex focus-ring focus-ring-light py-1 px-2 text-decoration-none border rounded-2">Light focus</a></p>

<p><a href="#" class="d-inline-flex focus-ring focus-ring-dark py-1 px-2 text-decoration-none border rounded-2">Dark focus</a></p>

```



\--------------------------------



\### Create a centered card with footer



Source: https://getbootstrap.com/docs/5.3/components/card



Use the text-center class on the card and add a card-footer section at the bottom.



```html

<div class="card text-center">

&#x20; <div class="card-header">

&#x20;   Featured

&#x20; </div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Special title treatment</h5>

&#x20;   <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>

&#x20;   <a href="#" class="btn btn-primary">Go somewhere</a>

&#x20; </div>

&#x20; <div class="card-footer text-body-secondary">

&#x20;   2 days ago

&#x20; </div>

</div>

```



\--------------------------------



\### Customizing Toast Content



Source: https://getbootstrap.com/docs/5.3/components/toasts



Create simplified or feature-rich toasts by removing headers or adding custom action buttons.



```html

<div class="toast align-items-center" role="alert" aria-live="assertive" aria-atomic="true">

&#x20; <div class="d-flex">

&#x20;   <div class="toast-body">

&#x20;     Hello, world! This is a toast message.

&#x20;   </div>

&#x20;   <button type="button" class="btn-close me-2 m-auto" data-bs-dismiss="toast" aria-label="Close"></button>

&#x20; </div>

</div>

```



```html

<div class="toast" role="alert" aria-live="assertive" aria-atomic="true">

&#x20; <div class="toast-body">

&#x20;   Hello, world! This is a toast message.

&#x20;   <div class="mt-2 pt-2 border-top">

&#x20;     <button type="button" class="btn btn-primary btn-sm">Take action</button>

&#x20;     <button type="button" class="btn btn-secondary btn-sm" data-bs-dismiss="toast">Close</button>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Build complex form layouts



Source: https://getbootstrap.com/docs/5.3/forms/layout



Combines grid classes and gutter modifiers to create sophisticated form structures.



```html

<form class="row g-3">

&#x20; <div class="col-md-6">

&#x20;   <label for="inputEmail4" class="form-label">Email</label>

&#x20;   <input type="email" class="form-control" id="inputEmail4">

&#x20; </div>

&#x20; <div class="col-md-6">

&#x20;   <label for="inputPassword4" class="form-label">Password</label>

&#x20;   <input type="password" class="form-control" id="inputPassword4">

&#x20; </div>

&#x20; <div class="col-12">

&#x20;   <label for="inputAddress" class="form-label">Address</label>

&#x20;   <input type="text" class="form-control" id="inputAddress" placeholder="1234 Main St">

&#x20; </div>

&#x20; <div class="col-12">

&#x20;   <label for="inputAddress2" class="form-label">Address 2</label>

&#x20;   <input type="text" class="form-control" id="inputAddress2" placeholder="Apartment, studio, or floor">

&#x20; </div>

&#x20; <div class="col-md-6">

&#x20;   <label for="inputCity" class="form-label">City</label>

&#x20;   <input type="text" class="form-control" id="inputCity">

&#x20; </div>

&#x20; <div class="col-md-4">

&#x20;   <label for="inputState" class="form-label">State</label>

&#x20;   <select id="inputState" class="form-select">

&#x20;     <option selected>Choose...</option>

&#x20;     <option>...</option>

&#x20;   </select>

&#x20; </div>

&#x20; <div class="col-md-2">

&#x20;   <label for="inputZip" class="form-label">Zip</label>

&#x20;   <input type="text" class="form-control" id="inputZip">

&#x20; </div>

&#x20; <div class="col-12">

&#x20;   <div class="form-check">

&#x20;     <input class="form-check-input" type="checkbox" id="gridCheck">

&#x20;     <label class="form-check-label" for="gridCheck">

&#x20;       Check me out

&#x20;     </label>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col-12">

&#x20;   <button type="submit" class="btn btn-primary">Sign in</button>

&#x20; </div>

</form>

```



\--------------------------------



\### Button element variations



Source: https://getbootstrap.com/docs/5.3/components/buttons



Demonstrates applying button classes to various HTML elements including anchors, buttons, and inputs.



```html

<a class="btn btn-primary" href="#" role="button">Link</a>

<button class="btn btn-primary" type="submit">Button</button>

<input class="btn btn-primary" type="button" value="Input">

<input class="btn btn-primary" type="submit" value="Submit">

<input class="btn btn-primary" type="reset" value="Reset">

```



\--------------------------------



\### Set tooltip direction



Source: https://getbootstrap.com/docs/5.3/components/tooltips



Use data-bs-placement to position tooltips on top, right, bottom, or left.



```html

<button type="button" class="btn btn-secondary" data-bs-toggle="tooltip" data-bs-placement="top" data-bs-title="Tooltip on top">

&#x20; Tooltip on top

</button>

<button type="button" class="btn btn-secondary" data-bs-toggle="tooltip" data-bs-placement="right" data-bs-title="Tooltip on right">

&#x20; Tooltip on right

</button>

<button type="button" class="btn btn-secondary" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Tooltip on bottom">

&#x20; Tooltip on bottom

</button>

<button type="button" class="btn btn-secondary" data-bs-toggle="tooltip" data-bs-placement="left" data-bs-title="Tooltip on left">

&#x20; Tooltip on left

</button>

```



\--------------------------------



\### Format multi-line code blocks



Source: https://getbootstrap.com/docs/5.3/content/reboot



Use <pre> and <code> tags for multi-line code. Escape angle brackets for proper rendering.



```html

<pre><code>\&lt;p\&gt;Sample text here...\&lt;/p\&gt;

\&lt;p\&gt;And another line of sample text here...\&lt;/p\&gt;

</code></pre>

```



\--------------------------------



\### Responsive Table Wrapper



Source: https://getbootstrap.com/docs/5.3/content/tables



Use the table-responsive class to enable horizontal scrolling for tables on smaller viewports.



```html

<div class="table-responsive">

&#x20; <table class="table">

&#x20;   ...

&#x20; </table>

</div>

```



\--------------------------------



\### Create contextual alert variants



Source: https://getbootstrap.com/docs/5.3/components/alerts



Use these HTML structures to display alerts with different color themes. Ensure each alert includes the appropriate contextual class and the alert role.



```html

<div class="alert alert-primary" role="alert">

&#x20; A simple primary alert—check it out!

</div>

<div class="alert alert-secondary" role="alert">

&#x20; A simple secondary alert—check it out!

</div>

<div class="alert alert-success" role="alert">

&#x20; A simple success alert—check it out!

</div>

<div class="alert alert-danger" role="alert">

&#x20; A simple danger alert—check it out!

</div>

<div class="alert alert-warning" role="alert">

&#x20; A simple warning alert—check it out!

</div>

<div class="alert alert-info" role="alert">

&#x20; A simple info alert—check it out!

</div>

<div class="alert alert-light" role="alert">

&#x20; A simple light alert—check it out!

</div>

<div class="alert alert-dark" role="alert">

&#x20; A simple dark alert—check it out!

</div>

```



\--------------------------------



\### Create custom gradient mixins



Source: https://getbootstrap.com/docs/5.3/utilities/background



A collection of mixins for generating horizontal, vertical, directional, radial, and striped gradients.



```scss

// Horizontal gradient, from left to right

//

// Creates two color stops, start and end, by specifying a color and position for each color stop.

@mixin gradient-x($start-color: $gray-700, $end-color: $gray-800, $start-percent: 0%, $end-percent: 100%) {

&#x20; background-image: linear-gradient(to right, $start-color $start-percent, $end-color $end-percent);

}



// Vertical gradient, from top to bottom

//

// Creates two color stops, start and end, by specifying a color and position for each color stop.

@mixin gradient-y($start-color: $gray-700, $end-color: $gray-800, $start-percent: null, $end-percent: null) {

&#x20; background-image: linear-gradient(to bottom, $start-color $start-percent, $end-color $end-percent);

}



@mixin gradient-directional($start-color: $gray-700, $end-color: $gray-800, $deg: 45deg) {

&#x20; background-image: linear-gradient($deg, $start-color, $end-color);

}



@mixin gradient-x-three-colors($start-color: $blue, $mid-color: $purple, $color-stop: 50%, $end-color: $red) {

&#x20; background-image: linear-gradient(to right, $start-color, $mid-color $color-stop, $end-color);

}



@mixin gradient-y-three-colors($start-color: $blue, $mid-color: $purple, $color-stop: 50%, $end-color: $red) {

&#x20; background-image: linear-gradient($start-color, $mid-color $color-stop, $end-color);

}



@mixin gradient-radial($inner-color: $gray-700, $outer-color: $gray-800) {

&#x20; background-image: radial-gradient(circle, $inner-color, $outer-color);

}



@mixin gradient-striped($color: rgba($white, .15), $angle: 45deg) {

&#x20; background-image: linear-gradient($angle, $color 25%, transparent 25%, transparent 50%, $color 50%, $color 75%, transparent 75%, transparent);

}

```



\--------------------------------



\### Configure File Input Sass Variables



Source: https://getbootstrap.com/docs/5.3/forms/form-control



Variables for customizing the button appearance within file inputs.



```scss

$form-file-button-color:          $input-color;

$form-file-button-bg:             var(--#{$prefix}tertiary-bg);

$form-file-button-hover-bg:       var(--#{$prefix}secondary-bg);

```



\--------------------------------



\### Apply striped variants to success tables



Source: https://getbootstrap.com/docs/5.3/content/tables



Combine the .table-success class with striping utilities for success-themed tables.



```html

<table class="table table-success table-striped">

&#x20; ...

</table>

```



```html

<table class="table table-success table-striped-columns">

&#x20; ...

</table>

```



\--------------------------------



\### Shadow Utilities API Configuration



Source: https://getbootstrap.com/docs/5.3/utilities/shadows



The configuration map used in the utilities API to generate shadow classes.



```scss

"shadow": (

&#x20; property: box-shadow,

&#x20; class: shadow,

&#x20; values: (

&#x20;   null: var(--#{$prefix}box-shadow),

&#x20;   sm: var(--#{$prefix}box-shadow-sm),

&#x20;   lg: var(--#{$prefix}box-shadow-lg),

&#x20;   none: none,

&#x20; )

),

```



\--------------------------------



\### Configure heading typography variables



Source: https://getbootstrap.com/docs/5.3/content/typography



Variables for controlling the margin, font family, style, weight, line height, and color of headings.



```scss

$headings-margin-bottom:      $spacer \* .5;

$headings-font-family:        null;

$headings-font-style:         null;

$headings-font-weight:        500;

$headings-line-height:        1.2;

$headings-color:              inherit;

```



\--------------------------------



\### Create an inline form with Bootstrap grid



Source: https://getbootstrap.com/docs/5.3/forms/layout



Uses .row-cols-lg-auto and gutter classes to create a responsive horizontal form layout that aligns elements vertically.



```html

<form class="row row-cols-lg-auto g-3 align-items-center">

&#x20; <div class="col-12">

&#x20;   <label class="visually-hidden" for="inlineFormInputGroupUsername">Username</label>

&#x20;   <div class="input-group">

&#x20;     <div class="input-group-text">@</div>

&#x20;     <input type="text" class="form-control" id="inlineFormInputGroupUsername" placeholder="Username">

&#x20;   </div>

&#x20; </div>



&#x20; <div class="col-12">

&#x20;   <label class="visually-hidden" for="inlineFormSelectPref">Preference</label>

&#x20;   <select class="form-select" id="inlineFormSelectPref">

&#x20;     <option selected>Choose...</option>

&#x20;     <option value="1">One</option>

&#x20;     <option value="2">Two</option>

&#x20;     <option value="3">Three</option>

&#x20;   </select>

&#x20; </div>



&#x20; <div class="col-12">

&#x20;   <div class="form-check">

&#x20;     <input class="form-check-input" type="checkbox" id="inlineFormCheck">

&#x20;     <label class="form-check-label" for="inlineFormCheck">

&#x20;       Remember me

&#x20;     </label>

&#x20;   </div>

&#x20; </div>



&#x20; <div class="col-12">

&#x20;   <button type="submit" class="btn btn-primary">Submit</button>

&#x20; </div>

</form>

```



\--------------------------------



\### Create background gradient mixin



Source: https://getbootstrap.com/docs/5.3/utilities/background



Applies a background color and optionally adds a gradient image based on the $enable-gradients variable.



```scss

@mixin gradient-bg($color: null) {

&#x20; background-color: $color;



&#x20; @if $enable-gradients {

&#x20;   background-image: var(--#{$prefix}gradient);

&#x20; }

}

```



\--------------------------------



\### Default and Checked Checkboxes



Source: https://getbootstrap.com/docs/5.3/forms/checks



Basic implementation of standard and pre-checked checkboxes using the form-check class.



```html

<div class="form-check">

&#x20; <input class="form-check-input" type="checkbox" value="" id="checkDefault">

&#x20; <label class="form-check-label" for="checkDefault">

&#x20;   Default checkbox

&#x20; </label>

</div>

<div class="form-check">

&#x20; <input class="form-check-input" type="checkbox" value="" id="checkChecked" checked>

&#x20; <label class="form-check-label" for="checkChecked">

&#x20;   Checked checkbox

&#x20; </label>

</div>

```



\--------------------------------



\### Apply Justify Content Utilities



Source: https://getbootstrap.com/docs/5.3/utilities/flex



Use these classes on flexbox containers to align items along the main axis. The container must have the d-flex class applied.



```html

<div class="d-flex justify-content-start">...</div>

<div class="d-flex justify-content-end">...</div>

<div class="d-flex justify-content-center">...</div>

<div class="d-flex justify-content-between">...</div>

<div class="d-flex justify-content-around">...</div>

<div class="d-flex justify-content-evenly">...</div>

```



\--------------------------------



\### Set progress bar width



Source: https://getbootstrap.com/docs/5.3/components/progress



Use width utility classes like .w-75 to quickly configure the width of the progress bar.



```html

<div class="progress" role="progressbar" aria-label="Basic example" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100">

&#x20; <div class="progress-bar w-75"></div>

</div>

```



\--------------------------------



\### Control Flex Items with Auto Margins



Source: https://getbootstrap.com/docs/5.3/utilities/flex



Use margin utilities like .me-auto and .ms-auto to push flex items within a container.



```html

<div class="d-flex mb-3">

&#x20; <div class="p-2">Flex item</div>

&#x20; <div class="p-2">Flex item</div>

&#x20; <div class="p-2">Flex item</div>

</div>



<div class="d-flex mb-3">

&#x20; <div class="me-auto p-2">Flex item</div>

&#x20; <div class="p-2">Flex item</div>

&#x20; <div class="p-2">Flex item</div>

</div>



<div class="d-flex mb-3">

&#x20; <div class="p-2">Flex item</div>

&#x20; <div class="p-2">Flex item</div>

&#x20; <div class="ms-auto p-2">Flex item</div>

</div>

```



\--------------------------------



\### Configure progress bar CSS variables



Source: https://getbootstrap.com/docs/5.3/components/progress



Local CSS variables defined in \_progress.scss for real-time customization of progress bar appearance.



```scss

\--#{$prefix}progress-height: #{$progress-height};

@include rfs($progress-font-size, --#{$prefix}progress-font-size);

\--#{$prefix}progress-bg: #{$progress-bg};

\--#{$prefix}progress-border-radius: #{$progress-border-radius};

\--#{$prefix}progress-box-shadow: #{$progress-box-shadow};

\--#{$prefix}progress-bar-color: #{$progress-bar-color};

\--#{$prefix}progress-bar-bg: #{$progress-bar-bg};

\--#{$prefix}progress-bar-transition: #{$progress-bar-transition};

```



\--------------------------------



\### Create an alert with an icon



Source: https://getbootstrap.com/docs/5.3/components/alerts



Uses flexbox utilities and an inline SVG to display an icon within an alert component.



```html

<div class="alert alert-primary d-flex align-items-center" role="alert">

&#x20; <svg xmlns="http://www.w3.org/2000/svg" class="bi flex-shrink-0 me-2" viewBox="0 0 16 16" role="img" aria-label="Warning:">

&#x20;   <path d="M8.982 1.566a1.13 1.13 0 0 0-1.96 0L.165 13.233c-.457.778.091 1.767.98 1.767h13.713c.889 0 1.438-.99.98-1.767L8.982 1.566zM8 5c.535 0 .954.462.9.995l-.35 3.507a.552.552 0 0 1-1.1 0L7.1 5.995A.905.905 0 0 1 8 5zm.002 6a1 1 0 1 1 0 2 1 1 0 0 1 0-2z"/>

&#x20; </svg>

&#x20; <div>

&#x20;   An example alert with an icon

&#x20; </div>

</div>

```



\--------------------------------



\### Configure sizing utilities in Sass



Source: https://getbootstrap.com/docs/5.3/utilities/sizing



The sizing utilities are defined in the Bootstrap utilities API within \_utilities.scss.



```scss

"width": (

&#x20; property: width,

&#x20; class: w,

&#x20; values: (

&#x20;   25: 25%,

&#x20;   50: 50%,

&#x20;   75: 75%,

&#x20;   100: 100%,

&#x20;   auto: auto

&#x20; )

),

"max-width": (

&#x20; property: max-width,

&#x20; class: mw,

&#x20; values: (100: 100%)

),

"viewport-width": (

&#x20; property: width,

&#x20; class: vw,

&#x20; values: (100: 100vw)

),

"min-viewport-width": (

&#x20; property: min-width,

&#x20; class: min-vw,

&#x20; values: (100: 100vw)

),

"height": (

&#x20; property: height,

&#x20; class: h,

&#x20; values: (

&#x20;   25: 25%,

&#x20;   50: 50%,

&#x20;   75: 75%,

&#x20;   100: 100%,

&#x20;   auto: auto

&#x20; )

),

"max-height": (

&#x20; property: max-height,

&#x20; class: mh,

&#x20; values: (100: 100%)

),

"viewport-height": (

&#x20; property: height,

&#x20; class: vh,

&#x20; values: (100: 100vh)

),

"min-viewport-height": (

&#x20; property: min-height,

&#x20; class: min-vh,

&#x20; values: (100: 100vh)

),

```



\--------------------------------



\### Apply background color badges



Source: https://getbootstrap.com/docs/5.3/components/badge



Use .text-bg-{color} helper classes to set a background color with a contrasting foreground color.



```html

<span class="badge text-bg-primary">Primary</span>

<span class="badge text-bg-secondary">Secondary</span>

<span class="badge text-bg-success">Success</span>

<span class="badge text-bg-danger">Danger</span>

<span class="badge text-bg-warning">Warning</span>

<span class="badge text-bg-info">Info</span>

<span class="badge text-bg-light">Light</span>

<span class="badge text-bg-dark">Dark</span>

```



\--------------------------------



\### Create Tabs with Dropdowns



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



Use the nav-tabs class combined with the dropdown-toggle and dropdown-menu classes to create a tabbed navigation with nested dropdowns.



```html

<ul class="nav nav-tabs">

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link active" aria-current="page" href="#">Active</a>

&#x20; </li>

&#x20; <li class="nav-item dropdown">

&#x20;   <a class="nav-link dropdown-toggle" data-bs-toggle="dropdown" href="#" role="button" aria-expanded="false">Dropdown</a>

&#x20;   <ul class="dropdown-menu">

&#x20;     <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;     <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;     <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;     <li><hr class="dropdown-divider"></li>

&#x20;     <li><a class="dropdown-item" href="#">Separated link</a></li>

&#x20;   </ul>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link" href="#">Link</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link disabled" aria-disabled="true">Disabled</a>

&#x20; </li>

</ul>

```



\--------------------------------



\### Apply contextual classes to list items



Source: https://getbootstrap.com/docs/5.3/components/list-group



Use contextual classes on list-group-item elements to apply specific background and color styles.



```html

<ul class="list-group">

&#x20; <li class="list-group-item">A simple default list group item</li>

&#x20; 

&#x20; <li class="list-group-item list-group-item-primary">A simple primary list group item</li>

&#x20; <li class="list-group-item list-group-item-secondary">A simple secondary list group item</li>

&#x20; <li class="list-group-item list-group-item-success">A simple success list group item</li>

&#x20; <li class="list-group-item list-group-item-danger">A simple danger list group item</li>

&#x20; <li class="list-group-item list-group-item-warning">A simple warning list group item</li>

&#x20; <li class="list-group-item list-group-item-info">A simple info list group item</li>

&#x20; <li class="list-group-item list-group-item-light">A simple light list group item</li>

&#x20; <li class="list-group-item list-group-item-dark">A simple dark list group item</li>

</ul>

```



\--------------------------------



\### Standard HTML Headings



Source: https://getbootstrap.com/docs/5.3/content/typography



Displays the default styling for standard HTML heading elements from h1 to h6.



```html

<h1>h1. Bootstrap heading</h1>

<h2>h2. Bootstrap heading</h2>

<h3>h3. Bootstrap heading</h3>

<h4>h4. Bootstrap heading</h4>

<h5>h5. Bootstrap heading</h5>

<h6>h6. Bootstrap heading</h6>

```



\--------------------------------



\### Configure popover CSS variables



Source: https://getbootstrap.com/docs/5.3/components/popovers



Local CSS variables used for real-time customization of popover components.



```scss

\--#{$prefix}popover-zindex: #{$zindex-popover};

\--#{$prefix}popover-max-width: #{$popover-max-width};

@include rfs($popover-font-size, --#{$prefix}popover-font-size);

\--#{$prefix}popover-bg: #{$popover-bg};

\--#{$prefix}popover-border-width: #{$popover-border-width};

\--#{$prefix}popover-border-color: #{$popover-border-color};

\--#{$prefix}popover-border-radius: #{$popover-border-radius};

\--#{$prefix}popover-inner-border-radius: #{$popover-inner-border-radius};

\--#{$prefix}popover-box-shadow: #{$popover-box-shadow};

\--#{$prefix}popover-header-padding-x: #{$popover-header-padding-x};

\--#{$prefix}popover-header-padding-y: #{$popover-header-padding-y};

@include rfs($popover-header-font-size, --#{$prefix}popover-header-font-size);

\--#{$prefix}popover-header-color: #{$popover-header-color};

\--#{$prefix}popover-header-bg: #{$popover-header-bg};

\--#{$prefix}popover-body-padding-x: #{$popover-body-padding-x};

\--#{$prefix}popover-body-padding-y: #{$popover-body-padding-y};

\--#{$prefix}popover-body-color: #{$popover-body-color};

\--#{$prefix}popover-arrow-width: #{$popover-arrow-width};

\--#{$prefix}popover-arrow-height: #{$popover-arrow-height};

\--#{$prefix}popover-arrow-border: var(--#{$prefix}popover-border-color);

```



\--------------------------------



\### Basic Table Markup



Source: https://getbootstrap.com/docs/5.3/content/tables



Apply the .table class to a standard HTML table element to enable Bootstrap styling.



```html

<table class="table">

&#x20; <thead>

&#x20;   <tr>

&#x20;     <th scope="col">#</th>

&#x20;     <th scope="col">First</th>

&#x20;     <th scope="col">Last</th>

&#x20;     <th scope="col">Handle</th>

&#x20;   </tr>

&#x20; </thead>

&#x20; <tbody>

&#x20;   <tr>

&#x20;     <th scope="row">1</th>

&#x20;     <td>Mark</td>

&#x20;     <td>Otto</td>

&#x20;     <td>@mdo</td>

&#x20;   </tr>

&#x20;   <tr>

&#x20;     <th scope="row">2</th>

&#x20;     <td>Jacob</td>

&#x20;     <td>Thornton</td>

&#x20;     <td>@fat</td>

&#x20;   </tr>

&#x20;   <tr>

&#x20;     <th scope="row">3</th>

&#x20;     <td>John</td>

&#x20;     <td>Doe</td>

&#x20;     <td>@social</td>

&#x20;   </tr>

&#x20; </tbody>

</table>

```



\--------------------------------



\### Optimize Bootstrap Sass imports



Source: https://getbootstrap.com/docs/5.3/customize/optimize



Customize your build by commenting out or removing unused component imports from the main bootstrap.scss file.



```scss

// Configuration

@import "functions";

@import "variables";

@import "variables-dark";

@import "maps";

@import "mixins";

@import "utilities";



// Layout \& components

@import "root";

@import "reboot";

@import "type";

@import "images";

@import "containers";

@import "grid";

@import "tables";

@import "forms";

@import "buttons";

@import "transitions";

@import "dropdown";

@import "button-group";

@import "nav";

@import "navbar";

@import "card";

@import "accordion";

@import "breadcrumb";

@import "pagination";

@import "badge";

@import "alert";

@import "progress";

@import "list-group";

@import "close";

@import "toasts";

@import "modal";

@import "tooltip";

@import "popover";

@import "carousel";

@import "spinners";

@import "offcanvas";

@import "placeholders";



// Helpers

@import "helpers";



// Utilities

@import "utilities/api";

```



\--------------------------------



\### Responsive dropdown alignment (Right on large screens)



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



Disable dynamic positioning with data-bs-display='static' and apply .dropdown-menu-lg-end to align the menu to the right on large screens and up.



```html

<div class="btn-group">

&#x20; <button type="button" class="btn btn-secondary dropdown-toggle" data-bs-toggle="dropdown" data-bs-display="static" aria-expanded="false">

&#x20;   Left-aligned but right aligned when large screen

&#x20; </button>

&#x20; <ul class="dropdown-menu dropdown-menu-lg-end">

&#x20;   <li><button class="dropdown-item" type="button">Action</button></li>

&#x20;   <li><button class="dropdown-item" type="button">Another action</button></li>

&#x20;   <li><button class="dropdown-item" type="button">Something else here</button></li>

&#x20; </ul>

</div>

```



\--------------------------------



\### Apply alert-link utility class



Source: https://getbootstrap.com/docs/5.3/components/alerts



Use the .alert-link class on anchor tags to ensure links match the color scheme of the parent alert component.



```html

<div class="alert alert-primary" role="alert">

&#x20; A simple primary alert with <a href="#" class="alert-link">an example link</a>. Give it a click if you like.

</div>

<div class="alert alert-secondary" role="alert">

&#x20; A simple secondary alert with <a href="#" class="alert-link">an example link</a>. Give it a click if you like.

</div>

<div class="alert alert-success" role="alert">

&#x20; A simple success alert with <a href="#" class="alert-link">an example link</a>. Give it a click if you like.

</div>

<div class="alert alert-danger" role="alert">

&#x20; A simple danger alert with <a href="#" class="alert-link">an example link</a>. Give it a click if you like.

</div>

<div class="alert alert-warning" role="alert">

&#x20; A simple warning alert with <a href="#" class="alert-link">an example link</a>. Give it a click if you like.

</div>

<div class="alert alert-info" role="alert">

&#x20; A simple info alert with <a href="#" class="alert-link">an example link</a>. Give it a click if you like.

</div>

<div class="alert alert-light" role="alert">

&#x20; A simple light alert with <a href="#" class="alert-link">an example link</a>. Give it a click if you like.

</div>

<div class="alert alert-dark" role="alert">

&#x20; A simple dark alert with <a href="#" class="alert-link">an example link</a>. Give it a click if you like.

</div>

```



\--------------------------------



\### Compiled CSS Min-width Media Queries



Source: https://getbootstrap.com/docs/5.3/layout/breakpoints



The resulting CSS output for min-width breakpoints based on Bootstrap's default variables.



```css

// X-Small devices (portrait phones, less than 576px)

// No media query for `xs` since this is the default in Bootstrap



// Small devices (landscape phones, 576px and up)

@media (min-width: 576px) { ... }



// Medium devices (tablets, 768px and up)

@media (min-width: 768px) { ... }



// Large devices (desktops, 992px and up)

@media (min-width: 992px) { ... }



// X-Large devices (large desktops, 1200px and up)

@media (min-width: 1200px) { ... }



// XX-Large devices (larger desktops, 1400px and up)

@media (min-width: 1400px) { ... }

```



\--------------------------------



\### Create Dropdown with Buttons



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



Uses button elements as dropdown items within a standard dropdown container.



```html

<div class="dropdown">

&#x20; <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   Dropdown

&#x20; </button>

&#x20; <ul class="dropdown-menu">

&#x20;   <li><button class="dropdown-item" type="button">Action</button></li>

&#x20;   <li><button class="dropdown-item" type="button">Another action</button></li>

&#x20;   <li><button class="dropdown-item" type="button">Something else here</button></li>

&#x20; </ul>

</div>

```



\--------------------------------



\### Apply border width utilities



Source: https://getbootstrap.com/docs/5.3/utilities/borders



Use these classes to set the width of an element's border.



```html

<span class="border border-1"></span>

<span class="border border-2"></span>

<span class="border border-3"></span>

<span class="border border-4"></span>

<span class="border border-5"></span>

```



\--------------------------------



\### Generating Custom Color Utilities



Source: https://getbootstrap.com/docs/5.3/customize/color



Using the utility API and map-merge-multiple to generate custom text color utility classes.



```scss

@import "bootstrap/scss/functions";

@import "bootstrap/scss/variables";

@import "bootstrap/scss/variables-dark";

@import "bootstrap/scss/maps";

@import "bootstrap/scss/mixins";

@import "bootstrap/scss/utilities";



$all-colors: map-merge-multiple($blues, $indigos, $purples, $pinks, $reds, $oranges, $yellows, $greens, $teals, $cyans);



$utilities: map-merge(

&#x20; $utilities,

&#x20; (

&#x20;   "color": map-merge(

&#x20;     map-get($utilities, "color"),

&#x20;     (

&#x20;       values: map-merge(

&#x20;         map-get(map-get($utilities, "color"), "values"),

&#x20;         (

&#x20;           $all-colors

&#x20;         ),

&#x20;       ),

&#x20;     ),

&#x20;   ),

&#x20; )

);



@import "bootstrap/scss/utilities/api";

```



\--------------------------------



\### Define grid Sass variables



Source: https://getbootstrap.com/docs/5.3/layout/grid



Configure grid columns, gutter widths, and row columns using Sass variables.



```scss

$grid-columns:      12;

$grid-gutter-width: 1.5rem;

$grid-row-columns:  6;

```



\--------------------------------



\### Auto Column Sizing



Source: https://getbootstrap.com/docs/5.3/layout/css-grid



Shows default behavior where grid items without classes are sized to one column, and how this can be mixed with explicit column classes.



```html

<div class="grid text-center">

&#x20; <div>1</div>

&#x20; <div>1</div>

&#x20; <div>1</div>

&#x20; <div>1</div>

&#x20; <div>1</div>

&#x20; <div>1</div>

&#x20; <div>1</div>

&#x20; <div>1</div>

&#x20; <div>1</div>

&#x20; <div>1</div>

&#x20; <div>1</div>

&#x20; <div>1</div>

</div>

```



```html

<div class="grid text-center">

&#x20; <div class="g-col-6">.g-col-6</div>

&#x20; <div>1</div>

&#x20; <div>1</div>

&#x20; <div>1</div>

&#x20; <div>1</div>

&#x20; <div>1</div>

&#x20; <div>1</div>

</div>

```



\--------------------------------



\### Add new colors to theme-colors



Source: https://getbootstrap.com/docs/5.3/customize/sass



Create a custom map and merge it with the existing $theme-colors map.



```scss

// Create your own map

$custom-colors: (

&#x20; "custom-color": #900

);



// Merge the maps

$theme-colors: map-merge($theme-colors, $custom-colors);

```



\--------------------------------



\### Fill navigation width with .nav-fill



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



Use .nav-fill to make nav items occupy all available horizontal space with varying widths.



```html

<ul class="nav nav-pills nav-fill">

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link active" aria-current="page" href="#">Active</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link" href="#">Much longer nav link</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link" href="#">Link</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link disabled" aria-disabled="true">Disabled</a>

&#x20; </li>

</ul>

```



```html

<nav class="nav nav-pills nav-fill">

&#x20; <a class="nav-link active" aria-current="page" href="#">Active</a>

&#x20; <a class="nav-link" href="#">Much longer nav link</a>

&#x20; <a class="nav-link" href="#">Link</a>

&#x20; <a class="nav-link disabled" aria-disabled="true">Disabled</a>

</nav>

```



\--------------------------------



\### Apply sizing to form controls



Source: https://getbootstrap.com/docs/5.3/forms/form-control



Use .form-control-lg and .form-control-sm classes to adjust the height of input fields.



```html

<input class="form-control form-control-lg" type="text" placeholder=".form-control-lg" aria-label=".form-control-lg example">

<input class="form-control" type="text" placeholder="Default input" aria-label="default input example">

<input class="form-control form-control-sm" type="text" placeholder=".form-control-sm" aria-label=".form-control-sm example">

```



\--------------------------------



\### Create custom containers with Sass mixins



Source: https://getbootstrap.com/docs/5.3/layout/containers



Use the make-container mixin to generate custom container classes with specific padding.



```scss

// Source mixin

@mixin make-container($padding-x: $container-padding-x) {

&#x20; width: 100%;

&#x20; padding-right: $padding-x;

&#x20; padding-left: $padding-x;

&#x20; margin-right: auto;

&#x20; margin-left: auto;

}



// Usage

.custom-container {

&#x20; @include make-container();

}

```



\--------------------------------



\### Define border utilities in Sass



Source: https://getbootstrap.com/docs/5.3/utilities/borders



Configuration for border, border-color, border-width, and border-opacity utilities within the Bootstrap utilities API.



```scss

"border": (

&#x20; property: border,

&#x20; values: (

&#x20;   null: var(--#{$prefix}border-width) var(--#{$prefix}border-style) var(--#{$prefix}border-color),

&#x20;   0: 0,

&#x20; )

),

"border-top": (

&#x20; property: border-top,

&#x20; values: (

&#x20;   null: var(--#{$prefix}border-width) var(--#{$prefix}border-style) var(--#{$prefix}border-color),

&#x20;   0: 0,

&#x20; )

),

"border-end": (

&#x20; property: border-right,

&#x20; class: border-end,

&#x20; values: (

&#x20;   null: var(--#{$prefix}border-width) var(--#{$prefix}border-style) var(--#{$prefix}border-color),

&#x20;   0: 0,

&#x20; )

),

"border-bottom": (

&#x20; property: border-bottom,

&#x20; values: (

&#x20;   null: var(--#{$prefix}border-width) var(--#{$prefix}border-style) var(--#{$prefix}border-color),

&#x20;   0: 0,

&#x20; )

),

"border-start": (

&#x20; property: border-left,

&#x20; class: border-start,

&#x20; values: (

&#x20;   null: var(--#{$prefix}border-width) var(--#{$prefix}border-style) var(--#{$prefix}border-color),

&#x20;   0: 0,

&#x20; )

),

"border-color": (

&#x20; property: border-color,

&#x20; class: border,

&#x20; local-vars: (

&#x20;   "border-opacity": 1

&#x20; ),

&#x20; values: $utilities-border-colors

),

"subtle-border-color": (

&#x20; property: border-color,

&#x20; class: border,

&#x20; values: $utilities-border-subtle

),

"border-width": (

&#x20; property: border-width,

&#x20; class: border,

&#x20; values: $border-widths

),

"border-opacity": (

&#x20; css-var: true,

&#x20; class: border-opacity,

&#x20; values: (

&#x20;   10: .1,

&#x20;   25: .25,

&#x20;   50: .5,

&#x20;   75: .75,

&#x20;   100: 1

&#x20; )

),

```



\--------------------------------



\### Basic Floating Labels



Source: https://getbootstrap.com/docs/5.3/forms/floating-labels



Standard implementation of floating labels for email and password inputs.



```html

<div class="form-floating mb-3">

&#x20; <input type="email" class="form-control" id="floatingInput" placeholder="name@example.com">

&#x20; <label for="floatingInput">Email address</label>

</div>

<div class="form-floating">

&#x20; <input type="password" class="form-control" id="floatingPassword" placeholder="Password">

&#x20; <label for="floatingPassword">Password</label>

</div>

```



\--------------------------------



\### Create an inline list



Source: https://getbootstrap.com/docs/5.3/content/typography



Combine .list-inline and .list-inline-item classes to remove bullets and display list items horizontally.



```html

<ul class="list-inline">

&#x20; <li class="list-inline-item">This is a list item.</li>

&#x20; <li class="list-inline-item">And another one.</li>

&#x20; <li class="list-inline-item">But they’re displayed inline.</li>

</ul>

```



\--------------------------------



\### Integrate Grow Spinners in Buttons



Source: https://getbootstrap.com/docs/5.3/components/spinners



Place small grow spinners inside disabled buttons to indicate processing states.



```html

<button class="btn btn-primary" type="button" disabled>

&#x20; <span class="spinner-grow spinner-grow-sm" aria-hidden="true"></span>

&#x20; <span class="visually-hidden" role="status">Loading...</span>

</button>

<button class="btn btn-primary" type="button" disabled>

&#x20; <span class="spinner-grow spinner-grow-sm" aria-hidden="true"></span>

&#x20; <span role="status">Loading...</span>

</button>

```



\--------------------------------



\### Apply Navbar Color Schemes



Source: https://getbootstrap.com/docs/5.3/components/navbar



Use data-bs-theme='dark' or 'light' on the navbar element to control the color mode, combined with background utilities.



```html

<nav class="navbar bg-dark border-bottom border-body" data-bs-theme="dark">

&#x20; <!-- Navbar content -->

</nav>



<nav class="navbar bg-primary" data-bs-theme="dark">

&#x20; <!-- Navbar content -->

</nav>



<nav class="navbar" style="background-color: #e3f2fd;" data-bs-theme="light">

&#x20; <!-- Navbar content -->

</nav>

```



\--------------------------------



\### Create standard radio buttons



Source: https://getbootstrap.com/docs/5.3/forms/checks



Use the form-check class to group radio inputs and labels. Include the checked attribute to set a default selection.



```html

<div class="form-check">

&#x20; <input class="form-check-input" type="radio" name="radioDefault" id="radioDefault1">

&#x20; <label class="form-check-label" for="radioDefault1">

&#x20;   Default radio

&#x20; </label>

</div>

<div class="form-check">

&#x20; <input class="form-check-input" type="radio" name="radioDefault" id="radioDefault2" checked>

&#x20; <label class="form-check-label" for="radioDefault2">

&#x20;   Default checked radio

&#x20; </label>

</div>

```



\--------------------------------



\### Apply relative width utilities



Source: https://getbootstrap.com/docs/5.3/utilities/sizing



Use these classes to set an element's width as a percentage of its parent container.



```html

<div class="w-25 p-3">Width 25%</div>

<div class="w-50 p-3">Width 50%</div>

<div class="w-75 p-3">Width 75%</div>

<div class="w-100 p-3">Width 100%</div>

<div class="w-auto p-3">Width auto</div>

```



\--------------------------------



\### Customize link opacity



Source: https://getbootstrap.com/docs/5.3/content



Adjust link color opacity using the --bs-link-opacity CSS variable.



```html

<a href="#" style="--bs-link-opacity: .5">This is an example link</a>

```



\--------------------------------



\### Tab Events



Source: https://getbootstrap.com/docs/5.3/components/list-group



Lifecycle events fired during the tab transition process.



```APIDOC

\## Tab Events



\- \*\*hide.bs.tab\*\*: Fires when a new tab is to be shown.

\- \*\*hidden.bs.tab\*\*: Fires after a new tab is shown.

\- \*\*show.bs.tab\*\*: Fires on tab show, but before the new tab has been shown.

\- \*\*shown.bs.tab\*\*: Fires on tab show after a tab has been shown.

```



\--------------------------------



\### Add block-level form text



Source: https://getbootstrap.com/docs/5.3/forms/form-control



Use .form-text for block-level help text, ensuring it is linked to the input via aria-describedby.



```html

<label for="inputPassword5" class="form-label">Password</label>

<input type="password" id="inputPassword5" class="form-control" aria-describedby="passwordHelpBlock">

<div id="passwordHelpBlock" class="form-text">

&#x20; Your password must be 8-20 characters long, contain letters and numbers, and must not contain spaces, special characters, or emoji.

</div>

```



\--------------------------------



\### Implement inline tooltips on links



Source: https://getbootstrap.com/docs/5.3/components/tooltips



Use the data-bs-toggle attribute on anchor tags to trigger tooltips with specific titles.



```html

<p class="muted">Placeholder text to demonstrate some <a href="#" data-bs-toggle="tooltip" data-bs-title="Default tooltip">inline links</a> with tooltips. This is now just filler, no killer. Content placed here just to mimic the presence of <a href="#" data-bs-toggle="tooltip" data-bs-title="Another tooltip">real text</a>. And all that just to give you an idea of how tooltips would look when used in real-world situations. So hopefully you’ve now seen how <a href="#" data-bs-toggle="tooltip" data-bs-title="Another one here too">these tooltips on links</a> can work in practice, once you use them on <a href="#" data-bs-toggle="tooltip" data-bs-title="The last tip!">your own</a> site or project.</p>

```



\--------------------------------



\### Initialize Bootstrap Toast



Source: https://getbootstrap.com/docs/5.3/docsref



JavaScript snippet to trigger a Bootstrap toast notification via a button click.



```javascript

const toastTrigger = document.getElementById('liveToastBtn')

const toastLiveExample = document.getElementById('liveToast')



if (toastTrigger) {

&#x20; const toastBootstrap = bootstrap.Toast.getOrCreateInstance(toastLiveExample)

&#x20; toastTrigger.addEventListener('click', () => {

&#x20;   toastBootstrap.show()

&#x20; })

}



```



\--------------------------------



\### Toggle between multiple modals



Source: https://getbootstrap.com/docs/5.3/components/modal



Use data-bs-target and data-bs-toggle attributes to switch between different modal instances.



```html

<div class="modal fade" id="exampleModalToggle" aria-hidden="true" aria-labelledby="exampleModalToggleLabel" tabindex="-1">

&#x20; <div class="modal-dialog modal-dialog-centered">

&#x20;   <div class="modal-content">

&#x20;     <div class="modal-header">

&#x20;       <h1 class="modal-title fs-5" id="exampleModalToggleLabel">Modal 1</h1>

&#x20;       <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>

&#x20;     </div>

&#x20;     <div class="modal-body">

&#x20;       Show a second modal and hide this one with the button below.

&#x20;     </div>

&#x20;     <div class="modal-footer">

&#x20;       <button class="btn btn-primary" data-bs-target="#exampleModalToggle2" data-bs-toggle="modal">Open second modal</button>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

<div class="modal fade" id="exampleModalToggle2" aria-hidden="true" aria-labelledby="exampleModalToggleLabel2" tabindex="-1">

&#x20; <div class="modal-dialog modal-dialog-centered">

&#x20;   <div class="modal-content">

&#x20;     <div class="modal-header">

&#x20;       <h1 class="modal-title fs-5" id="exampleModalToggleLabel2">Modal 2</h1>

&#x20;       <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>

&#x20;     </div>

&#x20;     <div class="modal-body">

&#x20;       Hide this modal and show the first with the button below.

&#x20;     </div>

&#x20;     <div class="modal-footer">

&#x20;       <button class="btn btn-primary" data-bs-target="#exampleModalToggle" data-bs-toggle="modal">Back to first</button>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

<button class="btn btn-primary" data-bs-target="#exampleModalToggle" data-bs-toggle="modal">Open first modal</button>

```



\--------------------------------



\### Create a button group with links



Source: https://getbootstrap.com/docs/5.3/components/button-group



Apply button group classes to anchor tags as an alternative to standard navigation components.



```html

<div class="btn-group">

&#x20; <a href="#" class="btn btn-primary active" aria-current="page">Active link</a>

&#x20; <a href="#" class="btn btn-primary">Link</a>

&#x20; <a href="#" class="btn btn-primary">Link</a>

</div>

```



\--------------------------------



\### Applying Object Fit Classes to Images



Source: https://getbootstrap.com/docs/5.3/utilities/object-fit



Apply object-fit utility classes to img elements to control how they fill their parent containers.



```html

<img src="..." class="object-fit-contain border rounded" alt="...">

<img src="..." class="object-fit-cover border rounded" alt="...">

<img src="..." class="object-fit-fill border rounded" alt="...">

<img src="..." class="object-fit-scale border rounded" alt="...">

<img src="..." class="object-fit-none border rounded" alt="...">

```



\--------------------------------



\### Create toggle switches



Source: https://getbootstrap.com/docs/5.3/forms/checks



Use the .form-switch class on a form-check container. Adding role="switch" improves accessibility for assistive technologies.



```html

<div class="form-check form-switch">

&#x20; <input class="form-check-input" type="checkbox" role="switch" id="switchCheckDefault">

&#x20; <label class="form-check-label" for="switchCheckDefault">Default switch checkbox input</label>

</div>

<div class="form-check form-switch">

&#x20; <input class="form-check-input" type="checkbox" role="switch" id="switchCheckChecked" checked>

&#x20; <label class="form-check-label" for="switchCheckChecked">Checked switch checkbox input</label>

</div>

<div class="form-check form-switch">

&#x20; <input class="form-check-input" type="checkbox" role="switch" id="switchCheckDisabled" disabled>

&#x20; <label class="form-check-label" for="switchCheckDisabled">Disabled switch checkbox input</label>

</div>

<div class="form-check form-switch">

&#x20; <input class="form-check-input" type="checkbox" role="switch" id="switchCheckCheckedDisabled" checked disabled>

&#x20; <label class="form-check-label" for="switchCheckCheckedDisabled">Disabled checked switch checkbox input</label>

</div>

```



\--------------------------------



\### Integrate dark dropdowns into a navbar



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



Demonstrates the use of dark dropdown menus within a dark-themed navbar component.



```html

<nav class="navbar navbar-expand-lg navbar-dark bg-dark">

&#x20; <div class="container-fluid">

&#x20;   <a class="navbar-brand" href="#">Navbar</a>

&#x20;   <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDarkDropdown" aria-controls="navbarNavDarkDropdown" aria-expanded="false" aria-label="Toggle navigation">

&#x20;     <span class="navbar-toggler-icon"></span>

&#x20;   </button>

&#x20;   <div class="collapse navbar-collapse" id="navbarNavDarkDropdown">

&#x20;     <ul class="navbar-nav">

&#x20;       <li class="nav-item dropdown">

&#x20;         <button class="btn btn-dark dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;           Dropdown

&#x20;         </button>

&#x20;         <ul class="dropdown-menu dropdown-menu-dark">

&#x20;           <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;           <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;           <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;         </ul>

&#x20;       </li>

&#x20;     </ul>

&#x20;   </div>

&#x20; </div>

</nav>

```



\--------------------------------



\### Apply Horizontal Collapse



Source: https://getbootstrap.com/docs/5.3/migration



Use the .collapse-horizontal class to enable width-based collapsing instead of height-based.



```html

.collapse-horizontal

```



\--------------------------------



\### Configure row columns



Source: https://getbootstrap.com/docs/5.3/layout/grid



Use .row-cols-\* classes on the parent row to set the number of columns, or use the Sass mixin for custom styling.



```html

<div class="container text-center">

&#x20; <div class="row row-cols-2">

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20; </div>

</div>

```



```html

<div class="container text-center">

&#x20; <div class="row row-cols-3">

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20; </div>

</div>

```



```html

<div class="container text-center">

&#x20; <div class="row row-cols-auto">

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20; </div>

</div>

```



```html

<div class="container text-center">

&#x20; <div class="row row-cols-4">

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20; </div>

</div>

```



```html

<div class="container text-center">

&#x20; <div class="row row-cols-4">

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col-6">Column</div>

&#x20;   <div class="col">Column</div>

&#x20; </div>

</div>

```



```html

<div class="container text-center">

&#x20; <div class="row row-cols-1 row-cols-sm-2 row-cols-md-4">

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20;   <div class="col">Column</div>

&#x20; </div>

</div>

```



```scss

.element {

&#x20; // Three columns to start

&#x20; @include row-cols(3);



&#x20; // Five columns from medium breakpoint up

&#x20; @include media-breakpoint-up(md) {

&#x20;   @include row-cols(5);

&#x20; }

}

```



\--------------------------------



\### Trigger live alerts with JavaScript



Source: https://getbootstrap.com/docs/5.3/components/alerts



JavaScript logic to dynamically append dismissible alerts to a placeholder element.



```javascript

const alertPlaceholder = document.getElementById('liveAlertPlaceholder')

const appendAlert = (message, type) => {

&#x20; const wrapper = document.createElement('div')

&#x20; wrapper.innerHTML = \[

&#x20;   `<div class="alert alert-${type} alert-dismissible" role="alert">`,

&#x20;   `   <div>${message}</div>`,

&#x20;   '   <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>',

&#x20;   '</div>'

&#x20; ].join('')



&#x20; alertPlaceholder.append(wrapper)

}



const alertTrigger = document.getElementById('liveAlertBtn')

if (alertTrigger) {

&#x20; alertTrigger.addEventListener('click', () => {

&#x20;   appendAlert('Nice, you triggered this alert message!', 'success')

&#x20; })

}

```



\--------------------------------



\### Configure Popper with a function



Source: https://getbootstrap.com/docs/5.3/components/popovers



Use a function within the popperConfig option to merge custom settings with the default Bootstrap Popper configuration.



```javascript

const popover = new bootstrap.Popover(element, {

&#x20; popperConfig(defaultBsPopperConfig) {

&#x20;   // const newPopperConfig = {...}

&#x20;   // use defaultBsPopperConfig if needed...

&#x20;   // return newPopperConfig

&#x20; }

})

```



\--------------------------------



\### Initialize Popover via JavaScript



Source: https://getbootstrap.com/docs/5.3/components/popovers



Use the Bootstrap Popover constructor to enable a popover on a specific DOM element.



```javascript

const exampleEl = document.getElementById('example')

const popover = new bootstrap.Popover(exampleEl, options)

```



\--------------------------------



\### Basic List Group



Source: https://getbootstrap.com/docs/5.3/components/list-group



The standard implementation using an unordered list with list-group classes.



```html

<ul class="list-group">

&#x20; <li class="list-group-item">An item</li>

&#x20; <li class="list-group-item">A second item</li>

&#x20; <li class="list-group-item">A third item</li>

&#x20; <li class="list-group-item">A fourth item</li>

&#x20; <li class="list-group-item">And a fifth one</li>

</ul>

```



\--------------------------------



\### Implement Floating Labels in a Grid



Source: https://getbootstrap.com/docs/5.3/forms/floating-labels



Use the grid system to arrange floating labels side-by-side by wrapping them in column classes.



```html

<div class="row g-2">

&#x20; <div class="col-md">

&#x20;   <div class="form-floating">

&#x20;     <input type="email" class="form-control" id="floatingInputGrid" placeholder="name@example.com" value="mdo@example.com">

&#x20;     <label for="floatingInputGrid">Email address</label>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col-md">

&#x20;   <div class="form-floating">

&#x20;     <select class="form-select" id="floatingSelectGrid">

&#x20;       <option selected>Open this select menu</option>

&#x20;       <option value="1">One</option>

&#x20;       <option value="2">Two</option>

&#x20;       <option value="3">Three</option>

&#x20;     </select>

&#x20;     <label for="floatingSelectGrid">Works with selects</label>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Apply active state to pagination



Source: https://getbootstrap.com/docs/5.3/components/pagination



Use the .active class on a .page-item to highlight the current page. Include aria-current='page' for accessibility when using an anchor tag.



```html

<nav aria-label="...">

&#x20; <ul class="pagination">

&#x20;   <li class="page-item"><a href="#" class="page-link">Previous</a></li>

&#x20;   <li class="page-item"><a class="page-link" href="#">1</a></li>

&#x20;   <li class="page-item active">

&#x20;     <a class="page-link" href="#" aria-current="page">2</a>

&#x20;   </li>

&#x20;   <li class="page-item"><a class="page-link" href="#">3</a></li>

&#x20;   <li class="page-item"><a class="page-link" href="#">Next</a></li>

&#x20; </ul>

</nav>

```



```html

<li class="page-item active">

&#x20; <span class="page-link">2</span>

</li>

```



\--------------------------------



\### Create input groups with dropdown menus



Source: https://getbootstrap.com/docs/5.3/forms/input-group



Integrate dropdown buttons into input groups using the data-bs-toggle attribute. Use dropdown-menu-end to align the menu to the right.



```html

<div class="input-group mb-3">

&#x20; <button class="btn btn-outline-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">Dropdown</button>

&#x20; <ul class="dropdown-menu">

&#x20;   <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;   <li><hr class="dropdown-divider"></li>

&#x20;   <li><a class="dropdown-item" href="#">Separated link</a></li>

&#x20; </ul>

&#x20; <input type="text" class="form-control" aria-label="Text input with dropdown button">

</div>



<div class="input-group mb-3">

&#x20; <input type="text" class="form-control" aria-label="Text input with dropdown button">

&#x20; <button class="btn btn-outline-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">Dropdown</button>

&#x20; <ul class="dropdown-menu dropdown-menu-end">

&#x20;   <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;   <li><hr class="dropdown-divider"></li>

&#x20;   <li><a class="dropdown-item" href="#">Separated link</a></li>

&#x20; </ul>

</div>



<div class="input-group">

&#x20; <button class="btn btn-outline-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">Dropdown</button>

&#x20; <ul class="dropdown-menu">

&#x20;   <li><a class="dropdown-item" href="#">Action before</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Another action before</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;   <li><hr class="dropdown-divider"></li>

&#x20;   <li><a class="dropdown-item" href="#">Separated link</a></li>

&#x20; </ul>

&#x20; <input type="text" class="form-control" aria-label="Text input with 2 dropdown buttons">

&#x20; <button class="btn btn-outline-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">Dropdown</button>

&#x20; <ul class="dropdown-menu dropdown-menu-end">

&#x20;   <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;   <li><hr class="dropdown-divider"></li>

&#x20;   <li><a class="dropdown-item" href="#">Separated link</a></li>

&#x20; </ul>

</div>

```



\--------------------------------



\### Responsive offcanvas navbar



Source: https://getbootstrap.com/docs/5.3/components/navbar



Uses .navbar-expand-\* classes to make the offcanvas expand into a standard navbar at specific breakpoints.



```html

<nav class="navbar navbar-expand-lg bg-body-tertiary fixed-top">

&#x20; <a class="navbar-brand" href="#">Offcanvas navbar</a>

&#x20; <button class="navbar-toggler" type="button" data-bs-toggle="offcanvas" data-bs-target="#navbarOffcanvasLg" aria-controls="navbarOffcanvasLg" aria-label="Toggle navigation">

&#x20;   <span class="navbar-toggler-icon"></span>

&#x20; </button>

&#x20; <div class="offcanvas offcanvas-end" tabindex="-1" id="navbarOffcanvasLg" aria-labelledby="navbarOffcanvasLgLabel">

&#x20;   ...

&#x20; </div>

</nav>

```



\--------------------------------



\### Define Default Sanitizer Allowlist



Source: https://getbootstrap.com/docs/5.3/getting-started/javascript



The default configuration for allowed HTML tags and attributes used by tooltip and popover components.



```javascript

const ARIA\_ATTRIBUTE\_PATTERN = /^aria-\[\\w-]\*$/i



export const DefaultAllowlist = {

&#x20; // Global attributes allowed on any supplied element below.

&#x20; '\*': \['class', 'dir', 'id', 'lang', 'role', ARIA\_ATTRIBUTE\_PATTERN],

&#x20; a: \['target', 'href', 'title', 'rel'],

&#x20; area: \[],

&#x20; b: \[],

&#x20; br: \[],

&#x20; col: \[],

&#x20; code: \[],

&#x20; dd: \[],

&#x20; div: \[],

&#x20; dl: \[],

&#x20; dt: \[],

&#x20; em: \[],

&#x20; hr: \[],

&#x20; h1: \[],

&#x20; h2: \[],

&#x20; h3: \[],

&#x20; h4: \[],

&#x20; h5: \[],

&#x20; h6: \[],

&#x20; i: \[],

&#x20; img: \['src', 'srcset', 'alt', 'title', 'width', 'height'],

&#x20; li: \[],

&#x20; ol: \[],

&#x20; p: \[],

&#x20; pre: \[],

&#x20; s: \[],

&#x20; small: \[],

&#x20; span: \[],

&#x20; sub: \[],

&#x20; sup: \[],

&#x20; strong: \[],

&#x20; u: \[],

&#x20; ul: \[]

}

```



\--------------------------------



\### Listen to Collapse Events



Source: https://getbootstrap.com/docs/5.3/components/collapse



Attach event listeners to handle actions after a collapse element has finished its transition.



```javascript

const myCollapsible = document.getElementById('myCollapsible')

myCollapsible.addEventListener('hidden.bs.collapse', event => {

&#x20; // do something...

})

```



\--------------------------------



\### Nest grid columns in HTML



Source: https://getbootstrap.com/docs/5.3/layout/grid



Create nested layouts by adding a new .row and .col-sm-\* columns within an existing column.



```html

<div class="container text-center">

&#x20; <div class="row">

&#x20;   <div class="col-sm-3">

&#x20;     Level 1: .col-sm-3

&#x20;   </div>

&#x20;   <div class="col-sm-9">

&#x20;     <div class="row">

&#x20;       <div class="col-8 col-sm-6">

&#x20;         Level 2: .col-8 .col-sm-6

&#x20;       </div>

&#x20;       <div class="col-4 col-sm-6">

&#x20;         Level 2: .col-4 .col-sm-6

&#x20;       </div>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Create Toggle Buttons with HTML



Source: https://getbootstrap.com/docs/5.3/components/buttons



Use data-bs-toggle="button" to enable toggle functionality on button elements. Pre-toggled buttons require the .active class and aria-pressed="true".



```html

<p class="d-inline-flex gap-1">

&#x20; <button type="button" class="btn" data-bs-toggle="button">Toggle button</button>

&#x20; <button type="button" class="btn active" data-bs-toggle="button" aria-pressed="true">Active toggle button</button>

&#x20; <button type="button" class="btn" disabled data-bs-toggle="button">Disabled toggle button</button>

</p>

<p class="d-inline-flex gap-1">

&#x20; <button type="button" class="btn btn-primary" data-bs-toggle="button">Toggle button</button>

&#x20; <button type="button" class="btn btn-primary active" data-bs-toggle="button" aria-pressed="true">Active toggle button</button>

&#x20; <button type="button" class="btn btn-primary" disabled data-bs-toggle="button">Disabled toggle button</button>

</p>

```



\--------------------------------



\### Configure Spacing Utilities API



Source: https://getbootstrap.com/docs/5.3/utilities/spacing



Spacing utilities are generated using the utilities API in scss/\_utilities.scss, mapping properties to the defined spacer values.



```scss

"margin": (

&#x20; responsive: true,

&#x20; property: margin,

&#x20; class: m,

&#x20; values: map-merge($spacers, (auto: auto))

),

"margin-x": (

&#x20; responsive: true,

&#x20; property: margin-right margin-left,

&#x20; class: mx,

&#x20; values: map-merge($spacers, (auto: auto))

),

"margin-y": (

&#x20; responsive: true,

&#x20; property: margin-top margin-bottom,

&#x20; class: my,

&#x20; values: map-merge($spacers, (auto: auto))

),

"margin-top": (

&#x20; responsive: true,

&#x20; property: margin-top,

&#x20; class: mt,

&#x20; values: map-merge($spacers, (auto: auto))

),

"margin-end": (

&#x20; responsive: true,

&#x20; property: margin-right,

&#x20; class: me,

&#x20; values: map-merge($spacers, (auto: auto))

),

"margin-bottom": (

&#x20; responsive: true,

&#x20; property: margin-bottom,

&#x20; class: mb,

&#x20; values: map-merge($spacers, (auto: auto))

),

"margin-start": (

&#x20; responsive: true,

&#x20; property: margin-left,

&#x20; class: ms,

&#x20; values: map-merge($spacers, (auto: auto))

),

// Negative margin utilities

"negative-margin": (

&#x20; responsive: true,

&#x20; property: margin,

&#x20; class: m,

&#x20; values: $negative-spacers

),

"negative-margin-x": (

&#x20; responsive: true,

&#x20; property: margin-right margin-left,

&#x20; class: mx,

&#x20; values: $negative-spacers

),

"negative-margin-y": (

&#x20; responsive: true,

&#x20; property: margin-top margin-bottom,

&#x20; class: my,

&#x20; values: $negative-spacers

),

"negative-margin-top": (

&#x20; responsive: true,

&#x20; property: margin-top,

&#x20; class: mt,

&#x20; values: $negative-spacers

),

"negative-margin-end": (

&#x20; responsive: true,

&#x20; property: margin-right,

&#x20; class: me,

&#x20; values: $negative-spacers

),

"negative-margin-bottom": (

&#x20; responsive: true,

&#x20; property: margin-bottom,

&#x20; class: mb,

&#x20; values: $negative-spacers

),

"negative-margin-start": (

&#x20; responsive: true,

&#x20; property: margin-left,

&#x20; class: ms,

&#x20; values: $negative-spacers

),

// Padding utilities

"padding": (

&#x20; responsive: true,

&#x20; property: padding,

&#x20; class: p,

&#x20; values: $spacers

),

"padding-x": (

&#x20; responsive: true,

&#x20; property: padding-right padding-left,

&#x20; class: px,

&#x20; values: $spacers

),

"padding-y": (

&#x20; responsive: true,

&#x20; property: padding-top padding-bottom,

&#x20; class: py,

&#x20; values: $spacers

),

"padding-top": (

&#x20; responsive: true,

&#x20; property: padding-top,

&#x20; class: pt,

&#x20; values: $spacers

),

"padding-end": (

&#x20; responsive: true,

&#x20; property: padding-right,

&#x20; class: pe,

&#x20; values: $spacers

),

"padding-bottom": (

&#x20; responsive: true,

&#x20; property: padding-bottom,

&#x20; class: pb,

&#x20; values: $spacers

),

"padding-start": (

&#x20; responsive: true,

&#x20; property: padding-left,

&#x20; class: ps,

&#x20; values: $spacers

),

// Gap utility

"gap": (

&#x20; responsive: true,

&#x20; property: gap,

&#x20; class: gap,

&#x20; values: $spacers

),

"row-gap": (

&#x20; responsive: true,

&#x20; property: row-gap,

&#x20; class: row-gap,

&#x20; values: $spacers

),

"column-gap": (

&#x20; responsive: true,

&#x20; property: column-gap,

&#x20; class: column-gap,

&#x20; values: $spacers

),

```



\--------------------------------



\### Importing Bootstrap Sass



Source: https://getbootstrap.com/docs/5.3/customize/sass



Methods for importing Bootstrap into a custom stylesheet, either by including the entire framework or specific components.



```scss

// Custom.scss

// Option A: Include all of Bootstrap



// Include any default variable overrides here (though functions won’t be available)



@import "../node\_modules/bootstrap/scss/bootstrap";



// Then add additional custom code here

```



```scss

// Custom.scss

// Option B: Include parts of Bootstrap



// 1. Include functions first (so you can manipulate colors, SVGs, calc, etc)

@import "../node\_modules/bootstrap/scss/functions";



// 2. Include any default variable overrides here



// 3. Include remainder of required Bootstrap stylesheets (including any separate color mode stylesheets)

@import "../node\_modules/bootstrap/scss/variables";

@import "../node\_modules/bootstrap/scss/variables-dark";



// 4. Include any default map overrides here



// 5. Include remainder of required parts

@import "../node\_modules/bootstrap/scss/maps";

@import "../node\_modules/bootstrap/scss/mixins";

@import "../node\_modules/bootstrap/scss/root";



// 6. Include any other optional stylesheet partials as desired; list below is not inclusive of all available stylesheets

@import "../node\_modules/bootstrap/scss/utilities";

@import "../node\_modules/bootstrap/scss/reboot";

@import "../node\_modules/bootstrap/scss/type";

@import "../node\_modules/bootstrap/scss/images";

@import "../node\_modules/bootstrap/scss/containers";

@import "../node\_modules/bootstrap/scss/grid";

@import "../node\_modules/bootstrap/scss/helpers";

// ...



// 7. Optionally include utilities API last to generate classes based on the Sass map in `\_utilities.scss`

@import "../node\_modules/bootstrap/scss/utilities/api";



// 8. Add additional custom code here

```



\--------------------------------



\### Basic Toast HTML Structure



Source: https://getbootstrap.com/docs/5.3/components/toasts



A standard toast layout containing a header with a dismiss button and a body for the message content.



```html

<div class="toast" role="alert" aria-live="assertive" aria-atomic="true">

&#x20; <div class="toast-header">

&#x20;   <img src="..." class="rounded me-2" alt="...">

&#x20;   <strong class="me-auto">Bootstrap</strong>

&#x20;   <small>11 mins ago</small>

&#x20;   <button type="button" class="btn-close" data-bs-dismiss="toast" aria-label="Close"></button>

&#x20; </div>

&#x20; <div class="toast-body">

&#x20;   Hello, world! This is a toast message.

&#x20; </div>

</div>

```



\--------------------------------



\### Define Spinner Keyframes



Source: https://getbootstrap.com/docs/5.3/components/spinners



CSS keyframe animations for border and growing spinner effects.



```scss

@keyframes spinner-border {

&#x20; to { transform: rotate(360deg) #{"/\* rtl:ignore \*/"}; }

}

```



```scss

@keyframes spinner-grow {

&#x20; 0% {

&#x20;   transform: scale(0);

&#x20; }

&#x20; 50% {

&#x20;   opacity: 1;

&#x20;   transform: none;

&#x20; }

}

```



\--------------------------------



\### Create a card group



Source: https://getbootstrap.com/docs/5.3/components/card



Uses the card-group class to render attached cards with equal width and height.



```html

<div class="card-group">

&#x20; <div class="card">

&#x20;   <img src="..." class="card-img-top" alt="...">

&#x20;   <div class="card-body">

&#x20;     <h5 class="card-title">Card title</h5>

&#x20;     <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>

&#x20;     <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="card">

&#x20;   <img src="..." class="card-img-top" alt="...">

&#x20;   <div class="card-body">

&#x20;     <h5 class="card-title">Card title</h5>

&#x20;     <p class="card-text">This card has supporting text below as a natural lead-in to additional content.</p>

&#x20;     <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="card">

&#x20;   <img src="..." class="card-img-top" alt="...">

&#x20;   <div class="card-body">

&#x20;     <h5 class="card-title">Card title</h5>

&#x20;     <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.</p>

&#x20;     <p class="card-text"><small class="text-body-secondary">Last updated 3 mins ago</small></p>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Configure Form Text Sass Variables



Source: https://getbootstrap.com/docs/5.3/forms/form-control



Variables for customizing the appearance and spacing of form helper text.



```scss

$form-text-margin-top:                  .25rem;

$form-text-font-size:                   $small-font-size;

$form-text-font-style:                  null;

$form-text-font-weight:                 null;

$form-text-color:                       var(--#{$prefix}secondary-color);

```



\--------------------------------



\### Implement a dark-themed offcanvas



Source: https://getbootstrap.com/docs/5.3/components/offcanvas



Uses the .text-bg-dark and .btn-close-white classes for dark styling. Note that this approach is deprecated in v5.3.0 in favor of data-bs-theme='dark'.



```html

<div class="offcanvas offcanvas-start show text-bg-dark" tabindex="-1" id="offcanvasDark" aria-labelledby="offcanvasDarkLabel">

&#x20; <div class="offcanvas-header">

&#x20;   <h5 class="offcanvas-title" id="offcanvasDarkLabel">Offcanvas</h5>

&#x20;   <button type="button" class="btn-close btn-close-white" data-bs-dismiss="offcanvasDark" aria-label="Close"></button>

&#x20; </div>

&#x20; <div class="offcanvas-body">

&#x20;   <p>Place offcanvas content here.</p>

&#x20; </div>

</div>

```



\--------------------------------



\### Generate SRI hash via OpenSSL



Source: https://getbootstrap.com/docs/5.3/getting-started/download



Use this command to verify the integrity of a file by generating its SHA-384 hash.



```bash

openssl dgst -sha384 -binary bootstrap.min.js | openssl base64 -A

```



\--------------------------------



\### Create a horizontal form with grid layout



Source: https://getbootstrap.com/docs/5.3/forms/layout



Use the .row class on form groups and .col-\*-\* classes to define label and control widths. Apply .col-form-label to labels for proper vertical alignment.



```html

<form>

&#x20; <div class="row mb-3">

&#x20;   <label for="inputEmail3" class="col-sm-2 col-form-label">Email</label>

&#x20;   <div class="col-sm-10">

&#x20;     <input type="email" class="form-control" id="inputEmail3">

&#x20;   </div>

&#x20; </div>

&#x20; <div class="row mb-3">

&#x20;   <label for="inputPassword3" class="col-sm-2 col-form-label">Password</label>

&#x20;   <div class="col-sm-10">

&#x20;     <input type="password" class="form-control" id="inputPassword3">

&#x20;   </div>

&#x20; </div>

&#x20; <fieldset class="row mb-3">

&#x20;   <legend class="col-form-label col-sm-2 pt-0">Radios</legend>

&#x20;   <div class="col-sm-10">

&#x20;     <div class="form-check">

&#x20;       <input class="form-check-input" type="radio" name="gridRadios" id="gridRadios1" value="option1" checked>

&#x20;       <label class="form-check-label" for="gridRadios1">

&#x20;         First radio

&#x20;       </label>

&#x20;     </div>

&#x20;     <div class="form-check">

&#x20;       <input class="form-check-input" type="radio" name="gridRadios" id="gridRadios2" value="option2">

&#x20;       <label class="form-check-label" for="gridRadios2">

&#x20;         Second radio

&#x20;       </label>

&#x20;     </div>

&#x20;     <div class="form-check disabled">

&#x20;       <input class="form-check-input" type="radio" name="gridRadios" id="gridRadios3" value="option3" disabled>

&#x20;       <label class="form-check-label" for="gridRadios3">

&#x20;         Third disabled radio

&#x20;       </label>

&#x20;     </div>

&#x20;   </div>

&#x20; </fieldset>

&#x20; <div class="row mb-3">

&#x20;   <div class="col-sm-10 offset-sm-2">

&#x20;     <div class="form-check">

&#x20;       <input class="form-check-input" type="checkbox" id="gridCheck1">

&#x20;       <label class="form-check-label" for="gridCheck1">

&#x20;         Example checkbox

&#x20;       </label>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <button type="submit" class="btn btn-primary">Sign in</button>

</form>

```



\--------------------------------



\### Offcanvas Methods



Source: https://getbootstrap.com/docs/5.3/components/offcanvas



Methods available on an initialized Offcanvas instance to control its state.



```APIDOC

\## Offcanvas Methods



\### Methods

\- \*\*show()\*\* - Shows the offcanvas element.

\- \*\*hide()\*\* - Hides the offcanvas element.

\- \*\*toggle()\*\* - Toggles the offcanvas element between shown and hidden states.

\- \*\*dispose()\*\* - Destroys an element's offcanvas instance.

\- \*\*getInstance(element)\*\* - Static method to get the offcanvas instance associated with a DOM element.

\- \*\*getOrCreateInstance(element)\*\* - Static method to get the existing offcanvas instance or create a new one if it wasn't initialized.

```



\--------------------------------



\### Apply responsive column breaks



Source: https://getbootstrap.com/docs/5.3/layout/columns



Uses responsive display utilities to trigger column breaks only at specific breakpoints.



```html

<div class="container text-center">

&#x20; <div class="row">

&#x20;   <div class="col-6 col-sm-4">.col-6 .col-sm-4</div>

&#x20;   <div class="col-6 col-sm-4">.col-6 .col-sm-4</div>



&#x20;   <!-- Force next columns to break to new line at md breakpoint and up -->

&#x20;   <div class="w-100 d-none d-md-block"></div>



&#x20;   <div class="col-6 col-sm-4">.col-6 .col-sm-4</div>

&#x20;   <div class="col-6 col-sm-4">.col-6 .col-sm-4</div>

&#x20; </div>

</div>

```



\--------------------------------



\### Create a dismissible alert



Source: https://getbootstrap.com/docs/5.3/components/alerts



Uses the .alert-dismissible class and a button with data-bs-dismiss="alert" to enable inline dismissal.



```html

<div class="alert alert-warning alert-dismissible fade show" role="alert">

&#x20; <strong>Holy guacamole!</strong> You should check in on some of those fields below.

&#x20; <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>

</div>

```



\--------------------------------



\### Breakpoint-Specific Responsive Tables



Source: https://getbootstrap.com/docs/5.3/content/tables



Apply responsive behavior up to specific breakpoints using the table-responsive-{breakpoint} classes.



```html

<div class="table-responsive">

&#x20; <table class="table">

&#x20;   ...

&#x20; </table>

</div>



<div class="table-responsive-sm">

&#x20; <table class="table">

&#x20;   ...

&#x20; </table>

</div>



<div class="table-responsive-md">

&#x20; <table class="table">

&#x20;   ...

&#x20; </table>

</div>



<div class="table-responsive-lg">

&#x20; <table class="table">

&#x20;   ...

&#x20; </table>

</div>



<div class="table-responsive-xl">

&#x20; <table class="table">

&#x20;   ...

&#x20; </table>

</div>



<div class="table-responsive-xxl">

&#x20; <table class="table">

&#x20;   ...

&#x20; </table>

</div>

```



\--------------------------------



\### Align spinners with text utilities



Source: https://getbootstrap.com/docs/5.3/components/spinners



Use text alignment utilities to center the spinner.



```html

<div class="text-center">

&#x20; <div class="spinner-border" role="status">

&#x20;   <span class="visually-hidden">Loading...</span>

&#x20; </div>

</div>

```



\--------------------------------



\### Sass utilities API configuration



Source: https://getbootstrap.com/docs/5.3/utilities/visibility



Visibility utilities are defined within the Bootstrap utilities API in scss/\_utilities.scss.



```scss

"visibility": (

&#x20; property: visibility,

&#x20; class: null,

&#x20; values: (

&#x20;   visible: visible,

&#x20;   invisible: hidden,

&#x20; )

),

```



\--------------------------------



\### Apply border radius size utilities



Source: https://getbootstrap.com/docs/5.3/utilities/borders



Control the scale of rounded corners using size classes from 0 to 5, circle, or pill.



```html

<img src="..." class="rounded-0" alt="...">

<img src="..." class="rounded-1" alt="...">

<img src="..." class="rounded-2" alt="...">

<img src="..." class="rounded-3" alt="...">

<img src="..." class="rounded-4" alt="...">

<img src="..." class="rounded-5" alt="...">

<img src="..." class="rounded-circle" alt="...">

<img src="..." class="rounded-pill" alt="...">

```



```html

<img src="..." class="rounded-bottom-1" alt="...">

<img src="..." class="rounded-start-2" alt="...">

<img src="..." class="rounded-end-circle" alt="...">

<img src="..." class="rounded-start-pill" alt="...">

<img src="..." class="rounded-5 rounded-top-0" alt="...">

```



\--------------------------------



\### Wrap text with .text-wrap



Source: https://getbootstrap.com/docs/5.3/utilities/text



Use the .text-wrap class to allow text to wrap within its container.



```html

<div class="badge text-bg-primary text-wrap" style="width: 6rem;">

&#x20; This text should wrap.

</div>

```



\--------------------------------



\### Responsive floated images with columns



Source: https://getbootstrap.com/docs/5.3/layout/columns



Combine column classes with utility classes to float images. Wrap the content in a .clearfix container to ensure proper layout flow.



```html

<div class="clearfix">

&#x20; <img src="..." class="col-md-6 float-md-end mb-3 ms-md-3" alt="...">



&#x20; <p>

&#x20;   A paragraph of placeholder text. We’re using it here to show the use of the clearfix class. We’re adding quite a few meaningless phrases here to demonstrate how the columns interact here with the floated image.

&#x20; </p>



&#x20; <p>

&#x20;   As you can see the paragraphs gracefully wrap around the floated image. Now imagine how this would look with some actual content in here, rather than just this boring placeholder text that goes on and on, but actually conveys no tangible information at. It simply takes up space and should not really be read.

&#x20; </p>



&#x20; <p>

&#x20;   And yet, here you are, still persevering in reading this placeholder text, hoping for some more insights, or some hidden easter egg of content. A joke, perhaps. Unfortunately, there’s none of that here.

&#x20; </p>

</div>

```



\--------------------------------



\### Justify navigation width with .nav-justified



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



Use .nav-justified to ensure all nav items have equal width while occupying all available horizontal space.



```html

<ul class="nav nav-pills nav-justified">

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link active" aria-current="page" href="#">Active</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link" href="#">Much longer nav link</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link" href="#">Link</a>

&#x20; </li>

&#x20; <li class="nav-item">

&#x20;   <a class="nav-link disabled" aria-disabled="true">Disabled</a>

&#x20; </li>

</ul>

```



```html

<nav class="nav nav-pills nav-justified">

&#x20; <a class="nav-link active" aria-current="page" href="#">Active</a>

&#x20; <a class="nav-link" href="#">Much longer nav link</a>

&#x20; <a class="nav-link" href="#">Link</a>

&#x20; <a class="nav-link disabled" aria-disabled="true">Disabled</a>

</nav>

```



\--------------------------------



\### Basic Vertical Rule Usage



Source: https://getbootstrap.com/docs/5.3/helpers/vertical-rule



The standard implementation of a vertical rule using the vr class.



```html

<div class="vr"></div>

```



\--------------------------------



\### Create a focusable visually hidden link



Source: https://getbootstrap.com/docs/5.3/getting-started/accessibility



Use the .visually-hidden-focusable class for interactive controls like skip links, which become visible upon receiving focus.



```html

<a class="visually-hidden-focusable" href="#content">Skip to main content</a>

```



\--------------------------------



\### Tooltip Markup Structure



Source: https://getbootstrap.com/docs/5.3/components/tooltips



Required HTML attributes for triggering a tooltip and the resulting DOM structure generated by the plugin.



```html

<!-- HTML to write -->

<a href="#" data-bs-toggle="tooltip" data-bs-title="Some tooltip text!">Hover over me</a>



<!-- Generated markup by the plugin -->

<div class="tooltip bs-tooltip-auto" role="tooltip">

&#x20; <div class="tooltip-arrow"></div>

&#x20; <div class="tooltip-inner">

&#x20;   Some tooltip text!

&#x20; </div>

</div>

```



\--------------------------------



\### Create a single button dropdown



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



Use a button element with the dropdown-toggle class to trigger the menu. Ensure the container has position: relative or uses the .dropdown class.



```html

<div class="dropdown">

&#x20; <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   Dropdown button

&#x20; </button>

&#x20; <ul class="dropdown-menu">

&#x20;   <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20; </ul>

</div>

```



```html

<div class="dropdown">

&#x20; <a class="btn btn-secondary dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   Dropdown link

&#x20; </a>



&#x20; <ul class="dropdown-menu">

&#x20;   <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20; </ul>

</div>

```



\--------------------------------



\### Configure color opacities and emphasis maps



Source: https://getbootstrap.com/docs/5.3/utilities/colors



Defines maps for text utilities and emphasis colors consumed by the utilities API.



```scss

$utilities-text: map-merge(

&#x20; $utilities-colors,

&#x20; (

&#x20;   "black": to-rgb($black),

&#x20;   "white": to-rgb($white),

&#x20;   "body": to-rgb($body-color)

&#x20; )

);

$utilities-text-colors: map-loop($utilities-text, rgba-css-var, "$key", "text");



$utilities-text-emphasis-colors: (

&#x20; "primary-emphasis": var(--#{$prefix}primary-text-emphasis),

&#x20; "secondary-emphasis": var(--#{$prefix}secondary-text-emphasis),

&#x20; "success-emphasis": var(--#{$prefix}success-text-emphasis),

&#x20; "info-emphasis": var(--#{$prefix}info-text-emphasis),

&#x20; "warning-emphasis": var(--#{$prefix}warning-text-emphasis),

&#x20; "danger-emphasis": var(--#{$prefix}danger-text-emphasis),

&#x20; "light-emphasis": var(--#{$prefix}light-emphasis),

&#x20; "dark-emphasis": var(--#{$prefix}dark-text-emphasis)

);

```



\--------------------------------



\### Adding navigation to card headers



Source: https://getbootstrap.com/docs/5.3/components/card



Integrate Bootstrap nav components into card headers using specific classes for tabs or pills.



```html

<div class="card text-center">

&#x20; <div class="card-header">

&#x20;   <ul class="nav nav-tabs card-header-tabs">

&#x20;     <li class="nav-item">

&#x20;       <a class="nav-link active" aria-current="true" href="#">Active</a>

&#x20;     </li>

&#x20;     <li class="nav-item">

&#x20;       <a class="nav-link" href="#">Link</a>

&#x20;     </li>

&#x20;     <li class="nav-item">

&#x20;       <a class="nav-link disabled" aria-disabled="true">Disabled</a>

&#x20;     </li>

&#x20;   </ul>

&#x20; </div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Special title treatment</h5>

&#x20;   <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>

&#x20;   <a href="#" class="btn btn-primary">Go somewhere</a>

&#x20; </div>

</div>

```



```html

<div class="card text-center">

&#x20; <div class="card-header">

&#x20;   <ul class="nav nav-pills card-header-pills">

&#x20;     <li class="nav-item">

&#x20;       <a class="nav-link active" href="#">Active</a>

&#x20;     </li>

&#x20;     <li class="nav-item">

&#x20;       <a class="nav-link" href="#">Link</a>

&#x20;     </li>

&#x20;     <li class="nav-item">

&#x20;       <a class="nav-link disabled" aria-disabled="true">Disabled</a>

&#x20;     </li>

&#x20;   </ul>

&#x20; </div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Special title treatment</h5>

&#x20;   <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>

&#x20;   <a href="#" class="btn btn-primary">Go somewhere</a>

&#x20; </div>

</div>

```



\--------------------------------



\### Import Bootstrap Sass



Source: https://getbootstrap.com/docs/5.3/getting-started/parcel



Add this import to your main Sass file to include all of Bootstrap's source styles.



```scss

// Import all of Bootstrap’s CSS

@import "bootstrap/scss/bootstrap";

```



\--------------------------------



\### Add titles, subtitles, and links to a card



Source: https://getbootstrap.com/docs/5.3/components/card



Utilize .card-title, .card-subtitle, and .card-link classes to structure text and navigation within a card body.



```html

<div class="card" style="width: 18rem;">

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Card title</h5>

&#x20;   <h6 class="card-subtitle mb-2 text-body-secondary">Card subtitle</h6>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20;   <a href="#" class="card-link">Card link</a>

&#x20;   <a href="#" class="card-link">Another link</a>

&#x20; </div>

</div>

```



\--------------------------------



\### Input group sizing



Source: https://getbootstrap.com/docs/5.3/forms/input-group



Apply sizing classes directly to the .input-group container to automatically resize all internal elements.



```html

<div class="input-group input-group-sm mb-3">

&#x20; <span class="input-group-text" id="inputGroup-sizing-sm">Small</span>

&#x20; <input type="text" class="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-sm">

</div>



<div class="input-group mb-3">

&#x20; <span class="input-group-text" id="inputGroup-sizing-default">Default</span>

&#x20; <input type="text" class="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-default">

</div>



<div class="input-group input-group-lg">

&#x20; <span class="input-group-text" id="inputGroup-sizing-lg">Large</span>

&#x20; <input type="text" class="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-lg">

</div>

```



\--------------------------------



\### Handle modal show event with JavaScript



Source: https://getbootstrap.com/docs/5.3/components/modal



Listens for the show.bs.modal event to extract data attributes from the triggering button and update the modal content accordingly.



```javascript

const exampleModal = document.getElementById('exampleModal')

if (exampleModal) {

&#x20; exampleModal.addEventListener('show.bs.modal', event => {

&#x20;   // Button that triggered the modal

&#x20;   const button = event.relatedTarget

&#x20;   // Extract info from data-bs-\* attributes

&#x20;   const recipient = button.getAttribute('data-bs-whatever')

&#x20;   // If necessary, you could initiate an Ajax request here

&#x20;   // and then do the updating in a callback.



&#x20;   // Update the modal's content.

&#x20;   const modalTitle = exampleModal.querySelector('.modal-title')

&#x20;   const modalBodyInput = exampleModal.querySelector('.modal-body input')



&#x20;   modalTitle.textContent = `New message to ${recipient}`

&#x20;   modalBodyInput.value = recipient

&#x20; })

}

```



\--------------------------------



\### Create form groups with margin utilities



Source: https://getbootstrap.com/docs/5.3/forms/layout



Use the mb-3 utility class to add consistent bottom margin to form groups for better vertical spacing.



```html

<div class="mb-3">

&#x20; <label for="formGroupExampleInput" class="form-label">Example label</label>

&#x20; <input type="text" class="form-control" id="formGroupExampleInput" placeholder="Example input placeholder">

</div>

<div class="mb-3">

&#x20; <label for="formGroupExampleInput2" class="form-label">Another label</label>

&#x20; <input type="text" class="form-control" id="formGroupExampleInput2" placeholder="Another input placeholder">

</div>

```



\--------------------------------



\### Grid without explicit classes



Source: https://getbootstrap.com/docs/5.3/layout/css-grid



Shows how immediate children of a .grid container are automatically treated as grid items.



```html

<div class="grid text-center" style="--bs-columns: 3;">

&#x20; <div>Auto-column</div>

&#x20; <div>Auto-column</div>

&#x20; <div>Auto-column</div>

</div>

```



\--------------------------------



\### Static Offcanvas Component



Source: https://getbootstrap.com/docs/5.3/components/offcanvas



Displays an offcanvas element that is visible by default using the .show class.



```html

<div class="offcanvas offcanvas-start show" tabindex="-1" id="offcanvas" aria-labelledby="offcanvasLabel">

&#x20; <div class="offcanvas-header">

&#x20;   <h5 class="offcanvas-title" id="offcanvasLabel">Offcanvas</h5>

&#x20;   <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>

&#x20; </div>

&#x20; <div class="offcanvas-body">

&#x20;   Content for the offcanvas goes here. You can place just about any Bootstrap component or custom elements here.

&#x20; </div>

</div>

```



\--------------------------------



\### Apply large button sizes



Source: https://getbootstrap.com/docs/5.3/components/buttons



Use the .btn-lg class to increase the size of button elements.



```html

<button type="button" class="btn btn-primary btn-lg">Large button</button>

<button type="button" class="btn btn-secondary btn-lg">Large button</button>

```



\--------------------------------



\### Tooltip CSS Variables



Source: https://getbootstrap.com/docs/5.3/components/tooltips



Local CSS variables defined in scss/\_tooltip.scss for tooltip styling and layout.



```scss

\--#{$prefix}tooltip-zindex: #{$zindex-tooltip};

\--#{$prefix}tooltip-max-width: #{$tooltip-max-width};

\--#{$prefix}tooltip-padding-x: #{$tooltip-padding-x};

\--#{$prefix}tooltip-padding-y: #{$tooltip-padding-y};

\--#{$prefix}tooltip-margin: #{$tooltip-margin};

@include rfs($tooltip-font-size, --#{$prefix}tooltip-font-size);

\--#{$prefix}tooltip-color: #{$tooltip-color};

\--#{$prefix}tooltip-bg: #{$tooltip-bg};

\--#{$prefix}tooltip-border-radius: #{$tooltip-border-radius};

\--#{$prefix}tooltip-opacity: #{$tooltip-opacity};

\--#{$prefix}tooltip-arrow-width: #{$tooltip-arrow-width};

\--#{$prefix}tooltip-arrow-height: #{$tooltip-arrow-height};

```



\--------------------------------



\### Range Input with Min and Max



Source: https://getbootstrap.com/docs/5.3/forms/range



Customizing the range boundaries using min and max attributes.



```html

<label for="range2" class="form-label">Example range</label>

<input type="range" class="form-range" min="0" max="5" id="range2">

```



\--------------------------------



\### Implement right-positioned offcanvas



Source: https://getbootstrap.com/docs/5.3/components/offcanvas



Uses the .offcanvas-end class to anchor the component to the right of the viewport.



```html

<button class="btn btn-primary" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasRight" aria-controls="offcanvasRight">Toggle right offcanvas</button>



<div class="offcanvas offcanvas-end" tabindex="-1" id="offcanvasRight" aria-labelledby="offcanvasRightLabel">

&#x20; <div class="offcanvas-header">

&#x20;   <h5 class="offcanvas-title" id="offcanvasRightLabel">Offcanvas right</h5>

&#x20;   <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>

&#x20; </div>

&#x20; <div class="offcanvas-body">

&#x20;   ...

&#x20; </div>

</div>

```



\--------------------------------



\### Implement a dark offcanvas navbar



Source: https://getbootstrap.com/docs/5.3/components/navbar



Use these classes to ensure proper styling for a dark-themed offcanvas menu within a fixed-top navbar.



```html

<nav class="navbar navbar-dark bg-dark fixed-top">

&#x20; <div class="container-fluid">

&#x20;   <a class="navbar-brand" href="#">Offcanvas dark navbar</a>

&#x20;   <button class="navbar-toggler" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasDarkNavbar" aria-controls="offcanvasDarkNavbar" aria-label="Toggle navigation">

&#x20;     <span class="navbar-toggler-icon"></span>

&#x20;   </button>

&#x20;   <div class="offcanvas offcanvas-end text-bg-dark" tabindex="-1" id="offcanvasDarkNavbar" aria-labelledby="offcanvasDarkNavbarLabel">

&#x20;     <div class="offcanvas-header">

&#x20;       <h5 class="offcanvas-title" id="offcanvasDarkNavbarLabel">Dark offcanvas</h5>

&#x20;       <button type="button" class="btn-close btn-close-white" data-bs-dismiss="offcanvas" aria-label="Close"></button>

&#x20;     </div>

&#x20;     <div class="offcanvas-body">

&#x20;       <ul class="navbar-nav justify-content-end flex-grow-1 pe-3">

&#x20;         <li class="nav-item">

&#x20;           <a class="nav-link active" aria-current="page" href="#">Home</a>

&#x20;         </li>

&#x20;         <li class="nav-item">

&#x20;           <a class="nav-link" href="#">Link</a>

&#x20;         </li>

&#x20;         <li class="nav-item dropdown">

&#x20;           <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;             Dropdown

&#x20;           </a>

&#x20;           <ul class="dropdown-menu dropdown-menu-dark">

&#x20;             <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;             <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;             <li>

&#x20;               <hr class="dropdown-divider">

&#x20;             </li>

&#x20;             <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;           </ul>

&#x20;         </li>

&#x20;       </ul>

&#x20;       <form class="d-flex mt-3" role="search">

&#x20;         <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search"/>

&#x20;         <button class="btn btn-success" type="submit">Search</button>

&#x20;       </form>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</nav>

```



\--------------------------------



\### Indicate variables



Source: https://getbootstrap.com/docs/5.3/content/reboot



Use the <var> tag to denote variables in mathematical or programming expressions.



```html

<var>y</var> = <var>m</var><var>x</var> + <var>b</var>

```



\--------------------------------



\### Implement Tabs with Data Attributes



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



Use data-bs-toggle attributes on navigation elements to enable tab functionality without custom JavaScript.



```html

<!-- Nav tabs -->

<ul class="nav nav-tabs" id="myTab" role="tablist">

&#x20; <li class="nav-item" role="presentation">

&#x20;   <button class="nav-link active" id="home-tab" data-bs-toggle="tab" data-bs-target="#home" type="button" role="tab" aria-controls="home" aria-selected="true">Home</button>

&#x20; </li>

&#x20; <li class="nav-item" role="presentation">

&#x20;   <button class="nav-link" id="profile-tab" data-bs-toggle="tab" data-bs-target="#profile" type="button" role="tab" aria-controls="profile" aria-selected="false">Profile</button>

&#x20; </li>

&#x20; <li class="nav-item" role="presentation">

&#x20;   <button class="nav-link" id="messages-tab" data-bs-toggle="tab" data-bs-target="#messages" type="button" role="tab" aria-controls="messages" aria-selected="false">Messages</button>

&#x20; </li>

&#x20; <li class="nav-item" role="presentation">

&#x20;   <button class="nav-link" id="settings-tab" data-bs-toggle="tab" data-bs-target="#settings" type="button" role="tab" aria-controls="settings" aria-selected="false">Settings</button>

&#x20; </li>

</ul>



<!-- Tab panes -->

<div class="tab-content">

&#x20; <div class="tab-pane active" id="home" role="tabpanel" aria-labelledby="home-tab" tabindex="0">...</div>

&#x20; <div class="tab-pane" id="profile" role="tabpanel" aria-labelledby="profile-tab" tabindex="0">...</div>

&#x20; <div class="tab-pane" id="messages" role="tabpanel" aria-labelledby="messages-tab" tabindex="0">...</div>

&#x20; <div class="tab-pane" id="settings" role="tabpanel" aria-labelledby="settings-tab" tabindex="0">...</div>

</div>

```



\--------------------------------



\### Listen for Popover Events



Source: https://getbootstrap.com/docs/5.3/components/popovers



Shows how to attach an event listener to a popover trigger element to execute code after the popover is hidden.



```javascript

const myPopoverTrigger = document.getElementById('myPopover')

myPopoverTrigger.addEventListener('hidden.bs.popover', () => {

&#x20; // do something...

})

```



\--------------------------------



\### Add new utility classes



Source: https://getbootstrap.com/docs/5.3/utilities/api



Use map-merge to add custom utilities to the existing $utilities map after importing required Bootstrap Sass files.



```scss

@import "bootstrap/scss/functions";

@import "bootstrap/scss/variables";

@import "bootstrap/scss/variables-dark";

@import "bootstrap/scss/maps";

@import "bootstrap/scss/mixins";

@import "bootstrap/scss/utilities";



$utilities: map-merge(

&#x20; $utilities,

&#x20; (

&#x20;   "cursor": (

&#x20;     property: cursor,

&#x20;     class: cursor,

&#x20;     responsive: true,

&#x20;     values: auto pointer grab,

&#x20;   )

&#x20; )

);



@import "bootstrap/scss/utilities/api";

```



\--------------------------------



\### Apply border color utilities to cards



Source: https://getbootstrap.com/docs/5.3/components/card



Use border color classes to change the appearance of cards. Apply text color classes to the parent card or specific child elements to coordinate colors.



```html

<div class="card border-primary mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body text-primary">

&#x20;   <h5 class="card-title">Primary card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

<div class="card border-secondary mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body text-secondary">

&#x20;   <h5 class="card-title">Secondary card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

<div class="card border-success mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body text-success">

&#x20;   <h5 class="card-title">Success card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

<div class="card border-danger mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body text-danger">

&#x20;   <h5 class="card-title">Danger card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

<div class="card border-warning mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Warning card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

<div class="card border-info mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Info card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

<div class="card border-light mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Light card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

<div class="card border-dark mb-3" style="max-width: 18rem;">

&#x20; <div class="card-header">Header</div>

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Dark card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

```



\--------------------------------



\### Default Bootstrap CSS Variables



Source: https://getbootstrap.com/docs/5.3/customize/css-variables



These variables are defined on the :root and \[data-bs-theme=light] selectors, making them available globally.



```css

:root,

\[data-bs-theme=light] {

&#x20; --bs-blue: #0d6efd;

&#x20; --bs-indigo: #6610f2;

&#x20; --bs-purple: #6f42c1;

&#x20; --bs-pink: #d63384;

&#x20; --bs-red: #dc3545;

&#x20; --bs-orange: #fd7e14;

&#x20; --bs-yellow: #ffc107;

&#x20; --bs-green: #198754;

&#x20; --bs-teal: #20c997;

&#x20; --bs-cyan: #0dcaf0;

&#x20; --bs-black: #000;

&#x20; --bs-white: #fff;

&#x20; --bs-gray: #6c757d;

&#x20; --bs-gray-dark: #343a40;

&#x20; --bs-gray-100: #f8f9fa;

&#x20; --bs-gray-200: #e9ecef;

&#x20; --bs-gray-300: #dee2e6;

&#x20; --bs-gray-400: #ced4da;

&#x20; --bs-gray-500: #adb5bd;

&#x20; --bs-gray-600: #6c757d;

&#x20; --bs-gray-700: #495057;

&#x20; --bs-gray-800: #343a40;

&#x20; --bs-gray-900: #212529;

&#x20; --bs-primary: #0d6efd;

&#x20; --bs-secondary: #6c757d;

&#x20; --bs-success: #198754;

&#x20; --bs-info: #0dcaf0;

&#x20; --bs-warning: #ffc107;

&#x20; --bs-danger: #dc3545;

&#x20; --bs-light: #f8f9fa;

&#x20; --bs-dark: #212529;

&#x20; --bs-primary-rgb: 13, 110, 253;

&#x20; --bs-secondary-rgb: 108, 117, 125;

&#x20; --bs-success-rgb: 25, 135, 84;

&#x20; --bs-info-rgb: 13, 202, 240;

&#x20; --bs-warning-rgb: 255, 193, 7;

&#x20; --bs-danger-rgb: 220, 53, 69;

&#x20; --bs-light-rgb: 248, 249, 250;

&#x20; --bs-dark-rgb: 33, 37, 41;

&#x20; --bs-primary-text-emphasis: #052c65;

&#x20; --bs-secondary-text-emphasis: #2b2f32;

&#x20; --bs-success-text-emphasis: #0a3622;

&#x20; --bs-info-text-emphasis: #055160;

&#x20; --bs-warning-text-emphasis: #664d03;

&#x20; --bs-danger-text-emphasis: #58151c;

&#x20; --bs-light-text-emphasis: #495057;

&#x20; --bs-dark-text-emphasis: #495057;

&#x20; --bs-primary-bg-subtle: #cfe2ff;

&#x20; --bs-secondary-bg-subtle: #e2e3e5;

&#x20; --bs-success-bg-subtle: #d1e7dd;

&#x20; --bs-info-bg-subtle: #cff4fc;

&#x20; --bs-warning-bg-subtle: #fff3cd;

&#x20; --bs-danger-bg-subtle: #f8d7da;

&#x20; --bs-light-bg-subtle: #fcfcfd;

&#x20; --bs-dark-bg-subtle: #ced4da;

&#x20; --bs-primary-border-subtle: #9ec5fe;

&#x20; --bs-secondary-border-subtle: #c4c8cb;

&#x20; --bs-success-border-subtle: #a3cfbb;

&#x20; --bs-info-border-subtle: #9eeaf9;

&#x20; --bs-warning-border-subtle: #ffe69c;

&#x20; --bs-danger-border-subtle: #f1aeb5;

&#x20; --bs-light-border-subtle: #e9ecef;

&#x20; --bs-dark-border-subtle: #adb5bd;

&#x20; --bs-white-rgb: 255, 255, 255;

&#x20; --bs-black-rgb: 0, 0, 0;

&#x20; --bs-font-sans-serif: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", "Noto Sans", "Liberation Sans", Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";

&#x20; --bs-font-monospace: SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;

&#x20; --bs-gradient: linear-gradient(180deg, rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0));

&#x20; --bs-body-font-family: var(--bs-font-sans-serif);

&#x20; --bs-body-font-size: 1rem;

&#x20; --bs-body-font-weight: 400;

&#x20; --bs-body-line-height: 1.5;

&#x20; --bs-body-color: #212529;

&#x20; --bs-body-color-rgb: 33, 37, 41;

&#x20; --bs-body-bg: #fff;

&#x20; --bs-body-bg-rgb: 255, 255, 255;

&#x20; --bs-emphasis-color: #000;

&#x20; --bs-emphasis-color-rgb: 0, 0, 0;

&#x20; --bs-secondary-color: rgba(33, 37, 41, 0.75);

&#x20; --bs-secondary-color-rgb: 33, 37, 41;

&#x20; --bs-secondary-bg: #e9ecef;

&#x20; --bs-secondary-bg-rgb: 233, 236, 239;

&#x20; --bs-tertiary-color: rgba(33, 37, 41, 0.5);

&#x20; --bs-tertiary-color-rgb: 33, 37, 41;

&#x20; --bs-tertiary-bg: #f8f9fa;

&#x20; --bs-tertiary-bg-rgb: 248, 249, 250;

&#x20; --bs-heading-color: inherit;

&#x20; --bs-link-color: #0d6efd;

&#x20; --bs-link-color-rgb: 13, 110, 253;

&#x20; --bs-link-decoration: underline;

&#x20; --bs-link-hover-color: #0a58ca;

&#x20; --bs-link-hover-color-rgb: 10, 88, 202;

&#x20; --bs-code-color: #d63384;

&#x20; --bs-highlight-color: #212529;

&#x20; --bs-highlight-bg: #fff3cd;

&#x20; --bs-border-width: 1px;

&#x20; --bs-border-style: solid;

&#x20; --bs-border-color: #dee2e6;

&#x20; --bs-border-color-translucent: rgba(0, 0, 0, 0.175);

&#x20; --bs-border-radius: 0.375rem;

&#x20; --bs-border-radius-sm: 0.25rem;

&#x20; --bs-border-radius-lg: 0.5rem;

&#x20; --bs-border-radius-xl: 1rem;

&#x20; --bs-border-radius-xxl: 2rem;

&#x20; --bs-border-radius-2xl: var(--bs-border-radius-xxl);

&#x20; --bs-border-radius-pill: 50rem;

&#x20; --bs-box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15);

&#x20; --bs-box-shadow-sm: 0 0.125rem 0.25rem rgba(0, 0, 0, 0.075);

&#x20; --bs-box-shadow-lg: 0 1rem 3rem rgba(0, 0, 0, 0.175);

&#x20; --bs-box-shadow-inset: inset 0 1px 2px rgba(0, 0, 0, 0.075);

&#x20; --bs-focus-ring-width: 0.25rem;

&#x20; --bs-focus-ring-opacity: 0.25;

&#x20; --bs-focus-ring-color: rgba(13, 110, 253, 0.25);

&#x20; --bs-form-valid-color: #198754;

&#x20; --bs-form-valid-border-color: #198754;

&#x20; --bs-form-invalid-color: #dc3545;

&#x20; --bs-form-invalid-border-color: #dc3545;

}

```



\--------------------------------



\### Apply text color utilities



Source: https://getbootstrap.com/docs/5.3/utilities/colors



Use these classes to set the text color of elements. Note that some classes like .text-warning or .text-info may require a contrasting background for visibility.



```html

<p class="text-primary">.text-primary</p>

<p class="text-primary-emphasis">.text-primary-emphasis</p>

<p class="text-secondary">.text-secondary</p>

<p class="text-secondary-emphasis">.text-secondary-emphasis</p>

<p class="text-success">.text-success</p>

<p class="text-success-emphasis">.text-success-emphasis</p>

<p class="text-danger">.text-danger</p>

<p class="text-danger-emphasis">.text-danger-emphasis</p>

<p class="text-warning bg-dark">.text-warning</p>

<p class="text-warning-emphasis">.text-warning-emphasis</p>

<p class="text-info bg-dark">.text-info</p>

<p class="text-info-emphasis">.text-info-emphasis</p>

<p class="text-light bg-dark">.text-light</p>

<p class="text-light-emphasis">.text-light-emphasis</p>

<p class="text-dark bg-white">.text-dark</p>

<p class="text-dark-emphasis">.text-dark-emphasis</p>



<p class="text-body">.text-body</p>

<p class="text-body-emphasis">.text-body-emphasis</p>

<p class="text-body-secondary">.text-body-secondary</p>

<p class="text-body-tertiary">.text-body-tertiary</p>



<p class="text-black bg-white">.text-black</p>

<p class="text-white bg-dark">.text-white</p>

<p class="text-black-50 bg-white">.text-black-50</p>

<p class="text-white-50 bg-dark">.text-white-50</p>

```



\--------------------------------



\### Listen for Toast Events



Source: https://getbootstrap.com/docs/5.3/components/toasts



Attach event listeners to toast elements to execute code when state changes occur.



```javascript

const myToastEl = document.getElementById('myToast')

myToastEl.addEventListener('hidden.bs.toast', () => {

&#x20; // do something...

})

```



\--------------------------------



\### Create Toggle Links with HTML



Source: https://getbootstrap.com/docs/5.3/components/buttons



Apply role="button" and data-bs-toggle="button" to anchor tags to create toggleable links. Disabled links require aria-disabled="true".



```html

<p class="d-inline-flex gap-1">

&#x20; <a href="#" class="btn" role="button" data-bs-toggle="button">Toggle link</a>

&#x20; <a href="#" class="btn active" role="button" data-bs-toggle="button" aria-pressed="true">Active toggle link</a>

&#x20; <a class="btn disabled" aria-disabled="true" role="button" data-bs-toggle="button">Disabled toggle link</a>

</p>

<p class="d-inline-flex gap-1">

&#x20; <a href="#" class="btn btn-primary" role="button" data-bs-toggle="button">Toggle link</a>

&#x20; <a href="#" class="btn btn-primary active" role="button" data-bs-toggle="button" aria-pressed="true">Active toggle link</a>

&#x20; <a class="btn btn-primary disabled" aria-disabled="true" role="button" data-bs-toggle="button">Disabled toggle link</a>

</p>

```



\--------------------------------



\### Configure Alert Sass Variables



Source: https://getbootstrap.com/docs/5.3/components/alerts



Sass variables that define the default spacing, borders, and typography for alerts.



```scss

$alert-padding-y:               $spacer;

$alert-padding-x:               $spacer;

$alert-margin-bottom:           1rem;

$alert-border-radius:           var(--#{$prefix}border-radius);

$alert-link-font-weight:        $font-weight-bold;

$alert-border-width:            var(--#{$prefix}border-width);

$alert-dismissible-padding-r:   $alert-padding-x \* 3; // 3x covers width of x plus default padding on either side

```



\--------------------------------



\### Columns with stretched link



Source: https://getbootstrap.com/docs/5.3/helpers/stretched-link



Demonstrates using the stretched link within a grid column structure that has been set to position: relative.



```html

<div class="row g-0 bg-body-secondary position-relative">

&#x20; <div class="col-md-6 mb-md-0 p-md-4">

&#x20;   <img src="..." class="w-100" alt="...">

&#x20; </div>

&#x20; <div class="col-md-6 p-4 ps-md-0">

&#x20;   <h5 class="mt-0">Columns with stretched link</h5>

&#x20;   <p>Another instance of placeholder content for this other custom component. It is intended to mimic what some real-world content would look like, and we’re using it here to give the component a bit of body and size.</p>

&#x20;   <a href="#" class="stretched-link">Go somewhere</a>

&#x20; </div>

</div>

```



\--------------------------------



\### Define button-outline-variant mixin



Source: https://getbootstrap.com/docs/5.3/components/buttons



Creates an outline button variant using the specified color.



```scss

@mixin button-outline-variant(

&#x20; $color,

&#x20; $color-hover: color-contrast($color),

&#x20; $active-background: $color,

&#x20; $active-border: $color,

&#x20; $active-color: color-contrast($active-background)

) {

&#x20; --#{$prefix}btn-color: #{$color};

&#x20; --#{$prefix}btn-border-color: #{$color};

&#x20; --#{$prefix}btn-hover-color: #{$color-hover};

&#x20; --#{$prefix}btn-hover-bg: #{$active-background};

&#x20; --#{$prefix}btn-hover-border-color: #{$active-border};

&#x20; --#{$prefix}btn-focus-shadow-rgb: #{to-rgb($color)};

&#x20; --#{$prefix}btn-active-color: #{$active-color};

&#x20; --#{$prefix}btn-active-bg: #{$active-background};

&#x20; --#{$prefix}btn-active-border-color: #{$active-border};

&#x20; --#{$prefix}btn-active-shadow: #{$btn-active-box-shadow};

&#x20; --#{$prefix}btn-disabled-color: #{$color};

&#x20; --#{$prefix}btn-disabled-bg: transparent;

&#x20; --#{$prefix}btn-disabled-border-color: #{$color};

&#x20; --#{$gradient: none;

}

```



\--------------------------------



\### Range Input with Output Value



Source: https://getbootstrap.com/docs/5.3/forms/range



Displaying the current range value using an output element and JavaScript event listener.



```html

<label for="range4" class="form-label">Example range</label>

<input type="range" class="form-range" min="0" max="100" value="50" id="range4">

<output for="range4" id="rangeValue" aria-hidden="true"></output>



<script>

&#x20; // This is an example script, please modify as needed

&#x20; const rangeInput = document.getElementById('range4');

&#x20; const rangeOutput = document.getElementById('rangeValue');



&#x20; // Set initial value

&#x20; rangeOutput.textContent = rangeInput.value;



&#x20; rangeInput.addEventListener('input', function() {

&#x20;   rangeOutput.textContent = this.value;

&#x20; });

</script>

```



\--------------------------------



\### Sass Link Utilities Configuration



Source: https://getbootstrap.com/docs/5.3/utilities/link



Defines link-related utility classes for opacity, offset, and underline within the Bootstrap Sass utilities API.



```scss

"link-opacity": (

&#x20; css-var: true,

&#x20; class: link-opacity,

&#x20; state: hover,

&#x20; values: (

&#x20;   10: .1,

&#x20;   25: .25,

&#x20;   50: .5,

&#x20;   75: .75,

&#x20;   100: 1

&#x20; )

),

"link-offset": (

&#x20; property: text-underline-offset,

&#x20; class: link-offset,

&#x20; state: hover,

&#x20; values: (

&#x20;   1: .125em,

&#x20;   2: .25em,

&#x20;   3: .375em,

&#x20; )

),

"link-underline": (

&#x20; property: text-decoration-color,

&#x20; class: link-underline,

&#x20; local-vars: (

&#x20;   "link-underline-opacity": 1

&#x20; ),

&#x20; values: map-merge(

&#x20;   $utilities-links-underline,

&#x20;   (

&#x20;     null: rgba(var(--#{$prefix}link-color-rgb), var(--#{$prefix}link-underline-opacity, 1)),

&#x20;   )

&#x20; )

),

"link-underline-opacity": (

&#x20; css-var: true,

&#x20; class: link-underline-opacity,

&#x20; state: hover,

&#x20; values: (

&#x20;   0: 0,

&#x20;   10: .1,

&#x20;   25: .25,

&#x20;   50: .5,

&#x20;   75: .75,

&#x20;   100: 1

&#x20; ),

),

```



\--------------------------------



\### Define button-variant mixin



Source: https://getbootstrap.com/docs/5.3/components/buttons



Creates a solid button variant based on background, border, and color parameters.



```scss

@mixin button-variant(

&#x20; $background,

&#x20; $border,

&#x20; $color: color-contrast($background),

&#x20; $hover-background: if($color == $color-contrast-light, shade-color($background, $btn-hover-bg-shade-amount), tint-color($background, $btn-hover-bg-tint-amount)),

&#x20; $hover-border: if($color == $color-contrast-light, shade-color($border, $btn-hover-border-shade-amount), tint-color($border, $btn-hover-border-tint-amount)),

&#x20; $hover-color: color-contrast($hover-background),

&#x20; $active-background: if($color == $color-contrast-light, shade-color($background, $btn-active-bg-shade-amount), tint-color($background, $btn-active-bg-tint-amount)),

&#x20; $active-border: if($color == $color-contrast-light, shade-color($border, $btn-active-border-shade-amount), tint-color($border, $btn-active-border-tint-amount)),

&#x20; $active-color: color-contrast($active-background),

&#x20; $disabled-background: $background,

&#x20; $disabled-border: $border,

&#x20; $disabled-color: color-contrast($disabled-background)

) {

&#x20; --#{$prefix}btn-color: #{$color};

&#x20; --#{$prefix}btn-bg: #{$background};

&#x20; --#{$prefix}btn-border-color: #{$border};

&#x20; --#{$prefix}btn-hover-color: #{$hover-color};

&#x20; --#{$prefix}btn-hover-bg: #{$hover-background};

&#x20; --#{$prefix}btn-hover-border-color: #{$hover-border};

&#x20; --#{$prefix}btn-focus-shadow-rgb: #{to-rgb(mix($color, $border, 15%))};

&#x20; --#{$prefix}btn-active-color: #{$active-color};

&#x20; --#{$prefix}btn-active-bg: #{$active-background};

&#x20; --#{$prefix}btn-active-border-color: #{$active-border};

&#x20; --#{$prefix}btn-active-shadow: #{$btn-active-box-shadow};

&#x20; --#{$prefix}btn-disabled-color: #{$disabled-color};

&#x20; --#{$prefix}btn-disabled-bg: #{$disabled-background};

&#x20; --#{$prefix}btn-disabled-border-color: #{$disabled-border};

}

```



\--------------------------------



\### Block Display Utilities



Source: https://getbootstrap.com/docs/5.3/utilities/display



Applies the block display property to elements.



```html

<span class="d-block p-2 text-bg-primary">d-block</span>

<span class="d-block p-2 text-bg-dark">d-block</span>

```



\--------------------------------



\### Apply order classes to grid columns



Source: https://getbootstrap.com/docs/5.3/layout/columns



Use numbered order classes to control the visual sequence of columns within a row.



```html

<div class="container text-center">

&#x20; <div class="row">

&#x20;   <div class="col">

&#x20;     First in DOM, no order applied

&#x20;   </div>

&#x20;   <div class="col order-5">

&#x20;     Second in DOM, with a larger order

&#x20;   </div>

&#x20;   <div class="col order-1">

&#x20;     Third in DOM, with an order of 1

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Listen for tab shown events



Source: https://getbootstrap.com/docs/5.3/components/list-group



Attach event listeners to tab elements to handle logic after a tab has been shown.



```javascript

const tabElms = document.querySelectorAll('a\[data-bs-toggle="list"]')

tabElms.forEach(tabElm => {

&#x20; tabElm.addEventListener('shown.bs.tab', event => {

&#x20;   event.target // newly activated tab

&#x20;   event.relatedTarget // previous active tab

&#x20; })

})

```



\--------------------------------



\### Define Z-index Utilities API



Source: https://getbootstrap.com/docs/5.3/utilities/z-index



Configures the z-index utility classes within the Bootstrap utilities API.



```scss

"z-index": (

&#x20; property: z-index,

&#x20; class: z,

&#x20; values: $zindex-levels,

)

```



\--------------------------------



\### Compiled Bootstrap Directory Structure



Source: https://getbootstrap.com/docs/5.3/getting-started/contents



The file structure of the compiled Bootstrap distribution, containing CSS and JS assets.



```text

bootstrap/

├── css/

│   ├── bootstrap-grid.css

│   ├── bootstrap-grid.css.map

│   ├── bootstrap-grid.min.css

│   ├── bootstrap-grid.min.css.map

│   ├── bootstrap-grid.rtl.css

│   ├── bootstrap-grid.rtl.css.map

│   ├── bootstrap-grid.rtl.min.css

│   ├── bootstrap-grid.rtl.min.css.map

│   ├── bootstrap-reboot.css

│   ├── bootstrap-reboot.css.map

│   ├── bootstrap-reboot.min.css

│   ├── bootstrap-reboot.min.css.map

│   ├── bootstrap-reboot.rtl.css

│   ├── bootstrap-reboot.rtl.css.map

│   ├── bootstrap-reboot.rtl.min.css

│   ├── bootstrap-reboot.rtl.min.css.map

│   ├── bootstrap-utilities.css

│   ├── bootstrap-utilities.css.map

│   ├── bootstrap-utilities.min.css

│   ├── bootstrap-utilities.min.css.map

│   ├── bootstrap-utilities.rtl.css

│   ├── bootstrap-utilities.rtl.css.map

│   ├── bootstrap-utilities.rtl.min.css

│   ├── bootstrap-utilities.rtl.min.css.map

│   ├── bootstrap.css

│   ├── bootstrap.css.map

│   ├── bootstrap.min.css

│   ├── bootstrap.min.css.map

│   ├── bootstrap.rtl.css

│   ├── bootstrap.rtl.css.map

│   ├── bootstrap.rtl.min.css

│   └── bootstrap.rtl.min.css.map

└── js/

&#x20;   ├── bootstrap.bundle.js

&#x20;   ├── bootstrap.bundle.js.map

&#x20;   ├── bootstrap.bundle.min.js

&#x20;   ├── bootstrap.bundle.min.js.map

&#x20;   ├── bootstrap.esm.js

&#x20;   ├── bootstrap.esm.js.map

&#x20;   ├── bootstrap.esm.min.js

&#x20;   ├── bootstrap.esm.min.js.map

&#x20;   ├── bootstrap.js

&#x20;   ├── bootstrap.js.map

&#x20;   ├── bootstrap.min.js

&#x20;   └── bootstrap.min.js.map

```



\--------------------------------



\### Sizing cards with grid markup



Source: https://getbootstrap.com/docs/5.3/components/card



Wrap cards in grid columns and rows to control their layout and width within a responsive grid system.



```html

<div class="row">

&#x20; <div class="col-sm-6 mb-3 mb-sm-0">

&#x20;   <div class="card">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Special title treatment</h5>

&#x20;       <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>

&#x20;       <a href="#" class="btn btn-primary">Go somewhere</a>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col-sm-6">

&#x20;   <div class="card">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Special title treatment</h5>

&#x20;       <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>

&#x20;       <a href="#" class="btn btn-primary">Go somewhere</a>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Define Modal CSS Variables



Source: https://getbootstrap.com/docs/5.3/components/modal



Local CSS variables for modal and backdrop styling defined in scss/\_modal.scss.



```scss

\--#{$prefix}modal-zindex: #{$zindex-modal};

\--#{$prefix}modal-width: #{$modal-md};

\--#{$prefix}modal-padding: #{$modal-inner-padding};

\--#{$prefix}modal-margin: #{$modal-dialog-margin};

\--#{$prefix}modal-color: #{$modal-content-color};

\--#{$prefix}modal-bg: #{$modal-content-bg};

\--#{$prefix}modal-border-color: #{$modal-content-border-color};

\--#{$prefix}modal-border-width: #{$modal-content-border-width};

\--#{$prefix}modal-border-radius: #{$modal-content-border-radius};

\--#{$prefix}modal-box-shadow: #{$modal-content-box-shadow-xs};

\--#{$prefix}modal-inner-border-radius: #{$modal-content-inner-border-radius};

\--#{$prefix}modal-header-padding-x: #{$modal-header-padding-x};

\--#{$prefix}modal-header-padding-y: #{$modal-header-padding-y};

\--#{$prefix}modal-header-padding: #{$modal-header-padding}; // Todo in v6: Split this padding into x and y

\--#{$prefix}modal-header-border-color: #{$modal-header-border-color};

\--#{$prefix}modal-header-border-width: #{$modal-header-border-width};

\--#{$prefix}modal-title-line-height: #{$modal-title-line-height};

\--#{$prefix}modal-footer-gap: #{$modal-footer-margin-between};

\--#{$prefix}modal-footer-bg: #{$modal-footer-bg};

\--#{$prefix}modal-footer-border-color: #{$modal-footer-border-color};

\--#{$prefix}modal-footer-border-width: #{$modal-footer-border-width};

```



```scss

\--#{$prefix}backdrop-zindex: #{$zindex-modal-backdrop};

\--#{$prefix}backdrop-bg: #{$modal-backdrop-bg};

\--#{$prefix}backdrop-opacity: #{$modal-backdrop-opacity};

```



\--------------------------------



\### Override existing utility classes



Source: https://getbootstrap.com/docs/5.3/utilities/api



Use the same key in the $utilities map to override default utility settings.



```scss

$utilities: (

&#x20; "overflow": (

&#x20;   responsive: true,

&#x20;   property: overflow,

&#x20;   values: visible hidden scroll auto,

&#x20; ),

);

```



\--------------------------------



\### Configure Offcanvas CSS Variables



Source: https://getbootstrap.com/docs/5.3/components/offcanvas



Local CSS variables defined in scss/\_offcanvas.scss for real-time customization of the offcanvas component.



```scss

\--#{$prefix}offcanvas-zindex: #{$zindex-offcanvas};

\--#{$prefix}offcanvas-width: #{$offcanvas-horizontal-width};

\--#{$prefix}offcanvas-height: #{$offcanvas-vertical-height};

\--#{$prefix}offcanvas-padding-x: #{$offcanvas-padding-x};

\--#{$prefix}offcanvas-padding-y: #{$offcanvas-padding-y};

\--#{$prefix}offcanvas-color: #{$offcanvas-color};

\--#{$prefix}offcanvas-bg: #{$offcanvas-bg-color};

\--#{$prefix}offcanvas-border-width: #{$offcanvas-border-width};

\--#{$prefix}offcanvas-border-color: #{$offcanvas-border-color};

\--#{$prefix}offcanvas-box-shadow: #{$offcanvas-box-shadow};

\--#{$prefix}offcanvas-transition: #{transform $offcanvas-transition-duration ease-in-out};

\--#{$prefix}offcanvas-title-line-height: #{$offcanvas-title-line-height};

```



\--------------------------------



\### Configure Form Label Sass Variables



Source: https://getbootstrap.com/docs/5.3/forms/form-control



Variables for customizing the appearance and spacing of form labels.



```scss

$form-label-margin-bottom:              .5rem;

$form-label-font-size:                  null;

$form-label-font-style:                 null;

$form-label-font-weight:                null;

$form-label-color:                      null;

```



\--------------------------------



\### Responsive Hiding Utilities



Source: https://getbootstrap.com/docs/5.3/utilities/display



Hides elements based on screen size using responsive display classes.



```html

<div class="d-lg-none">hide on lg and wider screens</div>

<div class="d-none d-lg-block">hide on screens smaller than lg</div>

```



\--------------------------------



\### Activate Tabs Programmatically



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



Use the Tab instance to show specific tabs programmatically by selecting the trigger element.



```javascript

const triggerEl = document.querySelector('#myTab button\[data-bs-target="#profile"]')

bootstrap.Tab.getInstance(triggerEl).show() // Select tab by name



const triggerFirstTabEl = document.querySelector('#myTab li:first-child button')

bootstrap.Tab.getInstance(triggerFirstTabEl).show() // Select first tab

```



\--------------------------------



\### Modal Methods



Source: https://getbootstrap.com/docs/5.3/components/modal



Methods available on the modal instance to control its state.



```APIDOC

\## Modal Methods



\### Methods

\- \*\*show(relatedTarget)\*\* - Manually opens a modal. Accepts an optional DOM element as an argument.

\- \*\*hide()\*\* - Manually hides a modal.

\- \*\*toggle()\*\* - Manually toggles a modal.

\- \*\*handleUpdate()\*\* - Manually readjust the modal's position if the height changes while open.

\- \*\*dispose()\*\* - Destroys an element's modal and removes stored data.

\- \*\*getInstance(element)\*\* - Static method to get the modal instance associated with a DOM element.

\- \*\*getOrCreateInstance(element)\*\* - Static method to get the modal instance or create a new one if it wasn't initialized.

```



\--------------------------------



\### Sass Utilities API Configuration



Source: https://getbootstrap.com/docs/5.3/utilities/object-fit



The object-fit utilities are defined within the Bootstrap utilities API in the scss/\_utilities.scss file.



```scss

"object-fit": (

&#x20; responsive: true,

&#x20; property: object-fit,

&#x20; values: (

&#x20;   contain: contain,

&#x20;   cover: cover,

&#x20;   fill: fill,

&#x20;   scale: scale-down,

&#x20;   none: none,

&#x20; )

),

```



\--------------------------------



\### Position badges on elements



Source: https://getbootstrap.com/docs/5.3/components/badge



Use positioning utilities to place badges in the corner of buttons or links.



```html

<button type="button" class="btn btn-primary position-relative">

&#x20; Inbox

&#x20; <span class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger">

&#x20;   99+

&#x20;   <span class="visually-hidden">unread messages</span>

&#x20; </span>

</button>

```



```html

<button type="button" class="btn btn-primary position-relative">

&#x20; Profile

&#x20; <span class="position-absolute top-0 start-100 translate-middle p-2 bg-danger border border-light rounded-circle">

&#x20;   <span class="visually-hidden">New alerts</span>

&#x20; </span>

</button>

```



\--------------------------------



\### Create a three-column card grid



Source: https://getbootstrap.com/docs/5.3/components/card



Uses row-cols-md-3 to force a three-column layout on medium screens, causing extra cards to wrap.



```html

<div class="row row-cols-1 row-cols-md-3 g-4">

&#x20; <div class="col">

&#x20;   <div class="card">

&#x20;     <img src="..." class="card-img-top" alt="...">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col">

&#x20;   <div class="card">

&#x20;     <img src="..." class="card-img-top" alt="...">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col">

&#x20;   <div class="card">

&#x20;     <img src="..." class="card-img-top" alt="...">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content.</p>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col">

&#x20;   <div class="card">

&#x20;     <img src="..." class="card-img-top" alt="...">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Apply visual order to flex items



Source: https://getbootstrap.com/docs/5.3/utilities/flex



Use order classes to change the display sequence of flex items within a container.



```html

<div class="d-flex flex-nowrap">

&#x20; <div class="order-3 p-2">First flex item</div>

&#x20; <div class="order-2 p-2">Second flex item</div>

&#x20; <div class="order-1 p-2">Third flex item</div>

</div>

```



\--------------------------------



\### Generate Pseudo-class States



Source: https://getbootstrap.com/docs/5.3/utilities/api



Use the state option to generate pseudo-class variations like :hover or :focus.



```scss

$utilities: (

&#x20; "opacity": (

&#x20;   property: opacity,

&#x20;   class: opacity,

&#x20;   state: hover,

&#x20;   values: (

&#x20;     0: 0,

&#x20;     25: .25,

&#x20;     50: .5,

&#x20;     75: .75,

&#x20;     100: 1,

&#x20;   )

&#x20; )

);

```



```css

.opacity-0-hover:hover { opacity: 0 !important; }

.opacity-25-hover:hover { opacity: .25 !important; }

.opacity-50-hover:hover { opacity: .5 !important; }

.opacity-75-hover:hover { opacity: .75 !important; }

.opacity-100-hover:hover { opacity: 1 !important; }

```



\--------------------------------



\### Implement Accessible Toast Markup



Source: https://getbootstrap.com/docs/5.3/components/toasts



Basic structure for a toast component using aria-live regions to ensure screen reader compatibility.



```html

<div class="toast" role="alert" aria-live="polite" aria-atomic="true" data-bs-delay="10000">

&#x20; <div role="alert" aria-live="assertive" aria-atomic="true">...</div>

</div>

```



\--------------------------------



\### Configure display heading variables



Source: https://getbootstrap.com/docs/5.3/content/typography



Customize display heading sizes, font family, style, weight, and line height using these Sass variables.



```scss

$display-font-sizes: (

&#x20; 1: 5rem,

&#x20; 2: 4.5rem,

&#x20; 3: 4rem,

&#x20; 4: 3.5rem,

&#x20; 5: 3rem,

&#x20; 6: 2.5rem

);



$display-font-family: null;

$display-font-style:  null;

$display-font-weight: 300;

$display-line-height: $headings-line-height;

```



\--------------------------------



\### Define custom component base and modifier classes



Source: https://getbootstrap.com/docs/5.3/customize/components



Uses a base class for shared styles and modifier classes for variant-specific styling.



```scss

// Base class

.callout {}



// Modifier classes

.callout-info {}

.callout-warning {}

.callout-danger {}

```



\--------------------------------



\### Implement an accordion with the flush variant



Source: https://getbootstrap.com/docs/5.3/components/accordion



Use the .accordion-flush class on the container to remove borders and rounded corners. Ensure each item uses unique IDs for the collapse targets.



```html

<div class="accordion accordion-flush" id="accordionFlushExample">

&#x20; <div class="accordion-item">

&#x20;   <h2 class="accordion-header">

&#x20;     <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#flush-collapseOne" aria-expanded="false" aria-controls="flush-collapseOne">

&#x20;       Accordion Item #1

&#x20;     </button>

&#x20;   </h2>

&#x20;   <div id="flush-collapseOne" class="accordion-collapse collapse" data-bs-parent="#accordionFlushExample">

&#x20;     <div class="accordion-body">Placeholder content for this accordion, which is intended to demonstrate the <code>.accordion-flush</code> class. This is the first item’s accordion body.</div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="accordion-item">

&#x20;   <h2 class="accordion-header">

&#x20;     <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#flush-collapseTwo" aria-expanded="false" aria-controls="flush-collapseTwo">

&#x20;       Accordion Item #2

&#x20;     </button>

&#x20;   </h2>

&#x20;   <div id="flush-collapseTwo" class="accordion-collapse collapse" data-bs-parent="#accordionFlushExample">

&#x20;     <div class="accordion-body">Placeholder content for this accordion, which is intended to demonstrate the <code>.accordion-flush</code> class. This is the second item’s accordion body. Let’s imagine this being filled with some actual content.</div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="accordion-item">

&#x20;   <h2 class="accordion-header">

&#x20;     <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#flush-collapseThree" aria-expanded="false" aria-controls="flush-collapseThree">

&#x20;       Accordion Item #3

&#x20;     </button>

&#x20;   </h2>

&#x20;   <div id="flush-collapseThree" class="accordion-collapse collapse" data-bs-parent="#accordionFlushExample">

&#x20;     <div class="accordion-body">Placeholder content for this accordion, which is intended to demonstrate the <code>.accordion-flush</code> class. This is the third item’s accordion body. Nothing more exciting happening here in terms of content, but just filling up the space to make it look, at least at first glance, a bit more representative of how this would look in a real-world application.</div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Stacking Toasts with Toast Container



Source: https://getbootstrap.com/docs/5.3/components/toasts



Use a toast container to vertically stack multiple toast elements with automatic spacing.



```html

<div class="toast-container position-static">

&#x20; <div class="toast" role="alert" aria-live="assertive" aria-atomic="true">

&#x20;   <div class="toast-header">

&#x20;     <img src="..." class="rounded me-2" alt="...">

&#x20;     <strong class="me-auto">Bootstrap</strong>

&#x20;     <small class="text-body-secondary">just now</small>

&#x20;     <button type="button" class="btn-close" data-bs-dismiss="toast" aria-label="Close"></button>

&#x20;   </div>

&#x20;   <div class="toast-body">

&#x20;     See? Just like this.

&#x20;   </div>

&#x20; </div>



&#x20; <div class="toast" role="alert" aria-live="assertive" aria-atomic="true">

&#x20;   <div class="toast-header">

&#x20;     <img src="..." class="rounded me-2" alt="...">

&#x20;     <strong class="me-auto">Bootstrap</strong>

&#x20;     <small class="text-body-secondary">2 seconds ago</small>

&#x20;     <button type="button" class="btn-close" data-bs-dismiss="toast" aria-label="Close"></button>

&#x20;   </div>

&#x20;   <div class="toast-body">

&#x20;     Heads up, toasts will stack automatically

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Create horizontal layouts with hstack



Source: https://getbootstrap.com/docs/5.3/helpers/stacks



Use the hstack class for horizontal layouts where items are vertically centered and take up necessary width.



```html

<div class="hstack gap-3">

&#x20; <div class="p-2">First item</div>

&#x20; <div class="p-2">Second item</div>

&#x20; <div class="p-2">Third item</div>

</div>

```



```html

<div class="hstack gap-3">

&#x20; <div class="p-2">First item</div>

&#x20; <div class="p-2 ms-auto">Second item</div>

&#x20; <div class="p-2">Third item</div>

</div>

```



```html

<div class="hstack gap-3">

&#x20; <div class="p-2">First item</div>

&#x20; <div class="p-2 ms-auto">Second item</div>

&#x20; <div class="vr"></div>

&#x20; <div class="p-2">Third item</div>

</div>

```



\--------------------------------



\### Override background opacity inline



Source: https://getbootstrap.com/docs/5.3/utilities/background



Demonstrates changing background opacity by overriding the --bs-bg-opacity CSS variable via inline styles.



```html

<div class="bg-success p-2 text-white">This is default success background</div>

<div class="bg-success p-2" style="--bs-bg-opacity: .5;">This is 50% opacity success background</div>

```



\--------------------------------



\### Create a custom aspect ratio



Source: https://getbootstrap.com/docs/5.3/helpers/ratio



Override the --bs-aspect-ratio CSS variable on the parent element to define a custom aspect ratio.



```html

<div class="ratio" style="--bs-aspect-ratio: 50%;">

&#x20; <div>2x1</div>

</div>

```



\--------------------------------



\### Large Button Dropdown Sizing



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



Implementation of large button dropdowns and split button dropdowns using the btn-lg class.



```html

<!-- Large button groups (default and split) -->

<div class="btn-group">

&#x20; <button class="btn btn-secondary btn-lg dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   Large button

&#x20; </button>

&#x20; <ul class="dropdown-menu">

&#x20;   ...

&#x20; </ul>

</div>

<div class="btn-group">

&#x20; <button class="btn btn-secondary btn-lg" type="button">

&#x20;   Large split button

&#x20; </button>

&#x20; <button type="button" class="btn btn-lg btn-secondary dropdown-toggle dropdown-toggle-split" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   <span class="visually-hidden">Toggle Dropdown</span>

&#x20; </button>

&#x20; <ul class="dropdown-menu">

&#x20;   ...

&#x20; </ul>

</div>

```



\--------------------------------



\### Implement Tabbable Panes with Bootstrap



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



Use the data-bs-toggle='tab' attribute on navigation buttons to control the visibility of associated tab-pane elements.



```html

<ul class="nav nav-tabs" id="myTab" role="tablist">

&#x20; <li class="nav-item" role="presentation">

&#x20;   <button class="nav-link active" id="home-tab" data-bs-toggle="tab" data-bs-target="#home-tab-pane" type="button" role="tab" aria-controls="home-tab-pane" aria-selected="true">Home</button>

&#x20; </li>

&#x20; <li class="nav-item" role="presentation">

&#x20;   <button class="nav-link" id="profile-tab" data-bs-toggle="tab" data-bs-target="#profile-tab-pane" type="button" role="tab" aria-controls="profile-tab-pane" aria-selected="false">Profile</button>

&#x20; </li>

&#x20; <li class="nav-item" role="presentation">

&#x20;   <button class="nav-link" id="contact-tab" data-bs-toggle="tab" data-bs-target="#contact-tab-pane" type="button" role="tab" aria-controls="contact-tab-pane" aria-selected="false">Contact</button>

&#x20; </li>

&#x20; <li class="nav-item" role="presentation">

&#x20;   <button class="nav-link" id="disabled-tab" data-bs-toggle="tab" data-bs-target="#disabled-tab-pane" type="button" role="tab" aria-controls="disabled-tab-pane" aria-selected="false" disabled>Disabled</button>

&#x20; </li>

</ul>

<div class="tab-content" id="myTabContent">

&#x20; <div class="tab-pane fade show active" id="home-tab-pane" role="tabpanel" aria-labelledby="home-tab" tabindex="0">...</div>

&#x20; <div class="tab-pane fade" id="profile-tab-pane" role="tabpanel" aria-labelledby="profile-tab" tabindex="0">...</div>

&#x20; <div class="tab-pane fade" id="contact-tab-pane" role="tabpanel" aria-labelledby="contact-tab" tabindex="0">...</div>

&#x20; <div class="tab-pane fade" id="disabled-tab-pane" role="tabpanel" aria-labelledby="disabled-tab" tabindex="0">...</div>

</div>

```



\--------------------------------



\### Basic Focus Ring Usage



Source: https://getbootstrap.com/docs/5.3/helpers/focus-ring



Apply the .focus-ring class to an element to replace the default browser outline with a customizable box-shadow.



```html

<a href="#" class="d-inline-flex focus-ring py-1 px-2 text-decoration-none border rounded-2">

&#x20; Custom focus ring

</a>

```



\--------------------------------



\### Apply custom property with RFS mixin



Source: https://getbootstrap.com/docs/5.3/getting-started/rfs



Shows how to pass any CSS property to the rfs() mixin.



```scss

.selector {

&#x20; @include rfs(4rem, border-radius);

}

```



\--------------------------------



\### Sass utilities API configuration



Source: https://getbootstrap.com/docs/5.3/utilities/interactions



Interaction utilities are defined within the Bootstrap utilities API in scss/\_utilities.scss.



```scss

"user-select": (

&#x20; property: user-select,

&#x20; values: all auto none

),

"pointer-events": (

&#x20; property: pointer-events,

&#x20; class: pe,

&#x20; values: none auto,

),

```



\--------------------------------



\### Create a list group with badges



Source: https://getbootstrap.com/docs/5.3/components/list-group



Use flexbox utilities to align badges within list group items for displaying counts or status indicators.



```html

<ul class="list-group">

&#x20; <li class="list-group-item d-flex justify-content-between align-items-center">

&#x20;   A list item

&#x20;   <span class="badge text-bg-primary rounded-pill">14</span>

&#x20; </li>

&#x20; <li class="list-group-item d-flex justify-content-between align-items-center">

&#x20;   A second list item

&#x20;   <span class="badge text-bg-primary rounded-pill">2</span>

&#x20; </li>

&#x20; <li class="list-group-item d-flex justify-content-between align-items-center">

&#x20;   A third list item

&#x20;   <span class="badge text-bg-primary rounded-pill">1</span>

&#x20; </li>

</ul>

```



\--------------------------------



\### Apply vertical gutters with .gy-\*



Source: https://getbootstrap.com/docs/5.3/layout/gutters



Use .gy-\* classes to control vertical spacing between wrapped columns. Wrap the row in .overflow-hidden if vertical gutters cause page overflow.



```html

<div class="container overflow-hidden text-center">

&#x20; <div class="row gy-5">

&#x20;   <div class="col-6">

&#x20;     <div class="p-3">Custom column padding</div>

&#x20;   </div>

&#x20;   <div class="col-6">

&#x20;     <div class="p-3">Custom column padding</div>

&#x20;   </div>

&#x20;   <div class="col-6">

&#x20;     <div class="p-3">Custom column padding</div>

&#x20;   </div>

&#x20;   <div class="col-6">

&#x20;     <div class="p-3">Custom column padding</div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Define Theme Color Variables



Source: https://getbootstrap.com/docs/5.3/utilities/background



Variables mapping theme roles to base color variables.



```scss

$primary:       $blue;

$secondary:     $gray-600;

$success:       $green;

$info:          $cyan;

$warning:       $yellow;

$danger:        $red;

$light:         $gray-100;

$dark:          $gray-900;

```



\--------------------------------



\### Create a grid of cards with footers



Source: https://getbootstrap.com/docs/5.3/components/card



Extends the equal height card grid by adding a card-footer element to each card.



```html

<div class="row row-cols-1 row-cols-md-3 g-4">

&#x20; <div class="col">

&#x20;   <div class="card h-100">

&#x20;     <img src="..." class="card-img-top" alt="...">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>

&#x20;     </div>

&#x20;     <div class="card-footer">

&#x20;       <small class="text-body-secondary">Last updated 3 mins ago</small>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col">

&#x20;   <div class="card h-100">

&#x20;     <img src="..." class="card-img-top" alt="...">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This card has supporting text below as a natural lead-in to additional content.</p>

&#x20;     </div>

&#x20;     <div class="card-footer">

&#x20;       <small class="text-body-secondary">Last updated 3 mins ago</small>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col">

&#x20;   <div class="card h-100">

&#x20;     <img src="..." class="card-img-top" alt="...">

&#x20;     <div class="card-body">

&#x20;       <h5 class="card-title">Card title</h5>

&#x20;       <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.</p>

&#x20;     </div>

&#x20;     <div class="card-footer">

&#x20;       <small class="text-body-secondary">Last updated 3 mins ago</small>

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Use form-control-plaintext for plain text inputs



Source: https://getbootstrap.com/docs/5.3/forms/form-control



Replace .form-control with .form-control-plaintext to remove default field styling while maintaining layout spacing.



```html

<div class="mb-3 row">

&#x20; <label for="staticEmail" class="col-sm-2 col-form-label">Email</label>

&#x20; <div class="col-sm-10">

&#x20;   <input type="text" readonly class="form-control-plaintext" id="staticEmail" value="email@example.com">

&#x20; </div>

</div>

<div class="mb-3 row">

&#x20; <label for="inputPassword" class="col-sm-2 col-form-label">Password</label>

&#x20; <div class="col-sm-10">

&#x20;   <input type="password" class="form-control" id="inputPassword">

&#x20; </div>

</div>

```



```html

<form class="row g-3">

&#x20; <div class="col-auto">

&#x20;   <label for="staticEmail2" class="visually-hidden">Email</label>

&#x20;   <input type="text" readonly class="form-control-plaintext" id="staticEmail2" value="email@example.com">

&#x20; </div>

&#x20; <div class="col-auto">

&#x20;   <label for="inputPassword2" class="visually-hidden">Password</label>

&#x20;   <input type="password" class="form-control" id="inputPassword2" placeholder="Password">

&#x20; </div>

&#x20; <div class="col-auto">

&#x20;   <button type="submit" class="btn btn-primary mb-3">Confirm identity</button>

&#x20; </div>

</form>

```



\--------------------------------



\### Add buttons to navbar forms



Source: https://getbootstrap.com/docs/5.3/components/navbar



Supports multiple button types and sizes, with alignment utilities available for mixed-size elements.



```html

<nav class="navbar bg-body-tertiary">

&#x20; <form class="container-fluid justify-content-start">

&#x20;   <button class="btn btn-outline-success me-2" type="button">Main button</button>

&#x20;   <button class="btn btn-sm btn-outline-secondary" type="button">Smaller button</button>

&#x20; </form>

</nav>

```



\--------------------------------



\### Format inline code



Source: https://getbootstrap.com/docs/5.3/content/reboot



Use the <code> tag for inline code snippets. Ensure HTML angle brackets are escaped.



```html

For example, <code>\&lt;section\&gt;</code> should be wrapped as inline.

```



\--------------------------------



\### Create a complex card layout



Source: https://getbootstrap.com/docs/5.3/components/card



Combine images, text, and list groups within a single card to create a comprehensive layout.



```html

<div class="card" style="width: 18rem;">

&#x20; <img src="..." class="card-img-top" alt="...">

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Card title</h5>

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

&#x20; <ul class="list-group list-group-flush">

&#x20;   <li class="list-group-item">An item</li>

&#x20;   <li class="list-group-item">A second item</li>

&#x20;   <li class="list-group-item">A third item</li>

&#x20; </ul>

&#x20; <div class="card-body">

&#x20;   <a href="#" class="card-link">Card link</a>

&#x20;   <a href="#" class="card-link">Another link</a>

&#x20; </div>

</div>

```



\--------------------------------



\### Sass Utilities API Configuration



Source: https://getbootstrap.com/docs/5.3/utilities/text



Definitions for text-related utility classes within the Bootstrap utilities API.



```scss

"font-family": (

&#x20; property: font-family,

&#x20; class: font,

&#x20; values: (monospace: var(--#{$prefix}font-monospace))

),

"font-size": (

&#x20; rfs: true,

&#x20; property: font-size,

&#x20; class: fs,

&#x20; values: $font-sizes

),

"font-style": (

&#x20; property: font-style,

&#x20; class: fst,

&#x20; values: italic normal

),

"font-weight": (

&#x20; property: font-weight,

&#x20; class: fw,

&#x20; values: (

&#x20;   lighter: $font-weight-lighter,

&#x20;   light: $font-weight-light,

&#x20;   normal: $font-weight-normal,

&#x20;   medium: $font-weight-medium,

&#x20;   semibold: $font-weight-semibold,

&#x20;   bold: $font-weight-bold,

&#x20;   bolder: $font-weight-bolder

&#x20; )

),

"line-height": (

&#x20; property: line-height,

&#x20; class: lh,

&#x20; values: (

&#x20;   1: 1,

&#x20;   sm: $line-height-sm,

&#x20;   base: $line-height-base,

&#x20;   lg: $line-height-lg,

&#x20; )

),

"text-align": (

&#x20; responsive: true,

&#x20; property: text-align,

&#x20; class: text,

&#x20; values: (

&#x20;   start: left,

&#x20;   end: right,

&#x20;   center: center,

&#x20; )

),

"text-decoration": (

&#x20; property: text-decoration,

&#x20; values: none underline line-through

),

"text-transform": (

&#x20; property: text-transform,

&#x20; class: text,

&#x20; values: lowercase uppercase capitalize

),

"white-space": (

&#x20; property: white-space,

&#x20; class: text,

&#x20; values: (

&#x20;   wrap: normal,

&#x20;   nowrap: nowrap,

&#x20; )

),

"word-wrap": (

&#x20; property: word-wrap word-break,

&#x20; class: text,

&#x20; values: (break: break-word),

&#x20; rtl: false

),

```



\--------------------------------



\### Integrate input groups



Source: https://getbootstrap.com/docs/5.3/components/navbar



Uses the form element as the primary container to host an input group component.



```html

<nav class="navbar bg-body-tertiary">

&#x20; <form class="container-fluid">

&#x20;   <div class="input-group">

&#x20;     <span class="input-group-text" id="basic-addon1">@</span>

&#x20;     <input type="text" class="form-control" placeholder="Username" aria-label="Username" aria-describedby="basic-addon1"/>

&#x20;   </div>

&#x20; </form>

</nav>

```



\--------------------------------



\### Implement an Autoplaying Carousel



Source: https://getbootstrap.com/docs/5.3/components/carousel



Set the data-bs-ride attribute to 'carousel' to enable automatic cycling on page load.



```html

<div id="carouselExampleAutoplaying" class="carousel slide" data-bs-ride="carousel">

&#x20; <div class="carousel-inner">

&#x20;   <div class="carousel-item active">

&#x20;     <img src="..." class="d-block w-100" alt="...">

&#x20;   </div>

&#x20;   <div class="carousel-item">

&#x20;     <img src="..." class="d-block w-100" alt="...">

&#x20;   </div>

&#x20;   <div class="carousel-item">

&#x20;     <img src="..." class="d-block w-100" alt="...">

&#x20;   </div>

&#x20; </div>

&#x20; <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleAutoplaying" data-bs-slide="prev">

&#x20;   <span class="carousel-control-prev-icon" aria-hidden="true"></span>

&#x20;   <span class="visually-hidden">Previous</span>

&#x20; </button>

&#x20; <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleAutoplaying" data-bs-slide="next">

&#x20;   <span class="carousel-control-next-icon" aria-hidden="true"></span>

&#x20;   <span class="visually-hidden">Next</span>

&#x20; </button>

</div>

```



\--------------------------------



\### Display badges in headings



Source: https://getbootstrap.com/docs/5.3/components/badge



Use badges within heading elements to scale automatically with the text size.



```html

<h1>Example heading <span class="badge text-bg-secondary">New</span></h1>

<h2>Example heading <span class="badge text-bg-secondary">New</span></h2>

<h3>Example heading <span class="badge text-bg-secondary">New</span></h3>

<h4>Example heading <span class="badge text-bg-secondary">New</span></h4>

<h5>Example heading <span class="badge text-bg-secondary">New</span></h5>

<h6>Example heading <span class="badge text-bg-secondary">New</span></h6>

```



\--------------------------------



\### Create horizontal list groups



Source: https://getbootstrap.com/docs/5.3/components/list-group



Use the .list-group-horizontal class or its responsive variants to align list items horizontally. These classes control the layout across different screen breakpoints.



```html

<ul class="list-group list-group-horizontal">

&#x20; <li class="list-group-item">An item</li>

&#x20; <li class="list-group-item">A second item</li>

&#x20; <li class="list-group-item">A third item</li>

</ul>

<ul class="list-group list-group-horizontal-sm">

&#x20; <li class="list-group-item">An item</li>

&#x20; <li class="list-group-item">A second item</li>

&#x20; <li class="list-group-item">A third item</li>

</ul>

<ul class="list-group list-group-horizontal-md">

&#x20; <li class="list-group-item">An item</li>

&#x20; <li class="list-group-item">A second item</li>

&#x20; <li class="list-group-item">A third item</li>

</ul>

<ul class="list-group list-group-horizontal-lg">

&#x20; <li class="list-group-item">An item</li>

&#x20; <li class="list-group-item">A second item</li>

&#x20; <li class="list-group-item">A third item</li>

</ul>

<ul class="list-group list-group-horizontal-xl">

&#x20; <li class="list-group-item">An item</li>

&#x20; <li class="list-group-item">A second item</li>

&#x20; <li class="list-group-item">A third item</li>

</ul>

<ul class="list-group list-group-horizontal-xxl">

&#x20; <li class="list-group-item">An item</li>

&#x20; <li class="list-group-item">A second item</li>

&#x20; <li class="list-group-item">A third item</li>

</ul>

```



\--------------------------------



\### Define Property Utility



Source: https://getbootstrap.com/docs/5.3/utilities/api



The property key is required for all utilities and determines the CSS property applied.



```scss

$utilities: (

&#x20; "text-decoration": (

&#x20;   property: text-decoration,

&#x20;   values: none underline line-through

&#x20; )

);

```



```css

.text-decoration-none { text-decoration: none !important; }

.text-decoration-underline { text-decoration: underline !important; }

.text-decoration-line-through { text-decoration: line-through !important; }

```



\--------------------------------



\### Implement custom select in input groups



Source: https://getbootstrap.com/docs/5.3/forms/input-group



Use the form-select class within an input-group to create custom select menus with labels or buttons.



```html

<div class="input-group mb-3">

&#x20; <label class="input-group-text" for="inputGroupSelect01">Options</label>

&#x20; <select class="form-select" id="inputGroupSelect01">

&#x20;   <option selected>Choose...</option>

&#x20;   <option value="1">One</option>

&#x20;   <option value="2">Two</option>

&#x20;   <option value="3">Three</option>

&#x20; </select>

</div>



<div class="input-group mb-3">

&#x20; <select class="form-select" id="inputGroupSelect02">

&#x20;   <option selected>Choose...</option>

&#x20;   <option value="1">One</option>

&#x20;   <option value="2">Two</option>

&#x20;   <option value="3">Three</option>

&#x20; </select>

&#x20; <label class="input-group-text" for="inputGroupSelect02">Options</label>

</div>



<div class="input-group mb-3">

&#x20; <button class="btn btn-outline-secondary" type="button">Button</button>

&#x20; <select class="form-select" id="inputGroupSelect03" aria-label="Example select with button addon">

&#x20;   <option selected>Choose...</option>

&#x20;   <option value="1">One</option>

&#x20;   <option value="2">Two</option>

&#x20;   <option value="3">Three</option>

&#x20; </select>

</div>



<div class="input-group">

&#x20; <select class="form-select" id="inputGroupSelect04" aria-label="Example select with button addon">

&#x20;   <option selected>Choose...</option>

&#x20;   <option value="1">One</option>

&#x20;   <option value="2">Two</option>

&#x20;   <option value="3">Three</option>

&#x20; </select>

&#x20; <button class="btn btn-outline-secondary" type="button">Button</button>

</div>

```



\--------------------------------



\### Configure Tooltip Boundary



Source: https://getbootstrap.com/docs/5.3/components/tooltips



Override the default clipping boundary to ensure the tooltip remains visible within a specific container.



```javascript

const tooltip = new bootstrap.Tooltip('#example', {

&#x20; boundary: document.body // or document.querySelector('#boundary')

})

```



\--------------------------------



\### Interactive Offcanvas with Triggers



Source: https://getbootstrap.com/docs/5.3/components/offcanvas



Demonstrates toggling an offcanvas element using a link or a button with data-bs-toggle attributes.



```html

<a class="btn btn-primary" data-bs-toggle="offcanvas" href="#offcanvasExample" role="button" aria-controls="offcanvasExample">

&#x20; Link with href

</a>

<button class="btn btn-primary" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasExample" aria-controls="offcanvasExample">

&#x20; Button with data-bs-target

</button>



<div class="offcanvas offcanvas-start" tabindex="-1" id="offcanvasExample" aria-labelledby="offcanvasExampleLabel">

&#x20; <div class="offcanvas-header">

&#x20;   <h5 class="offcanvas-title" id="offcanvasExampleLabel">Offcanvas</h5>

&#x20;   <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>

&#x20; </div>

&#x20; <div class="offcanvas-body">

&#x20;   <div>

&#x20;     Some text as placeholder. In real life you can have the elements you have chosen. Like, text, images, lists, etc.

&#x20;   </div>

&#x20;   <div class="dropdown mt-3">

&#x20;     <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown">

&#x20;       Dropdown button

&#x20;     </button>

&#x20;     <ul class="dropdown-menu">

&#x20;       <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;       <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;       <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;     </ul>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Offcanvas Options



Source: https://getbootstrap.com/docs/5.3/components/offcanvas



Configuration options for the Offcanvas component, applicable via data attributes or JavaScript.



```APIDOC

\## Offcanvas Options



\### Configuration

\- \*\*backdrop\*\* (boolean|string) - Default: true - Apply a backdrop on body while offcanvas is open. Use 'static' to prevent closing on click.

\- \*\*keyboard\*\* (boolean) - Default: true - Closes the offcanvas when the escape key is pressed.

\- \*\*scroll\*\* (boolean) - Default: false - Allow body scrolling while offcanvas is open.

```



\--------------------------------



\### Define Growing Spinner CSS Variables



Source: https://getbootstrap.com/docs/5.3/components/spinners



Local CSS variables for the growing spinner component.



```scss

\--#{$prefix}spinner-width: #{$spinner-width};

\--#{$prefix}spinner-height: #{$spinner-height};

\--#{$prefix}spinner-vertical-align: #{$spinner-vertical-align};

\--#{$prefix}spinner-animation-speed: #{$spinner-animation-speed};

\--#{$prefix}spinner-animation-name: spinner-grow;

```



\--------------------------------



\### Configure border-subtle Sass variables



Source: https://getbootstrap.com/docs/5.3/utilities/borders



Variables for light and dark mode border-subtle utilities.



```scss

$primary-border-subtle:   tint-color($primary, 60%);

$secondary-border-subtle: tint-color($secondary, 60%);

$success-border-subtle:   tint-color($success, 60%);

$info-border-subtle:      tint-color($info, 60%);

$warning-border-subtle:   tint-color($warning, 60%);

$danger-border-subtle:    tint-color($danger, 60%);

$light-border-subtle:     $gray-200;

$dark-border-subtle:      $gray-500;

```



```scss

$primary-border-subtle-dark:        shade-color($primary, 40%);

$secondary-border-subtle-dark:      shade-color($secondary, 40%);

$success-border-subtle-dark:        shade-color($success, 40%);

$info-border-subtle-dark:           shade-color($info, 40%);

$warning-border-subtle-dark:        shade-color($warning, 40%);

$danger-border-subtle-dark:         shade-color($danger, 40%);

$light-border-subtle-dark:          $gray-700;

$dark-border-subtle-dark:           $gray-800;

```



\--------------------------------



\### Include extracted CSS in HTML



Source: https://getbootstrap.com/docs/5.3/getting-started/webpack



Manually link the generated CSS file in the HTML document.



```html

\--- a/dist/index.html

+++ b/dist/index.html

@@ -3,6 +3,7 @@

&#x20;  <head>

&#x20;    <meta charset="utf-8">

&#x20;    <meta name="viewport" content="width=device-width, initial-scale=1">

\+    <link rel="stylesheet" href="./main.css">

&#x20;    <title>Bootstrap w/ Webpack</title>

&#x20;  </head>

&#x20;  <body>

```



\--------------------------------



\### Apply relative height utilities



Source: https://getbootstrap.com/docs/5.3/utilities/sizing



Use these classes to set an element's height as a percentage of its parent container. Requires the parent to have a defined height.



```html

<div style="height: 100px;">

&#x20; <div class="h-25 d-inline-block" style="width: 120px;">Height 25%</div>

&#x20; <div class="h-50 d-inline-block" style="width: 120px;">Height 50%</div>

&#x20; <div class="h-75 d-inline-block" style="width: 120px;">Height 75%</div>

&#x20; <div class="h-100 d-inline-block" style="width: 120px;">Height 100%</div>

&#x20; <div class="h-auto d-inline-block" style="width: 120px;">Height auto</div>

</div>

```



\--------------------------------



\### Primary text utility structure



Source: https://getbootstrap.com/docs/5.3/utilities/colors



The internal CSS structure for the .text-primary utility using RGB variables and opacity overrides.



```css

.text-primary {

&#x20; --bs-text-opacity: 1;

&#x20; color: rgba(var(--bs-primary-rgb), var(--bs-text-opacity)) !important;

}

```



\--------------------------------



\### Retrieve Toast Instances



Source: https://getbootstrap.com/docs/5.3/components/toasts



Use static methods to access existing toast instances associated with DOM elements.



```javascript

const myToastEl = document.getElementById('myToastEl')

const myToast = bootstrap.Toast.getInstance(myToastEl)

```



```javascript

const myToastEl = document.getElementById('myToastEl')

const myToast = bootstrap.Toast.getOrCreateInstance(myToastEl)

```



\--------------------------------



\### Positioning Toasts with Select Input



Source: https://getbootstrap.com/docs/5.3/components/toasts



Uses a select element to dynamically apply positioning classes to a toast container.



```html

<form>

&#x20; <div class="mb-3">

&#x20;   <label for="selectToastPlacement">Toast placement</label>

&#x20;   <select class="form-select mt-2" id="selectToastPlacement">

&#x20;     <option value="" selected>Select a position...</option>

&#x20;     <option value="top-0 start-0">Top left</option>

&#x20;     <option value="top-0 start-50 translate-middle-x">Top center</option>

&#x20;     <option value="top-0 end-0">Top right</option>

&#x20;     <option value="top-50 start-0 translate-middle-y">Middle left</option>

&#x20;     <option value="top-50 start-50 translate-middle">Middle center</option>

&#x20;     <option value="top-50 end-0 translate-middle-y">Middle right</option>

&#x20;     <option value="bottom-0 start-0">Bottom left</option>

&#x20;     <option value="bottom-0 start-50 translate-middle-x">Bottom center</option>

&#x20;     <option value="bottom-0 end-0">Bottom right</option>

&#x20;   </select>

&#x20; </div>

</form>

<div aria-live="polite" aria-atomic="true" class="bg-body-secondary position-relative bd-example-toasts rounded-3">

&#x20; <div class="toast-container p-3" id="toastPlacement">

&#x20;   <div class="toast">

&#x20;     <div class="toast-header">

&#x20;       <img src="..." class="rounded me-2" alt="...">

&#x20;       <strong class="me-auto">Bootstrap</strong>

&#x20;       <small>11 mins ago</small>

&#x20;     </div>

&#x20;     <div class="toast-body">

&#x20;       Hello, world! This is a toast message.

&#x20;     </div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Tab Methods



Source: https://getbootstrap.com/docs/5.3/components/list-group



Methods available on the Tab instance to control tab behavior.



```APIDOC

\## Tab Methods



\### dispose()

Destroys an element’s tab.



\### getInstance(element)

Static method which allows you to get the tab instance associated with a DOM element.



\### getOrCreateInstance(element)

Static method which returns a tab instance associated to a DOM element or creates a new one if it wasn’t initialized.



\### show()

Selects the given tab and shows its associated pane. Any other tab that was previously selected becomes unselected and its associated pane is hidden.

```



\--------------------------------



\### Mapping focus ring variables to CSS root



Source: https://getbootstrap.com/docs/5.3/customize/css-variables



Reassigning Sass variables to CSS custom properties at the root level for real-time customization.



```scss

\--#{$prefix}focus-ring-width: #{$focus-ring-width};

\--#{$prefix}focus-ring-opacity: #{$focus-ring-opacity};

\--#{$prefix}focus-ring-color: #{$focus-ring-color};

```



\--------------------------------



\### Sass Max-width Breakpoint Mixins



Source: https://getbootstrap.com/docs/5.3/layout/breakpoints



Use these mixins to apply styles for a specific screen size or smaller.



```scss

// No media query necessary for xs breakpoint as it’s effectively `@media (max-width: 0) { ... }`

@include media-breakpoint-down(sm) { ... }

@include media-breakpoint-down(md) { ... }

@include media-breakpoint-down(lg) { ... }

@include media-breakpoint-down(xl) { ... }

@include media-breakpoint-down(xxl) { ... }



// Example: Style from medium breakpoint and down

@include media-breakpoint-down(md) {

&#x20; .custom-class {

&#x20;   display: block;

&#x20; }

}

```



\--------------------------------



\### Create Tabbable List Group with HTML



Source: https://getbootstrap.com/docs/5.3/components/list-group



Uses the tab JavaScript plugin to link list group items to specific tab content panes.



```html

<div class="row">

&#x20; <div class="col-4">

&#x20;   <div class="list-group" id="list-tab" role="tablist">

&#x20;     <a class="list-group-item list-group-item-action active" id="list-home-list" data-bs-toggle="list" href="#list-home" role="tab" aria-controls="list-home">Home</a>

&#x20;     <a class="list-group-item list-group-item-action" id="list-profile-list" data-bs-toggle="list" href="#list-profile" role="tab" aria-controls="list-profile">Profile</a>

&#x20;     <a class="list-group-item list-group-item-action" id="list-messages-list" data-bs-toggle="list" href="#list-messages" role="tab" aria-controls="list-messages">Messages</a>

&#x20;     <a class="list-group-item list-group-item-action" id="list-settings-list" data-bs-toggle="list" href="#list-settings" role="tab" aria-controls="list-settings">Settings</a>

&#x20;   </div>

&#x20; </div>

&#x20; <div class="col-8">

&#x20;   <div class="tab-content" id="nav-tabContent">

&#x20;     <div class="tab-pane fade show active" id="list-home" role="tabpanel" aria-labelledby="list-home-list">...</div>

&#x20;     <div class="tab-pane fade" id="list-profile" role="tabpanel" aria-labelledby="list-profile-list">...</div>

&#x20;     <div class="tab-pane fade" id="list-messages" role="tabpanel" aria-labelledby="list-messages-list">...</div>

&#x20;     <div class="tab-pane fade" id="list-settings" role="tabpanel" aria-labelledby="list-settings-list">...</div>

&#x20;   </div>

&#x20; </div>

</div>

```



\--------------------------------



\### Customize tooltip appearance with CSS variables



Source: https://getbootstrap.com/docs/5.3/components/tooltips



Define a custom class and override Bootstrap CSS variables to change tooltip background and color.



```scss

.custom-tooltip {

&#x20; --bs-tooltip-bg: var(--bd-violet-bg);

&#x20; --bs-tooltip-color: var(--bs-white);

}

```



\--------------------------------



\### Define Navbar-Nav CSS Variables



Source: https://getbootstrap.com/docs/5.3/components/navbar



These variables are applied to the .navbar-nav class to manage link styling.



```scss

\--#{$prefix}nav-link-padding-x: 0;

\--#{$prefix}nav-link-padding-y: #{$nav-link-padding-y};

@include rfs($nav-link-font-size, --#{$prefix}nav-link-font-size);

\--#{$prefix}nav-link-font-weight: #{$nav-link-font-weight};

\--#{$prefix}nav-link-color: var(--#{$prefix}navbar-color);

\--#{$prefix}nav-link-hover-color: var(--#{$prefix}navbar-hover-color);

\--#{$prefix}nav-link-disabled-color: var(--#{$prefix}navbar-disabled-color);

```



\--------------------------------



\### Basic Range Input



Source: https://getbootstrap.com/docs/5.3/forms/range



Standard range input using the .form-range class.



```html

<label for="range1" class="form-label">Example range</label>

<input type="range" class="form-range" id="range1">

```



\--------------------------------



\### Sizing cards with custom CSS



Source: https://getbootstrap.com/docs/5.3/components/card



Use inline styles or external CSS rules to define a specific width for the card component.



```html

<div class="card" style="width: 18rem;">

&#x20; <div class="card-body">

&#x20;   <h5 class="card-title">Special title treatment</h5>

&#x20;   <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>

&#x20;   <a href="#" class="btn btn-primary">Go somewhere</a>

&#x20; </div>

</div>

```



\--------------------------------



\### Inline Display Utilities



Source: https://getbootstrap.com/docs/5.3/utilities/display



Applies the inline display property to elements.



```html

<div class="d-inline p-2 text-bg-primary">d-inline</div>

<div class="d-inline p-2 text-bg-dark">d-inline</div>

```



\--------------------------------



\### Create an animated striped progress bar



Source: https://getbootstrap.com/docs/5.3/components/progress



Add the .progress-bar-animated class to a striped progress bar to enable CSS3 animations.



```html

<div class="progress" role="progressbar" aria-label="Animated striped example" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100">

&#x20; <div class="progress-bar progress-bar-striped progress-bar-animated" style="width: 75%"></div>

</div>

```



\--------------------------------



\### Apply colored borders to tables



Source: https://getbootstrap.com/docs/5.3/content/tables



Combine .table-bordered with border color utilities to change the border color.



```html

<table class="table table-bordered border-primary">

&#x20; ...

</table>

```



\--------------------------------



\### Define progress bar animation keyframes



Source: https://getbootstrap.com/docs/5.3/components/progress



CSS keyframes used for the .progress-bar-animated class, conditional on $enable-transitions.



```scss

@if $enable-transitions {

&#x20; @keyframes progress-bar-stripes {

&#x20;   0% { background-position-x: var(--#{$prefix}progress-height); }

&#x20; }

}

```



\--------------------------------



\### Heading Utility Classes



Source: https://getbootstrap.com/docs/5.3/content/typography



Applies heading font styling to non-heading elements using utility classes.



```html

<p class="h1">h1. Bootstrap heading</p>

<p class="h2">h2. Bootstrap heading</p>

<p class="h3">h3. Bootstrap heading</p>

<p class="h4">h4. Bootstrap heading</p>

<p class="h5">h5. Bootstrap heading</p>

<p class="h6">h6. Bootstrap heading</p>

```



\--------------------------------



\### Apply Clearfix via HTML Class



Source: https://getbootstrap.com/docs/5.3/helpers/clearfix



Add the .clearfix class to a parent element to clear floats of its children.



```html

<div class="clearfix">...</div>

```



\--------------------------------



\### Configure Webpack for CSS extraction



Source: https://getbootstrap.com/docs/5.3/getting-started/webpack



Update webpack.config.js to use mini-css-extract-plugin instead of style-loader.



```javascript

\--- a/webpack.config.js

+++ b/webpack.config.js

@@ -3,6 +3,7 @@

&#x20;const path = require('path')

&#x20;const autoprefixer = require('autoprefixer')

&#x20;const HtmlWebpackPlugin = require('html-webpack-plugin')

+const miniCssExtractPlugin = require('mini-css-extract-plugin')



&#x20;module.exports = {

&#x20;  mode: 'development',

@@ -17,7 +18,8 @@ module.exports = {

&#x20;    hot: true

&#x20;  },

&#x20;  plugins: \[

\-    new HtmlWebpackPlugin({ template: './src/index.html' })

\+    new HtmlWebpackPlugin({ template: './src/index.html' }),

\+    new miniCssExtractPlugin()

&#x20;  ],

&#x20;  module: {

&#x20;    rules: \[

@@ -25,8 +27,8 @@ module.exports = {

&#x20;        test: /\\.(scss)$/,

&#x20;        use: \[

&#x20;          {

\-            // Adds CSS to the DOM by injecting a `<style>` tag

\-            loader: 'style-loader'

\+            // Extracts CSS for each JS file that includes CSS

\+            loader: miniCssExtractPlugin.loader

&#x20;          },

&#x20;          {

```



\--------------------------------



\### Flex Wrapping Options



Source: https://getbootstrap.com/docs/5.3/utilities/flex



Control how flex items wrap within a container using nowrap, wrap, or wrap-reverse classes.



```html

<div class="d-flex flex-nowrap">

&#x20; ...

</div>

```



```html

<div class="d-flex flex-wrap">

&#x20; ...

</div>

```



```html

<div class="d-flex flex-wrap-reverse">

&#x20; ...

</div>

```



\--------------------------------



\### Navbar Brand Image



Source: https://getbootstrap.com/docs/5.3/components/navbar



Shows how to replace text within the navbar-brand class with an image.



```html

<nav class="navbar bg-body-tertiary">

&#x20; <div class="container">

&#x20;   <a class="navbar-brand" href="#">

&#x20;     <img src="/docs/5.3/assets/brand/bootstrap-logo.svg" alt="Bootstrap" width="30" height="24">

&#x20;   </a>

&#x20; </div>

</nav>

```



\--------------------------------



\### Configure aspect ratios in Sass



Source: https://getbootstrap.com/docs/5.3/helpers/ratio



Modify the $aspect-ratios map in \_variables.scss to customize the available ratio classes.



```scss

$aspect-ratios: (

&#x20; "1x1": 100%,

&#x20; "4x3": calc(3 / 4 \* 100%),

&#x20; "16x9": calc(9 / 16 \* 100%),

&#x20; "21x9": calc(9 / 21 \* 100%)

);

```



\--------------------------------



\### Nest dropdowns in button groups



Source: https://getbootstrap.com/docs/5.3/components/button-group



Place a .btn-group containing a dropdown toggle inside another .btn-group to mix buttons and menus.



```html

<div class="btn-group" role="group" aria-label="Button group with nested dropdown">

&#x20; <button type="button" class="btn btn-primary">1</button>

&#x20; <button type="button" class="btn btn-primary">2</button>



&#x20; <div class="btn-group" role="group">

&#x20;   <button type="button" class="btn btn-primary dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;     Dropdown

&#x20;   </button>

&#x20;   <ul class="dropdown-menu">

&#x20;     <li><a class="dropdown-item" href="#">Dropdown link</a></li>

&#x20;     <li><a class="dropdown-item" href="#">Dropdown link</a></li>

&#x20;   </ul>

&#x20; </div>

</div>

```



\--------------------------------



\### Using Bootstrap theme colors



Source: https://getbootstrap.com/docs/5.3/customize/sass



Apply theme colors as standalone variables in custom CSS rules.



```scss

.custom-element {

&#x20; color: $gray-100;

&#x20; background-color: $dark;

}



```



\--------------------------------



\### Control text selection behavior



Source: https://getbootstrap.com/docs/5.3/utilities/interactions



Use these classes to define whether text content is selectable by the user.



```html

<p class="user-select-all">This paragraph will be entirely selected when clicked by the user.</p>

<p class="user-select-auto">This paragraph has default select behavior.</p>

<p class="user-select-none">This paragraph will not be selectable when clicked by the user.</p>

```



\--------------------------------



\### Utilize grid Sass mixins



Source: https://getbootstrap.com/docs/5.3/layout/grid



Generate semantic grid structures using built-in mixins for rows and columns.



```scss

// Creates a wrapper for a series of columns

@include make-row();



// Make the element grid-ready (applying everything but the width)

@include make-col-ready();



// Without optional size values, the mixin will create equal columns (similar to using .col)

@include make-col();

@include make-col($size, $columns: $grid-columns);



// Offset with margins

@include make-col-offset($size, $columns: $grid-columns);

```



\--------------------------------



\### Apply striped variants to dark tables



Source: https://getbootstrap.com/docs/5.3/content/tables



Combine the .table-dark class with striping utilities for dark-themed tables.



```html

<table class="table table-dark table-striped">

&#x20; ...

</table>

```



```html

<table class="table table-dark table-striped-columns">

&#x20; ...

</table>

```



\--------------------------------



\### Create a split button dropdown



Source: https://getbootstrap.com/docs/5.3/components/dropdowns



Use the dropdown-toggle-split class on a secondary button to create a distinct caret area for the dropdown menu.



```html

<!-- Example split danger button -->

<div class="btn-group">

&#x20; <button type="button" class="btn btn-danger">Danger</button>

&#x20; <button type="button" class="btn btn-danger dropdown-toggle dropdown-toggle-split" data-bs-toggle="dropdown" aria-expanded="false">

&#x20;   <span class="visually-hidden">Toggle Dropdown</span>

&#x20; </button>

&#x20; <ul class="dropdown-menu">

&#x20;   <li><a class="dropdown-item" href="#">Action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Another action</a></li>

&#x20;   <li><a class="dropdown-item" href="#">Something else here</a></li>

&#x20;   <li><hr class="dropdown-divider"></li>

&#x20;   <li><a class="dropdown-item" href="#">Separated link</a></li>

&#x20; </ul>

</div>

```



\--------------------------------



\### Listen for Tab Events



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



Attach event listeners to tab elements to handle transitions, such as accessing the newly activated tab and the previously active tab.



```javascript

const tabEl = document.querySelector('button\[data-bs-toggle="tab"]')

tabEl.addEventListener('shown.bs.tab', event => {

&#x20; event.target // newly activated tab

&#x20; event.relatedTarget // previous active tab

})

```



\--------------------------------



\### Inline Border Opacity Adjustment



Source: https://getbootstrap.com/docs/5.3/utilities/borders



Demonstrates overriding the --bs-border-opacity CSS variable using inline styles.



```html

<div class="border border-success p-2 mb-2">This is default success border</div>

<div class="border border-success p-2" style="--bs-border-opacity: .5;">This is 50% opacity success border</div>

```



\--------------------------------



\### Define Local CSS Variables



Source: https://getbootstrap.com/docs/5.3/utilities/api



Use local-vars to inject CSS variables within the utility class ruleset.



```scss

$utilities: (

&#x20; "background-color": (

&#x20;   property: background-color,

&#x20;   class: bg,

&#x20;   local-vars: (

&#x20;     "bg-opacity": 1

&#x20;   ),

&#x20;   values: map-merge(

&#x20;     $utilities-bg-colors,

&#x20;     (

&#x20;       "transparent": transparent

&#x20;     )

&#x20;   )

&#x20; )

);

```



```css

.bg-primary {

&#x20; --bs-bg-opacity: 1;

&#x20; background-color: rgba(var(--bs-primary-rgb), var(--bs-bg-opacity)) !important;

}

```



\--------------------------------



\### Using the color-mode Sass mixin



Source: https://getbootstrap.com/docs/5.3/customize/color-modes



This mixin handles the logic for switching between media-query based themes and data-attribute based themes.



```scss

@mixin color-mode($mode: light, $root: false) {

&#x20; @if $color-mode-type == "media-query" {

&#x20;   @if $root == true {

&#x20;     @media (prefers-color-scheme: $mode) {

&#x20;       :root {

&#x20;         @content;

&#x20;       }

&#x20;     }

&#x20;   } @else {

&#x20;     @media (prefers-color-scheme: $mode) {

&#x20;       @content;

&#x20;     }

&#x20;   }

&#x20; } @else {

&#x20;   \[data-bs-theme="#{$mode}"] {

&#x20;     @content;

&#x20;   }

&#x20; }

}

```



\--------------------------------



\### Include images in a card



Source: https://getbootstrap.com/docs/5.3/components/card



Apply .card-img-top or .card-img-bottom to images to ensure they align with the card's rounded corners.



```html

<div class="card" style="width: 18rem;">

&#x20; <img src="..." class="card-img-top" alt="...">

&#x20; <div class="card-body">

&#x20;   <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card’s content.</p>

&#x20; </div>

</div>

```



\--------------------------------



\### Implement Color Mode Toggler JavaScript



Source: https://getbootstrap.com/docs/5.3/customize/color-modes



This script manages theme persistence via localStorage and updates the document's data-bs-theme attribute. It is recommended to place this at the top of the page to prevent flickering.



```javascript

/\*!

&#x20;\* Color mode toggler for Bootstrap's docs (https://getbootstrap.com/)

&#x20;\* Copyright 2011-2025 The Bootstrap Authors

&#x20;\* Licensed under the Creative Commons Attribution 3.0 Unported License.

&#x20;\*/



(() => {

&#x20; 'use strict'



&#x20; const getStoredTheme = () => localStorage.getItem('theme')

&#x20; const setStoredTheme = theme => localStorage.setItem('theme', theme)



&#x20; const getPreferredTheme = () => {

&#x20;   const storedTheme = getStoredTheme()

&#x20;   if (storedTheme) {

&#x20;     return storedTheme

&#x20;   }



&#x20;   return window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light'

&#x20; }



&#x20; const setTheme = theme => {

&#x20;   if (theme === 'auto') {

&#x20;     document.documentElement.setAttribute('data-bs-theme', (window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light'))

&#x20;   } else {

&#x20;     document.documentElement.setAttribute('data-bs-theme', theme)

&#x20;   }

&#x20; }



&#x20; setTheme(getPreferredTheme())



&#x20; const showActiveTheme = (theme, focus = false) => {

&#x20;   const themeSwitcher = document.querySelector('#bd-theme')



&#x20;   if (!themeSwitcher) {

&#x20;     return

&#x20;   }



&#x20;   const themeSwitcherText = document.querySelector('#bd-theme-text')

&#x20;   const activeThemeIcon = document.querySelector('.theme-icon-active use')

&#x20;   const btnToActive = document.querySelector(`\[data-bs-theme-value="${theme}"]`)

&#x20;   const svgOfActiveBtn = btnToActive.querySelector('svg use').getAttribute('href')



&#x20;   document.querySelectorAll('\[data-bs-theme-value]').forEach(element => {

&#x20;     element.classList.remove('active')

&#x20;     element.setAttribute('aria-pressed', 'false')

&#x20;   })



&#x20;   btnToActive.classList.add('active')

&#x20;   btnToActive.setAttribute('aria-pressed', 'true')

&#x20;   activeThemeIcon.setAttribute('href', svgOfActiveBtn)

&#x20;   const themeSwitcherLabel = `${themeSwitcherText.textContent} (${btnToActive.dataset.bsThemeValue})`

&#x20;   themeSwitcher.setAttribute('aria-label', themeSwitcherLabel)



&#x20;   if (focus) {

&#x20;     themeSwitcher.focus()

&#x20;   }

&#x20; }



&#x20; window.matchMedia('(prefers-color-scheme: dark)').addEventListener('change', () => {

&#x20;   const storedTheme = getStoredTheme()

&#x20;   if (storedTheme !== 'light' \&\& storedTheme !== 'dark') {

&#x20;     setTheme(getPreferredTheme())

&#x20;   }

&#x20; })



&#x20; window.addEventListener('DOMContentLoaded', () => {

&#x20;   showActiveTheme(getPreferredTheme())



&#x20;   document.querySelectorAll('\[data-bs-theme-value]')

&#x20;     .forEach(toggle => {

&#x20;       toggle.addEventListener('click', () => {

&#x20;         const theme = toggle.getAttribute('data-bs-theme-value')

&#x20;         setStoredTheme(theme)

&#x20;         setTheme(theme)

&#x20;         showActiveTheme(theme, true)

&#x20;       })

&#x20;     })

&#x20; })

})()

```



\--------------------------------



\### Define Nav CSS Variables



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



CSS variables applied to the .nav base class for link styling.



```scss

\--#{$prefix}nav-link-padding-x: #{$nav-link-padding-x};

\--#{$prefix}nav-link-padding-y: #{$nav-link-padding-y};

@include rfs($nav-link-font-size, --#{$prefix}nav-link-font-size);

\--#{$prefix}nav-link-font-weight: #{$nav-link-font-weight};

\--#{$prefix}nav-link-color: #{$nav-link-color};

\--#{$prefix}nav-link-hover-color: #{$nav-link-hover-color};

\--#{$prefix}nav-link-disabled-color: #{$nav-link-disabled-color};

```



\--------------------------------



\### Update Stacked Progress Bar Markup



Source: https://getbootstrap.com/docs/5.3/migration



Use the new .progress-stacked class to wrap multiple progress bars into a single container.



```html

<!-- Previous markup -->

<div class="progress">

&#x20; <div class="progress-bar" role="progressbar" aria-label="Segment one" style="width: 15%" aria-valuenow="15" aria-valuemin="0" aria-valuemax="100"></div>

&#x20; <div class="progress-bar bg-success" role="progressbar" aria-label="Segment two" style="width: 30%" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100"></div>

&#x20; <div class="progress-bar bg-info" role="progressbar" aria-label="Segment three" style="width: 20%" aria-valuenow="20" aria-valuemin="0" aria-valuemax="100"></div>

</div>



<!-- New markup -->

<div class="progress-stacked">

&#x20; <div class="progress" role="progressbar" aria-label="Segment one" aria-valuenow="15" aria-valuemin="0" aria-valuemax="100" style="width: 15%">

&#x20;   <div class="progress-bar"></div>

&#x20; </div>

&#x20; <div class="progress" role="progressbar" aria-label="Segment two" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100" style="width: 30%">

&#x20;   <div class="progress-bar bg-success"></div>

&#x20; </div>

&#x20; <div class="progress" role="progressbar" aria-label="Segment three" aria-valuenow="20" aria-valuemin="0" aria-valuemax="100" style="width: 20%">

&#x20;   <div class="progress-bar bg-info"></div>

&#x20; </div>

</div>

```



\--------------------------------



\### Use RGB Color Variables



Source: https://getbootstrap.com/docs/5.3/customize/color



Utilize -rgb variables to define custom colors with alpha transparency using rgba().



```css

rgba(var(--bs-secondary-bg-rgb), .5)

```



\--------------------------------



\### Configure Opacity in Sass Utilities API



Source: https://getbootstrap.com/docs/5.3/utilities/opacity



The opacity utilities are defined in the utilities API within scss/\_utilities.scss.



```scss

"opacity": (

&#x20; property: opacity,

&#x20; values: (

&#x20;   0: 0,

&#x20;   25: .25,

&#x20;   50: .5,

&#x20;   75: .75,

&#x20;   100: 1,

&#x20; )

),

```



\--------------------------------



\### Configure native font stack



Source: https://getbootstrap.com/docs/5.3/content/reboot



The system font stack is defined via the $font-family-sans-serif variable, which includes platform-specific fallbacks and emoji support.



```scss

$font-family-sans-serif:

&#x20; // Cross-platform generic font family (default user interface font)

&#x20; system-ui,

&#x20; // Safari for macOS and iOS (San Francisco)

&#x20; -apple-system,

&#x20; // Windows

&#x20; "Segoe UI",

&#x20; // Android

&#x20; Roboto,

&#x20; // older macOS and iOS

&#x20; "Helvetica Neue",

&#x20; // Linux

&#x20; "Noto Sans",

&#x20; "Liberation Sans",

&#x20; // Basic web fallback

&#x20; Arial,

&#x20; // Sans serif fallback

&#x20; sans-serif,

&#x20; // Emoji fonts

&#x20; "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji" !default;

```



\--------------------------------



\### Configure Toast Sass Variables



Source: https://getbootstrap.com/docs/5.3/components/toasts



Default Sass variables that define the values for toast CSS variables.



```scss

$toast-max-width:                   350px;

$toast-padding-x:                   .75rem;

$toast-padding-y:                   .5rem;

$toast-font-size:                   .875rem;

$toast-color:                       null;

$toast-background-color:            rgba(var(--#{$prefix}body-bg-rgb), .85);

$toast-border-width:                var(--#{$prefix}border-width);

$toast-border-color:                var(--#{$prefix}border-color-translucent);

$toast-border-radius:               var(--#{$prefix}border-radius);

$toast-box-shadow:                  var(--#{$prefix}box-shadow);

$toast-spacing:                     $container-padding-x;



$toast-header-color:                var(--#{$prefix}secondary-color);

$toast-header-background-color:     rgba(var(--#{$prefix}body-bg-rgb), .85);

$toast-header-border-color:         $toast-border-color;

```



\--------------------------------



\### Print Display Utilities



Source: https://getbootstrap.com/docs/5.3/utilities/display



Controls element visibility and display properties specifically for print media.



```html

<div class="d-print-none">Screen Only (Hide on print only)</div>

<div class="d-none d-print-block">Print Only (Hide on screen only)</div>

<div class="d-none d-lg-block d-print-block">Hide up to large on screen, but always show on print</div>

```



\--------------------------------



\### Configure Navbar Placement



Source: https://getbootstrap.com/docs/5.3/components/navbar



Use position utility classes to fix or stick the navbar to specific viewport edges. Fixed navbars are removed from the DOM flow and may require body padding to prevent overlap.



```html

<nav class="navbar bg-body-tertiary">

&#x20; <div class="container-fluid">

&#x20;   <a class="navbar-brand" href="#">Default</a>

&#x20; </div>

</nav>

```



```html

<nav class="navbar fixed-top bg-body-tertiary">

&#x20; <div class="container-fluid">

&#x20;   <a class="navbar-brand" href="#">Fixed top</a>

&#x20; </div>

</nav>

```



```html

<nav class="navbar fixed-bottom bg-body-tertiary">

&#x20; <div class="container-fluid">

&#x20;   <a class="navbar-brand" href="#">Fixed bottom</a>

&#x20; </div>

</nav>

```



```html

<nav class="navbar sticky-top bg-body-tertiary">

&#x20; <div class="container-fluid">

&#x20;   <a class="navbar-brand" href="#">Sticky top</a>

&#x20; </div>

</nav>

```



```html

<nav class="navbar sticky-bottom bg-body-tertiary">

&#x20; <div class="container-fluid">

&#x20;   <a class="navbar-brand" href="#">Sticky bottom</a>

&#x20; </div>

</nav>

```



\--------------------------------



\### Define Background Utilities Maps



Source: https://getbootstrap.com/docs/5.3/utilities/background



Maps used by the utilities API to define background colors and subtle variants.



```scss

$utilities-bg: map-merge(

&#x20; $utilities-colors,

&#x20; (

&#x20;   "black": to-rgb($black),

&#x20;   "white": to-rgb($white),

&#x20;   "body": to-rgb($body-bg)

&#x20; )

);

$utilities-bg-colors: map-loop($utilities-bg, rgba-css-var, "$key", "bg");



$utilities-bg-subtle: (

&#x20; "primary-subtle": var(--#{$prefix}primary-bg-subtle),

&#x20; "secondary-subtle": var(--#{$prefix}secondary-bg-subtle),

&#x20; "success-subtle": var(--#{$prefix}success-bg-subtle),

&#x20; "info-subtle": var(--#{$prefix}info-bg-subtle),

&#x20; "warning-subtle": var(--#{$prefix}warning-bg-subtle),

&#x20; "danger-subtle": var(--#{$prefix}danger-bg-subtle),

&#x20; "light-subtle": var(--#{$prefix}light-bg-subtle),

&#x20; "dark-subtle": var(--#{$prefix}dark-bg-subtle)

);

```



\--------------------------------



\### Implement tabbed navigation with custom markup



Source: https://getbootstrap.com/docs/5.3/components/navs-tabs



Uses a div-based structure for the tab list to avoid overriding the <nav> element's native role. Requires data-bs-toggle and data-bs-target attributes to link buttons to their respective tab panes.



```html

<nav>

&#x20; <div class="nav nav-tabs" id="nav-tab" role="tablist">

&#x20;   <button class="nav-link active" id="nav-home-tab" data-bs-toggle="tab" data-bs-target="#nav-home" type="button" role="tab" aria-controls="nav-home" aria-selected="true">Home</button>

&#x20;   <button class="nav-link" id="nav-profile-tab" data-bs-toggle="tab" data-bs-target="#nav-profile" type="button" role="tab" aria-controls="nav-profile" aria-selected="false">Profile</button>

&#x20;   <button class="nav-link" id="nav-contact-tab" data-bs-toggle="tab" data-bs-target="#nav-contact" type="button" role="tab" aria-controls="nav-contact" aria-selected="false">Contact</button>

&#x20;   <button class="nav-link" id="nav-disabled-tab" data-bs-toggle="tab" data-bs-target="#nav-disabled" type="button" role="tab" aria-controls="nav-disabled" aria-selected="false" disabled>Disabled</button>

&#x20; </div>

</nav>

<div class="tab-content" id="nav-tabContent">

&#x20; <div class="tab-pane fade show active" id="nav-home" role="tabpanel" aria-labelledby="nav-home-tab" tabindex="0">...</div>

&#x20; <div class="tab-pane fade" id="nav-profile" role="tabpanel" aria-labelledby="nav-profile-tab" tabindex="0">...</div>

&#x20; <div class="tab-pane fade" id="nav-contact" role="tabpanel" aria-labelledby="nav-contact-tab" tabindex="0">...</div>

&#x20; <div class="tab-pane fade" id="nav-disabled" role="tabpanel" aria-labelledby="nav-disabled-tab" tabindex="0">...</div>

</div>

```



\--------------------------------



\### Horizontal Centering with mx-auto



Source: https://getbootstrap.com/docs/5.3/utilities/spacing



Use the .mx-auto class to horizontally center block-level elements with a defined width.



```html

<div class="mx-auto p-2" style="width: 200px;">

&#x20; Centered element

</div>

```



\--------------------------------



\### Define Base Color Variables



Source: https://getbootstrap.com/docs/5.3/utilities/background



Standard color palette variables used for theme colors.



```scss

$blue:    #0d6efd;

$indigo:  #6610f2;

$purple:  #6f42c1;

$pink:    #d63384;

$red:     #dc3545;

$orange:  #fd7e14;

$yellow:  #ffc107;

$green:   #198754;

$teal:    #20c997;

$cyan:    #0dcaf0;

```



\--------------------------------



\### Modify and add utilities



Source: https://getbootstrap.com/docs/5.3/utilities/api



Combine multiple modifications into a single map-merge call to add, remove, or update utility properties.



```scss

@import "bootstrap/scss/functions";

@import "bootstrap/scss/variables";

@import "bootstrap/scss/variables-dark";

@import "bootstrap/scss/maps";

@import "bootstrap/scss/mixins";

@import "bootstrap/scss/utilities";



$utilities: map-merge(

&#x20; $utilities,

&#x20; (

&#x20;   // Remove the `width` utility

&#x20;   "width": null,

&#x20;   // Make an existing utility responsive

&#x20;   "border": map-merge(

&#x20;     map-get($utilities, "border"),

&#x20;     ( responsive: true ),

&#x20;   ),

&#x20;   // Add new utilities

&#x20;   "cursor": (

&#x20;     property: cursor,

&#x20;     class: cursor,

&#x20;     responsive: true,

&#x20;     values: auto pointer grab,

&#x20;   )

&#x20; )

);



@import "bootstrap/scss/utilities/api";

```



\--------------------------------



\### Generate Contextual Alert Classes



Source: https://getbootstrap.com/docs/5.3/components/alerts



A Sass loop that iterates over theme colors to generate modifier classes for alerts.



```scss

// Generate contextual modifier classes for colorizing the alert

@each $state in map-keys($theme-colors) {

&#x20; .alert-#{$state} {

&#x20;   --#{$prefix}alert-color: var(--#{$prefix}#{$state}-text-emphasis);

&#x20;   --#{$prefix}alert-bg: var(--#{$prefix}#{$state}-bg-subtle);

&#x20;   --#{$prefix}alert-border-color: var(--#{$prefix}#{$state}-border-subtle);

&#x20;   --#{$prefix}alert-link-color: var(--#{$prefix}#{$state}-text-emphasis);

&#x20; }

}

```



\--------------------------------



\### Display badges in buttons



Source: https://getbootstrap.com/docs/5.3/components/badge



Integrate badges into buttons to serve as counters or status indicators.



```html

<button type="button" class="btn btn-primary">

&#x20; Notifications <span class="badge text-bg-secondary">4</span>

</button>

```



\--------------------------------



\### Apply color-scheme mixin



Source: https://getbootstrap.com/docs/5.3/customize/sass



Use the color-scheme mixin to apply specific styles based on the user's light or dark mode preference.



```scss

.custom-element {

&#x20; @include color-scheme(light) {

&#x20;   // Insert light mode styles here

&#x20; }



&#x20; @include color-scheme(dark) {

&#x20;   // Insert dark mode styles here

&#x20; }

}

```



\--------------------------------



\### Apply bordered table styles



Source: https://getbootstrap.com/docs/5.3/content/tables



Use the .table-bordered class to add borders to all sides of the table and cells.



```html

<table class="table table-bordered">

&#x20; ...

</table>

```



\--------------------------------



\### Apply flex-grow to a flex item



Source: https://getbootstrap.com/docs/5.3/utilities/flex



Toggles a flex item's ability to expand and consume available space.



```html

<div class="d-flex">

&#x20; <div class="p-2 flex-grow-1">Flex item</div>

&#x20; <div class="p-2">Flex item</div>

&#x20; <div class="p-2">Third flex item</div>

</div>

```



\--------------------------------



\### Define Toast CSS Variables



Source: https://getbootstrap.com/docs/5.3/components/toasts



Local CSS variables used within the .toast component for styling and layout.



```scss

\--#{$prefix}toast-zindex: #{$zindex-toast};

\--#{$prefix}toast-padding-x: #{$toast-padding-x};

\--#{$prefix}toast-padding-y: #{$toast-padding-y};

\--#{$prefix}toast-spacing: #{$toast-spacing};

\--#{$prefix}toast-max-width: #{$toast-max-width};

@include rfs($toast-font-size, --#{$prefix}toast-font-size);

\--#{$prefix}toast-color: #{$toast-color};

\--#{$prefix}toast-bg: #{$toast-background-color};

\--#{$prefix}toast-border-width: #{$toast-border-width};

\--#{$prefix}toast-border-color: #{$toast-border-color};

\--#{$prefix}toast-border-radius: #{$toast-border-radius};

\--#{$prefix}toast-box-shadow: #{$toast-box-shadow};

\--#{$prefix}toast-header-color: #{$toast-header-color};

\--#{$prefix}toast-header-bg: #{$toast-header-background-color};

\--#{$prefix}toast-header-border-color: #{$toast-header-border-color};

```



\--------------------------------



\### Apply margin to spinners



Source: https://getbootstrap.com/docs/5.3/components/spinners



Use margin utility classes to add spacing around the spinner.



```html

<div class="spinner-border m-5" role="status">

&#x20; <span class="visually-hidden">Loading...</span>

</div>

```



\--------------------------------



\### Configure Sass border variables



Source: https://getbootstrap.com/docs/5.3/utilities/borders



Sass variables used to define default border widths, styles, colors, and radii.



```scss

$border-width:                1px;

$border-widths: (

&#x20; 1: 1px,

&#x20; 2: 2px,

&#x20; 3: 3px,

&#x20; 4: 4px,

&#x20; 5: 5px

);

$border-style:                solid;

$border-color:                $gray-300;

$border-color-translucent:    rgba($black, .175);

```



```scss

$border-radius:               .375rem;

$border-radius-sm:            .25rem;

$border-radius-lg:            .5rem;

$border-radius-xl:            1rem;

$border-radius-xxl:           2rem;

$border-radius-pill:          50rem;

```



\--------------------------------



\### Size Attribute



Source: https://getbootstrap.com/docs/5.3/forms/select



The standard HTML size attribute can be used to define the number of visible options.



```html

<select class="form-select" size="3" aria-label="Size 3 select example">

&#x20; <option selected>Open this select menu</option>

&#x20; <option value="1">One</option>

&#x20; <option value="2">Two</option>

&#x20; <option value="3">Three</option>

</select>

```



\--------------------------------



\### Create a vertical radio button group



Source: https://getbootstrap.com/docs/5.3/components/button-group



Use radio inputs with the .btn-check class to create toggleable vertical button groups.



```html

<div class="btn-group-vertical" role="group" aria-label="Vertical radio toggle button group">

&#x20; <input type="radio" class="btn-check" name="vbtn-radio" id="vbtn-radio1" autocomplete="off" checked>

&#x20; <label class="btn btn-outline-danger" for="vbtn-radio1">Radio 1</label>

&#x20; <input type="radio" class="btn-check" name="vbtn-radio" id="vbtn-radio2" autocomplete="off">

&#x20; <label class="btn btn-outline-danger" for="vbtn-radio2">Radio 2</label>

&#x20; <input type="radio" class="btn-check" name="vbtn-radio" id="vbtn-radio3" autocomplete="off">

&#x20; <label class="btn btn-outline-danger" for="vbtn-radio3">Radio 3</label>

</div>

```



\--------------------------------



\### Define Alert CSS Variables



Source: https://getbootstrap.com/docs/5.3/components/alerts



Local CSS variables used on the .alert component for real-time customization.



```scss

\--#{$prefix}alert-bg: transparent;

\--#{$prefix}alert-padding-x: #{$alert-padding-x};

\--#{$prefix}alert-padding-y: #{$alert-padding-y};

\--#{$prefix}alert-margin-bottom: #{$alert-margin-bottom};

\--#{$prefix}alert-color: inherit;

\--#{$prefix}alert-border-color: transparent;

\--#{$prefix}alert-border: #{$alert-border-width} solid var(--#{$prefix}alert-border-color);

\--#{$prefix}alert-border-radius: #{$alert-border-radius};

\--#{$prefix}alert-link-color: inherit;

```



\--------------------------------



\### Bootstrap color manipulation functions



Source: https://getbootstrap.com/docs/5.3/customize/sass



Definitions for tint-color, shade-color, and shift-color functions used to mix colors with white or black.



```scss

// Tint a color: mix a color with white

@function tint-color($color, $weight) {

&#x20; @return mix(white, $color, $weight);

}



// Shade a color: mix a color with black

@function shade-color($color, $weight) {

&#x20; @return mix(black, $color, $weight);

}



// Shade the color if the weight is positive, else tint it

@function shift-color($color, $weight) {

&#x20; @return if($weight > 0, shade-color($color, $weight), tint-color($color, -$weight));

}



```



\--------------------------------



\### Basic Carousel Implementation



Source: https://getbootstrap.com/docs/5.3/components/carousel



A standard carousel structure with three slides and previous/next navigation buttons. Ensure one slide has the .active class and the carousel container has a unique ID.



```html

<div id="carouselExample" class="carousel slide">

&#x20; <div class="carousel-inner">

&#x20;   <div class="carousel-item active">

&#x20;     <img src="..." class="d-block w-100" alt="...">

&#x20;   </div>

&#x20;   <div class="carousel-item">

&#x20;     <img src="..." class="d-block w-100" alt="...">

&#x20;   </div>

&#x20;   <div class="carousel-item">

&#x20;     <img src="..." class="d-block w-100" alt="...">

&#x20;   </div>

&#x20; </div>

&#x20; <button class="carousel-control-prev" type="button" data-bs-target="#carouselExample" data-bs-slide="prev">

&#x20;   <span class="carousel-control-prev-icon" aria-hidden="true"></span>

&#x20;   <span class="visually-hidden">Previous</span>

&#x20; </button>

&#x20; <button class="carousel-control-next" type="button" data-bs-target="#carouselExample" data-bs-slide="next">

&#x20;   <span class="carousel-control-next-icon" aria-hidden="true"></span>

&#x20;   <span class="visually-hidden">Next</span>

&#x20; </button>

</div>

```



\--------------------------------



\### Display text in a navbar



Source: https://getbootstrap.com/docs/5.3/components/navbar



Uses the .navbar-text class to ensure proper vertical alignment and spacing for inline text strings.



```html

<nav class="navbar bg-body-tertiary">

&#x20; <div class="container-fluid">

&#x20;   <span class="navbar-text">

&#x20;     Navbar text with an inline element

&#x20;   </span>

&#x20; </div>

</nav>

```



```html

<nav class="navbar navbar-expand-lg bg-body-tertiary">

&#x20; <div class="container-fluid">

&#x20;   <a class="navbar-brand" href="#">Navbar w/ text</a>

&#x20;   <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarText" aria-controls="navbarText" aria-expanded="false" aria-label="Toggle navigation">

&#x20;     <span class="navbar-toggler-icon"></span>

&#x20;   </button>

&#x20;   <div class="collapse navbar-collapse" id="navbarText">

&#x20;     <ul class="navbar-nav me-auto mb-2 mb-lg-0">

&#x20;       <li class="nav-item">

&#x20;         <a class="nav-link active" aria-current="page" href="#">Home</a>

&#x20;       </li>

&#x20;       <li class="nav-item">

&#x20;         <a class="nav-link" href="#">Features</a>

&#x20;       </li>

&#x20;       <li class="nav-item">

&#x20;         <a class="nav-link" href="#">Pricing</a>

&#x20;       </li>

&#x20;     </ul>

&#x20;     <span class="navbar-text">

&#x20;       Navbar text with an inline element

&#x20;     </span>

&#x20;   </div>

&#x20; </div>

</nav>

```

