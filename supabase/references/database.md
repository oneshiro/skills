# Supabase — Database

Sourced snippets (31 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Install Postgres.js

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/postgres-js.mdx

Install the Postgres.js client package via npm.

```shell
npm i postgres
```


--------------------------------

### Create and populate sample table

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/extensions/pg_plan_filter.mdx

Sets up a sample `book` table and inserts 10,000 rows using `generate_series` to prepare for query cost testing.

```sql
create table book(
  id int primary key
);
-- CREATE TABLE

insert into book(id) select * from generate_series(1, 10000);
-- INSERT 0 10000
```


--------------------------------

### Initialize Prisma project with bun

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/prisma.mdx

Initializes a Node project, installs Prisma CLI, TypeScript dependencies, and database client adapters using bun, and runs Prisma initialization.

```bash
bun init -y
bun install prisma tsx @types/pg --save-dev
bun install @prisma/client @prisma/adapter-pg dotenv pg

bunx tsc --init

bunx prisma init
```


--------------------------------

### Deploy Metabase locally using Docker

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/metabase.mdx

Pull the latest Metabase Docker image and start the container on port 3000. Once running, access the setup page at http://localhost:3000/setup.

```sh
docker pull metabase/metabase:latest
```

```sh
docker run -d -p 3000:3000 --name metabase metabase/metabase
```


--------------------------------

### View example cron job start log

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/postgres/postgres-log-config.mdx

Shows sample output produced by pg_cron when cron.log_statement is enabled and a job starts.

```sh
cron job 1 starting: select 1
```


--------------------------------

### Example log output for log_startup_progress_interval

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/postgres/postgres-log-config.mdx

Sample Postgres log indicating startup progress during crash recovery when a task takes longer than the configured interval.

```sh
syncing data directory (pre-fsync), elapsed time: 0.00 s, current path: ./base/4/13456
```


--------------------------------

### Initialize Prisma project with npm

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/prisma.mdx

Initializes a Node project, installs Prisma CLI, TypeScript dependencies, and database client adapters using npm, and runs Prisma initialization.

```bash
npm init -y
npm install prisma tsx @types/pg --save-dev
npm install @prisma/client @prisma/adapter-pg dotenv pg

npx tsc --init

npx prisma init
```


--------------------------------

### net.http_get

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/extensions/pg_net.mdx

Creates an HTTP GET request returning the request's ID. HTTP requests are not started until the transaction is committed.

```APIDOC
## net.http_get

### Description
Creates an HTTP GET request returning the request's ID. HTTP requests are not started until the transaction is committed.

### Function Signature
```sql
net.http_get(
    url text,
    params jsonb default '{}'::jsonb,
    headers jsonb default '{}'::jsonb,
    timeout_milliseconds int default 2000
) returns bigint
```

### Parameters
- **url** (text) - Required - URL for the request.
- **params** (jsonb) - Optional (default: `'{}'::jsonb`) - Key/value pairs to be URL encoded and appended to the `url`.
- **headers** (jsonb) - Optional (default: `'{}'::jsonb`) - Key/values to be included in request headers.
- **timeout_milliseconds** (int) - Optional (default: `2000`) - The maximum number of milliseconds the request may take before being canceled.

### Returns
- **bigint** - The `request_id` reference.

### Usage Example
```sql
select
    net.http_get('https://news.ycombinator.com')
    as request_id;
```
```


--------------------------------

### Create a Blog table and insert sample record

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/extensions/pg_graphql.mdx

Sets up a sample table and inserts a row to demonstrate querying reflected GraphQL collections.

```sql
create table "Blog"(
  id serial primary key,
  name text not null,
  description text
);

insert into "Blog"(name)
values ('My Blog');
```


--------------------------------

### Create and populate sample account table

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/extensions/hypopg.mdx

Creates an account table and populates it with 10,000 generated rows to test query planning.

```sql
create table account (
  id int,
  address text
);

insert into account(id, address)
select
  id,
  id || ' main street'
from
  generate_series(1, 10000) id;
```


--------------------------------

### Install pgloader

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/import-data.mdx

Installs the pgloader utility using apt-get on a local machine or server prior to performing data migration.

```bash
$ apt-get install pgloader
```


--------------------------------

### Run initial Prisma migration with bun

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/prisma.mdx

Applies the initial Prisma development migration and generates the Prisma client using bun.

```bash
bunx prisma migrate dev --name first_prisma_migration
bunx prisma generate
```


--------------------------------

### Example query with join, WHERE filters, and ORDER BY

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/query-optimization.mdx

Retrieves customer names and purchase dates by joining the customers and orders tables, filtering by sign_up_date and status, and sorting by date_of_purchase.

```sql
select
  a.name,
  b.date_of_purchase
from
  customers as a
  join orders as b on a.id = b.customer_id
where a.sign_up_date > '2023-01-01' and b.status = 'shipped'
order by b.date_of_purchase
limit 10;
```


--------------------------------

### Create sample tables and insert relation data in SQL

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/joins-and-nesting.mdx

Sets up the orchestral_sections and instruments tables with a foreign key relationship and sample rows.

```sql
create table orchestral_sections (
  "id" serial primary key,
  "name" text
);

insert into orchestral_sections
  (id, name)
values
  (1, 'strings'),
  (2, 'woodwinds'),
  (3, 'percussion');

create table instruments (
  "id" serial primary key,
  "name" text,
  "section_id" int references orchestral_sections
);

insert into instruments
  (id, name, section_id)
values
  (1, 'violin', 1),
  (2, 'viola', 1),
  (3, 'flute', 2),
  (4, 'oboe', 2);
```


--------------------------------

### Run initial Prisma migration with npm

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/prisma.mdx

Applies the initial Prisma development migration and generates the Prisma client using npm.

```bash
npx prisma migrate dev --name first_prisma_migration
npx prisma generate
```


--------------------------------

### Initialize Prisma project with pnpm

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/prisma.mdx

Initializes a Node project, installs Prisma CLI, TypeScript dependencies, and database client adapters using pnpm, and runs Prisma initialization.

```bash
pnpm init
pnpm install prisma tsx @types/pg --save-dev
pnpm install @prisma/client @prisma/adapter-pg dotenv pg

pnpx tsc --init

pnpx prisma init
```


--------------------------------

### Create sample books table and insert records in SQL

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/full-text-search.mdx

Creates a books table with title, author, and description columns and populates it with sample records for full text search testing.

```sql
create table books (
  id serial primary key,
  title text,
  author text,
  description text
);

insert into books
  (title, author, description)
values
  (
    'The Poky Little Puppy',
    'Janette Sebring Lowrey',
    'Puppy is slower than other, bigger animals.'
  ),
  ('The Tale of Peter Rabbit', 'Beatrix Potter', 'Rabbit eats some vegetables.'),
  ('Tootle', 'Gertrude Crampton', 'Little toy train has big dreams.'),
  (
    'Green Eggs and Ham',
    'Dr. Seuss',
    'Sam has changing food preferences and eats unusually colored food.'
  ),
  (
    'Harry Potter and the Goblet of Fire',
    'J.K. Rowling',
    'Fourth year of school starts, big drama ensues.'
  );
```


--------------------------------

### Create and populate instruments table

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/debugging-performance.mdx

Sets up the sample instruments table with primary key and text columns, and inserts initial records.

```sql
create table instruments (
  id int8 primary key,
  name text
);

insert into instruments
  (id, name)
values
  (1, 'violin'),
  (2, 'viola'),
  (3, 'cello');
```


--------------------------------

### View log_connections example output

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/postgres/postgres-log-config.mdx

Sample log output emitted when a client establishes a database connection, capturing connection receipt, authorization, and authentication details.

```sh
connection received: host=127.0.0.1
connection authorized: user=postgres database=postgres application_name=Supavisor auth_query
connection authenticated: identity="pgbouncer" method=scram-sha-256
```


--------------------------------

### View example log output with query subfield

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/postgres/postgres-log-config.mdx

Displays an example log entry illustrating how the query subfield captures the offending query when log_min_error_statement criteria are satisfied.

```sh
duplicate key value violates unique constraint "example_pkey"
...
# affiliated subfield
query: "insert into example (id) values (1), (1);
```


--------------------------------

### Initialize Prisma project with yarn

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/prisma.mdx

Initializes a Node project, installs Prisma CLI, TypeScript dependencies, and database client adapters using yarn, and runs Prisma initialization.

```bash
yarn init -y
yarn add prisma tsx @types/pg --save-dev
yarn add @prisma/client @prisma/adapter-pg dotenv pg

yarn tsc --init

yarn prisma init
```


--------------------------------

### Run initial Prisma migration with pnpm

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/prisma.mdx

Applies the initial Prisma development migration and generates the Prisma client using pnpm.

```bash
pnpx prisma migrate dev --name first_prisma_migration
pnpx prisma generate
```


--------------------------------

### View example auto_explain query plan log

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/postgres/postgres-log-config.mdx

Shows sample output recorded by auto_explain including query duration, query text, and execution plan details.

```sh
duration: 1661.934 ms plan: Query Text: SELECT * FROM example;
Seq Scan on example (cost=0.00..1443.00 rows=100000 width=36)
```


--------------------------------

### Create example persons table

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/postgres/indexes.mdx

Defines an example persons table used for demonstrating index operations in Postgres.

```sql
create table persons (
  id bigint generated by default as identity primary key,
  age int,
  height int,
  weight int,
  name text,
  deceased boolean
);
```


--------------------------------

### Run initial Prisma migration with yarn

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/prisma.mdx

Applies the initial Prisma development migration and generates the Prisma client using yarn.

```bash
yarn prisma migrate dev --name first_prisma_migration
yarn prisma generate
```


--------------------------------

### Check Postgres server start time

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/custom-postgres-config.mdx

Returns the server postmaster start time to confirm if a database restart has occurred.

```sql
-- If the timestamp hasn’t changed, no restart occurred
select pg_postmaster_start_time();
```


--------------------------------

### Create sample Star Wars planets and people tables in SQL

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/functions.mdx

Creates sample tables for planets and people with foreign key references and inserts seed data.

```sql
create table planets (
  id serial primary key,
  name text
);

insert into planets
  (name)
values
  ('Tatooine'),
  ('Alderaan'),
  ('Kashyyyk');

create table people (
  id serial primary key,
  name text,
  planet_id bigint references planets
);

insert into people
  (name, planet_id)
values
  ('Anakin Skywalker', 1),
  ('Luke Skywalker', 1),
  ('Princess Leia', 2),
  ('Chewbacca', 3);
```


--------------------------------

### Install Drizzle and dependencies

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/drizzle.mdx

Installs the required Drizzle ORM, postgres driver, and Drizzle Kit development dependency via npm.

```shell
npm i drizzle-orm postgres
npm i -D drizzle-kit
```


--------------------------------

### Create sample hierarchy tables and data

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/postgres/cascade-deletes.mdx

Sets up grandparent, parent, and child tables with foreign key constraints and inserts initial relational records.

```sql
create table grandparent (
  id serial primary key,
  name text
);

create table parent (
  id serial primary key,
  name text,
  parent_id integer references grandparent (id)
    on delete cascade
);

create table child (
  id serial primary key,
  name text,
  father integer references parent (id)
    on delete restrict
);

insert into grandparent
  (id, name)
values
  (1, 'Elizabeth');

insert into parent
  (id, name, parent_id)
values
  (1, 'Charles', 1);

insert into parent
  (id, name, parent_id)
values
  (2, 'Diana', 1);

-- We'll just link the father for now
insert into child
  (id, name, father)
values
  (1, 'William', 1);
```


--------------------------------

### Create and populate sample coordinate table

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/extensions/pgrouting.mdx

Creates the sample table wi29 with geometry and float coordinate columns, then inserts a set of points representing city coordinates.

```sql
create table wi29 (
  id bigint,
  x float,
  y float,
  geom gis.geometry
);

insert into wi29 (id, x, y)
values
  (1,20833.3333,17100.0000),
  (2,20900.0000,17066.6667),
  (3,21300.0000,13016.6667),
  (4,21600.0000,14150.0000),
  (5,21600.0000,14966.6667),
  (6,21600.0000,16500.0000),
  (7,22183.3333,13133.3333),
  (8,22583.3333,14300.0000),
  (9,22683.3333,12716.6667),
  (10,23616.6667,15866.6667),
  (11,23700.0000,15933.3333),
  (12,23883.3333,14533.3333),
  (13,24166.6667,13250.0000),
  (14,25149.1667,12365.8333),
  (15,26133.3333,14500.0000),
  (16,26150.0000,10550.0000),
  (17,26283.3333,12766.6667),
  (18,26433.3333,13433.3333),
  (19,26550.0000,13850.0000),
  (20,26733.3333,11683.3333),
  (21,27026.1111,13051.9444),
  (22,27096.1111,13415.8333),
  (23,27153.6111,13203.3333),
  (24,27166.6667,9833.3333),
  (25,27233.3333,10450.0000),
  (26,27233.3333,11783.3333),
  (27,27266.6667,10383.3333),
  (28,27433.3333,12400.0000),
  (29,27462.5000,12992.2222);
```


--------------------------------

### Perform a basic GET request with http_get

Source: https://github.com/supabase/supabase/blob/master/apps/docs/content/guides/database/extensions/http.mdx

Sends an HTTP GET request to a URL and casts the returned content response string to jsonb.

```sql
select
  "status", "content"::jsonb
from
  extensions.http_get('https://jsonplaceholder.typicode.com/todos/1');
```
