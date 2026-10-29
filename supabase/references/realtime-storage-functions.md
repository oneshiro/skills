# Supabase — Realtime, Storage & Functions

Sourced snippets (30 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Initialize a new Supabase project

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/functions/quickstart.mdx

Create a new project directory and initialize Supabase configuration files using the CLI.

```bash
mkdir my-edge-functions-project
cd my-edge-functions-project
supabase init
```


--------------------------------

### Start local Supabase services and serve the function

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/functions/quickstart.mdx

Starts local Docker services and serves the `hello-world` function with hot reloading enabled at localhost:54321/functions/v1/hello-world.

```bash
supabase start  # Start all Supabase services
supabase functions serve hello-world
```


--------------------------------

### Initialize Supabase in an existing project directory

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/functions/quickstart.mdx

Navigate to an existing project directory and run supabase init to generate the supabase directory and config.toml file.

```bash
cd your-existing-project
supabase init # Initialize Supabase, if you haven't already
```


--------------------------------

### Install @supabase/supabase-js and fetch-retry

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/api/automatic-retries-in-supabase-js.mdx

Install both the Supabase client library and the fetch-retry package using npm.

```bash
npm install @supabase/supabase-js fetch-retry
```


--------------------------------

### Start local Supabase services with Supabase CLI

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/functions/examples/mcp-server-mcp-lite.mdx

Run this command from your project directory to start the local Supabase environment.

```bash
supabase start
```


--------------------------------

### Initialize Supabase client in Kotlin

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/realtime/broadcast.mdx

Create the Supabase client and install the Realtime plugin with your project URL and publishable key.

```kotlin
val supabaseUrl = "https://<project>.supabase.co"
val supabaseKey = "<sb_publishable_... key>"
val supabase = createSupabaseClient(supabaseUrl, supabaseKey) {
    install(Realtime)
}
```


--------------------------------

### Deploy Edge Functions with Bitbucket Pipelines

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/functions/deploy.mdx

Defines a Bitbucket pipeline workflow that installs the Supabase CLI in a setup step and runs function deployment using Docker services.

```yaml
image: node:20

pipelines:
  default:
    - step:
        name: Setup
        caches:
          - node
        script:
          - npm i supabase
    - parallel:
        - step:
            name: Functions Deploy
            script:
              - npx supabase init
              - npx supabase functions deploy --debug
            services:
              - docker
```


--------------------------------

### Install Supabase client library with Conda

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/realtime/getting_started.mdx

Installs the Supabase Python SDK from conda-forge.

```bash
conda install -c conda-forge supabase
```


--------------------------------

### Test Iceberg REST Catalog connection with cURL

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/storage/analytics/connecting-to-analytics-bucket.mdx

Send a GET request to the Iceberg REST Catalog configuration endpoint to verify your credentials and setup. Pass your Supabase service key as a Bearer token in the Authorization header.

```bash
curl \
  --request GET -sL \
  --url 'https://<your-project-ref>.supabase.co/storage/v1/iceberg/v1/config?warehouse=<bucket-name>' \
  --header 'Authorization: Bearer <your-service-key>'
```


--------------------------------

### Install Supabase client library with pip

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/realtime/getting_started.mdx

Installs the Supabase Python SDK using the pip package manager.

```bash
pip install supabase
```


--------------------------------

### Install PySpark

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/storage/analytics/examples/apache-spark.mdx

Installs the PySpark package for Python-based analytical processing workflows.

```bash
pip install pyspark

```


--------------------------------

### Start local Supabase environment and serve function

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/functions/examples/sentry-monitoring.mdx

Starts local Supabase services and runs the Edge Function locally with JWT verification bypassed for testing.

```bash
supabase start
supabase functions serve --no-verify-jwt
```


--------------------------------

### Initialize Supabase client in C#

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/realtime/broadcast.mdx

Instantiate the Supabase client with your project URL and key, then call InitializeAsync.

```csharp
var supabase = new Supabase.Client(
    "https://<project>.supabase.co",
    "<sb_publishable_... key>"
);
await supabase.InitializeAsync();
```


--------------------------------

### Install Supabase client library with .NET CLI

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/realtime/getting_started.mdx

Adds the Supabase C# NuGet package to a .NET project.

```bash
dotnet add package Supabase
```


--------------------------------

### Start local Supabase stack and serve Edge Function

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/functions/examples/image-manipulation.mdx

Starts the local Supabase environment and serves the Edge Functions locally without JWT verification.

```bash
supabase start
supabase functions serve --no-verify-jwt

```


--------------------------------

### Initialize Supabase client in Kotlin

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/realtime/presence.mdx

Initializes a Supabase client in Kotlin with the Realtime plugin installed.

```kotlin
val supabaseUrl = "https://<project>.supabase.co"
val supabaseKey = "<sb_publishable_... key>"
val supabase = createSupabaseClient(supabaseUrl, supabaseKey) {
    install(Realtime)
}
```


--------------------------------

### Copy environment variable template

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/functions/examples/upstash-redis.mdx

Copy the example environment file to configure UPSTASH_REDIS_REST_URL and UPSTASH_REDIS_REST_TOKEN credentials.

```bash
cp supabase/functions/upstash-redis-counter/.env.example supabase/functions/upstash-redis-counter/.env
```


--------------------------------

### Start the Ollama server

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/functions/ai-models.mdx

Runs the local Ollama server to handle model inference requests.

```bash
ollama serve
```


--------------------------------

### Broadcast text frame example

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/realtime/protocol.mdx

Example text-frame broadcast event message on protocol version 2.0.0.

```json
[
  null,
  null,
  "realtime:chat-room",
  "broadcast",
  {
    "event": "message",
    "type": "broadcast",
    "meta": {
      "id": "006554ce-d22d-469c-877a-88bef47214a3"
    },
    "payload": {
      "id": "513edcc1-4cbc-4274-aa26-c195f7e8c090",
      "content": "oi",
      "username": "hpK9jN2iY-I2HioHWr5ml",
      "createdAt": "2025-11-18T22:44:29Z"
    }
  }
]
```


--------------------------------

### Install Supabase with Iceberg support

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/storage/analytics/examples/pyiceberg.mdx

Install the Supabase Python package with Apache Iceberg extras via pip.

```bash
pip install "supabase[iceberg]"
```


--------------------------------

### Install DuckDB and Iceberg extension

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/storage/analytics/examples/duckdb.mdx

Installs the DuckDB database library and its Iceberg extension package via pip.

```bash
pip install duckdb duckdb-iceberg
```


--------------------------------

### System message postgres_changes example

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/realtime/protocol.mdx

Example message for a successful PostgreSQL subscription status on protocol version 2.0.0.

```json
[
  "13",
  null,
  "realtime:chat-room",
  "system",
  {
    "message": "Subscribed to PostgreSQL",
    "status": "ok",
    "extension": "postgres_changes",
    "channel": "main"
  }
]
```


--------------------------------

### Example custom claims payload

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/api/custom-claims-and-role-based-access-control-rbac.mdx

Example JSON structure showing custom claims attached to a user token.

```json
{
  "user_role": "admin",
  "plan": "TRIAL",
  "user_level": 100,
  "group_name": "Super Guild!",
  "joined_on": "2022-05-20T14:28:18.217Z",
  "group_manager": false,
  "items": ["toothpick", "string", "ring"]
}
```


--------------------------------

### Initialize Supabase client in Python

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/realtime/presence.mdx

Initializes the Supabase Python client using create_client with the project URL and key.

```python
from supabase import create_client

SUPABASE_URL = 'https://<project>.supabase.co'
SUPABASE_KEY = '<sb_publishable_... key>'

supabase = create_client(SUPABASE_URL, SUPABASE_KEY)
```


--------------------------------

### Initialize the Supabase client in Python

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/realtime/getting_started.mdx

Creates a Supabase Client instance using the project URL and API key.

```python
from supabase import create_client, Client

url: str = "https://<project>.supabase.co"
key: str = "<sb_publishable_key>"
supabase: Client = create_client(url, key)
```


--------------------------------

### Initialize Supabase client in Python

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/realtime/broadcast.mdx

Asynchronously initialize the Supabase client using acreate_client with the project URL and key.

```python
import asyncio
from supabase import acreate_client

URL = "https://<project>.supabase.co"
KEY = "<sb_publishable_... key>"

async def create_supabase():
  supabase = await acreate_client(URL, KEY)
  return supabase
```


--------------------------------

### Create a storage bucket using C#

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/storage/buckets/creating-buckets.mdx

Calls CreateBucket with BucketUpsertOptions configured for public access in C#.

```c#
var bucket = await supabase.Storage.CreateBucket("avatars", new BucketUpsertOptions { Public = true });
```


--------------------------------

### Initialize Supabase client in C#

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/realtime/presence.mdx

Creates and initializes a Supabase.Client asynchronously in C#.

```csharp
var supabase = new Supabase.Client(
    "https://<project>.supabase.co",
    "<sb_publishable_... key>"
);
await supabase.InitializeAsync();
```


--------------------------------

### Initialize Supabase project

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/api/rest/generating-python-types.mdx

Initializes a Supabase project configuration in your local working directory prior to generating types.

```bash
npx supabase init
```


--------------------------------

### Install Supabase CLI with npm

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/api/rest/generating-python-types.mdx

Installs the Supabase CLI as a development dependency. The minimum required CLI version for generating Python types is v2.66.0.

```bash
npm i supabase --save-dev
```
