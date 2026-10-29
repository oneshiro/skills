# Supabase — AI, Platform & Security

Sourced snippets (26 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Install and start Roboflow Inference server

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai/integrations/roboflow.mdx

Installs the Roboflow inference packages via pip and starts the local inference server at http://localhost:9001. Requires Docker to be installed on your machine.

```bash
pip install inference inference-cli inference-sdk && inference server start
```


--------------------------------

### Install all Supabase agent skills with the skills CLI

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai-tools/ai-skills.mdx

Installs all Supabase skills at project scope by default so that repository contributors and cloud agents share the setup. Use --global for all projects or --all for all detected agents.

```bash
npx skills add supabase/agent-skills
```


--------------------------------

### View Vercel Postgres psql connection command

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/platform/migrating-to-supabase/vercel-postgres.mdx

Example connection command shown in the Vercel Dashboard under the Storage Quickstart section.

```bash
psql "postgres://default:xxxxxxxxxxxx@yy-yyyyy-yyyyyy-yyyyyyy.us-west-2.aws.neon.tech:5432/verceldb?sslmode=require"
```


--------------------------------

### Initialize and start local Postgres with Supabase CLI

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai/vecs-python-client.mdx

Initializes a project folder and starts a local Postgres database container. Requires Docker to be running on your machine.

```bash
# Initialize your project
supabase init

# Start Postgres
supabase start
```


--------------------------------

### Install the Supabase plugin with npx plugins add

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai-tools/plugins.mdx

Auto-detects installed AI coding agents and installs the Supabase plugin across all of them. Pass the --yes flag to skip the confirmation prompt.

```bash
npx plugins add supabase-community/supabase-plugin
```


--------------------------------

### Initialize and start local Supabase environment

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai/quickstarts/generate-text-embeddings.mdx

Initializes a Supabase configuration in the project root and starts the local Docker development stack using the Supabase CLI.

```shell
supabase init
supabase start
```


--------------------------------

### Neon connection string example

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/platform/migrating-to-supabase/neon.mdx

Example connection string retrieved from the Neon Project Dashboard without pooling enabled.

```bash
postgresql://neondb_owner:xxxxxxxxxxxxxxx-random-word-yyyyyyyy.us-west-2.aws.neon.tech/neondb?sslmode=require
```


--------------------------------

### Install vecs and boto3 libraries

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai/integrations/amazon-bedrock.mdx

Install the required Python client libraries for Amazon Bedrock and Postgres vector storage using pip.

```sh
pip install vecs boto3
```


--------------------------------

### Start the plugin development server with Poetry

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai/examples/building-chatgpt-plugins.mdx

Runs the local retrieval plugin on port 3333 with automatic reloading on file changes.

```bash
poetry run dev
# output
INFO:     Will watch for changes in these directories: ['./chatgpt-retrieval-plugin']
INFO:     Uvicorn running on http://localhost:3333 (Press CTRL+C to quit)
INFO:     Started reloader process [87843] using WatchFiles
INFO:     Started server process [87849]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
```


--------------------------------

### Initialize a new Poetry project

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai/examples/mixpeek-video-search.mdx

Creates a new Python project named video-search.

```shell
poetry new video-search
```


--------------------------------

### Start the local Supabase stack

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai/examples/image-search-openai-clip.mdx

Starts local Supabase services and outputs local environment details, including the local DB URL.

```shell
supabase start
```


--------------------------------

### Provision a Supabase project with Stripe CLI

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/integrations/stripe-projects.mdx

Installs the Stripe Projects plugin, initializes a new application, provisions a Supabase project, and writes credentials to a local .env file.

```bash
stripe plugin install projects
stripe projects init my-app
stripe projects add supabase/project
stripe projects env --sync
```


--------------------------------

### Install Supabase and Mixpeek dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai/examples/mixpeek-video-search.mdx

Adds the Supabase and Mixpeek Python clients to the project using Poetry.

```shell
poetry add supabase mixpeek
```


--------------------------------

### Install dependencies with Poetry

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai/examples/building-chatgpt-plugins.mdx

Installs the required dependencies for the ChatGPT Retrieval Plugin after configuring pyproject.toml.

```bash
poetry install
```


--------------------------------

### Install Poetry with pip

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai/examples/image-search-openai-clip.mdx

Installs the Poetry packaging and dependency management tool using pip.

```shell
pip install poetry
```


--------------------------------

### Install MCP Server block via shadcn CLI

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai-tools/byo-mcp.mdx

Quickly installs a pre-wired Edge Function containing middleware, a whoami tool, and an extensible tool registry.

```bash
npx shadcn@latest add https://supabase.com/library/r/mcp.json
```


--------------------------------

### Initialize pgvector extension, documents table, and match_documents function in SQL

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai/langchain.mdx

Prepares the database for LangChain by enabling the vector extension, creating a documents table with vector embeddings, and defining a match_documents similarity search function.

```sql
-- Enable the pgvector extension to work with embedding vectors
create extension vector
with
  schema extensions;

-- Create a table to store your documents
create table documents (
  id bigserial primary key,
  content text, -- corresponds to Document.pageContent
  metadata jsonb, -- corresponds to Document.metadata
  embedding extensions.vector(1536) -- 1536 works for OpenAI embeddings, change if needed
);

-- Create a function to search for documents
create function match_documents (
  query_embedding extensions.vector(1536),
  match_count int default null,
  filter jsonb DEFAULT '{}'
) returns table (
  id bigint,
  content text,
  metadata jsonb,
  similarity float
)
language plpgsql
as $$
#variable_conflict use_column
begin
  return query
  select
    id,
    content,
    metadata,
    1 - (documents.embedding <=> query_embedding) as similarity
  from documents
  where metadata @> filter
  order by documents.embedding <=> query_embedding
  limit match_count;
end;
$$;
```


--------------------------------

### Handle v1.project.created payload for new projects

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/platform/webhooks/events.mdx

Fires when a project is created and initial setup begins. The project might not be healthy yet upon receiving this event, and source is null for scratch creations.

```json
{
  "actor": { "user_id": "6cf38595-f5ff-43ca-ba0f-84617bbe192e" },
  "source": null
}
```


--------------------------------

### Create a project via Management API

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/integrations/supabase-for-platforms.mdx

Send a POST request to create a new project. To enable scale to zero pricing on Nano instances, omit the desired_instance_size parameter.

```sh
curl https://api.supabase.com/v1/projects \
  --request POST \
  --header "Content-Type: application/json" \
  --header "Authorization: Bearer YOUR_SECRET_TOKEN" \
  --data '{
    "name": "Todo App",
    "organization_slug": "aaaabbbbccccddddeeee",
    "db_pass": "SUPER_SECURE_PASSWORD",
    "region_selection": {
      "type": "smartGroup",
      "code": "americas"
    },
    "desired_instance_size": "micro"
  }'
```


--------------------------------

### Install OpenTelemetry SDK and httpx instrumentation

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/observability/client-side-tracing.mdx

Installs the OpenTelemetry SDK and HTTPX instrumentation packages using uv.

```sh
uv add opentelemetry-sdk opentelemetry-instrumentation-httpx
```


--------------------------------

### Install vecs client library

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai/integrations/roboflow.mdx

Installs the vecs Python package for managing PostgreSQL vector collections in Supabase.

```shell
pip install vecs
```


--------------------------------

### Add package with minimum-release-age in Bun CLI

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/security/npm-security.mdx

Run an ad-hoc package installation in Bun with a specified quarantine period in seconds.

```bash
bun add @supabase/supabase-js --minimum-release-age 604800
```


--------------------------------

### Install packages with min-release-age in npm CLI

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/security/npm-security.mdx

Specify the minimum release age directly on an ad-hoc npm install invocation.

```bash
npm install --min-release-age=7
```


--------------------------------

### Install Vecs in Google Colab

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai/google-colab.mdx

Install the Supabase Vecs client at the top of a Google Colab notebook to manage vector collections.

```py
pip install vecs
```


--------------------------------

### Install a specific Supabase agent skill using --skill

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai-tools/ai-skills.mdx

Installs an individual skill from the Supabase agent skills repository by name.

```bash
npx skills add supabase/agent-skills --skill SKILL_NAME
```


--------------------------------

### Install dependencies using Poetry

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/ai/examples/image-search-openai-clip.mdx

Installs the required packages: vecs for vector storage, sentence-transformers for CLIP embeddings, and matplotlib for displaying search results.

```shell
poetry add vecs sentence-transformers matplotlib
```
