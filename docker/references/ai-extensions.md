# Docker — AI, Extensions & Related

Sourced snippets (97 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Clone the Docker Scout demo repository

Source: https://github.com/docker/docs/blob/main/content/manuals/scout/quickstart.md

Clone the example vulnerable Node.js application repository used to follow along with the Docker Scout quickstart guide.

```console
$ git clone https://github.com/docker/scout-demo-service.git
```


--------------------------------

### Enable SSH access with sbx setup ssh

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/integrations/_index.md

Configures your SSH client and starts the Docker Sandboxes daemon if needed. This command can be re-run at any time.

```console
$ sbx setup ssh
```


--------------------------------

### Install skills with the skills CLI

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/skills/install.md

Runs the interactive installer from the project directory to select supported agents and skills. Defaults to project-scoped installation, or user scope when run with `--global`.

```console
$ npx skills add docker/skills
```


--------------------------------

### Install an internal CA certificate in internal-ca/spec.yaml

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/customize/kits-v2.md

Configures a mixin setup to install a PEM-encoded certificate from /home/agent/ into the system CA certificates store and updates the trust store. Run installation commands as user 0. For multiple CAs, install every certificate before running update-ca-certificates.

```yaml
schemaVersion: "2"
kind: mixin
name: internal-ca
setup:
  install:
    - command: "install -m 0644 /home/agent/internal-ca.crt /usr/local/share/ca-certificates/internal-ca.crt && update-ca-certificates"
      user: "0"
```


--------------------------------

### Install Docker Engine and SBX on Ubuntu

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/install.md

Run Docker's convenience installation script with SBX=1 to install both Docker Engine and the docker-sbx package.

```console
$ curl -fsSL https://get.docker.com | sudo SBX=1 sh
```


--------------------------------

### Start mirroring DHI repositories using Docker CLI

Source: https://github.com/docker/docs/blob/main/content/manuals/dhi/how-to/mirror.md

Start mirroring multiple image and chart repositories to your organization namespace using the docker dhi mirror start command.

```console
$ docker dhi mirror start --org my-org \
  dhi/golang,my-org/dhi-golang \
  dhi/nginx,my-org/dhi-nginx \
  dhi/prometheus-chart,my-org/dhi-prometheus-chart
```


--------------------------------

### Complete TypeScript example in quickstart/run.ts

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes-api/cookbook/create-your-first-sandbox.md

Defines the full `createAndRun` function in `quickstart/run.ts` configuring kit launch parameters, timeout signals, and process execution.

```typescript
import type { Sandboxes } from '@docker/sandboxes';

export async function createAndRun(
  client: Sandboxes,
  kitName: string,
  args: string[],
  timeoutMs = 300_000,
) {
  const signal = AbortSignal.timeout(timeoutMs);
  const created = await client.kits.launch(
    kitName,
    { resources: { cpus: 2, memoryMib: 4096 } },
    { timeoutMs, signal },
  );
  const sandbox = await created.waitUntilRunning({ timeoutMs, signal });
  const result = await sandbox.processes.run(
    { args },
    { timeoutMs, signal },
  );
  return { sandbox, result };
}
```


--------------------------------

### Install the extension with docker extension install

Source: https://github.com/docker/docs/blob/main/content/manuals/extensions/extensions-sdk/build/frontend-extension-tutorial.md

Installs the built extension image into Docker Desktop to make it appear in the Dashboard.

```bash
docker extension install awesome-inc/my-extension:latest
```


--------------------------------

### Start Docker Offload via CLI (`docker offload start`)

Source: https://github.com/docker/docs/blob/main/content/manuals/offload/quickstart.md

Starts Docker Offload from the terminal. If you are a member of multiple organizations with access, you can select which profile to associate with your usage.

```console
$ docker offload start
```


--------------------------------

### Example directory structure for a sandbox kit

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/customize/author/_index.md

Demonstrates the directory layout for a kit pairing a descriptor (`my-kit.yaml`) with a Dockerfile (`my-kit.dockerfile`) and supporting assets.

```text
my-kit/
├── my-kit.yaml
├── my-kit.dockerfile
├── context.md
└── files/
    └── settings.json
```


--------------------------------

### Install skills to Docker Sandboxes with sbx skills

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/skills/install.md

Installs skills from the repository into the shared sandbox skill store. Note that the `sbx skills` installer is experimental.

```console
$ sbx skills add docker/skills
```


--------------------------------

### Add Docker marketplace in Codex CLI

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/skills/install.md

Registers Docker's repository as a plugin marketplace in the Codex CLI. After running, use /plugins to browse and install docker-skills, then start a new session.

```console
$ codex plugin marketplace add docker/skills
```


--------------------------------

### Start mirroring a repository with docker dhi mirror start

Source: https://github.com/docker/docs/blob/main/content/manuals/dhi/how-to/select-enterprise.md

Starts mirroring a DHI repository into your organization namespace on Docker Hub. Requires DHI CLI authentication with a Docker token and organization owner permissions.

```console
$ docker dhi mirror start --org <your-org> dhi/python,<your-org>/dhi-python
```


--------------------------------

### Install base packages in Dockerfile

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/customize/author/build-an-agent.md

Initializes the Dockerfile using Red Hat UBI 9 and installs essential system packages as root. Bash, Git, and curl-minimal provide core execution and networking capabilities, while shadow-utils, tar, and gzip enable user creation and archive unpacking.

```dockerfile
FROM registry.access.redhat.com/ubi9/ubi:9.8

USER root
RUN dnf install -y bash ca-certificates curl-minimal git shadow-utils tar gzip \
    && dnf clean all
```


--------------------------------

### Install @docker/extension-api-client

Source: https://github.com/docker/docs/blob/main/content/manuals/extensions/extensions-sdk/build/frontend-extension-tutorial.md

Install the Docker Extension API client library required to perform actions with Docker Desktop in an extension.

```bash
npm install @docker/extension-api-client
```


--------------------------------

### Install sbx for all users with msiexec

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/install.md

Silently install the machine-wide DockerSandboxesMachine.msi package for all users from an elevated PowerShell prompt.

```powershell
msiexec.exe /i DockerSandboxesMachine.msi /quiet
```


--------------------------------

### Start, list, stop, and remove sandboxes

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/usage.md

Standard workflow commands to start an agent in the current directory, check status, stop, and delete a sandbox.

```console
$ sbx run claude                    # start an agent in the current directory
$ sbx ls                            # see what's running
$ sbx stop my-sandbox               # pause it
$ sbx rm my-sandbox                 # delete it entirely

```


--------------------------------

### Start a process with an idempotency key in TypeScript

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes-api/cookbook/retry-without-creating-duplicates.md

Start a sandbox process using an idempotency key to avoid re-executing identical process starts across retries.

```typescript
return sandbox.processes.start({ args }, { idempotencyKey: requestId });
```


--------------------------------

### Start a detached cloud sandbox with sbx run

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/cloud/usage.md

Starts a cloud sandbox without opening an interactive agent session. Reuses and starts the named sandbox if stopped, or creates a new one if it does not exist or if --name is omitted.

```console
$ sbx --cloud run --detached claude --name cloud-task
```


--------------------------------

### Build Go application with Ubuntu base image (Before migration)

Source: https://github.com/docker/docs/blob/main/content/manuals/dhi/migration/examples/go.md

Sample Go Dockerfile using an Ubuntu-based image before migrating to Docker Hardened Images.

```dockerfile
#syntax=docker/dockerfile:1

FROM ubuntu/go:1.22-24.04

WORKDIR /app
ADD . ./

# Install any additional packages if needed using apt
# RUN apt-get update && apt-get install -y git && rm -rf /var/lib/apt/lists/*

RUN CGO_ENABLED=0 GOOS=linux go build -a -ldflags="-s -w" --installsuffix cgo -o main .

ENTRYPOINT ["/app/main"]
```


--------------------------------

### Install sbx for current user with winget

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/install.md

Install the per-user Docker Sandboxes MSI package via Windows Package Manager without requiring administrator privileges.

```powershell
winget install -h Docker.sbx
```


--------------------------------

### Start a terminal process with pty configuration

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes-api/cookbook/run-an-interactive-shell-in-a-cloud-sandbox.md

Starts a process with a pseudo-terminal and an initial terminal size using sandbox.processes.start. Pass an idempotency key so reconnecting does not require starting another process.

```typescript
return sandbox.processes.start(
  { args, pty: { initialSize: { rows: 40, cols: 120 } } },
  { idempotencyKey: requestId },
);
```


--------------------------------

### Start a sandbox environment using sbx env run

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/configuration/environment-files.md

Run the environment from the directory containing sbxenv.yaml to prompt plan approval and create or attach to the sandbox.

```console
$ sbx env run
```


--------------------------------

### Install build toolchain manually with sbx exec

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/integrations/t3-code.md

Installs g++, make, and python3 in an existing sandbox to allow node-pty to compile from source during the initial T3 Code connection.

```console
$ sbx exec <sandbox> -- sudo apt-get update
$ sbx exec <sandbox> -- sudo DEBIAN_FRONTEND=noninteractive apt-get install -y g++ make python3
```


--------------------------------

### Inspect default sandbox startup command

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/agents/docker-agent.md

Displays the command executed by default inside the sandbox when no extra arguments are passed.

```text
docker-agent run --yolo
```


--------------------------------

### Deploy Linux configuration file and set permissions

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/governance/monitor-and-enforce/sign-in-enforcement.md

Creates the `/etc/docker-sbx` directory, writes the configuration, and sets ownership to `root:root` with permissions `644`.

```console
$ sudo mkdir -p /etc/docker-sbx
$ sudo tee /etc/docker-sbx/config.json <<'EOF'
{"allowedOrgs": ["acme-corp"], "adminEmail": "it@acme.com"}
EOF
$ sudo chown root:root /etc/docker-sbx/config.json
$ sudo chmod 644 /etc/docker-sbx/config.json
```


--------------------------------

### Install extension into Docker Desktop

Source: https://github.com/docker/docs/blob/main/content/manuals/extensions/extensions-sdk/build/minimal-frontend-extension.md

Installs the built extension image into Docker Desktop to make it visible in the dashboard.

```console
$ docker extension install awesome-inc/my-extension:latest
```


--------------------------------

### Initialize a new extension with docker extension init

Source: https://github.com/docker/docs/blob/main/content/manuals/extensions/extensions-sdk/quickstart.md

Generates a boilerplate extension directory containing a Go backend service and React frontend. Prompts for configuration details such as extension name, description, and Docker Hub repository.

```console
$ docker extension init <my-extension>
```


--------------------------------

### sandbox.processes.start

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes-api/cookbook/run-an-interactive-shell-in-a-cloud-sandbox.md

Starts an interactive process with a pseudo-terminal in a cloud sandbox. Returns a process handle identifying the session.

```APIDOC
## sandbox.processes.start(options, requestOptions)

### Description
Starts a process with a pseudo-terminal (PTY) and initial terminal size in a cloud sandbox.

### Parameters
#### options (object)
- **args** (string[]) - The command and arguments to execute (e.g., `['sh']`).
- **pty** (object) - Pseudo-terminal configuration.
  - **initialSize** (object) - Initial terminal window size.
    - **rows** (number) - Number of rows for the terminal.
    - **cols** (number) - Number of columns for the terminal.

#### requestOptions (object)
- **idempotencyKey** (string) - Optional idempotency key for the request.

### Return Value
Returns a promise that resolves to a process handle for the started session.

### Example
```typescript
const process = await sandbox.processes.start(
  { args: ['sh'], pty: { initialSize: { rows: 40, cols: 120 } } },
  { idempotencyKey: requestId },
);
```
```


--------------------------------

### Start Docker Desktop in GitHub Actions

Source: https://github.com/docker/docs/blob/main/content/manuals/extensions/extensions-sdk/dev/continuous-integration.md

Configures a GitHub Actions workflow step to start Docker Desktop using the desktop-action. Requires running on macOS runners (runs-on: macOS-latest).

```yaml
steps:
  - id: start_desktop
    uses: docker/desktop-action/start@v0.1.0
```


--------------------------------

### Run OpenCode for a project directory

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/agents/opencode.md

Creates a sandbox and starts OpenCode targeting a specific project directory path.

```console
$ sbx run opencode ~/my-project
```


--------------------------------

### View installed package metadata on Debian with apt-cache show

Source: https://github.com/docker/docs/blob/main/content/manuals/dhi/how-to/hardened-packages.md

Displays package records and metadata for an installed package on Debian.

```console
$ apt-cache show <package-name>
```


--------------------------------

### Download and run the Docker Scout CLI installation script

Source: https://github.com/docker/docs/blob/main/content/manuals/scout/install.md

Downloads and executes the convenience script to install the latest standalone binary version of the Docker Scout plugin. Always review scripts downloaded from the internet before running them locally.

```console
$ curl -fsSL https://raw.githubusercontent.com/docker/scout-cli/main/install.sh -o install-scout.sh
$ sh install-scout.sh
```


--------------------------------

### Install the Docker Sandboxes SDK using npm

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes-api/install.md

Installs the @docker/sandboxes package in your project. Requires Node.js 20 or later.

```console
$ npm install @docker/sandboxes
```


--------------------------------

### Run sandbox using local kit or shortcut with mixin

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/customize/kits-v2.md

Starts a sandbox using a local kit path or built-in agent shortcut like claude, applying mixins with the --kit flag. Uses the current directory as the default workspace.

```console
$ sbx run ./my-agent --name my-project --kit ./team-config
$ sbx run claude --name claude-project --kit ./team-config
```


--------------------------------

### Launch an agent sandbox using sbx run

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/get-started.md

Navigate to your project directory and start an agent inside a new sandbox. Replace claude with any supported agent name.

```console
$ cd ~/my-project
$ sbx run --name my-sandbox claude
```


--------------------------------

### Start sandbox with t3code kit

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/integrations/t3-code.md

Creates a sandbox using the t3code kit, which pre-installs the build toolchain and t3 package for T3 Code connections.

```console
$ sbx run claude --kit docker.io/sbx/t3code-kit:latest
```


--------------------------------

### Add all skills from a Git repository using sbx skills add

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/workflows/agent-skills.md

Installs every skill from a Git repository containing valid SKILL.md files. Accepts GitHub owner/repository shorthand or standard Git HTTPS/SSH URLs.

```console
$ sbx skills add anthropics/skills
```


--------------------------------

### Start a shell sandbox in a specific workspace

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/agents/shell.md

Starts an agent-less Bash login shell sandbox with the specified workspace directory.

```console
$ sbx run shell ~/my-project
```


--------------------------------

### Build Go application with Wolfi base image (Before migration)

Source: https://github.com/docker/docs/blob/main/content/manuals/dhi/migration/examples/go.md

Sample Go Dockerfile using a Chainguard Wolfi distribution image before migrating to Docker Hardened Images.

```dockerfile
#syntax=docker/dockerfile:1

FROM cgr.dev/chainguard/go:latest-dev

WORKDIR /app
ADD . ./

# Install any additional packages if needed using apk
# RUN apk add --no-cache git

RUN CGO_ENABLED=0 GOOS=linux go build -a -ldflags="-s -w" --installsuffix cgo -o main .

ENTRYPOINT ["/app/main"]
```


--------------------------------

### Start a sandbox with an exposed MCP server using sbx run

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/mcp-gateway.md

Launches a sandbox and pre-loads the specified registered MCP server through the MCP gateway. The host registration remains available for reuse across other sandboxes.

```console
$ sbx run claude --name mcp-demo --static-mcp notion
```


--------------------------------

### Install TypeScript definitions for Extension API client

Source: https://github.com/docker/docs/blob/main/content/manuals/extensions/extensions-sdk/build/frontend-extension-tutorial.md

Install @docker/extension-api-client-types as a development dependency to enable type definitions and IDE auto-completion.

```bash
npm install @docker/extension-api-client-types --save-dev
```


--------------------------------

### Verify build toolchain installation

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/integrations/t3-code.md

Checks that g++, make, and python3 are present and accessible in the sandbox environment.

```console
$ sbx exec <sandbox> -- sh -lc 'command -v g++ && command -v make && command -v python3'
```


--------------------------------

### Inspect Debian package metadata before installing with dpkg-deb

Source: https://github.com/docker/docs/blob/main/content/manuals/dhi/how-to/hardened-packages.md

Downloads the .deb package file and inspects its control information without installing it.

```console
$ apt-get download <package-name>
$ dpkg-deb -I <package-name>_*.deb
```


--------------------------------

### Inspect Alpine package metadata before installing

Source: https://github.com/docker/docs/blob/main/content/manuals/dhi/how-to/hardened-packages.md

Fetches the package stream and extracts its .PKGINFO metadata file without installing the package.

```console
$ apk fetch --stdout <package-name> | tar -xzO .PKGINFO
```


--------------------------------

### Build Java application using Ubuntu base images (Before migration)

Source: https://github.com/docker/docs/blob/main/content/manuals/dhi/migration/examples/java.md

Multi-stage Dockerfile using Ubuntu 24.04 base images with apt-get package installations for JDK, Maven, and JRE.

```dockerfile
#syntax=docker/dockerfile:1

FROM ubuntu:24.04 AS builder

WORKDIR /app
COPY . ./

RUN apt-get update && apt-get install -y default-jdk maven --no-install-recommends && rm -rf /var/lib/apt/lists/*

RUN mvn -B package -DskipTests

FROM ubuntu:24.04

RUN apt-get update && apt-get install -y default-jre --no-install-recommends && rm -rf /var/lib/apt/lists/*

WORKDIR /app
COPY --from=builder /app/target/app.jar /app/app.jar

ENTRYPOINT ["java", "-jar", "/app/app.jar"]
```


--------------------------------

### Install Docker skills extension in Gemini CLI

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/skills/install.md

Installs the Docker skills repository as a Gemini CLI extension directly from GitHub.

```console
$ gemini extensions install https://github.com/docker/skills
```


--------------------------------

### Add a mixin using sbx run with --kit

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/customize/use-kits.md

Start a sandbox workload with an attached mixin tool. For v3 kits, both the workload and mixin must use v3 format.

```console
$ sbx run docker.io/docker/sbx-kit-codex:0.155.1 --name codex-tools \
    --kit docker.io/<NAMESPACE>/company-cli:1.0.0
```


--------------------------------

### Navigate to the demo repository directory

Source: https://github.com/docker/docs/blob/main/content/manuals/scout/quickstart.md

Change into the cloned scout-demo-service directory before building the container image.

```console
$ cd scout-demo-service
```


--------------------------------

### Launch local agent kit with sbx run

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/customize/author/build-an-agent.md

Builds the kit, mounts the current working directory as the workspace, and launches the Claude Code agent.

```console
$ sbx run --name claude-team ./claude-team
```


--------------------------------

### Import skills from host directories with sbx skills import

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/workflows/agent-skills.md

Scans host directories and copies skill subdirectories into the shared store. If a skill already exists in the store, sbx prompts before replacing it unless --force is specified.

```console
$ sbx skills import
```


--------------------------------

### Initialize a Node.js project

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes-api/get-started.md

Sets up a new project directory, generates a package.json file, and sets the project type to module for ES module support.

```console
$ mkdir sandboxes-api-tutorial
$ cd sandboxes-api-tutorial
$ npm init --yes
$ npm pkg set type=module
```


--------------------------------

### Build Node.js application with Ubuntu base image (Before)

Source: https://github.com/docker/docs/blob/main/content/manuals/dhi/migration/examples/node.md

Sample Dockerfile configuring a Node.js application on an Ubuntu 24.04 base before migrating to Docker Hardened Images.

```dockerfile
#syntax=docker/dockerfile:1

FROM ubuntu:24.04

RUN apt-get update && apt-get install -y nodejs npm --no-install-recommends && rm -rf /var/lib/apt/lists/*

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install

COPY . .

CMD ["node", "index.js"]
```


--------------------------------

### Set up and connect with SSH

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/cloud/usage.md

Configures cloud SSH access and connects via standard SSH client using the sandbox's sbx_-prefixed ID.

```console
$ sbx --cloud setup ssh
$ ssh sbx_01abc123@sbx_cloud
```


--------------------------------

### Install Docker Sandboxes SDK and TypeScript tooling

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes-api/get-started.md

Installs the @docker/sandboxes SDK along with tsx, typescript, and Node type definitions for development.

```console
$ npm install @docker/sandboxes
$ npm install --save-dev tsx typescript @types/node
```


--------------------------------

### Install only docker-sbx package on Ubuntu

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/install.md

Configure the Docker apt repository using REPO_ONLY=1 and install only the docker-sbx package without Docker Engine.

```console
$ curl -fsSL https://get.docker.com | sudo REPO_ONLY=1 sh
$ sudo apt install docker-sbx
```


--------------------------------

### Expose registered MCP server to sandbox with sbx run

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/mcp-gateway.md

Starts a sandbox container and exposes the configured MCP server using `--static-mcp`.

```console
$ sbx run claude --name acme-demo --static-mcp acme
```


--------------------------------

### Run a new sandbox from a template using -t

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/usage.md

Creates and starts a new sandbox from a saved template image in the local image store.

```console
$ sbx run -t my-template:v1 claude
```


--------------------------------

### Install sbx CLI on macOS with Homebrew

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/install.md

Trust the Docker Homebrew tap and install the sbx CLI package on macOS Sonoma or later.

```console
$ brew trust docker/tap
$ brew install docker/tap/sbx
```


--------------------------------

### Install docker-model-plugin on RPM-based distributions

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/model-runner/get-started.md

Updates dnf repositories and installs the Docker Model Runner plugin package on RPM-based Linux distributions.

```bash
$ sudo dnf update
$ sudo dnf install docker-model-plugin
```


--------------------------------

### Create a cloud sandbox with a kit and kit argument

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/cloud/usage.md

Supplies a mixin kit and configures its parameters using the --kit-arg flag during sandbox creation. Prefix the argument name with the kit's repository name.

```console
$ sbx --cloud create --name cloud-tools claude \
    --kit docker.io/<NAMESPACE>/company-cli:1.0.0 \
    --kit-arg company-cli.version=1.2
```


--------------------------------

### Default Gemini startup command

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/agents/gemini.md

Executes inside the sandbox by default when no additional arguments are supplied.

```text
gemini --yolo
```


--------------------------------

### Send HTTP GET request with ddClient.extension.vm.service.get

Source: https://github.com/docker/docs/blob/main/content/manuals/extensions/extensions-sdk/dev/api/backend.md

Performs an HTTP GET request to a backend service defined in the VM section of the extension metadata.

```typescript
ddClient.extension.vm.service
 .get("/some/service")
 .then((value: any) => console.log(value))
```


--------------------------------

### Push and sign an OCI kit in one step

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/customize/kits-v2.md

Pushes a kit directory to an OCI registry and signs it in a single command, storing the signature as an OCI referrer.

```console
$ sbx kit push ./my-kit/ ghcr.io/myorg/my-kit:1.0 --sign
```


--------------------------------

### Complete example for downloadFiles in TypeScript (download/download.ts)

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes-api/cookbook/read-files-out-of-a-sandbox.md

A complete helper function demonstrating how to stream bytes from `sandbox.files.download` to a write callback and ensure proper cleanup.

```typescript
import type { Sandbox } from '@docker/sandboxes';

export async function downloadFiles(
  sandbox: Sandbox,
  path: string,
  write: (bytes: Uint8Array) => void,
) {
  const download = await sandbox.files.download(path);
  try {
    for await (const chunk of download) write(chunk);
  } finally {
    await download.close();
  }
}
```


--------------------------------

### Run Copilot for a project directory

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/agents/copilot.md

Create a sandbox and launch Copilot pointing to a specified project path.

```console
$ sbx run copilot ~/my-project

```


--------------------------------

### View installed package provenance metadata on Alpine with apk info -a

Source: https://github.com/docker/docs/blob/main/content/manuals/dhi/how-to/hardened-packages.md

Displays verifiable metadata and details for an installed package on Alpine Linux.

```console
$ apk info -a <package-name>
```


--------------------------------

### Create and run a mountless sandbox

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/security/isolation.md

Omit the workspace path when executing `sbx create` to start a mountless sandbox, then attach to it by name using `sbx run`. Files written inside the sandbox remain isolated within its filesystem and persist across stops and restarts.

```console
$ sbx create --name scratch claude
$ sbx run --name scratch
```


--------------------------------

### Install engine runner with docker model install-runner

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/model-runner/inference-engines.md

Installs an inference engine backend such as llama.cpp, vllm, or diffusers, with optional GPU type specification.

```console
$ docker model install-runner --backend <engine> [--gpu <type>]
```


--------------------------------

### Install Model Runner with vLLM backend on Linux

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/model-runner/inference-engines.md

Installs the Docker Model Runner configured with the vLLM backend and CUDA GPU acceleration on Linux.

```console
$ docker model install-runner --backend vllm --gpu cuda
```


--------------------------------

### Install docker-model-plugin on Ubuntu and Debian

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/model-runner/get-started.md

Updates apt package lists and installs the Docker Model Runner plugin package on Ubuntu and Debian distributions.

```bash
$ sudo apt-get update
$ sudo apt-get install docker-model-plugin
```


--------------------------------

### Authenticate, launch, execute, and delete a sandbox in TypeScript (hello/main.ts)

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes-api/cookbook/run-a-complete-example.md

Full runnable example that initiates OAuth login, provisions a 2-CPU/4096 MiB shell sandbox, runs a command, and ensures sandbox deletion upon completion or failure.

```typescript
import { pathToFileURL } from 'node:url';
import { oauth, Sandboxes, type Sandbox } from '@docker/sandboxes';

export async function main() {
  const auth = oauth({
    onVerification: ({ verificationUri, userCode }) => {
      console.log(`Open ${verificationUri} and enter ${userCode}`);
    },
  });
  const client = new Sandboxes({ auth });
  let sandbox: Sandbox | undefined;
  try {
    await auth.getAccessToken();
    const operation = {
      signal: AbortSignal.timeout(300_000),
      timeoutMs: 300_000,
    };
    sandbox = await client.kits.launch(
      'shell',
      {
        resources: { cpus: 2, memoryMib: 4096 },
      },
      operation,
    );
    console.log(`Sandbox: ${sandbox.name}`);
    sandbox = await sandbox.waitUntilRunning(operation);
    const result = await sandbox.processes.run(
      {
        args: ['echo', 'Hello from Docker Sandboxes'],
      },
      operation,
    );
    console.log(result.stdout);
    if (result.exitCode !== 0)
      throw new Error(`Command exited with status ${result.exitCode}`);
  } finally {
    try {
      if (sandbox) {
        const cleanup = { signal: AbortSignal.timeout(30_000) };
        const deleting = await sandbox.delete({ force: true }, cleanup);
        await deleting?.waitUntilDeleted(cleanup);
      }
    } finally {
      await client.close();
    }
  }
}

if (
  process.argv[1] &&
  import.meta.url === pathToFileURL(process.argv[1]).href
) {
  main().catch((error: unknown) => {
    console.error(error);
    process.exitCode = 1;
  });
}
```


--------------------------------

### Default Devin startup command

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/agents/devin.md

The default command executed inside the sandbox when no extra arguments are supplied.

```text
devin --permission-mode dangerous --respect-workspace-trust=false
```


--------------------------------

### Initialize cloud account policy with sbx --cloud policy init

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/cloud/network-policy.md

Sets the default cloud account policy preset to allow-all, balanced, or deny-all. This default applies across your Docker account, while explicit sandbox or agent-kit rules can still grant access.

```console
$ sbx --cloud policy init deny-all
```


--------------------------------

### Re-build and update the extension

Source: https://github.com/docker/docs/blob/main/content/manuals/extensions/extensions-sdk/build/backend-extension-tutorial.md

Re-build the extension image after modifying its configuration or Dockerfile, then update the extension in Docker Desktop. If the extension is not yet installed, install it instead.

```bash
docker build --tag=awesome-inc/my-extension:latest .
```

```bash
docker extension update awesome-inc/my-extension:latest
```


--------------------------------

### Configure prometheus/prometheus.yml for sample project

Source: https://github.com/docker/docs/blob/main/content/manuals/scout/explore/metrics-exporter.md

Sample Prometheus configuration with scrape intervals, target endpoint, and bearer token authorization configured.

```yaml
global:
  scrape_interval: 60s
  scrape_timeout: 40s
scrape_configs:
  - job_name: Docker Scout policy
    metrics_path: /v1/exporter/org/<ORG>/metrics
    scheme: https
    static_configs:
      - targets:
          - api.scout.docker.com
    authorization:
      type: Bearer
      credentials_file: /etc/prometheus/token
```


--------------------------------

### Verify DMR installation and run a test model

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/model-runner/get-started.md

Tests the Docker Model Runner installation by checking the model CLI version and running the ai/smollm2 model.

```bash
$ docker model version
$ docker model run ai/smollm2
```


--------------------------------

### Start server authorization with client.mcp.authorizations.authorize

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes-api/cookbook/give-a-sandbox-an-mcp-gateway.md

Start authorization for an MCP server that requires user sign-in. Present the resulting authorization URL to the user to complete sign-in.

```typescript
return client.mcp.authorizations.authorize({
  server: name,
  forceReauth,
});
```


--------------------------------

### Build Node.js application with Wolfi base image (Before)

Source: https://github.com/docker/docs/blob/main/content/manuals/dhi/migration/examples/node.md

Sample Dockerfile using a Wolfi development base image before migrating to Docker Hardened Images.

```dockerfile
#syntax=docker/dockerfile:1

FROM cgr.dev/chainguard/node:latest-dev
WORKDIR /usr/src/app

COPY package*.json ./

# Install any additional packages if needed using apk
# RUN apk add --no-cache python3 make g++

RUN npm install

COPY . .

CMD ["index.js"]
```


--------------------------------

### Initialize network policy preset with sbx policy init

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/governance/access-controls/local.md

Sets the default policy preset in non-interactive environments like CI pipelines or headless servers before running other sbx commands. Accepts allow-all, balanced, and deny-all.

```console
$ sbx policy init balanced
```


--------------------------------

### Default Kiro sandbox startup command

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/agents/kiro.md

Displays the default command executed inside the sandbox when no extra arguments are supplied.

```text
kiro chat --trust-all-tools
```


--------------------------------

### Build image with docker buildx build

Source: https://github.com/docker/docs/blob/main/content/manuals/dhi/how-to/build.md

Builds the image from `base.yaml` with SBOM indexing and provenance metadata generation enabled, then loads it into the local Docker daemon.

```console
$ docker buildx build . -f base.yaml \
    --sbom=generator=dhi.io/scout-sbom-indexer:1 \
    --provenance=1 \
    --tag my-base:latest \
    --load
```


--------------------------------

### Create Docker Desktop client instance

Source: https://github.com/docker/docs/blob/main/content/manuals/extensions/extensions-sdk/build/frontend-extension-tutorial.md

Initialize a Docker Desktop client using createDockerDesktopClient to call extension APIs.

```js
import { createDockerDesktopClient } from '@docker/extension-api-client';

const ddClient = createDockerDesktopClient();
```


--------------------------------

### Create the kit directory

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/customize/author/build-an-agent.md

Creates a directory beside the project to hold the agent kit configuration and definition files.

```console
$ mkdir claude-team
```


--------------------------------

### Create a clone-mode sandbox and attach later

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/usage.md

Create a named clone-mode sandbox in the background with sbx create --clone and attach to the agent session later using sbx run.

```console
$ sbx create --clone --name my-sandbox claude .
$ sbx run --name my-sandbox
```


--------------------------------

### Start a sandbox with an explicit name using --name

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/usage.md

Assigns an explicit name to a sandbox upon creation with sbx run.

```console
$ sbx run --name my-project claude
```


--------------------------------

### Create cloud sandbox with initial allow and deny rules

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/cloud/network-policy.md

Specifies initial allow and deny network rules directly during cloud sandbox creation using --allow-network and --deny-network flags.

```console
$ sbx --cloud create --name cloud-project \
    --allow-network api.github.com:443 \
    --deny-network example.com claude
```


--------------------------------

### Plan, run detached, and execute commands with sbx --cloud env

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/configuration/environment-files.md

Preview environment plans, start a cloud sandbox in detached mode, and run commands inside the cloud instance.

```console
$ sbx --cloud env plan ./cloud.sbxenv.yaml
$ sbx --cloud env run --detached ./cloud.sbxenv.yaml
$ sbx --cloud env exec ./cloud.sbxenv.yaml -- printenv PROJECT_NAME
```


--------------------------------

### Inspect default startup command for Claude Code

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/agents/claude-code.md

Shows the default command executed inside the sandbox when no extra arguments are passed.

```text
claude --dangerously-skip-permissions

```


--------------------------------

### Save and create a cloud sandbox from a template

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/cloud/usage.md

Captures a running sandbox to a cloud template and launches a new sandbox from it. Do not combine --template with an agent name, --cpus, or --memory as the template provides its own configuration.

```console
$ sbx --cloud template save cloud-project cloud-template
$ sbx --cloud create --name cloud-copy --template cloud-template
```


--------------------------------

### Directory layout for an initialized frontend extension

Source: https://github.com/docker/docs/blob/main/content/manuals/extensions/extensions-sdk/build/frontend-extension-tutorial.md

Shows the standard file and folder structure created when initializing a React-based Docker Desktop extension.

```bash
.
├── Dockerfile # (1)
├── ui # (2)
│   ├── public # (3)
│   │   └── index.html
│   ├── src # (4)
│   │   ├── App.tsx
│   │   ├── index.tsx
│   ├── package.json
│   └── package-lock.lock
│   ├── tsconfig.json
├── docker.svg # (5)
└── metadata.json # (6)
```


--------------------------------

### Build and publish a v3 kit image using Docker Buildx

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/customize/author/distribute.md

Builds and pushes a v3 kit as an OCI image to a registry using its YAML descriptor and source directory context. Push the image before referencing it by registry name because sbx pulls from the remote registry.

```console
$ docker login
$ docker buildx build ./my-kit -f ./my-kit/my-kit.yaml \
    -t docker.io/<NAMESPACE>/my-kit:1.0.0 --push
```


--------------------------------

### Build a sandbox kit with docker buildx

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/customize/author/_index.md

Builds the kit container image by passing the YAML descriptor to `-f` and pointing build context to the kit source directory.

```console
$ docker buildx build -f my-kit/my-kit.yaml -t my-kit:dev my-kit/
```


--------------------------------

### Get Customization Build Details with docker dhi customization build get

Source: https://github.com/docker/docs/blob/main/content/manuals/dhi/tools/cli.md

Retrieve detailed information for a specific customization build by providing the customization ID and build ID.

```console
$ docker dhi customization build get <customization-id> <build-id> --org my-org
$ docker dhi customization build get <customization-id> <build-id> --org my-org --json
```


--------------------------------

### Get and verify SLSA provenance with docker scout attest get

Source: https://github.com/docker/docs/blob/main/content/manuals/dhi/explore/security-concepts/slsa.md

Retrieve and verify the SLSA provenance attestation for a specified Docker Hardened Image using Docker Scout.

```console
$ docker scout attest get dhi.io/<image>:<tag> \
  --predicate-type https://slsa.dev/provenance/v0.2 \
  --verify
```


--------------------------------

### Run sandbox from registry template

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/usage.md

Creates a sandbox from a template image in a registry using its full image reference. Pass the agent name that the template image was prepared for.

```console
$ sbx run --template docker.io/my-org/my-template:v1 claude
```


--------------------------------

### Probe npm installation output with sbx exec

Source: https://github.com/docker/docs/blob/main/content/manuals/ai/sandboxes/integrations/t3-code.md

Runs a test npm install of T3 inside the sandbox to capture diagnostic output and identify the root cause of connection failures.

```console
$ sbx exec <sandbox> -- sh -lc \
  'rm -rf /tmp/t3probe && mkdir -p /tmp/t3probe && cd /tmp/t3probe \
   && npm init -y >/dev/null && npm install t3@latest 2>&1 | tail -40'
```
