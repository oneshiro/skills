# Supabase — Auth

Sourced snippets (29 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Install react-apple-signin-auth for Web

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/quickstarts/with-expo-react-native-social-auth.mdx

Installs the web-specific Apple Sign In authentication library.

```bash
npx expo install react-apple-signin-auth
```


--------------------------------

### Configure TanStack Start environment variables

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/server-side/creating-a-client.mdx

Define Vite-prefixed Supabase credentials in .env.local for TanStack Start.

```bash
VITE_SUPABASE_URL=supabase_project_url
VITE_SUPABASE_PUBLISHABLE_KEY=supabase_publishable_key
```


--------------------------------

### Start development server with npm run dev

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/quickstarts/nextjs.mdx

Launch the local Next.js development server to view the app at http://localhost:3000.

```bash
npm run dev
```


--------------------------------

### Start the React development server

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/quickstarts/react.mdx

Run the local Vite development server to test registration and sign-in functionality in the browser.

```bash
npm run dev
```


--------------------------------

### Install @supabase/supabase-js client library

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/quickstarts/react.mdx

Navigate into the React project directory and install the Supabase JavaScript library.

```bash
cd my-app && npm install @supabase/supabase-js
```


--------------------------------

### Install Supabase and Expo dependencies with expo install

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/quickstarts/with-expo-react-native-social-auth.mdx

Installs the Supabase client and required Expo storage and UI utility packages.

```bash
npx expo install @supabase/supabase-js @react-native-async-storage/async-storage expo-secure-store expo-splash-screen
```


--------------------------------

### Install Supabase libraries and Node adapter

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/quickstarts/astrojs.mdx

Install @supabase/supabase-js, @supabase/ssr, and the @astrojs/node adapter required for server-side auth.

```bash
npm install @supabase/supabase-js @supabase/ssr @astrojs/node
```


--------------------------------

### Install @react-oauth/google for Web Support

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/quickstarts/with-expo-react-native-social-auth.mdx

Installs the @react-oauth/google library dependency for Google Sign-In on the web.

```bash
npx expo install @react-oauth/google
```


--------------------------------

### Install @supabase/ssr

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/server-side/migrating-to-ssr-from-auth-helpers.mdx

Install the @supabase/ssr package to replace the framework-specific Auth Helpers package.

```bash
npm install @supabase/ssr
```


--------------------------------

### Install Supabase client and dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/quickstarts/react-native.mdx

Install @supabase/supabase-js alongside AsyncStorage, RNEUI themed UI library, and react-native-url-polyfill.

```bash
      cd my-app && npx expo install @supabase/supabase-js @react-native-async-storage/async-storage @rneui/themed react-native-url-polyfill
```


--------------------------------

### Sign up a user with email and password in Python

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/passwords.mdx

Signs up a user by calling signUp() with an email, password, and an optional email_redirect_to URL.

```python
data = await supabase.auth.sign_up({
  'email': 'valid.email@supabase.io',
  'password': 'example-password',
  'options': {
    'email_redirect_to': 'https://example.com/welcome',
  },
})
```


--------------------------------

### Install @supabase/supabase-js and @supabase/ssr

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/server-side/creating-a-client.mdx

Install the required Supabase JavaScript and SSR helper packages using your preferred package manager.

```bash
npm install @supabase/supabase-js @supabase/ssr
```

```bash
yarn add @supabase/supabase-js @supabase/ssr
```

```bash
pnpm add @supabase/supabase-js @supabase/ssr
```


--------------------------------

### Sign up a user with email and password in C#

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/passwords.mdx

Calls SignUp() with user credentials and a SignUpOptions object specifying a post-confirmation redirect URL.

```c#
var options = new SignUpOptions { RedirectTo = "https://example.com/welcome" };
var session = await supabase.Auth.SignUp("valid.email@supabase.io", "example-password", options);
```


--------------------------------

### Start the Expo application

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/quickstarts/react-native.mdx

Launch the local Expo development server and follow terminal instructions to run the app on a device or emulator.

```bash
      npm start
```


--------------------------------

### Install Invertase Apple authentication package

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/quickstarts/with-expo-react-native-social-auth.mdx

Installs the @invertase/react-native-apple-authentication library into the Expo project.

```bash
npx expo install @invertase/react-native-apple-authentication
```


--------------------------------

### Start or restart local Supabase instance

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/oauth-server/getting-started.mdx

Starts or restarts the local Supabase CLI instance to apply updated OAuth server settings.

```bash
supabase start
# or if already running:
supabase stop && supabase start
```


--------------------------------

### Example PKCE redirect URL format

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/sessions/pkce-flow.mdx

Shows the format of the redirect URL containing the Auth Code parameter after verification.

```text
https://yourapp.com/...?code=<...>
```


--------------------------------

### Install expo-apple-authentication for iOS

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/quickstarts/with-expo-react-native-social-auth.mdx

Installs the official Expo Apple Authentication library for iOS native authentication.

```bash
npx expo install expo-apple-authentication
```


--------------------------------

### Create an Astro application

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/quickstarts/astrojs.mdx

Scaffold a new Astro project and change into the project directory.

```bash
npm create astro@latest my-app
cd my-app
```


--------------------------------

### Sign up with phone and password in C#

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/passwords.mdx

Call Auth.SignUp specifying SignUpType.Phone, phone number, and password in C#.

```c#
var session = await supabase.Auth.SignUp(SignUpType.Phone, "+13334445555", "some-password");
```


--------------------------------

### Sign in with email and password using Python

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/passwords.mdx

Calls sign_in_with_password() on client.auth with a dictionary containing email and password.

```python
data = client.auth.sign_in_with_password({
  'email': 'valid.email@supabase.io',
  'password': 'example-password',
})
```


--------------------------------

### Install Android Apple authentication dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/quickstarts/with-expo-react-native-social-auth.mdx

Installs the Invertase Apple authentication library and required UUID generator utilities for Android.

```bash
npx expo install @invertase/react-native-apple-authentication react-native-get-random-values uuid
```


--------------------------------

### Sign up with phone and password in Python

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/passwords.mdx

Call auth.sign_up with a dictionary containing phone and password in Python.

```python
supabase.auth.sign_up({
  'phone': "+13334445555",
  'password': "some-password"
})
```


--------------------------------

### Sign up with phone and password via HTTP

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/passwords.mdx

Send a POST request to /auth/v1/signup with phone and password payload.

```bash
curl -X POST 'https://cvwawazfelidkloqmbma.supabase.co/auth/v1/signup' \
-H "apikey: SUPABASE_KEY" \
-H "Content-Type: application/json" \
-d '{
  "phone": "+13334445555",
  "password": "some-password"
}'
```


--------------------------------

### Configure environment variables in .env.local

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/quickstarts/nextjs.mdx

Define Supabase connection settings by setting the project URL and publishable key in .env.local.

```text
NEXT_PUBLIC_SUPABASE_URL=your-project-url
NEXT_PUBLIC_SUPABASE_PUBLISHABLE_KEY=sb_publishable_... key
```


--------------------------------

### Install CocoaPods and run Expo prebuild

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/quickstarts/with-expo-react-native-social-auth.mdx

Installs iOS Pod dependencies and runs the Expo prebuild command to update the native project.

```bash
cd ios
pod install
cd ..
npx expo prebuild
```


--------------------------------

### Create signup_networks table and hook_restrict_signup_by_network function in SQL

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/auth-hooks/before-user-created-hook.mdx

Sets up the `signup_networks` table, inserts sample CIDR network rules, and defines the `hook_restrict_signup_by_network` function to evaluate incoming signup IP addresses.

```sql
-- Create ENUM type for network rule classification
create type signup_network_type as enum ('allow', 'deny');

-- Create the signup_networks table for controlling sign-up access by CIDR
create table if not exists public.signup_networks (
  id serial primary key,
  cidr cidr not null,
  type public.signup_network_type not null,
  reason text default null,
  note text default null,
  created_at timestamp with time zone not null default now(),
  constraint signup_networks_cidr_key unique (cidr)
);

-- Assign appropriate permissions
grant all
  on table public.signup_networks
  to supabase_auth_admin;

revoke all
  on table public.signup_networks
  from authenticated, anon, public;

-- Insert some sample data into the table
insert into public.signup_networks (cidr, type, reason, note)
values
  ('192.0.2.0/24', 'allow', '', 'Corporate VPN'),
  ('198.51.100.158/32', 'deny',
    'Your IP Address has been blocked for abuse.',
    'blocked by abuse: (Ticket: ABUSE-185)'),
  ('203.0.113.0/24', 'deny',
    'Your network has been blocked for abuse.',
    'blocked by abuse: (Ticket: ABUSE-212)');

-- Create the hook function to be called by the auth server
create or replace function public.hook_restrict_signup_by_network(event jsonb)
returns jsonb
language plpgsql
as $$
declare
  ip inet;
  allow_count int;
  deny_count int;
begin
  ip := event->'metadata'->>'ip_address';

  -- Step 1: Check for explicit allow
  select count(*) into allow_count
  from public.signup_networks
  where type = 'allow' and ip::inet << cidr;

  if allow_count > 0 then
    -- If explicitly allowed, allow signup
    return '{}'::jsonb;
  end if;

  -- Step 2: Check for explicit deny
  select count(*) into deny_count
  from public.signup_networks
  where type = 'deny' and ip::inet << cidr;

  if deny_count > 0 then
    return jsonb_build_object(
      'error', jsonb_build_object(
        'message', 'Signups are not allowed from your network.',
        'http_code', 403
      )
    );
  end if;

  -- Step 3: No match: allow by default
  return '{}'::jsonb;
end;
$$;

-- Assign permissions
grant execute
  on function public.hook_restrict_signup_by_network
  to supabase_auth_admin;

revoke execute
  on function public.hook_restrict_signup_by_network
  from authenticated, anon, public;
```


--------------------------------

### Sign in with Bitbucket in C#

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/social-login/auth-bitbucket.mdx

Initiates authentication using SignIn with Provider.Bitbucket and retrieves the authorization URI.

```csharp
var state = await supabase.Auth.SignIn(Provider.Bitbucket);
var signInUrl = state.Uri;
```


--------------------------------

### Sign up user with email and password in Python

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/auth/passwords.mdx

Calls supabase.auth.sign_up with an email and password dictionary to initiate user registration in Python.

```python
data = supabase.auth.sign_up({
  'email': 'valid.email@supabase.io',
  'password': 'example-password',
})
```
