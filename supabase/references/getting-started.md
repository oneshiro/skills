# Supabase — Getting Started

Sourced snippets (49 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Start development server

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-redwoodjs.mdx

Starts the RedwoodJS development server to test the initial setup.

```bash
yarn rw dev
```


--------------------------------

### Start local Supabase stack with supabase start

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/api-keys.mdx

Initialize and start local Supabase containers. Output includes local authentication keys under Authentication Keys.

```bash
supabase start
```


--------------------------------

### Install @supabase/server

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-solidjs.mdx

Install the @supabase/server package to support server-side rendering and authenticated API routes in SolidStart.

```bash
npm install @supabase/server
```


--------------------------------

### Start Expo development server with npm start

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-expo-react-native.mdx

Starts the local development server to test the completed Expo application across target environments.

```bash
npm start
```


--------------------------------

### Configure Supabase auth via Redwood CLI

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-redwoodjs.mdx

Executes the setup auth command to install supabase-js and configure Supabase authentication in the RedwoodJS application.

```bash
yarn redwood setup auth supabase
```

```bash
✔ Generating auth lib...
  ✔ Successfully wrote file `./api/src/lib/auth.js`
  ✔ Adding auth config to web...
  ✔ Adding auth config to GraphQL API...
  ✔ Adding required web packages...
  ✔ Installing packages...
  ✔ One more thing...

  You will need to add your Supabase URL (SUPABASE_URL), public API KEY,
  and JWT SECRET (SUPABASE_KEY, and SUPABASE_JWT_SECRET) to your .env file.
```


--------------------------------

### Bootstrap Hono example app with Supabase CLI

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/hono.mdx

Bootstraps a new Hono example application from the Supabase Samples repository using the CLI.

```bash
npx supabase@latest bootstrap hono
```


--------------------------------

### Create a blank Reflex app with uv

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/reflex.mdx

Initializes a new directory with uv, adds Reflex as a dependency, and scaffolds a blank project template.

```bash
mkdir my_app && cd my_app
uv init
uv add reflex
uv run reflex init --template blank
```


--------------------------------

### Start Laravel development server

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/laravel.mdx

Start the local development server to test authentication and application features.

```bash
php artisan serve
```


--------------------------------

### Install Supabase client library and Node adapter

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/astrojs.mdx

Install @supabase/supabase-js and the @astrojs/node adapter to enable server-side rendering support in Astro.

```bash
npm install @supabase/supabase-js @astrojs/node
```


--------------------------------

### Initialize a SvelteKit project

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-sveltekit.mdx

Create a minimal SvelteKit project with TypeScript and install dependencies.

```bash
npx sv create supabase-sveltekit
cd supabase-sveltekit
npm install
```


--------------------------------

### Install Flask and Supabase client

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/flask.mdx

Installs the Flask framework and the supabase-py client library via pip.

```bash
pip install flask supabase
```


--------------------------------

### Start the Reflex development server with uv

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/reflex.mdx

Runs the local Reflex development server accessible at http://localhost:3000 to display the loaded data.

```bash
uv run reflex run
```


--------------------------------

### Create a TanStack Start app

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/tanstack.mdx

Create a new TanStack Start application using the official CLI tool.

```bash
npx @tanstack/cli@latest create my-app
```


--------------------------------

### Start the Rails development server

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/ruby-on-rails.mdx

Starts the local development server at http://127.0.0.1:3000.

```bash
bin/rails server
```


--------------------------------

### Install project dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/hono.mdx

Installs the required project dependencies including @supabase/supabase-js and @supabase/ssr.

```bash
npm install
```


--------------------------------

### Install Laravel Breeze authentication template

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/laravel.mdx

Install and configure Laravel Breeze for user authentication scaffolding.

```bash
composer require laravel/breeze --dev
php artisan breeze:install blade
```


--------------------------------

### Install Refine Inferencer dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/refine.mdx

Installs packages required by the `<HeadlessInferencer />` component. Install these dependencies to avoid errors during page generation.

```bash
npm install @refinedev/react-table @refinedev/react-hook-form react-live
```


--------------------------------

### Install Supabase client libraries

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/tanstack.mdx

Navigate into the project directory and install supabase-js along with @supabase/ssr for server-side cookie session handling.

```bash
cd my-app && npm install @supabase/supabase-js @supabase/ssr
```


--------------------------------

### Create AppView entry point in Swift

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-swift.mdx

Create `AppView.swift` to manage application routing based on authentication state changes from `supabase.auth.authStateChanges`.

```swift
import SwiftUI

struct AppView: View {
  @State var isAuthenticated = false

  var body: some View {
    Group {
      if isAuthenticated {
        ProfileView()
      } else {
        AuthView()
      }
    }
    .task {
      for await state in supabase.auth.authStateChanges {
        if [.initialSession, .signedIn, .signedOut].contains(state.event) {
          isAuthenticated = state.session != nil
        }
      }
    }
  }
}
```


--------------------------------

### Install @nuxtjs/supabase module

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-nuxt-3.mdx

Installs the Nuxt Supabase module as a development dependency.

```bash
npm install @nuxtjs/supabase --save-dev
```


--------------------------------

### Install Supabase client and storage dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/expo-react-native.mdx

Installs `@supabase/supabase-js` along with `react-native-url-polyfill` and `expo-sqlite` for URL handling and session persistence.

```bash
cd my-app && npx expo install @supabase/supabase-js react-native-url-polyfill expo-sqlite
```


--------------------------------

### Install python-dotenv

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/flask.mdx

Installs python-dotenv to load environment variables from the .env file into Python.

```bash
pip install python-dotenv
```


--------------------------------

### Create a React app with Vite

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/reactjs.mdx

Initializes a new React application using the Vite react template.

```bash
npm create vite@latest my-app -- --template react
```


--------------------------------

### Initialize a Flutter app

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-flutter.mdx

Initializes a new Flutter project named supabase_quickstart using the Flutter CLI.

```bash
flutter create supabase_quickstart
```


--------------------------------

### Create a Vue app using npm init

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/vue.mdx

Scaffold a new Vue project using the npm init command.

```sh
npm init vue@latest my-app
```


--------------------------------

### Install expo-image-picker Dependency

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-expo-react-native.mdx

Installs the `expo-image-picker` package to enable profile photo selection in Expo.

```bash
npx expo install expo-image-picker
```


--------------------------------

### Create a Nuxt app using nuxi

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/nuxtjs.mdx

Initialize a new Nuxt application using the nuxi CLI.

```bash
npx nuxi@latest init my-app
```


--------------------------------

### Install @supabase/supabase-js

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/nuxtjs.mdx

Install the Supabase JavaScript client library inside the Nuxt application directory.

```bash
cd my-app && npm install @supabase/supabase-js
```


--------------------------------

### Initialize Ionic React application with Ionic CLI

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-ionic-react.mdx

Installs the Ionic CLI globally, creates a blank Ionic React project named supabase-ionic-react, and navigates into the project directory.

```bash
npm install -g @ionic/cli
ionic start supabase-ionic-react blank --type react
cd supabase-ionic-react
```


--------------------------------

### Create project directory and virtual environment

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/flask.mdx

Sets up a new project folder and activates an isolated Python virtual environment.

```bash
mkdir my-app && cd my-app
python3 -m venv venv
source venv/bin/activate
```


--------------------------------

### Create a SvelteKit app using sv CLI

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/sveltekit.mdx

Scaffold a new SvelteKit application using the official sv CLI tool.

```bash
npx sv create my-app
```


--------------------------------

### Install @supabase/supabase-js dependency

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-ionic-react.mdx

Installs the official Supabase JavaScript client library into the Ionic React project.

```bash
npm install @supabase/supabase-js
```


--------------------------------

### Initialize Supabase client in src/lib/supabaseClient

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/sveltekit.mdx

Create and export a Supabase client instance using static public environment variables.

```javascript
import { createClient } from '@supabase/supabase-js'
import { PUBLIC_SUPABASE_PUBLISHABLE_KEY, PUBLIC_SUPABASE_URL } from '$env/static/public'

export const supabase = createClient(PUBLIC_SUPABASE_URL, PUBLIC_SUPABASE_PUBLISHABLE_KEY)
```

```typescript
import { createClient } from '@supabase/supabase-js'
import { PUBLIC_SUPABASE_PUBLISHABLE_KEY, PUBLIC_SUPABASE_URL } from '$env/static/public'

export const supabase = createClient(PUBLIC_SUPABASE_URL, PUBLIC_SUPABASE_PUBLISHABLE_KEY)
```


--------------------------------

### Start the Flask development server

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/flask.mdx

Runs the Flask app locally on port 5000.

```bash
python app.py
```


--------------------------------

### Start the Expo development server

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/expo-react-native.mdx

Launches the Expo bundler to run the application on mobile devices, iOS simulators, or Android emulators.

```bash
npx expo start
```


--------------------------------

### Initialize Supabase client using createSupabaseClient in MainActivity.kt

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/kotlin.mdx

Create a Supabase client instance configured with Postgrest at the top of MainActivity.kt below the imports. Replace the placeholder URL and key with your project credentials.

```kotlin
import io.github.jan.supabase.postgrest.from
import ...

val supabase = createSupabaseClient(
    supabaseUrl = "YOUR_SUPABASE_URL",
    supabaseKey = "YOUR_SUPABASE_PUBLISHABLE_KEY"
  ) {
    install(Postgrest)
}
...
```


--------------------------------

### Initialize the Supabase client in src/lib/supabaseClient.js

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/reactjs.mdx

Creates and exports the Supabase client instance using environment variables.

```javascript
import { createClient } from '@supabase/supabase-js'

const supabaseUrl = import.meta.env.VITE_SUPABASE_URL
const supabasePublishableKey = import.meta.env.VITE_SUPABASE_PUBLISHABLE_KEY

export const supabase = createClient(supabaseUrl, supabasePublishableKey)
```


--------------------------------

### Initialize a Nuxt 3 app with nuxi

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-nuxt-3.mdx

Creates a new Nuxt 3 project called nuxt-user-management and navigates into the created project directory.

```bash
npx nuxi init nuxt-user-management

cd nuxt-user-management
```


--------------------------------

### Define framework quickstart frontmatter

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/_template.mdx

Specifies the mandatory frontmatter keys required for all framework quickstart markdown documents.

```yaml
---
title: 'Use Supabase with <Framework>'
subtitle: '<one sentence: what the reader builds>'
breadcrumb: 'Framework Quickstarts'
---
```


--------------------------------

### Initialize a React app with Vite

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-react.mdx

Scaffold a new React application named supabase-react using the Vite React template and navigate into the project folder.

```bash
npm create vite@latest supabase-react -- --template react
cd supabase-react
```


--------------------------------

### Install Supabase and AsyncStorage dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-expo-react-native.mdx

Installs the Supabase JavaScript client and React Native AsyncStorage library in an Expo project.

```bash
npx expo install @supabase/supabase-js @react-native-async-storage/async-storage
```


--------------------------------

### Create a Spring Boot project with Spring Initializr

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/spring-boot.mdx

Scaffolds a new Maven-based Spring Boot Java project with Web, Spring Data JPA, and PostgreSQL dependencies using curl, then unzips it.

```bash
curl https://start.spring.io/starter.zip \
  -d dependencies=web,data-jpa,postgresql \
  -d type=maven-project \
  -d language=java \
  -d groupId=com.example \
  -d artifactId=instruments \
  -d name=instruments \
  -o instruments.zip
unzip instruments.zip -d instruments && cd instruments
```


--------------------------------

### Configure main entrypoint in lib/main.dart

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-flutter.mdx

Initializes Supabase with project credentials and configures MaterialApp to display LoginPage or AccountPage based on user authentication status. Also adds theme styling and a BuildContext helper for showing snackbars.

```dart
import 'package:flutter/material.dart';
import 'package:supabase_flutter/supabase_flutter.dart';
import 'package:supabase_quickstart/pages/account_page.dart';
import 'package:supabase_quickstart/pages/login_page.dart';

Future<void> main() async {
  await Supabase.initialize(
    url: 'YOUR_SUPABASE_URL',
    publishableKey: 'YOUR_SUPABASE_PUBLISHABLE_KEY',
  );
  runApp(const MyApp());
}

final supabase = Supabase.instance.client;

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Supabase Flutter',
      theme: ThemeData.dark().copyWith(
        primaryColor: Colors.green,
        textButtonTheme: TextButtonThemeData(
          style: TextButton.styleFrom(
            foregroundColor: Colors.green,
          ),
        ),
        elevatedButtonTheme: ElevatedButtonThemeData(
          style: ElevatedButton.styleFrom(
            foregroundColor: Colors.white,
            backgroundColor: Colors.green,
          ),
        ),
      ),
      home: supabase.auth.currentSession == null
          ? const LoginPage()
          : const AccountPage(),
    );
  }
}

extension ContextExtension on BuildContext {
  void showSnackBar(String message, {bool isError = false}) {
    ScaffoldMessenger.of(this).showSnackBar(
      SnackBar(
        content: Text(message),
        backgroundColor: isError
            ? Theme.of(this).colorScheme.error
            : Theme.of(this).snackBarTheme.backgroundColor,
      ),
    );
  }
}
```


--------------------------------

### Install React Hook Form packages

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-refine.mdx

Installs the required form handling packages for using React Hook Form inside Refine.

```bash
npm install @refinedev/react-hook-form react-hook-form
```


--------------------------------

### Initialize a Vue 3 app with Vite

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-vue-3.mdx

Scaffold a new Vue 3 project named `supabase-vue-3` using Vite and change into the project directory.

```bash
# npm 6.x
npm create vite@latest supabase-vue-3 --template vue

# npm 7+, extra double-dash is needed:
npm create vite@latest supabase-vue-3 -- --template vue

cd supabase-vue-3
```


--------------------------------

### Install SecureStore and AES encryption dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-expo-react-native.mdx

Installs dependencies required to support encrypted session storage via Expo SecureStore and AES encryption.

```bash
npm install @supabase/supabase-js
npm install @react-native-async-storage/async-storage
npm install aes-js react-native-get-random-values
npm install --save-dev @types/aes-js
npx expo install expo-secure-store
```


--------------------------------

### Install Supabase and python-dotenv dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/reflex.mdx

Installs the supabase-py client library and python-dotenv using uv to enable database interaction and environment variable loading.

```bash
uv add supabase python-dotenv
```


--------------------------------

### Initialize Refine app with refine-supabase preset

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/tutorials/with-refine.mdx

Initializes a headless Refine application using plain React and CSS with the Supabase supplementary package (@refinedev/supabase).

```bash
npm create refine-app@latest -- --preset refine-supabase
```


--------------------------------

### Initialize an async Supabase client in my_app/my_app.py

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/getting-started/quickstarts/reflex.mdx

Creates an async Supabase client singleton using acreate_client. This allows the client to be reused across requests within Reflex's async event loop.

```python
import os
import reflex as rx
from supabase import acreate_client, AsyncClient
from dotenv import load_dotenv

load_dotenv()

_supabase: AsyncClient | None = None


async def get_supabase() -> AsyncClient:
    global _supabase
    if _supabase is None:
        _supabase = await acreate_client(
            os.environ.get("SUPABASE_URL"),
            os.environ.get("SUPABASE_PUBLISHABLE_KEY"),
        )
    return _supabase
```
