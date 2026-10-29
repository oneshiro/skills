# Docker — Guides & Other Manuals

Sourced snippets (99 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Install dependencies and start the Node server

Source: https://github.com/docker/docs/blob/main/content/guides/wiremock.md

Installs the required npm packages and boots the Node.js application listening on port 5001.

```console
npm install 
npm run start
```

```plaintext
> express-api-starter@1.2.0 start
> node src/index.js

API_ENDPOINT_BASE: http://localhost:8080
..
Listening: http://localhost:5001
```


--------------------------------

### Navigate to backend directory

Source: https://github.com/docker/docs/blob/main/content/guides/localstack.md

Change into the backend/ directory before installing dependencies and starting the application.

```console
$ cd backend/
```


--------------------------------

### Clone example repository

Source: https://github.com/docker/docs/blob/main/content/guides/bake.md

Clone the example repository containing the Dockerfile and docker-bake.hcl setup.

```bash
git clone https://github.com/dvdksn/bakeme.git
cd bakeme
```


--------------------------------

### Start the frontend service

Source: https://github.com/docker/docs/blob/main/content/guides/localstack.md

Navigate to the frontend directory, install required packages, and launch the Vite development server. Once running, access the application locally at http://localhost:5173.

```console
$ cd frontend
```

```console
$ npm install
```

```console
$ npm run dev
```

```console
VITE v5.4.2  ready in 110 ms
➜  Local: http://localhost:5173/
➜  Network: use --host to expose
➜  press h + enter to show help
```


--------------------------------

### Start OpenCode

Source: https://github.com/docker/docs/blob/main/content/guides/opencode-model-runner.md

Run this command from your project directory to launch OpenCode.

```console
$ opencode
```


--------------------------------

### Build and serve the documentation site with Hugo

Source: https://github.com/docker/docs/blob/main/hack/api-docs/README.md

Installs Node dependencies and starts the local Hugo server from the repository root. Uses the committed data/api-reference.json without running the generator.

```console
$ npm ci
$ hugo server
```


--------------------------------

### Navigate to the hello directory and inspect files

Source: https://github.com/docker/docs/blob/main/content/guides/cpp.md

Changes directory into the sample hello project and lists the directory contents.

```bash
$ cd c-plus-plus-docker/hello
$ ls
```

```text
Dockerfile  hello.cpp
```


--------------------------------

### Initialize Go module

Source: https://github.com/docker/docs/blob/main/content/guides/testcontainers-go-getting-started.md

Create the project directory and initialize a new Go module.

```console
$ mkdir testcontainers-go-demo
$ cd testcontainers-go-demo
$ go mod init github.com/testcontainers/testcontainers-go-demo
```


--------------------------------

### Start the Node server with npm start

Source: https://github.com/docker/docs/blob/main/content/guides/wiremock.md

Starts the local Express application server and displays startup logs indicating the port and environment variable status.

```console
$ npm run start
```

```plaintext
> express-api-starter@1.2.0 start
> node src/index.js

API_ENDPOINT_BASE: http://dataservice.accuweather.com
ACCUWEATHER_API_KEY is set: true 
Listening: http://localhost:5001
```


--------------------------------

### Install project dependencies

Source: https://github.com/docker/docs/blob/main/content/guides/testcontainers-go-getting-started.md

Install pgx PostgreSQL driver, testcontainers-go core and postgres modules, and testify for testing assertions.

```console
$ go get github.com/jackc/pgx/v5
$ go get github.com/testcontainers/testcontainers-go
$ go get github.com/testcontainers/testcontainers-go/modules/postgres
$ go get github.com/stretchr/testify
```


--------------------------------

### Define JupyterLab environment in a Dockerfile

Source: https://github.com/docker/docs/blob/main/content/guides/jupyter.md

Defines a custom image starting from quay.io/jupyter/base-notebook and installs dependencies with pip so they do not need to be reinstalled in new containers.

```dockerfile
# syntax=docker/dockerfile:1

FROM quay.io/jupyter/base-notebook
RUN pip install --no-cache-dir matplotlib scikit-learn
```


--------------------------------

### Install dependencies and generate requirements.txt

Source: https://github.com/docker/docs/blob/main/content/guides/testcontainers-python-getting-started.md

Installs psycopg, pytest, and testcontainers with postgres support, then exports the installed packages to requirements.txt.

```console
$ pip install "psycopg[binary]" pytest testcontainers[postgres]
$ pip freeze > requirements.txt
```


--------------------------------

### Install and launch rqt GUI

Source: https://github.com/docker/docs/blob/main/content/guides/ros2.md

Installs rqt plugins and launches the `rqt_gui` graphical interface for ROS 2 introspection and visualization.

```console
$ sudo apt update
```

```console
$ sudo apt install -y 'ros-humble-rqt*'
```

```console
$ ros2 run rqt_gui rqt_gui
```


--------------------------------

### Install and test pre-commit hooks

Source: https://github.com/docker/docs/blob/main/content/guides/python.md

Install pre-commit, configure the git hooks in the repository, and execute a test commit.

```console
$ pip install pre-commit
$ pre-commit install
$ git commit -m "Test commit"  # Automatically runs checks
```


--------------------------------

### View the sample application directory structure

Source: https://github.com/docker/docs/blob/main/content/guides/deno.md

Shows the expected files and folders contained within the cloned deno-docker repository.

```text
├── deno-docker/
│ ├── compose.yml
│ ├── Dockerfile
│ ├── LICENSE
│ ├── server.ts
│ └── README.md
```


--------------------------------

### Install Docker using the convenience script

Source: https://github.com/docker/docs/blob/main/content/includes/install-script.md

Downloads and executes the convenience script to install the latest stable release of Docker Engine on Linux.

```console
$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sudo sh get-docker.sh
Executing docker install script, commit: 7cae5f8b0decc17d6571f9f52eb840fbc13b2737
<...>
```


--------------------------------

### Build and start services with docker compose up

Source: https://github.com/docker/docs/blob/main/content/guides/rust.md

Runs docker compose with the --build flag to compile the image and start all defined containers.

```console
$ docker compose up --build
```


--------------------------------

### Initialize Python virtual environment and install dependencies

Source: https://github.com/docker/docs/blob/main/content/guides/github-sonarqube-sandbox.md

Creates the project directory, sets up and activates an isolated Python virtual environment, and installs e2b and python-dotenv packages.

```bash
mkdir github-sonarqube-workflow
cd github-sonarqube-workflow
```

```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

```bash
pip install e2b python-dotenv
```


--------------------------------

### Install backend dependencies

Source: https://github.com/docker/docs/blob/main/content/guides/localstack.md

Install the required Node.js packages for the backend service.

```console
$ npm install
```


--------------------------------

### Install and run Pyright

Source: https://github.com/docker/docs/blob/main/content/guides/python.md

Install Pyright via pip and run the type checker against the project.

```console
$ pip install pyright
$ pyright
```


--------------------------------

### Clone example voting app repository

Source: https://github.com/docker/docs/blob/main/content/guides/compose-bake.md

Clone the example voting app repository and change directory into the project root.

```console
$ git clone https://github.com/dvdksn/example-voting-app.git
$ cd example-voting-app
```


--------------------------------

### Install Docker pre-releases using test.docker.com script

Source: https://github.com/docker/docs/blob/main/content/includes/install-script.md

Downloads and runs the test convenience script to install Docker packages from the test channel on Linux.

```console
$ curl -fsSL https://test.docker.com -o test-docker.sh
$ sudo sh test-docker.sh
```


--------------------------------

### Install Ruff via pip

Source: https://github.com/docker/docs/blob/main/content/guides/python.md

Install Ruff into the local environment or activated virtual environment.

```console
$ pip install ruff
```


--------------------------------

### Start Docker Desktop on Linux via systemctl

Source: https://github.com/docker/docs/blob/main/content/includes/desktop-linux-launch.md

Starts the Docker Desktop application service for the current user from the terminal.

```console
$ systemctl --user start docker-desktop
```


--------------------------------

### Start the Node.js backend server

Source: https://github.com/docker/docs/blob/main/content/guides/localstack.md

Execute index.js using Node to start the backend application on port 5000.

```console
$ node index.js
```


--------------------------------

### Start the Docker daemon

Source: https://github.com/docker/docs/blob/main/static/get-started/docker_cheatsheet.pdf

Starts the background Docker daemon process.

```bash
docker -d
```


--------------------------------

### Run sync-sandboxes-docs.py to import sandbox docs

Source: https://github.com/docker/docs/blob/main/hack/sandboxes/README.md

Executes the documentation import script from the repository root. Requires Python 3 and gh CLI authenticated for docker/sbx-api.

```console
$ python3 hack/sync-sandboxes-docs.py

```


--------------------------------

### Enable Docker Desktop to start on sign in via systemctl

Source: https://github.com/docker/docs/blob/main/content/includes/desktop-linux-launch.md

Configures the Docker Desktop systemd user service to start automatically upon user sign in.

```console
$ systemctl --user enable docker-desktop
```


--------------------------------

### Set up GenAI stack with CPU acceleration on Linux

Source: https://github.com/docker/docs/blob/main/content/guides/genai-leveraging-rag.md

Clones the GenAI stack repository, starts the Linux CPU Compose profile, and configures environment variables in the .env file.

```bash
git clone https://github.com/docker/genai-stack
docker compose --profile linux up -d
mv env.example .env
nano .env
```

```txt
    NEO4J_URI=neo4j://database:7687
    NEO4J_USERNAME=neo4j
    NEO4J_PASSWORD=password
    OLLAMA_BASE_URL=http://llm:11434
```


--------------------------------

### Build and start containers with docker compose up

Source: https://github.com/docker/docs/blob/main/content/guides/localstack.md

Builds and starts the entire application stack in detached mode from the project root directory.

```console
$ docker compose -f compose.yml up -d --build
```


--------------------------------

### Include prerequisite file

Source: https://github.com/docker/docs/blob/main/COMPONENTS.md

Includes the install-prerequisites.md file from content/includes/.

```markdown
{{</* include "install-prerequisites.md" */>}}
```


--------------------------------

### Build and start the ROS 2 container on Linux

Source: https://github.com/docker/docs/blob/main/content/guides/ros2.md

Builds the Docker image, starts the container in the background, and opens a bash shell inside the container on Linux.

```console
$ cd ws_linux
$ docker compose up -d
$ docker compose exec ros2 /bin/bash
```


--------------------------------

### Install and run Turtlesim inside the container

Source: https://github.com/docker/docs/blob/main/content/guides/ros2.md

Updates apt packages, installs the `ros-humble-turtlesim` package, and launches the Turtlesim GUI simulation window.

```console
$ sudo apt update
```

```console
$ sudo apt install -y ros-humble-turtlesim
```

```console
$ ros2 run turtlesim turtlesim_node
```


--------------------------------

### Initialize PostgreSQL container using classpath SQL script

Source: https://github.com/docker/docs/blob/main/content/guides/testcontainers-java-service-configuration.md

Create an initialization SQL script and copy it into `/docker-entrypoint-initdb.d/` using `MountableFile.forClasspathResource()`. PostgreSQL automatically runs scripts located in this directory when the container starts.

```sql
create table customers (
     id bigint not null,
     name varchar not null,
     primary key (id)
);
```

```java
package com.testcontainers.demo;

import static org.junit.jupiter.api.Assertions.assertFalse;

import java.util.List;
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;
import org.testcontainers.postgresql.PostgreSQLContainer;
import org.testcontainers.junit.jupiter.Container;
import org.testcontainers.junit.jupiter.Testcontainers;
import org.testcontainers.utility.MountableFile;

@Testcontainers
class CustomerServiceTest {

  @Container
  static PostgreSQLContainer postgres = new PostgreSQLContainer(
    "postgres:16-alpine"
  )
    .withCopyFileToContainer(
      MountableFile.forClasspathResource("init-db.sql"),
      "/docker-entrypoint-initdb.d/"
    );

  CustomerService customerService;

  @BeforeEach
  void setUp() {
    customerService =
    new CustomerService(
      postgres.getJdbcUrl(),
      postgres.getUsername(),
      postgres.getPassword()
    );
  }

  @Test
  void shouldGetCustomers() {
    customerService.createCustomer(new Customer(1L, "George"));
    customerService.createCustomer(new Customer(2L, "John"));

    List<Customer> customers = customerService.getAllCustomers();
    assertFalse(customers.isEmpty());
  }
}
```


--------------------------------

### Start Dex container with Docker Compose

Source: https://github.com/docker/docs/blob/main/content/guides/dex.md

Downloads the official Dex Docker image if needed and starts the service in detached mode.

```bash
docker compose up -d
```


--------------------------------

### Start or stop an existing container

Source: https://github.com/docker/docs/blob/main/static/get-started/docker_cheatsheet.pdf

Starts or stops a specific container identified by name or ID.

```bash
docker start|stop <container_name> (or <container-id>)
```


--------------------------------

### Verify docker-dotnet-sample directory structure

Source: https://github.com/docker/docs/blob/main/content/guides/dotnet.md

Displays the required file and folder layout for the docker-dotnet-sample project before building.

```text
├── docker-dotnet-sample/
│ ├── .git/
│ ├── src/
│ ├── .dockerignore
│ ├── compose.yaml
│ ├── Dockerfile
│ └── README.md
```


--------------------------------

### Render example cURL request for operation

Source: https://github.com/docker/docs/blob/main/layouts/api-docs.markdown.md

Generates an example cURL command for invoking the operation.

```console
{{ .curl }}
```


--------------------------------

### Start the Compose stack with docker compose up

Source: https://github.com/docker/docs/blob/main/content/guides/pgadmin.md

Runs the Docker Compose services in the stack and displays server initialization logs indicating that pgAdmin is ready to accept connections.

```console
$ docker compose up
```

```console
pgadmin-1   | [2025-09-22 15:52:47 +0000] [1] [INFO] Starting gunicorn 23.0.0
pgadmin-1   | [2025-09-22 15:52:47 +0000] [1] [INFO] Listening at: http://[::]:80 (1)
pgadmin-1   | [2025-09-22 15:52:47 +0000] [1] [INFO] Using worker: gthread
pgadmin-1   | [2025-09-22 15:52:47 +0000] [119] [INFO] Booting worker with pid: 119
```


--------------------------------

### Clone the docker-gs-ping sample repository

Source: https://github.com/docker/docs/blob/main/content/guides/golang.md

Clones the example Go HTTP microservice repository from GitHub to your local machine.

```console
$ git clone https://github.com/docker/docker-gs-ping
```


--------------------------------

### Start PostgreSQL container with Docker Compose

Source: https://github.com/docker/docs/blob/main/content/guides/postgresql.md

Starts the database container in the background using detached mode.

```console
$ docker compose up -d
```


--------------------------------

### Create project directory for Dex

Source: https://github.com/docker/docs/blob/main/content/guides/dex.md

Initializes and navigates into a new project directory for running the Dex mock server.

```bash
mkdir dex-mock-server
cd dex-mock-server
```


--------------------------------

### Render dynamic variant code example

Source: https://github.com/docker/docs/blob/main/layouts/api-docs.markdown.md

Renders an example code block for a variant in its specified language.

```{{ .language }}
{{ .text }}
```


--------------------------------

### Preview convenience script steps with --dry-run

Source: https://github.com/docker/docs/blob/main/content/includes/install-script.md

Downloads the convenience script from get.docker.com and runs it with the --dry-run flag to inspect the steps without making changes.

```console
$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sudo sh ./get-docker.sh --dry-run
```


--------------------------------

### Verify docker-genai-sample directory structure

Source: https://github.com/docker/docs/blob/main/content/guides/genai-pdf-bot.md

Displays the expected file and directory tree of `docker-genai-sample` after adding all application and Docker assets.

```text
├── docker-genai-sample/
│ ├── .dockerignore
│ ├── .gitignore
│ ├── app.py
│ ├── chains.py
│ ├── compose.yaml
│ ├── env.example
│ ├── requirements.txt
│ ├── util.py
│ ├── Dockerfile
│ ├── LICENSE
│ └── README.md
```


--------------------------------

### Clone the repository with git clone

Source: https://github.com/docker/docs/blob/main/content/guides/genai-video-bot.md

Run this command in the terminal to download the sample application repository.

```console
$ git clone https://github.com/Davidnet/docker-genai.git
```


--------------------------------

### Build and run the Bun application with Docker Compose

Source: https://github.com/docker/docs/blob/main/content/guides/bun.md

Builds and starts the Bun application in the foreground inside the bun-docker directory. Press ctrl+c to stop.

```console
$ docker compose up --build
```


--------------------------------

### Implement customer Repository in customer/repo.go

Source: https://github.com/docker/docs/blob/main/content/guides/testcontainers-go-getting-started.md

Create Repository struct and methods to connect to PostgreSQL, insert customer records, and query customer details by email using pgx.

```go
package customer

import (
	"context"
	"fmt"
	"os"

	"github.com/jackc/pgx/v5"
)

type Repository struct {
	conn *pgx.Conn
}

func NewRepository(ctx context.Context, connStr string) (*Repository, error) {
	conn, err := pgx.Connect(ctx, connStr)
	if err != nil {
		_, _ = fmt.Fprintf(os.Stderr, "Unable to connect to database: %v\n", err)
		return nil, err
	}
	return &Repository{
		conn: conn,
	}, nil
}

func (r Repository) CreateCustomer(ctx context.Context, customer Customer) (Customer, error) {
	err := r.conn.QueryRow(ctx,
		"INSERT INTO customers (name, email) VALUES ($1, $2) RETURNING id",
		customer.Name, customer.Email).Scan(&customer.Id)
	return customer, err
}

func (r Repository) GetCustomerByEmail(ctx context.Context, email string) (Customer, error) {
	var customer Customer
	query := "SELECT id, name, email FROM customers WHERE email = $1"
	err := r.conn.QueryRow(ctx, query, email).
		Scan(&customer.Id, &customer.Name, &customer.Email)
	if err != nil {
		return Customer{}, err
	}
	return customer, nil
}
```


--------------------------------

### Get help with Docker

Source: https://github.com/docker/docs/blob/main/static/get-started/docker_cheatsheet.pdf

Displays help information and available subcommands for the Docker CLI.

```bash
docker --help
```


--------------------------------

### Initialize a Node.js project with npm init

Source: https://github.com/docker/docs/blob/main/content/guides/testcontainers-nodejs-getting-started.md

Initializes a new Node.js project with default package configuration.

```console
$ npm init -y
```


--------------------------------

### Build and start the ROS 2 container on macOS

Source: https://github.com/docker/docs/blob/main/content/guides/ros2.md

Builds the Docker image, starts the container in the background, and opens a bash shell inside the container on macOS.

```console
$ cd ws_mac
$ docker compose up -d
$ docker compose exec ros2 /bin/bash
```


--------------------------------

### Install pg, jest, and @testcontainers/postgresql dependencies

Source: https://github.com/docker/docs/blob/main/content/guides/testcontainers-nodejs-getting-started.md

Installs pg as a runtime dependency and jest along with @testcontainers/postgresql as development dependencies.

```console
$ npm install pg --save
$ npm install jest @testcontainers/postgresql --save-dev
```


--------------------------------

### Install XQuartz on macOS with Homebrew

Source: https://github.com/docker/docs/blob/main/content/guides/ros2.md

Installs the XQuartz cask to provide X11 support on macOS before configuring display settings.

```console
$ brew install --cask xquartz
```


--------------------------------

### Install required packages in Jupyter notebook

Source: https://github.com/docker/docs/blob/main/content/guides/jupyter.md

Installs scikit-learn and matplotlib dependencies directly from within a Jupyter notebook cell.

```console
!pip install matplotlib scikit-learn
```


--------------------------------

### Set up GenAI stack with GPU acceleration on Linux

Source: https://github.com/docker/docs/blob/main/content/guides/genai-leveraging-rag.md

Clones the GenAI stack repository, starts the Linux GPU Compose profile, and configures environment variables in the .env file.

```bash
git clone https://github.com/docker/genai-stack
docker compose --profile linux-gpu up -d
mv env.example .env
nano .env
```

```txt
    NEO4J_URI=neo4j://database:7687
    NEO4J_USERNAME=neo4j
    NEO4J_PASSWORD=password
    OLLAMA_BASE_URL=http://llm-gpu:11434
```


--------------------------------

### Start a secondary application container with Host router rule

Source: https://github.com/docker/docs/blob/main/content/guides/traefik.md

Deploys a welcome-to-docker container configured via Traefik labels to route HTTP traffic matching the welcome.localhost hostname.

```console
$ docker run -d --network=traefik-demo --label 'traefik.http.routers.welcome.rule=Host(`welcome.localhost`)' docker/welcome-to-docker
```


--------------------------------

### Start new MySQL container using existing volume

Source: https://github.com/docker/docs/blob/main/content/guides/databases.md

Starts a new MySQL container attaching the existing volume without repeating initial environment variable configurations.

```console
$ docker run --name my-mysql -v my-db-volume:/var/lib/mysql -d mysql:latest

```


--------------------------------

### Install Vitest and React Testing Library dependencies

Source: https://github.com/docker/docs/blob/main/content/guides/reactjs.md

Installs Vitest, React Testing Library, jest-dom, and jsdom as development dependencies.

```console
$ npm install --save-dev vitest @testing-library/react @testing-library/jest-dom jsdom
```


--------------------------------

### Run hello-world container on Linux

Source: https://github.com/docker/docs/blob/main/COMPONENTS.md

Displays the CLI command to run the hello-world container in a Linux tab.

```console
$ docker run hello-world
```


--------------------------------

### Build and run the Backstage container

Source: https://github.com/docker/docs/blob/main/content/guides/dhi-backstage.md

Builds the backstage:init image and runs it with in-memory sqlite configuration, non-root user 1000, dropped capabilities, and a read-only filesystem.

```console
docker build -t backstage:init .
docker run -d \
    -e APP_CONFIG_backend_database_client='better-sqlite3' \
    -e APP_CONFIG_backend_database_connection=':memory:' \
    -e APP_CONFIG_auth_providers_guest_dangerouslyAllowOutsideDevelopment='true' \
    -p 7007:7007 \
    -u 1000 \
    --cap-drop=ALL \
    --read-only \
    --tmpfs /tmp \
    backstage:init
```


--------------------------------

### Clone the PHP sample application repository

Source: https://github.com/docker/docs/blob/main/content/guides/php.md

Clones the pre-built PHP sample application repository using git. Run this command in your desired working directory.

```console
$ git clone https://github.com/docker/docker-php-sample
```


--------------------------------

### Directory structure of the sample application

Source: https://github.com/docker/docs/blob/main/content/guides/genai-pdf-bot.md

Displays the file and directory layout inside the cloned docker-genai-sample repository.

```text
├── docker-genai-sample/
│ ├── .gitignore
│ ├── app.py
│ ├── chains.py
│ ├── env.example
│ ├── requirements.txt
│ ├── util.py
│ ├── LICENSE
│ └── README.md
```


--------------------------------

### Configure Sandbox Credentials in Python

Source: https://github.com/docker/docs/blob/main/content/guides/github-sonarqube-sandbox.md

Pass required environment variables and MCP server configurations simultaneously using AsyncSandbox.beta_create.

```python
# python
sbx = await AsyncSandbox.beta_create(
    envs={
        "ANTHROPIC_API_KEY": os.getenv("ANTHROPIC_API_KEY"),
        "GITHUB_TOKEN": os.getenv("GITHUB_TOKEN"),
        "SONARQUBE_TOKEN": os.getenv("SONARQUBE_TOKEN"),
    },
    mcp={
        "githubOfficial": {
            "githubPersonalAccessToken": os.getenv("GITHUB_TOKEN"),
        },
        "sonarqube": {
            "org": os.getenv("SONARQUBE_ORG"),
            "token": os.getenv("SONARQUBE_TOKEN"),
            "url": "https://sonarcloud.io",
        },
    },
)
```


--------------------------------

### Install ESLint dependencies for Next.js

Source: https://github.com/docker/docs/blob/main/content/guides/nextjs.md

Installs ESLint, the Next.js ESLint configuration, and ESLint legacy config compatibility utilities as development dependencies.

```console
$ npm install --save-dev eslint eslint-config-next @eslint/eslintrc
```


--------------------------------

### Install Vitest and React Testing Library dependencies

Source: https://github.com/docker/docs/blob/main/content/guides/nextjs.md

Installs Vitest, React testing utilities, and jsdom as development dependencies in a custom project.

```console
$ npm install --save-dev vitest @vitejs/plugin-react @testing-library/react @testing-library/dom jsdom
```


--------------------------------

### Create database schema and enable initialization in application.properties

Source: https://github.com/docker/docs/blob/main/content/guides/testcontainers-java-keycloak-spring-boot.md

Defines the products table in schema.sql and enables schema initialization mode in application.properties. For production, database migration tools like Flyway or Liquibase are recommended instead.

```sql
CREATE TABLE products (
    id bigserial primary key,
    title varchar not null,
    description text
);
```

```properties
spring.sql.init.mode=always
```


--------------------------------

### Start services for a specific profile using docker compose

Source: https://github.com/docker/docs/blob/main/content/guides/docker-compose.md

Starts only the services associated with the `dev` profile from `compose.yaml`, leaving other services inactive.

```console
$ docker compose --profile dev up
```


--------------------------------

### Clone the example application repository

Source: https://github.com/docker/docs/blob/main/content/guides/golang.md

Clones the recommended docker-gs-ping-dev repository containing the updated application code and multi-stage Dockerfile.

```console
$ git clone https://github.com/docker/docker-gs-ping-dev.git
# ... output omitted ...
```


--------------------------------

### Fetch heroes with GET request and view response

Source: https://github.com/docker/docs/blob/main/content/guides/python.md

Performs a GET request to retrieve heroes from the /heroes/ endpoint along with the JSON output.

```console
$ curl -X 'GET' \
  'http://localhost:8000/heroes/' \
  -H 'accept: application/json'
```

```json
{
  "age": 12,
  "id": 1,
  "name": "my hero",
  "secret_name": "austing"
}
```


--------------------------------

### Clone the Bun sample application repository

Source: https://github.com/docker/docs/blob/main/content/guides/bun.md

Clone the sample Bun Docker repository and navigate into the directory to verify the project contents.

```console
$ git clone https://github.com/dockersamples/bun-docker.git && cd bun-docker
```

```text
├── bun-docker/
│ ├── compose.yml
│ ├── Dockerfile
│ ├── LICENSE
│ ├── server.js
│ └── README.md
```


--------------------------------

### Clone the sample Deno application repository

Source: https://github.com/docker/docs/blob/main/content/guides/deno.md

Clone the docker-deno sample repository from GitHub and navigate into the project directory.

```console
$ git clone https://github.com/dockersamples/docker-deno.git && cd docker-deno
```


--------------------------------

### Initialize Python virtual environment

Source: https://github.com/docker/docs/blob/main/content/guides/testcontainers-python-getting-started.md

Sets up a new project directory and activates an isolated Python virtual environment.

```console
$ mkdir tc-python-demo
$ cd tc-python-demo
$ python3 -m venv venv
$ source venv/bin/activate
```


--------------------------------

### Create Docker assets (Dockerfile, compose.yaml, .dockerignore)

Source: https://github.com/docker/docs/blob/main/content/guides/genai-pdf-bot.md

Create these configuration files in the `docker-genai-sample` directory to define the container build, service setup, and build context exclusions.

```dockerfile
# syntax=docker/dockerfile:1

# Comments are provided throughout this file to help you get started.
# If you need more help, visit the Dockerfile reference guide at
# https://docs.docker.com/go/dockerfile-reference/

ARG PYTHON_VERSION=3.11.4
FROM python:${PYTHON_VERSION}-slim as base

# Prevents Python from writing pyc files.
ENV PYTHONDONTWRITEBYTECODE=1

# Keeps Python from buffering stdout and stderr to avoid situations where
# the application crashes without emitting any logs due to buffering.
ENV PYTHONUNBUFFERED=1

WORKDIR /app

# Create a non-privileged user that the app will run under.
# See https://docs.docker.com/go/dockerfile-user-best-practices/
ARG UID=10001
RUN adduser \
    --disabled-password \
    --gecos "" \
    --home "/nonexistent" \
    --shell "/sbin/nologin" \
    --no-create-home \
    --uid "${UID}" \
    appuser

# Download dependencies as a separate step to take advantage of Docker's caching.
# Leverage a cache mount to /root/.cache/pip to speed up subsequent builds.
# Leverage a bind mount to requirements.txt to avoid having to copy them into
# into this layer.
RUN --mount=type=cache,target=/root/.cache/pip \
    --mount=type=bind,source=requirements.txt,target=requirements.txt \
    python -m pip install -r requirements.txt

# Switch to the non-privileged user to run the application.
USER appuser

# Copy the source code into the container.
COPY . .

# Expose the port that the application listens on.
EXPOSE 8000

# Run the application.
CMD ["streamlit", "run", "app.py", "--server.address=0.0.0.0", "--server.port=8000"]
```

```yaml
# Comments are provided throughout this file to help you get started.
# If you need more help, visit the Docker Compose reference guide at
# https://docs.docker.com/go/compose-spec-reference/

# Here the instructions define your application as a service called "server".
# This service is built from the Dockerfile in the current directory.
# You can add other services your application may depend on here, such as a
# database or a cache. For examples, see the Awesome Compose repository:
# https://github.com/docker/awesome-compose
services:
  server:
    build:
      context: .
    ports:
      - 8000:8000

# The commented out section below is an example of how to define a PostgreSQL
# database that your application can use. `depends_on` tells Docker Compose to
# start the database before your application. The `db-data` volume persists the
# database data between container restarts. The `db-password` secret is used
# to set the database password. You must create `db/password.txt` and add
# a password of your choosing to it before running `docker compose up`.
#     depends_on:
#       db:
#         condition: service_healthy
#   db:
#     image: postgres
#     restart: always
#     user: postgres
#     secrets:
#       - db-password
#     volumes:
#       - db-data:/var/lib/postgresql/data
#     environment:
#       - POSTGRES_DB=example
#       - POSTGRES_PASSWORD_FILE=/run/secrets/db-password
#     expose:
#       - 5432
#     healthcheck:
#       test: [ "CMD", "pg_isready" ]
#       interval: 10s
#       timeout: 5s
#       retries: 5
# volumes:
#   db-data:
# secrets:
#   db-password:
#     file: db/password.txt
```

```text
# Include any files or directories that you don't want to be copied to your
# container here (e.g., local build artifacts, temporary files, etc.).
#
# For more help, visit the .dockerignore file reference guide at
# https://docs.docker.com/go/build-context-dockerignore/

**/.DS_Store
**/__pycache__
**/.venv
**/.classpath
**/.dockerignore
**/.env
**/.git
**/.gitignore
**/.project
**/.settings
**/.toolstarget
**/.vs
**/.vscode
**/*.*proj.user
**/*.dbmdl
**/*.jfm
**/bin
**/charts
**/docker-compose*
**/compose.y*ml
**/Dockerfile*
**/node_modules
**/npm-debug.log
**/obj
**/secrets.dev.yaml
**/values.dev.yaml
LICENSE
README.md
```


--------------------------------

### Create Basic Express Node.js Application

Source: https://github.com/docker/docs/blob/main/content/guides/genai-claude-code-mcp.md

Initializes an Express application in an app directory, creates the index.js server file, and configures the start script in package.json.

```console
$ mkdir app
$ cd app
$ npm init -y
$ npm install express
```

```console
const express = require("express");
const app = express();

app.get("/", (req, res) => {
  res.send("Node.js, Docker, and MCP Toolkit are working together!");
});

app.listen(3000, () => {
  console.log("Server running on port 3000");
});
```

```console
"scripts": {
  "start": "node index.js"
}
```


--------------------------------

### Start Compose Watch for angular-dev service

Source: https://github.com/docker/docs/blob/main/content/guides/angular.md

Runs Docker Compose in watch mode to start development container services and begin automatic file synchronization.

```console
$ docker compose watch angular-dev
```


--------------------------------

### Run the application with docker compose up

Source: https://github.com/docker/docs/blob/main/content/guides/agentic-ai.md

Builds and starts the application stack locally. The initial run pulls the Gemma 3 4B model from Docker Hub.

```console
$ docker compose up
```


--------------------------------

### Project directory layout for Docker Next.js setup

Source: https://github.com/docker/docs/blob/main/content/guides/nextjs.md

Displays the required project directory structure after adding Docker and Compose configuration files.

```text
├── docker-nextjs-sample/
│ ├── Dockerfile
│ ├── Dockerfile.dev
│ ├── .dockerignore
│ ├── compose.yaml
│ └── next.config.ts
```


--------------------------------

### Create Dockerfile copying seed.sql to entrypoint directory

Source: https://github.com/docker/docs/blob/main/content/guides/pre-seeding.md

Copies `seed.sql` directly into PostgreSQL's `/docker-entrypoint-initdb.d/` directory for automatic execution on first startup.

```plaintext
# syntax=docker/dockerfile:1
FROM postgres:18
COPY seed.sql /docker-entrypoint-initdb.d/
```


--------------------------------

### Project directory structure for Vue.js Docker setup

Source: https://github.com/docker/docs/blob/main/content/guides/vuejs.md

Shows the expected directory layout containing the Dockerfile, .dockerignore, compose.yaml, and nginx.conf files before building the image.

```text
├── docker-vuejs-sample/
│ ├── Dockerfile
│ ├── .dockerignore
│ ├── compose.yaml
│ └── nginx.conf
```


--------------------------------

### Clone the sample repository with git clone

Source: https://github.com/docker/docs/blob/main/content/guides/rust.md

Clones the sample Rust and PostgreSQL backend repository to your local development machine.

```console
$ git clone https://github.com/docker/docker-rust-postgres
```


--------------------------------

### Install Zscaler root certificate in a multi-stage build

Source: https://github.com/docker/docs/blob/main/content/guides/zscaler.md

Ensures the Zscaler root certificate is downloaded, verified, and installed in the final runtime stage of a multi-stage Docker build.

```dockerfile
FROM debian:bookworm AS build
WORKDIR /build
RUN apt-get update && apt-get install -y \
    build-essential \
    cmake \
    curl \
    git
RUN --mount=target=. cmake -B output/

FROM debian:bookworm-slim AS final
ADD --checksum=sha256:24454f830cdb571e2c4ad15481119c43b3cafd48dd869a9b2945d1036d1dc68d \
    https://artifacts.example/certs/zscaler-root-ca.crt /usr/local/share/ca-certificates/zscaler-root-ca.crt
RUN apt-get update && \
    apt-get install -y ca-certificates && \
    update-ca-certificates
WORKDIR /app
COPY --from=build /build/output/bin .
ENTRYPOINT ["/app/bin"]
```


--------------------------------

### Clone the sample .NET repository

Source: https://github.com/docker/docs/blob/main/content/guides/dotnet.md

Clones the pre-built sample .NET application repository used throughout the containerization guide.

```console
$ git clone https://github.com/docker/docker-dotnet-sample
```


--------------------------------

### Start Traefik using Docker Hardened Images

Source: https://github.com/docker/docs/blob/main/content/guides/traefik.md

Authenticates with dhi.io and starts a Traefik container on port 80 with the Docker socket mounted and Docker provider enabled.

```bash
$ docker login dhi.io
```

```console
$ docker run -d --network=traefik-demo \
  -p 80:80 \
  -v /var/run/docker.sock:/var/run/docker.sock \
  dhi.io/traefik:3.6.2 \
  --providers.docker
```


--------------------------------

### Start development environment with docker compose up

Source: https://github.com/docker/docs/blob/main/content/guides/laravel.md

Builds and starts the development containers in detached mode using compose.dev.yaml. After startup, the Laravel application is accessible at http://localhost/.

```console
$ docker compose -f compose.dev.yaml up --build -d
```


--------------------------------

### Run a container with a custom name

Source: https://github.com/docker/docs/blob/main/static/get-started/docker_cheatsheet.pdf

Creates and starts a new container from an image with an assigned custom container name.

```bash
docker run --name <container_name> <image_name>
```


--------------------------------

### Build and export binary for the local platform

Source: https://github.com/docker/docs/blob/main/content/guides/bake.md

Configure a bake target with local output and target platform, define a scratch stage in the Dockerfile to export the binary, and execute the build. Setting platforms to local forces the output to match the local host architecture instead of the default BuildKit host VM.

```hcl
target "bin" {
  target = "bin"
  output = ["build/bin"]
  platforms = ["local"]
}
```

```dockerfile
FROM scratch AS bin
COPY --from=build "/usr/bin/bakeme" /
```

```console
$ docker buildx bake bin
$ file ./build/bin/bakeme
./build/bin/bakeme: Mach-O 64-bit executable arm64
```


--------------------------------

### Structure code examples with the three-step pattern

Source: https://github.com/docker/docs/blob/main/STYLE.md

Follow this three-step pattern when authoring code examples: state the action, show the command, and explain key parts or results.

```markdown
Build your image:

```console
$ docker build -t my-app .
```

This creates an image tagged `my-app` using the Dockerfile in the
current directory.
```


--------------------------------

### Initialize TypeScript project and install dependencies

Source: https://github.com/docker/docs/blob/main/content/guides/github-sonarqube-sandbox.md

Initializes a Node.js project directory, configures package.json for ES module execution with tsx, and installs required runtime and development dependencies.

```bash
mkdir github-sonarqube-workflow
cd github-sonarqube-workflow
npm init -y
```

```json
{
  "name": "github-sonarqube-workflow",
  "version": "1.0.0",
  "description": "Automated code quality workflow using E2B, GitHub, and SonarQube",
  "type": "module",
  "main": "quality-workflow.ts",
  "scripts": {
    "start": "tsx quality-workflow.ts"
  },
  "keywords": ["e2b", "github", "sonarqube", "mcp", "code-quality"],
  "author": "",
  "license": "MIT"
}
```

```bash
npm install e2b dotenv
npm install -D typescript tsx @types/node
```


--------------------------------

### Start local development server with docker compose watch

Source: https://github.com/docker/docs/blob/main/CONTRIBUTING.md

Serves the site for local preview at http://localhost:1313, watching for changes and automatically rebuilding. Requires Docker Desktop 4.24+ or Docker Engine with Docker Compose 2.22+.

```console
$ docker compose watch
```


--------------------------------

### Initialize pgbench benchmark tables

Source: https://github.com/docker/docs/blob/main/content/guides/postgresql.md

Generates pgbench test tables in the benchmark database. The scale factor -s 50 populates approximately 5 million rows.

```bash
docker exec postgres pgbench -i -s 50 -U postgres benchmark
```


--------------------------------

### Build the basic-nlp Docker image with docker build

Source: https://github.com/docker/docs/blob/main/content/guides/language-translation.md

Run this command inside the directory where the Dockerfile is located to build and tag the Docker image.

```console
$ docker build -t basic-nlp .
```


--------------------------------

### Install Python dependencies with pip

Source: https://github.com/docker/docs/blob/main/content/guides/sentiment-analysis.md

Installs packages defined in requirements.txt using pip. The --no-cache-dir flag prevents storing cache data to reduce the final image size.

```dockerfile
RUN pip install --no-cache-dir -r requirements.txt
```


--------------------------------

### Build Backstage using Debian multi-stage Dockerfile

Source: https://github.com/docker/docs/blob/main/content/guides/dhi-backstage.md

Standard multi-stage Dockerfile configuration recommended by Backstage using node:24-trixie-slim for skeleton creation, dependency installation, and runtime.

```dockerfile
# Stage 1 - Create yarn install skeleton layer
FROM node:24-trixie-slim AS packages
WORKDIR /app
COPY backstage.json package.json yarn.lock ./
COPY .yarn ./.yarn
COPY .yarnrc.yml ./
COPY packages packages
COPY plugins plugins
RUN find packages \! -name "package.json" -mindepth 2 -maxdepth 2 \
    -exec rm -rf {} \+

# Stage 2 - Install dependencies and build packages
FROM node:24-trixie-slim AS build
ENV PYTHON=/usr/bin/python3
RUN --mount=type=cache,target=/var/cache/apt,sharing=locked \
    --mount=type=cache,target=/var/lib/apt,sharing=locked \
    apt-get update && \
    apt-get install -y --no-install-recommends python3 g++ build-essential && \
    rm -rf /var/lib/apt/lists/*
RUN --mount=type=cache,target=/var/cache/apt,sharing=locked \
    --mount=type=cache,target=/var/lib/apt,sharing=locked \
    apt-get update && \
    apt-get install -y --no-install-recommends libsqlite3-dev && \
    rm -rf /var/lib/apt/lists/*
USER node
WORKDIR /app
COPY --from=packages --chown=node:node /app .
RUN --mount=type=cache,target=/home/node/.cache/yarn,sharing=locked,uid=1000,gid=1000 \
    yarn install --immutable
COPY --chown=node:node . .
RUN yarn tsc
RUN yarn --cwd packages/backend build
RUN mkdir packages/backend/dist/skeleton packages/backend/dist/bundle \
    && tar xzf packages/backend/dist/skeleton.tar.gz \
       -C packages/backend/dist/skeleton \
    && tar xzf packages/backend/dist/bundle.tar.gz \
       -C packages/backend/dist/bundle

# Stage 3 - Build the actual backend image
FROM node:24-trixie-slim
ENV PYTHON=/usr/bin/python3
RUN --mount=type=cache,target=/var/cache/apt,sharing=locked \
    --mount=type=cache,target=/var/lib/apt,sharing=locked \
    apt-get update && \
    apt-get install -y --no-install-recommends python3 g++ build-essential && \
    rm -rf /var/lib/apt/lists/*
RUN --mount=type=cache,target=/var/cache/apt,sharing=locked \
    --mount=type=cache,target=/var/lib/apt,sharing=locked \
    apt-get update && \
    apt-get install -y --no-install-recommends libsqlite3-dev && \
    rm -rf /var/lib/apt/lists/*
USER node
WORKDIR /app
COPY --from=build --chown=node:node /app/.yarn ./.yarn
COPY --from=build --chown=node:node /app/.yarnrc.yml ./
COPY --from=build --chown=node:node /app/backstage.json ./
COPY --from=build --chown=node:node /app/yarn.lock \
     /app/package.json \
     /app/packages/backend/dist/skeleton/ ./
RUN --mount=type=cache,target=/home/node/.cache/yarn,sharing=locked,uid=1000,gid=1000 \
    yarn workspaces focus --all --production
COPY --from=build --chown=node:node /app/packages/backend/dist/bundle/ ./
CMD ["node", "packages/backend", "--config", "app-config.yaml"]
```


--------------------------------

### Create database connection helper in db/connection.py

Source: https://github.com/docker/docs/blob/main/content/guides/testcontainers-python-getting-started.md

Establishes a PostgreSQL database connection using environment variables with local defaults for flexible deployment.

```python
import os

import psycopg


def get_connection():
    host = os.getenv("DB_HOST", "localhost")
    port = os.getenv("DB_PORT", "5432")
    username = os.getenv("DB_USERNAME", "postgres")
    password = os.getenv("DB_PASSWORD", "postgres")
    database = os.getenv("DB_NAME", "postgres")
    return psycopg.connect(f"host={host} dbname={database} user={username} password={password} port={port}")
```


--------------------------------

### Start Quarkus application in dev mode with Gradle

Source: https://github.com/docker/docs/blob/main/content/guides/testcontainers-java-quarkus.md

Starts the Quarkus application in development mode using Gradle. Quarkus Dev Services automatically provisions an unconfigured PostgreSQL container.

```console
$ ./gradlew quarkusDev
```


--------------------------------

### Clone the sample repository

Source: https://github.com/docker/docs/blob/main/content/guides/agentic-ai.md

Clones the sample compose-for-agents repository and navigates to the adk directory.

```console
$ git clone https://github.com/docker/compose-for-agents.git
$ cd compose-for-agents/adk/
```


--------------------------------

### Start Quarkus application in dev mode with Maven

Source: https://github.com/docker/docs/blob/main/content/guides/testcontainers-java-quarkus.md

Starts the Quarkus application in development mode using Maven. Quarkus Dev Services automatically provisions an unconfigured PostgreSQL container.

```console
$ ./mvnw compile quarkus:dev
```


--------------------------------

### Start Compose stack in detached mode with build

Source: https://github.com/docker/docs/blob/main/content/guides/golang.md

Starts the application stack defined in the Compose file in detached mode using the -d flag after rebuilding images with --build.

```console
$ docker compose up --build -d
```


--------------------------------

### View PostgreSQL container initialization and connection logs

Source: https://github.com/docker/docs/blob/main/content/guides/postgresql.md

Fetches logs from the postgres-dev container to check for startup status or error messages. Look for "database system is ready to accept connections" to verify startup completion.

```bash
docker logs postgres-dev
```
