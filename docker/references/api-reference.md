# Docker — API Reference

Sourced snippets (155 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### docker agent serve acp usage examples

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/features/cli/index.md

Examples for starting an ACP server over stdio using configuration files or an agent image tag.

```bash
# Examples
$ docker agent serve acp agent.yaml
$ docker agent serve acp ./team.yaml
$ docker agent serve acp myorg/agent:tag
```


--------------------------------

### Install the Go SDK using go get

Source: https://github.com/docker/docs/blob/main/content/reference/api/engine/sdk/_index.md

Installs the Docker Engine Go client package. Ensure a currently supported version of Go is running before installation.

```console
$ go get github.com/moby/moby/client
```


--------------------------------

### docker agent serve a2a usage examples

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/features/cli/index.md

Examples for starting an A2A server with a YAML config file, a custom listen address, or an agent image tag.

```bash
# Examples
$ docker agent serve a2a agent.yaml
$ docker agent serve a2a agent.yaml --listen 127.0.0.1:9000
$ docker agent serve a2a myorg/agent:tag
```


--------------------------------

### Run interactive setup for custom OpenAI-compatible endpoint

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/getting-started/set-up-a-model/index.md

Launches the interactive setup wizard to configure a custom OpenAI-compatible endpoint.

```bash
$ docker agent setup   # pick "Custom OpenAI-compatible endpoint"
```


--------------------------------

### Install and start vLLM OpenAI API server

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/providers/local/index.md

Installs vLLM using pip and launches the OpenAI-compatible API server using the meta-llama/Llama-3.2-3B-Instruct model on port 8000.

```bash
# Install vLLM
pip install vllm

# Start the server
python -m vllm.entrypoints.openai.api_server \
  --model meta-llama/Llama-3.2-3B-Instruct \
  --port 8000
```


--------------------------------

### Configure worktree_create hook to seed environment and install dependencies

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/configuration/hooks/index.md

Runs setup commands inside a freshly created git worktree checkout before the agent session starts. Uses worktree_source_dir to copy untracked files and aborts the run on setup failure using exit code 2.

```yaml
hooks:
  worktree_create:
    # Copy untracked dotfiles git won't bring into the new worktree.
    - name: seed local env
      type: command
      command: |
        INPUT=$(cat)
        SRC=$(echo "$INPUT" | jq -r '.worktree_source_dir // ""')
        [ -n "$SRC" ] && [ -f "$SRC/.env" ] && [ ! -f .env ] && cp "$SRC/.env" .env
        echo "Prepared worktree"
    # Install dependencies, aborting the run on failure.
    - name: install dependencies
      type: command
      timeout: 600
      command: |
        if [ -f package.json ]; then
          npm install || { echo '{"continue": false, "system_message": "npm install failed"}'; exit 2; }
        fi
```


--------------------------------

### Start a container (POST /containers/(id)/start)

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.6.md

Starts a container with optional host configuration settings such as port bindings, binds, and LxcConf.

```http
POST /containers/(id)/start HTTP/1.1
Content-Type: application/json

{
     "Binds":["/tmp:/tmp"],
     "LxcConf":[{"Key":"lxc.utsname","Value":"docker"}],
     "ContainerIDFile": "",
     "Privileged": false,
     "PortBindings": {"22/tcp": [{"HostIp":"", "HostPort":""}]},
     "Links": [],
     "PublishAllPorts": false
}
```

```http
HTTP/1.1 204 No Content
Content-Type: text/plain
```


--------------------------------

### Sign in with ChatGPT using docker agent setup

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/providers/chatgpt/index.md

Launches the setup wizard to authenticate with a ChatGPT account via browser OAuth, storing credentials in ~/.config/cagent/chatgpt-auth.json.

```bash
docker agent setup
```


--------------------------------

### Interactively configure model providers with docker agent setup

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/features/cli/index.md

Launches the interactive setup wizard to configure built-in cloud providers, local models, custom OpenAI-compatible endpoints, or the Claude Code harness.

```bash
$ docker agent setup
```


--------------------------------

### Install sample plugin and view daemon logs

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/cli/docs/extend/_index.md

Installs a Docker plugin and displays the corresponding dockerd daemon log entry tagged with the plugin ID suffix.

```console
$ docker plugin install tiborvass/sample-volume-plugin

INFO[0036] Starting...       Found 0 volumes on startup  plugin=f52a3df433b9aceee436eaada0752f5797aab1de47e5485f1690a073b860ff62
```


--------------------------------

### Launch the interactive getting-started tour

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/getting-started/quickstart/index.md

Starts a scripted onboarding tour inside the chat UI to demonstrate messages, tool approval, and commands.

```bash
$ docker agent getting-started
```


--------------------------------

### Start a container via POST /containers/(id or name)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.14.md

Starts an existing container using optional host configuration settings such as volume binds, port bindings, and capabilities.

```http
POST /containers/e90e34656806/start HTTP/1.1
Content-Type: application/json

{
     "Binds":["/tmp:/tmp"],
     "Links":["redis3:redis"],
     "LxcConf":[{"Key":"lxc.utsname","Value":"docker"}],
     "PortBindings":{ "22/tcp": [{ "HostPort": "11022" }] },
     "PublishAllPorts":false,
     "Privileged":false,
     "Dns": ["8.8.8.8"],
     "VolumesFrom": ["parent", "other:ro"],
     "CapAdd": ["NET_ADMIN"],
     "CapDrop": ["MKNOD"]
}
```

```http
HTTP/1.1 204 No Content
```


--------------------------------

### Start the Ollama server with ollama serve

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/providers/local/index.md

Start the Ollama server instance manually if it does not launch automatically.

```bash
ollama serve
```


--------------------------------

### Start container with POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.8.md

Starts a container with optional JSON configuration for volume binds, LXC options, port bindings, and extended privileges. Returns status 204 No Content on success.

```http
POST /containers/(id)/start HTTP/1.1
Content-Type: application/json

{
     "Binds":["/tmp:/tmp"],
     "LxcConf":[{"Key":"lxc.utsname","Value":"docker"}],
     "PortBindings":{ "22/tcp": [{ "HostPort": "11022" }] },
     "PublishAllPorts":false,
     "Privileged":false
}
```

```http
HTTP/1.1 204 No Content
Content-Type: text/plain
```


--------------------------------

### Start a container via POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.3.md

Starts the specified container ID, optionally taking hostConfig parameters such as bind mounts. Returns 204 No Content upon successful start.

```http
POST /containers/(id)/start HTTP/1.1
Content-Type: application/json

{
     "Binds":["/tmp:/tmp"]
}
```

```http
HTTP/1.1 204 No Content
Content-Type: text/plain
```


--------------------------------

### Start a container with POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.7.md

Starts the specified container ID. Binds must reference volumes defined during container creation.

```http
POST /containers/(id)/start HTTP/1.1
Content-Type: application/json

{
     "Binds":["/tmp:/tmp"],
     "LxcConf":[{"Key":"lxc.utsname","Value":"docker"}],
     "PortBindings":{ "22/tcp": [{ "HostPort": "11022" }] },
     "Privileged":false,
     "PublishAllPorts":false
}
```

```http
HTTP/1.1 204 No Content
Content-Type: text/plain
```


--------------------------------

### Start a container with POST /containers/(id or name)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.15.md

Starts a container using runtime configuration parameters including volume binds, port mappings, and restart policies. Returns HTTP status 204 on success, 304 if already started, or 404 if the container does not exist.

```http
POST /containers/e90e34656806/start HTTP/1.1
Content-Type: application/json

{
     "Binds": ["/tmp:/tmp"],
     "Links": ["redis3:redis"],
     "LxcConf": {"lxc.utsname":"docker"},
     "PortBindings": { "22/tcp": [{ "HostPort": "11022" }] },
     "PublishAllPorts": false,
     "Privileged": false,
     "Dns": ["8.8.8.8"],
     "DnsSearch": [""],
     "VolumesFrom": ["parent", "other:ro"],
     "CapAdd": ["NET_ADMIN"],
     "CapDrop": ["MKNOD"],
     "RestartPolicy": { "Name": "", "MaximumRetryCount": 0 },
     "NetworkMode": "bridge",
     "Devices": []
}
```

```http
HTTP/1.1 204 No Content
```


--------------------------------

### Start Exec Instance via POST /exec/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.20.md

Starts a previously set up exec instance. If detach is false, sets up an interactive session over a raw stream; otherwise returns immediately after starting.

```http
POST /v1.20/exec/e90e34656806/start HTTP/1.1
Content-Type: application/json
Content-Length: 12345

{
 "Detach": false,
 "Tty": false
}
```

```http
HTTP/1.1 200 OK
Content-Type: application/vnd.docker.raw-stream

{% raw %}
{{ STREAM }}
{% endraw %}
```


--------------------------------

### Start container via POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.10.md

Starts the specified container with optional host configuration settings such as port bindings, binds, and DNS.

```http
POST /containers/(id)/start HTTP/1.1
Content-Type: application/json

{
     "Binds":["/tmp:/tmp"],
     "LxcConf":[{"Key":"lxc.utsname","Value":"docker"}],
     "PortBindings":{ "22/tcp": [{ "HostPort": "11022" }] },
     "PublishAllPorts":false,
     "Privileged":false,
     "Dns": ["8.8.8.8"],
     "VolumesFrom": ["parent", "other:ro"]
}
```

```http
HTTP/1.1 204 No Content
Content-Type: text/plain
```


--------------------------------

### Start container via POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.13.md

Starts an existing container using host configurations such as port bindings, volume mounts, DNS settings, and link configurations.

```http
POST /containers/(id)/start HTTP/1.1
Content-Type: application/json

{
     "Binds":["/tmp:/tmp"],
     "Links":["redis3:redis"],
     "LxcConf":[{"Key":"lxc.utsname","Value":"docker"}],
     "PortBindings":{ "22/tcp": [{ "HostPort": "11022" }] },
     "PublishAllPorts":false,
     "Privileged":false,
     "Dns": ["8.8.8.8"],
     "VolumesFrom": ["parent", "other:ro"]
}
```

```http
HTTP/1.1 204 No Content
Content-Type: text/plain
```


--------------------------------

### POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.3.md

Start a container with optional host configuration bindings.

```APIDOC
## POST /containers/(id)/start

### Description
Start the container `id`

### Method
POST

### Endpoint
`/containers/(id)/start`

### Parameters
#### Path Parameters
- **id** (string) - Required - Container ID

#### Request Body
- **hostConfig** (object) - Optional - The container's host configuration

### Request Example
```http
POST /containers/4fa6e0f0c678/start HTTP/1.1
Content-Type: application/json

{
     "Binds":["/tmp:/tmp"]
}
```

### Response
#### Status Codes
- **200** – no error
- **404** – no such container
- **500** – server error

#### Response Example
```http
HTTP/1.1 204 No Content
Content-Type: text/plain
```
```


--------------------------------

### Diagnose and setup Claude Code harness

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/features/harnesses/index.md

Probe harness installation and login state using docker agent doctor, or run interactive harness configuration via docker agent setup.

```bash
$ docker agent doctor ./agent.yaml   # checks install + login for claude-code harness files
$ docker agent setup                 # pick "Claude Code harness" to be walked through it
```


--------------------------------

### Generate shell completion scripts

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/features/cli/index.md

Generates autocompletion scripts for bash, zsh, fish, or powershell, with examples for session loading and permanent installation.

```bash
$ docker agent completion <bash|zsh|fish|powershell>

# Examples
# Bash: load for the current session
$ source <(docker agent completion bash)

# Zsh: install permanently (adjust the path for your $fpath)
$ docker agent completion zsh > "${fpath[1]}/_docker-agent"
```


--------------------------------

### Complete user settings configuration in config.yaml

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/configuration/user-settings/index.md

Example ~/.config/cagent/config.yaml file demonstrating the full suite of user settings including theme, layout, permission filters, session hooks, and keybindings.

```yaml
# ~/.config/cagent/config.yaml
settings:
  theme: auto
  theme_dark: dracula
  theme_light: default-light
  lean: false
  expand_thinking: false
  split_diff_view: true
  render_images: true
  hide_tool_results: false
  sound: true
  sound_threshold: 10
  snapshot: true
  cache_stable_prompts: true
  warn_on_cache_miss: true
  busy_send_mode: queue
  interrupt_confirmation: double-tap
  restore_tabs: true
  tab_title_max_length: 24
  layout:
    sidebar_position: right
    section_spacing: normal
  permissions:
    deny:
      - "shell:cmd=sudo*"
    allow:
      - "read_*"
  hooks:
    session_start:
      - type: command
        command: "~/.config/cagent/hooks/session-start.sh"
  keybindings:
    - action: "commands"
      keys: ["f2", "ctrl+k"]
```


--------------------------------

### Start an exec instance with POST /exec/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.15.md

Starts a previously configured exec instance interactively or detached. Returns a raw stream on success or HTTP 404 if the exec instance is not found.

```http
POST /exec/e90e34656806/start HTTP/1.1
Content-Type: application/json

{
     "Detach": false,
     "Tty": false,
}
```

```http
HTTP/1.1 200 OK
Content-Type: application/vnd.docker.raw-stream

{{ STREAM }}
```


--------------------------------

### Start an exec instance with POST /exec/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.18.md

Starts a previously created exec instance. When Detach is false, it establishes an interactive raw stream session; if true, it returns immediately after starting.

```http
POST /v1.18/exec/e90e34656806/start HTTP/1.1
Content-Type: application/json
Content-Length: 12345

{
 "Detach": false,
 "Tty": false
}
```

```http
HTTP/1.1 200 OK
Content-Type: application/vnd.docker.raw-stream

{% raw %}
{{ STREAM }}
{% endraw %}
```


--------------------------------

### GET /v1.22/events

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.22.md

Streams real-time events from Docker, including container, image, volume, and network activity. Allows filtering events starting from a specific timestamp.

```APIDOC
## GET /v1.22/events

### Description
Get container events from docker, in real time via streaming.

### Method
GET

### Endpoint
/v1.22/events

### Parameters
#### Query Parameters
- **since** (string/integer) - Optional - Timestamp to monitor events from.

### Request Example
```http
GET /v1.22/events?since=1374067924
```

### Response
#### Success Response (200 OK)
Streamed event messages in real time.

#### Response Example
```http
HTTP/1.1 200 OK
Content-Type: application/json
Server: Docker/1.10.0 (linux)
Date: Fri, 29 Apr 2016 15:18:06 GMT
Transfer-Encoding: chunked
```
```


--------------------------------

### Create and inspect network to verify default options

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/cli/docs/reference/dockerd.md

Demonstrates creating a new network and inspecting its options to confirm default network settings are applied. Changing daemon default configuration does not update existing networks.

```console
$ docker network create mynet
$ docker network inspect mynet --format "{{json .Options}}"
{"com.docker.network.bridge.host_binding_ipv4":"127.0.0.1","com.docker.network.driver.mtu":"1234"}
```


--------------------------------

### Start a container with POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.0.md

Start an existing container by container ID. Returns status code 200 OK when successfully started, or 404 if the container is not found.

```http
POST /containers/e90e34656806/start HTTP/1.1
```

```http
HTTP/1.1 200 OK
```


--------------------------------

### GET /info

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.16.md

Display system-wide information regarding the Docker daemon installation. Returns container and image counts, storage drivers, memory limits, and kernel details.

```APIDOC
## GET /info

### Description
Display system-wide information.

### Method
GET

### Endpoint
/info

### Request Example
```http
GET /info HTTP/1.1
```

### Response
#### Status Codes
- **200** - No error
- **500** - Server error

#### Response Example
```json
{
     "Containers": 11,
     "Images": 16,
     "Driver": "btrfs",
     "DriverStatus": [[""]],
     "ExecutionDriver": "native-0.1",
     "KernelVersion": "3.12.0-1-amd64",
     "NCPU": 1,
     "MemTotal": 2099236864,
     "Name": "prod-server-42",
     "ID": "7TRN:IPZB:QYBB:VPBQ:UMPP:KARE:6ZNR:XE6T:7EWV:PKF4:ZOJD:TPYS",
     "Debug": false,
     "NFd": 11,
     "NGoroutines": 21,
     "NEventsListener": 0,
     "InitPath": "/usr/bin/docker",
     "InitSha1": "",
     "IndexServerAddress": ["https://index.docker.io/v1/"],
     "MemoryLimit": true,
     "SwapLimit": false,
     "IPv4Forwarding": true,
     "Labels": ["storage=ssd"],
     "DockerRootDir": "/var/lib/docker",
     "OperatingSystem": "Boot2Docker"
}
```
```


--------------------------------

### Create a skill directory and SKILL.md file

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/features/skills/index.md

Sets up a new skill directory under ~/.agents/skills and writes a SKILL.md file with frontmatter metadata and instructions. Once created, the skill is automatically available to agents with skills enabled.

```bash
# Create the skill directory
$ mkdir -p ~/.agents/skills/create-dockerfile

# Write the SKILL.md file
$ cat > ~/.agents/skills/create-dockerfile/SKILL.md << 'EOF'
---
name: create-dockerfile
description: Create optimized Dockerfiles for applications
---

# Creating Dockerfiles

When asked to create a Dockerfile:

1. Analyze the application type and language
2. Use multi-stage builds for compiled languages
3. Use slim base images to minimize size
4. Run as non-root user for security
EOF
```


--------------------------------

### Install Docker Agent with Homebrew

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/getting-started/installation/index.md

Install Docker Agent on macOS or Linux using Homebrew and verify the installation.

```bash
# Install
$ brew install docker-agent

# Verify
$ docker-agent version
```


--------------------------------

### GET /info

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.21.md

Display system-wide information regarding the Docker daemon installation and environment. Includes container counts, storage driver details, memory limits, and registry configurations.

```APIDOC
## GET /info

### Description
Display system-wide information.

### Method
GET

### Endpoint
/info

### Response
#### Success Response (200)
- **ClusterStore** (string) - Cluster store address
- **Containers** (integer) - Total number of containers
- **CpuCfsPeriod** (boolean) - CPU CFS period support
- **CpuCfsQuota** (boolean) - CPU CFS quota support
- **Debug** (boolean) - Debug mode status
- **DockerRootDir** (string) - Root directory for Docker storage
- **Driver** (string) - Storage driver
- **DriverStatus** (array) - Driver status details
- **ExecutionDriver** (string) - Execution driver
- **ExperimentalBuild** (boolean) - Experimental build flag
- **HttpProxy** (string) - HTTP proxy address
- **HttpsProxy** (string) - HTTPS proxy address
- **ID** (string) - Unique system ID
- **IPv4Forwarding** (boolean) - IPv4 forwarding status
- **Images** (integer) - Total number of images
- **IndexServerAddress** (string) - Index server address
- **InitPath** (string) - Path to docker init
- **InitSha1** (string) - Init SHA1 hash
- **KernelVersion** (string) - Operating system kernel version
- **Labels** (array) - System labels
- **MemTotal** (integer) - Total system memory
- **MemoryLimit** (boolean) - Memory limit support
- **NCPU** (integer) - Number of CPUs
- **NEventsListener** (integer) - Number of event listeners
- **NFd** (integer) - Number of open file descriptors
- **NGoroutines** (integer) - Number of Goroutines
- **Name** (string) - System host name
- **NoProxy** (string) - No proxy configuration
- **OomKillDisable** (boolean) - OOM kill disable support
- **OperatingSystem** (string) - Operating system name
- **RegistryConfig** (object) - Registry configuration details
- **ServerVersion** (string) - Server version
- **SwapLimit** (boolean) - Swap limit support
- **SystemTime** (string) - Current system time

#### Response Example
```json
{
    "ClusterStore": "etcd://localhost:2379",
    "Containers": 11,
    "CpuCfsPeriod": true,
    "CpuCfsQuota": true,
    "Debug": false,
    "DockerRootDir": "/var/lib/docker",
    "Driver": "btrfs",
    "DriverStatus": [[""]],
    "ExecutionDriver": "native-0.1",
    "ExperimentalBuild": false,
    "HttpProxy": "http://test:test@localhost:8080",
    "HttpsProxy": "https://test:test@localhost:8080",
    "ID": "7TRN:IPZB:QYBB:VPBQ:UMPP:KARE:6ZNR:XE6T:7EWV:PKF4:ZOJD:TPYS",
    "IPv4Forwarding": true,
    "Images": 16,
    "IndexServerAddress": "https://index.docker.io/v1/",
    "InitPath": "/usr/bin/docker",
    "InitSha1": "",
    "KernelVersion": "3.12.0-1-amd64",
    "Labels": [
        "storage=ssd"
    ],
    "MemTotal": 2099236864,
    "MemoryLimit": true,
    "NCPU": 1,
    "NEventsListener": 0,
    "NFd": 11,
    "NGoroutines": 21,
    "Name": "prod-server-42",
    "NoProxy": "9.81.1.160",
    "OomKillDisable": true,
    "OperatingSystem": "Boot2Docker",
    "RegistryConfig": {
        "IndexConfigs": {
            "docker.io": {
                "Mirrors": null,
                "Name": "docker.io",
                "Official": true,
                "Secure": true
            }
        },
        "InsecureRegistryCIDRs": [
            "127.0.0.0/8"
        ]
    },
    "ServerVersion": "1.9.0",
    "SwapLimit": false,
    "SystemTime": "2015-03-10T11:11:23.730591467-07:00"
}
```

#### Status Codes
- **200** – no error
- **500** – server error
```


--------------------------------

### Start an exec instance

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.23.md

Starts a previously configured exec instance. Returns a raw stream session if detach is false, or returns immediately after starting if detach is true.

```http
POST /v1.23/exec/e90e34656806/start HTTP/1.1
Content-Type: application/json
Content-Length: 12345

{
 "Detach": false,
 "Tty": false
}
```

```http
HTTP/1.1 200 OK
Content-Type: application/vnd.docker.raw-stream

{% raw %}
{{ STREAM }}
{% endraw %}
```


--------------------------------

### Monitor Docker events with GET /events

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.10.md

Streams real-time events or polls past container and image lifecycle events starting from a given timestamp using the since parameter.

```http
GET /events?since=1374067924
```

```http
HTTP/1.1 200 OK
Content-Type: application/json

{"status": "create", "id": "dfdf82bd3881","from": "ubuntu:latest", "time":1374067924}
{"status": "start", "id": "dfdf82bd3881","from": "ubuntu:latest", "time":1374067924}
{"status": "stop", "id": "dfdf82bd3881","from": "ubuntu:latest", "time":1374067966}
{"status": "destroy", "id": "dfdf82bd3881","from": "ubuntu:latest", "time":1374067970}
```


--------------------------------

### Start a container with POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.5.md

Starts the specified container with optional host configuration parameters like Binds and LxcConf. Returns status code 204 No Content on success.

```http
POST /containers/(id)/start HTTP/1.1
Content-Type: application/json

{
  "Binds":["/tmp:/tmp"],
  "LxcConf":[{"Key":"lxc.utsname","Value":"docker"}]
}
```

```http
HTTP/1.1 204 No Content
Content-Type: text/plain
```


--------------------------------

### Eval session JSON format example

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/features/evaluation/index.md

Defines an evaluation session recording a user prompt, expected assistant tool calls and responses, along with evaluation criteria and setup configuration.

```json
{
  "id": "41b179a2-ed19-4ae2-a45d-95775aaa90f7",
  "title": "Counting Files in Local Folder",
  "messages": [
    {
      "message": {
        "message": {
          "role": "user",
          "content": "How many files in the local folder?"
        }
      }
    },
    {
      "message": {
        "agent_name": "root",
        "message": {
          "role": "assistant",
          "tool_calls": [
            {
              "id": "call_abc123",
              "type": "function",
              "function": {
                "name": "list_directory",
                "arguments": "{\"path\":\"./\"}"
              }
            }
          ]
        }
      }
    },
    {
      "message": {
        "agent_name": "root",
        "message": {
          "role": "assistant",
          "content": "There are 2 files in the local folder..."
        }
      }
    }
  ],
  "evals": {
    "relevance": [
      "The response mentions exactly 2 files",
      "The response lists README.md and agent.yaml"
    ],
    "size": "S",
    "working_dir": "my-project",
    "setup": "echo 'hello' > test.txt"
  }
}
```


--------------------------------

### POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.10.md

Starts the specified container with optional host configuration settings.

```APIDOC
## POST /containers/(id)/start

### Description
Start the container `id`.

### Method
POST

### Endpoint
`/containers/(id)/start`

### Parameters
#### Path Parameters
- **id** (string) - Required - Container ID

#### Request Body
- **hostConfig** (object) - Optional - The container's host configuration (e.g., `Binds`, `LxcConf`, `PortBindings`, `PublishAllPorts`, `Privileged`, `Dns`, `VolumesFrom`).

### Request Example
```http
POST /containers/(id)/start HTTP/1.1
Content-Type: application/json

{
     "Binds":["/tmp:/tmp"],
     "LxcConf":[{"Key":"lxc.utsname","Value":"docker"}],
     "PortBindings":{ "22/tcp": [{ "HostPort": "11022" }] },
     "PublishAllPorts":false,
     "Privileged":false,
     "Dns": ["8.8.8.8"],
     "VolumesFrom": ["parent", "other:ro"]
}
```

### Response
#### Success Response (204)
- **Content-Type**: `text/plain`

#### Response Example
```http
HTTP/1.1 204 No Content
Content-Type: text/plain
```

### Status Codes
- **204** – no error
- **404** – no such container
- **500** – server error
```


--------------------------------

### Start an exec instance via POST /exec/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.19.md

Starts a previously configured exec instance, either detaching or setting up an interactive raw stream session.

```http
POST /v1.19/exec/e90e34656806/start HTTP/1.1
Content-Type: application/json
Content-Length: 12345

{
 "Detach": false,
 "Tty": false
}
```

```http
HTTP/1.1 200 OK
Content-Type: application/vnd.docker.raw-stream

{% raw %}
{{ STREAM }}
{% endraw %}
```


--------------------------------

### Stream real-time Docker events with GET /events

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.18.md

Streams real-time container and image events from Docker starting from an optional Unix timestamp. Supports filtering by container, event, or image name.

```http
GET /v1.18/events?since=1374067924
```

```http
HTTP/1.1 200 OK
Content-Type: application/json

{"status": "create", "id": "dfdf82bd3881","from": "ubuntu:latest", "time":1374067924}
{"status": "start", "id": "dfdf82bd3881","from": "ubuntu:latest", "time":1374067924}
{"status": "stop", "id": "dfdf82bd3881","from": "ubuntu:latest", "time":1374067966}
{"status": "destroy", "id": "dfdf82bd3881","from": "ubuntu:latest", "time":1374067970}
```


--------------------------------

### Use desktop-install-v2 Shortcode in Markdown

Source: https://github.com/docker/docs/blob/main/_autodocs/api-reference/shortcodes-download.md

Demonstrates invoking the desktop-install-v2 shortcode in Markdown with all platforms enabled and a root build path.

```markdown
{{</* desktop-install-v2 all="true" build_path="/" */>}}
```


--------------------------------

### Register custom provider interactively with docker agent setup

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/providers/custom/index.md

Run docker agent setup to launch the interactive wizard for registering a custom OpenAI-compatible endpoint.

```bash
docker agent setup
# pick "3. Custom OpenAI-compatible endpoint", then enter the base URL,
# API format, and the environment variable holding the API key
```


--------------------------------

### GET /events

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.5.md

Streams real-time events or polls past events from the Docker daemon using a timestamp. Reports container lifecycle events (such as create, start, stop) and image events (such as untag, delete).

```APIDOC
## GET /events

### Description
Get events from docker, either in real time via streaming, or via polling (using since).

Docker containers will report the following events: `create`, `destroy`, `die`, `export`, `kill`, `pause`, `restart`, `start`, `stop`, `unpause`
Docker images will report: `untag`, `delete`

### Method
GET

### Endpoint
/events

### Parameters
#### Query Parameters
- **since** (string) - Optional - Timestamp used for polling

### Request Example
```http
GET /events?since=1374067924
```

### Response
#### Status Codes
- **200** - No error
- **500** - Server error

#### Success Response (200)
- **status** (string) - Event action status
- **id** (string) - Target container or image ID
- **from** (string) - Source image reference
- **time** (integer) - Timestamp of the event

#### Response Example
```json
{"status":"create","id":"dfdf82bd3881","from":"ubuntu:latest","time":1374067924}
{"status":"start","id":"dfdf82bd3881","from":"ubuntu:latest","time":1374067924}
{"status":"stop","id":"dfdf82bd3881","from":"ubuntu:latest","time":1374067966}
{"status":"destroy","id":"dfdf82bd3881","from":"ubuntu:latest","time":1374067970}
```
```


--------------------------------

### Define desktop-install template signature in layouts/_shortcodes/desktop-install.html

Source: https://github.com/docker/docs/blob/main/_autodocs/api-reference/shortcodes-download.md

Reads parameter values for platform flags, versioning, and build paths within the shortcode definition. Applies the tip class to the blockquote element when build_path is set to "/".

```go-html-template
{{- $all := .Get "all" -}}
{{- $win := .Get "win" -}}
{{- $win_arm_release := .Get "win_arm_release" -}}
{{- $mac := .Get "mac" -}}
{{- $linux := .Get "linux" -}}
{{- $version := .Get "version" -}}
{{- $build_path := .Get "build_path" -}}
<blockquote {{ if eq $build_path "/" }} class="tip" {{ end }}>
<p>Download Docker Desktop</p>
<p>
```


--------------------------------

### Monitor Docker's events JSON stream output

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.22.md

Example JSON event stream emitted by the Docker daemon when monitoring events. Represents actions across image, container, and network lifecycle transitions including pull, create, attach, connect, start, resize, die, disconnect, and destroy.

```json
{
  "status": "pull",
  "id": "alpine:latest",
  "Type": "image",
  "Action": "pull",
  "Actor": {
    "ID": "alpine:latest",
    "Attributes": {
      "name": "alpine"
    }
  },
  "time": 1461943101,
  "timeNano": 1461943101301854122
}
{
  "status": "create",
  "id": "ede54ee1afda366ab42f824e8a5ffd195155d853ceaec74a927f249ea270c743",
  "from": "alpine",
  "Type": "container",
  "Action": "create",
  "Actor": {
    "ID": "ede54ee1afda366ab42f824e8a5ffd195155d853ceaec74a927f249ea270c743",
    "Attributes": {
      "com.example.some-label": "some-label-value",
      "image": "alpine",
      "name": "my-container"
    }
  },
  "time": 1461943101,
  "timeNano": 1461943101381709551
}
{
  "status": "attach",
  "id": "ede54ee1afda366ab42f824e8a5ffd195155d853ceaec74a927f249ea270c743",
  "from": "alpine",
  "Type": "container",
  "Action": "attach",
  "Actor": {
    "ID": "ede54ee1afda366ab42f824e8a5ffd195155d853ceaec74a927f249ea270c743",
    "Attributes": {
      "com.example.some-label": "some-label-value",
      "image": "alpine",
      "name": "my-container"
    }
  },
  "time": 1461943101,
  "timeNano": 1461943101383858412
}
{
  "Type": "network",
  "Action": "connect",
  "Actor": {
    "ID": "7dc8ac97d5d29ef6c31b6052f3938c1e8f2749abbd17d1bd1febf2608db1b474",
    "Attributes": {
      "container": "ede54ee1afda366ab42f824e8a5ffd195155d853ceaec74a927f249ea270c743",
      "name": "bridge",
      "type": "bridge"
    }
  },
  "time": 1461943101,
  "timeNano": 1461943101394865557
}
{
  "status": "start",
  "id": "ede54ee1afda366ab42f824e8a5ffd195155d853ceaec74a927f249ea270c743",
  "from": "alpine",
  "Type": "container",
  "Action": "start",
  "Actor": {
    "ID": "ede54ee1afda366ab42f824e8a5ffd195155d853ceaec74a927f249ea270c743",
    "Attributes": {
      "com.example.some-label": "some-label-value",
      "image": "alpine",
      "name": "my-container"
    }
  },
  "time": 1461943101,
  "timeNano": 1461943101607533796
}
{
  "status": "resize",
  "id": "ede54ee1afda366ab42f824e8a5ffd195155d853ceaec74a927f249ea270c743",
  "from": "alpine",
  "Type": "container",
  "Action": "resize",
  "Actor": {
    "ID": "ede54ee1afda366ab42f824e8a5ffd195155d853ceaec74a927f249ea270c743",
    "Attributes": {
      "com.example.some-label": "some-label-value",
      "height": "46",
      "image": "alpine",
      "name": "my-container",
      "width": "204"
    }
  },
  "time": 1461943101,
  "timeNano": 1461943101610269268
}
{
  "status": "die",
  "id": "ede54ee1afda366ab42f824e8a5ffd195155d853ceaec74a927f249ea270c743",
  "from": "alpine",
  "Type": "container",
  "Action": "die",
  "Actor": {
    "ID": "ede54ee1afda366ab42f824e8a5ffd195155d853ceaec74a927f249ea270c743",
    "Attributes": {
      "com.example.some-label": "some-label-value",
      "exitCode": "0",
      "image": "alpine",
      "name": "my-container"
    }
  },
  "time": 1461943105,
  "timeNano": 1461943105079144137
}
{
  "Type": "network",
  "Action": "disconnect",
  "Actor": {
    "ID": "7dc8ac97d5d29ef6c31b6052f3938c1e8f2749abbd17d1bd1febf2608db1b474",
    "Attributes": {
      "container": "ede54ee1afda366ab42f824e8a5ffd195155d853ceaec74a927f249ea270c743",
      "name": "bridge",
      "type": "bridge"
    }
  },
  "time": 1461943105,
  "timeNano": 1461943105230860245
}
{
  "status": "destroy",
  "id": "ede54ee1afda366ab42f824e8a5ffd195155d853ceaec74a927f249ea270c743",
  "from": "alpine",
  "Type": "container",
  "Action": "destroy",
  "Actor": {
    "ID": "ede54ee1afda366ab42f824e8a5ffd195155d853ceaec74a927f249ea270c743",
    "Attributes": {
      "com.example.some-label": "some-label-value",
      "image": "alpine",
      "name": "my-container"
    }
  },
  "time": 1461943105,
  "timeNano": 1461943105338056026
}
```


--------------------------------

### POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.6.md

Start a container with optional host configuration settings such as port bindings and volume mounts.

```APIDOC
## POST /containers/(id)/start

### Description
Start the container `id`

### Method
POST

### Endpoint
`/containers/(id)/start`

### Parameters
#### Path Parameters
- **id** (string) - Required - Container ID

#### Request Body
- **hostConfig** (object) - Optional - the container's host configuration

### Request Example
```http
POST /containers/(id)/start HTTP/1.1
Content-Type: application/json

{
     "Binds":["/tmp:/tmp"],
     "LxcConf":[{"Key":"lxc.utsname","Value":"docker"}],
     "ContainerIDFile": "",
     "Privileged": false,
     "PortBindings": {"22/tcp": [{"HostIp":"", "HostPort":""}]},
     "Links": [],
     "PublishAllPorts": false
}
```

### Response
#### Success Response (204)
Status Codes:
- **204** – no error
- **404** – no such container
- **500** – server error

#### Response Example
```http
HTTP/1.1 204 No Content
Content-Type: text/plain
```
```


--------------------------------

### POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.5.md

Starts the specified container with optional host configuration.

```APIDOC
## POST /containers/(id)/start

### Description
Start the container `id`.

### Method
POST

### Endpoint
/containers/(id)/start

### Parameters
#### Path Parameters
- **id** (string) - Required - Container ID or name

#### Request Body
- **hostConfig** (object) - Optional - The container's host configuration

### Request Example
```json
{
  "Binds":["/tmp:/tmp"],
  "LxcConf":[{"Key":"lxc.utsname","Value":"docker"}]
}
```

### Response
#### Success Response (204 No Content)
No content is returned on success.

#### Status Codes
- **204** – no error
- **404** – no such container
- **500** – server error
```


--------------------------------

### POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.13.md

Starts the specified container with optional host configuration settings including volume bindings, port bindings, and DNS configuration.

```APIDOC
## POST /containers/(id)/start

### Description
Start the container `id`.

### Method
POST

### Endpoint
`/containers/(id)/start`

### Parameters
#### Path Parameters
- **id** (string) - Required - Container ID or name

#### Request Body
- **hostConfig** (object) - Optional - The container's host configuration

### Request Example
```json
{
  "Binds": ["/tmp:/tmp"],
  "Links": ["redis3:redis"],
  "LxcConf": [{"Key": "lxc.utsname", "Value": "docker"}],
  "PortBindings": { "22/tcp": [{ "HostPort": "11022" }] },
  "PublishAllPorts": false,
  "Privileged": false,
  "Dns": ["8.8.8.8"],
  "VolumesFrom": ["parent", "other:ro"]
}
```

### Response
#### Success Response (204)
- No Content

#### Status Codes
- **204** - no error
- **304** - container already started
- **404** - no such container
- **500** - server error
```


--------------------------------

### POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.8.md

Starts a specific container with optional configurations such as mounts, port bindings, and custom LXC options. Returns status code 204 upon successful start.

```APIDOC
## POST /containers/(id)/start

### Description
Start the container `id`

### Method
POST

### Endpoint
/containers/(id)/start

### Parameters
#### Path Parameters
- **id** - Required - The container ID

#### Request Body
- **Binds** (array) - Optional - Create a bind mount to a directory or file with [host-path]:[container-path]:[rw|ro]. If a directory "container-path" is missing, then docker creates a new volume.
- **LxcConf** (array) - Optional - Map of custom lxc options
- **PortBindings** (object) - Optional - Expose ports from the container, optionally publishing them via the HostPort flag
- **PublishAllPorts** (boolean) - Optional - 1/True/true or 0/False/false, publish all exposed ports to the host interfaces. Default false
- **Privileged** (boolean) - Optional - 1/True/true or 0/False/false, give extended privileges to this container. Default false

### Request Example
```http
POST /containers/(id)/start HTTP/1.1
Content-Type: application/json

{
     "Binds":["/tmp:/tmp"],
     "LxcConf":[{"Key":"lxc.utsname","Value":"docker"}],
     "PortBindings":{ "22/tcp": [{ "HostPort": "11022" }] },
     "PublishAllPorts":false,
     "Privileged":false
}
```

### Response
#### Success Response (204)

#### Response Example
```http
HTTP/1.1 204 No Content
Content-Type: text/plain
```

#### Status Codes
- **204** – no error
- **404** – no such container
- **500** – server error
```


--------------------------------

### Define desktop-install-v2 Shortcode Template

Source: https://github.com/docker/docs/blob/main/_autodocs/api-reference/shortcodes-download.md

Shortcode template definition for desktop-install-v2 that parses platform and build path parameters to render styled download links with UTM tracking.

```go-html-template
{{- $all := .Get "all" -}}
{{- $win := .Get "win" -}}
{{- $win_arm_release := .Get "win_arm_release" -}}
{{- $mac := .Get "mac" -}}
{{- $linux := .Get "linux" -}}
{{- $build_path := .Get "build_path" -}}
<blockquote {{ if eq $build_path "/" }} class="tip" {{ end }} class="not-prose download-links">
  <p class="font-semibold mb-1">Download Docker Desktop</p>
```


--------------------------------

### POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.12.md

Start an existing container by ID or name with optional host configuration settings.

```APIDOC
## POST /containers/(id)/start

### Description
Start the container `id`.

### Method
POST

### Endpoint
`/containers/(id)/start`

### Parameters
#### Path Parameters
- **id** (string) - Required - Container ID or name

#### Request Body
- **hostConfig** (object) - Optional - The container's host configuration

### Request Example
```json
{
     "Binds":["/tmp:/tmp"],
     "Links":["redis3:redis"],
     "LxcConf":[{"Key":"lxc.utsname","Value":"docker"}],
     "PortBindings":{ "22/tcp": [{ "HostPort": "11022" }] },
     "PublishAllPorts":false,
     "Privileged":false,
     "Dns": ["8.8.8.8"],
     "VolumesFrom": ["parent", "other:ro"]
}
```

### Response
#### Success Response (204)
- No Content

#### Response Example
```http
HTTP/1.1 204 No Content
Content-Type: text/plain
```

#### Status Codes
- **204** - no error
- **404** - no such container
- **500** - server error
```


--------------------------------

### Example interaction with user_prompt tool

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/tools/user-prompt/index.md

Illustrates how an agent prompts a user for input using enum and boolean schemas to select an environment and confirm deployment.

```text
Agent: I need to deploy this application. Let me ask which environment to target.

[Calls user_prompt with message: "Which environment should I deploy to?"
 and schema with enum: ["development", "staging", "production"]]

User selects: "staging"

Agent: Great, I'll deploy to staging. Let me confirm this action.

[Calls user_prompt with message: "Deploy to staging? This will replace the current version."
 and schema with type: "boolean"]

User confirms: true

Agent: Deploying to staging...
```


--------------------------------

### Configure sample volume plugin (tiborvass/sample-volume-plugin)

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/cli/docs/extend/config.md

Demonstrates a complete plugin configuration for a volume driver implementing docker.volumedriver/1.0 with a custom entrypoint, debug environment variable, socket, and propagated mount path.

```json
{
  "Args": {
    "Description": "",
    "Name": "",
    "Settable": null,
    "Value": null
  },
  "Description": "A sample volume plugin for Docker",
  "Documentation": "https://docs.docker.com/engine/extend/plugins/",
  "Entrypoint": [
    "/usr/bin/sample-volume-plugin",
    "/data"
  ],
  "Env": [
    {
      "Description": "",
      "Name": "DEBUG",
      "Settable": [
        "value"
      ],
      "Value": "0"
    }
  ],
  "Interface": {
    "Socket": "plugin.sock",
    "Types": [
      "docker.volumedriver/1.0"
    ]
  },
  "Linux": {
    "Capabilities": null,
    "AllowAllDevices": false,
    "Devices": null
  },
  "Mounts": null,
  "Network": {
    "Type": ""
  },
  "PropagatedMount": "/data",
  "User": {},
  "Workdir": ""
}
```


--------------------------------

### View git_status output example

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/tools/git/index.md

Example structured text output returned by invoking the git_status tool.

```text
On branch master
1 changed file(s) [XY = staged/worktree; M=modified A=added D=deleted R=renamed ?=untracked]:
   M main.go
```


--------------------------------

### Perform HTTP GET request with get

Source: https://github.com/docker/docs/blob/main/content/reference/api/extensions-sdk/BackendV0.md

Performs an HTTP GET request to a backend service URL. Note that this method will be removed in a future version in favor of HttpService.

```typescript
window.ddClient.backend
 .get("/some/service")
 .then((value: any) => console.log(value));
```


--------------------------------

### docker agent serve mcp usage examples

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/features/cli/index.md

Examples for serving agents using stdio transport, streaming HTTP with a custom listen address, a custom working directory, or a prebuilt agent image.

```bash
# Examples
$ docker agent serve mcp agent.yaml                                # stdio transport
$ docker agent serve mcp agent.yaml --http --listen 127.0.0.1:9090 # streaming HTTP
$ docker agent serve mcp agent.yaml --working-dir /path/to/project
$ docker agent serve mcp myorg/coder
```


--------------------------------

### get(url)

Source: https://github.com/docker/docs/blob/main/content/reference/api/extensions-sdk/HttpService.md

Performs an HTTP GET request to a backend service.

```APIDOC
## get(url)

### Description
Performs an HTTP GET request to a backend service.

### Signature
```typescript
get(url: string): Promise<unknown>
```

### Parameters
- **url** (`string`) - The URL of the backend service.

### Returns
- `Promise<unknown>`

### Example
```typescript
ddClient.extension.vm.service
 .get("/some/service")
 .then((value: any) => console.log(value)
```
```


--------------------------------

### Run docker agent serve api examples

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/features/cli/index.md

Common command invocations demonstrating serving a single file, binding to a specific address, exposing a directory of agent configurations, and auto-refreshing an OCI reference.

```bash
# Examples
$ docker agent serve api agent.yaml
$ docker agent serve api agent.yaml --listen :8080
$ docker agent serve api ./agents/                          # directory of agent YAML/HCL configs
$ docker agent serve api ociReference --pull-interval 10    # auto-refresh
```


--------------------------------

### Create and run a basic agent using Go SDK

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/guides/go-sdk/index.md

Initializes an OpenAI model provider, creates an assistant agent, wraps it in a team runtime, and executes a session with a user prompt.

```go
package main

import (
    "context"
    "fmt"
    "log"
    "os/signal"
    "syscall"

    "github.com/docker/docker-agent/pkg/agent"
    "github.com/docker/docker-agent/pkg/config/latest"
    "github.com/docker/docker-agent/pkg/environment"
    "github.com/docker/docker-agent/pkg/model/provider/openai"
    "github.com/docker/docker-agent/pkg/runtime"
    "github.com/docker/docker-agent/pkg/session"
    "github.com/docker/docker-agent/pkg/team"
)

func main() {
    ctx, cancel := signal.NotifyContext(context.Background(),
        syscall.SIGINT, syscall.SIGTERM)
    defer cancel()

    if err := run(ctx); err != nil {
        log.Fatal(err)
    }
}

func run(ctx context.Context) error {
    // Create model provider
    llm, err := openai.NewClient(
        ctx,
        &latest.ModelConfig{
            Provider: "openai",
            Model:    "gpt-4o",
        },
        environment.NewDefaultProvider(),
    )
    if err != nil {
        return err
    }

    // Create agent
    assistant := agent.New(
        "root",
        "You are a helpful assistant.",
        agent.WithModel(llm),
        agent.WithDescription("A helpful assistant"),
    )

    // Create team and runtime
    t := team.New(team.WithAgents(assistant))
    rt, err := runtime.New(t)
    if err != nil {
        return err
    }

    // Run with a user message
    sess := session.New(
        session.WithUserMessage("What is 2 + 2?"),
    )

    messages, err := rt.Run(ctx, sess)
    if err != nil {
        return err
    }

    // Print the response
    fmt.Println(messages[len(messages)-1].Message.Content)
    return nil
}
```


--------------------------------

### Download and install binary release on macOS / Linux

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/getting-started/installation/index.md

Download the latest release binary for your system architecture, set execution permissions, and install it to `/usr/local/bin/` or as a Docker CLI plugin in `~/.docker/cli-plugins`.

```bash
# Download the latest release
OS=$(uname -s | tr '[:upper:]' '[:lower:]')
ARCH=$(uname -m); case "$ARCH" in x86_64) ARCH=amd64;; aarch64) ARCH=arm64;; esac
curl -L "https://github.com/docker/docker-agent/releases/latest/download/docker-agent-${OS}-${ARCH}" -o docker-agent
chmod +x docker-agent
sudo mv docker-agent /usr/local/bin/
docker-agent version

# or alternatively, instead of moving to /usr/local/bin:
mkdir -p ~/.docker/cli-plugins
sudo mv docker-agent ~/.docker/cli-plugins
docker agent version
```


--------------------------------

### Start Chat Server with docker agent serve chat

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/features/cli/index.md

Syntax for starting an OpenAI-compatible Chat Completions HTTP server exposing one or more configured agents.

```bash
$ docker agent serve chat <config> [flags]
```


--------------------------------

### get

Source: https://github.com/docker/docs/blob/main/content/reference/api/extensions-sdk/BackendV0.md

Performs an HTTP GET request to a backend service. Returns a promise resolving with the response.

```APIDOC
## get(url)

### Description
Performs an HTTP GET request to a backend service. Note: It will be removed in a future version. Use HttpService get instead.

### Signature
```typescript
get(url: string): Promise<unknown>
```

### Parameters
- **url** (`string`) - The URL of the backend service.

### Returns
- `Promise<unknown>` - Promise resolving to the response data.

### Example
```typescript
window.ddClient.backend
 .get("/some/service")
 .then((value: any) => console.log(value));
```
```


--------------------------------

### Configure services with bind mounts, dependencies, and build stages

Source: https://github.com/docker/docs/blob/main/content/reference/compose-file/services.md

Sets up a proxy service with a read-only bind mount and dependency on a backend service built from a specific build stage.

```yaml
services:
  proxy:
    image: nginx
    volumes:
      - type: bind
        source: ./proxy/nginx.conf
        target: /etc/nginx/conf.d/default.conf
        read_only: true
    ports:
      - 80:80
    depends_on:
      - backend

  backend:
    build:
      context: backend
      target: builder
```


--------------------------------

### GET /containers/(id or name)/archive

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.21.md

Get a tar archive of a resource in the filesystem of a container.

```APIDOC
## GET /containers/(id or name)/archive

### Description
Get a tar archive of a resource in the filesystem of container `id`.

### Method
GET

### Endpoint
/containers/(id or name)/archive

### Parameters
#### Path Parameters
- **id or name** (string) - Required - Container ID or name

#### Query Parameters
- **path** (string) - Required - Resource in the container's filesystem to archive. If not an absolute path, it is relative to the container's root directory. The resource must exist. End in `/` or `/.` to assert directory behavior.

### Request Example
```http
GET /v1.21/containers/8cce319429b2/archive?path=/root HTTP/1.1
```

### Response
#### Success Response (200)
Returns a tar stream (`application/x-tar`) along with the `X-Docker-Container-Path-Stat` header containing base64-encoded stat JSON.

#### Response Stat Object Example (Decoded Header)
```json
{
  "name": "root",
  "size": 4096,
  "mode": 2147484096,
  "mtime": "2014-02-27T20:51:23Z",
  "linkTarget": ""
}
```

#### Status Codes
- **200** - success, returns archive of copied resource
- **400** - client error, bad parameter (must specify path parameter or not a directory)
- **404** - client error, resource not found (no such container or no such file/directory)
- **500** - server error
```


--------------------------------

### GET /containers/(id or name)/logs

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.16.md

Get stdout and stderr logs from the specified container.

```APIDOC
## GET /containers/(id or name)/logs

### Description
Get stdout and stderr logs from the container id.

### Method
GET

### Endpoint
/containers/(id or name)/logs

### Parameters
#### Path Parameters
- **id or name** (string) - Required - Container ID or name

#### Query Parameters
- **follow** (boolean/integer) - Optional - 1/True/true or 0/False/false, return stream. Default false
- **stdout** (boolean/integer) - Optional - 1/True/true or 0/False/false, show stdout log. Default false
- **stderr** (boolean/integer) - Optional - 1/True/true or 0/False/false, show stderr log. Default false
- **timestamps** (boolean/integer) - Optional - 1/True/true or 0/False/false, print timestamps for every log line. Default false
- **tail** (string) - Optional - Output specified number of lines at the end of logs: `all` or `<number>`. Default all

### Request Example
```http
GET /containers/4fa6e0f0c678/logs?stderr=1&stdout=1&timestamps=1&follow=1&tail=10 HTTP/1.1
```

### Response
#### Success Response (200)
- **Content-Type**: `application/vnd.docker.raw-stream`
- Returns raw log stream

#### Response Example
```http
HTTP/1.1 200 OK
Content-Type: application/vnd.docker.raw-stream

{{ STREAM }}
```

#### Status Codes
- **200** – no error
- **404** – no such container
- **500** – server error
```


--------------------------------

### Start a container via POST /containers/(id or name)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.23.md

Starts the specified container. For backwards compatibility, accepts a HostConfig JSON payload in the request body, and supports detachKeys query parameter.

```http
POST /v1.23/containers/e90e34656806/start HTTP/1.1
```

```http
HTTP/1.1 204 No Content
```


--------------------------------

### POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.11.md

Starts an existing container. Accepts host configuration settings in the request body.

```APIDOC
## POST /containers/(id)/start

### Description
Start the container id.

### Method
POST

### Endpoint
`/containers/(id)/start`

### Parameters
#### Path Parameters
- **id** (string) - Required - Container ID

#### Request Body
- **hostConfig** (object) - Optional - The container's host configuration

### Request Example
```json
{
     "Binds":["/tmp:/tmp"],
     "LxcConf":[{"Key":"lxc.utsname","Value":"docker"}],
     "PortBindings":{ "22/tcp": [{ "HostPort": "11022" }] },
     "PublishAllPorts":false,
     "Privileged":false,
     "Dns": ["8.8.8.8"],
     "VolumesFrom": ["parent", "other:ro"]
}
```

### Response
#### Success Response (204)
- No Content

#### Status Codes
- **204** – no error
- **404** – no such container
- **500** – server error

#### Response Example
```http
HTTP/1.1 204 No Content
Content-Type: text/plain
```
```


--------------------------------

### GET /images/get

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.22.md

Get a tarball containing all images and metadata for one or more repositories specified by query parameters.

```APIDOC
## GET /images/get

### Description
Get a tarball containing all images and metadata for one or more repositories. For each value of the `names` parameter: if it is a specific name and tag (e.g. `ubuntu:latest`), then only that image (and its parents) are returned; if it is an image ID, similarly only that image (and its parents) are returned and there would be no names referenced in the 'repositories' file for this image ID.

### Method
GET

### Endpoint
`/images/get`

### Parameters
#### Query Parameters
- **names** (string) - Optional - Image names or IDs to include in the tarball (can be specified multiple times)

### Request Example
```http
GET /v1.22/images/get?names=myname%2Fmyapp%3Alatest&names=busybox HTTP/1.1
```

### Response
#### Success Response (200)
- Returns binary data stream (`application/x-tar`)

#### Response Example
```http
HTTP/1.1 200 OK
Content-Type: application/x-tar

Binary data stream
```

#### Status Codes
- **200** – no error
- **500** – server error
```


--------------------------------

### GET /images/(name)/get

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.14.md

Get a tarball containing all images and metadata for the specified repository name.

```APIDOC
## GET /images/(name)/get

### Description
Get a tarball containing all images and metadata for the repository specified by name.

### Method
GET

### Endpoint
/images/(name)/get

### Parameters
#### Path Parameters
- **name** (string) - Required - Repository name

### Request Example
```http
GET /images/ubuntu/get
```

### Response
#### Success Response (200)
Content-Type: application/x-tar
Binary data stream

#### Status Codes
- **200** – No error
- **500** – Server error
```


--------------------------------

### POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.0.md

Start a container by ID or name.

```APIDOC
## POST /containers/(id)/start

### Description
Start the container `id`.

### Method
POST

### Endpoint
`/containers/(id)/start`

### Parameters
#### Path Parameters
- **id** (string) - Required - Container ID or name

### Request Example
```http
POST /containers/e90e34656806/start HTTP/1.1
```

### Response
#### Success Response (200)
Status: `200 OK`

#### Status Codes
- **200** – no error
- **404** – no such container
- **500** – server error
```


--------------------------------

### POST /containers/(id or name)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.15.md

Starts the specified container with optional host, network, volume, and security configurations. Returns a 204 status on success.

```APIDOC
## POST /containers/(id or name)/start

### Description
Start the container `id`

### Method
POST

### Endpoint
/containers/(id or name)/start

### Parameters
#### Path Parameters
- **id or name** (string) - Required - Container ID or name to start

#### Request Body
- **Binds** (array of strings) - Optional - A list of volume bindings for this container. Each volume binding is a string of the form `container_path`, `host_path:container_path`, or `host_path:container_path:ro`.
- **Links** (array of strings) - Optional - A list of links for the container in the form `container_name:alias`.
- **LxcConf** (object) - Optional - LXC specific configurations (only works with the `lxc` execution driver).
- **PortBindings** (object) - Optional - A map of exposed container ports and the host port they should map to in the form `{ <port>/<protocol>: [{ "HostPort": "<port>" }] }`.
- **PublishAllPorts** (boolean) - Optional - Allocates a random host port for all of a container's exposed ports.
- **Privileged** (boolean) - Optional - Gives the container full access to the host.
- **Dns** (array of strings) - Optional - A list of dns servers for the container to use.
- **DnsSearch** (array of strings) - Optional - A list of DNS search domains.
- **VolumesFrom** (array of strings) - Optional - A list of volumes to inherit from another container in the form `<container name>[:<ro|rw>]`.
- **CapAdd** (array of strings) - Optional - A list of kernel capabilities to add to the container.
- **CapDrop** (array of strings) - Optional - A list of kernel capabilities to drop from the container.
- **RestartPolicy** (object) - Optional - The behavior to apply when the container exits. Contains `Name` ("always" or "on-failure") and `MaximumRetryCount`.
- **NetworkMode** (string) - Optional - Sets the networking mode (`bridge`, `host`, `none`, or `container:<name|id>`).
- **Devices** (array of objects) - Optional - A list of devices to add in the form `{ "PathOnHost": "/dev/deviceName", "PathInContainer": "/dev/deviceName", "CgroupPermissions": "mrw" }`.

### Request Example
```json
{
     "Binds": ["/tmp:/tmp"],
     "Links": ["redis3:redis"],
     "LxcConf": {"lxc.utsname":"docker"},
     "PortBindings": { "22/tcp": [{ "HostPort": "11022" }] },
     "PublishAllPorts": false,
     "Privileged": false,
     "Dns": ["8.8.8.8"],
     "DnsSearch": [""],
     "VolumesFrom": ["parent", "other:ro"],
     "CapAdd": ["NET_ADMIN"],
     "CapDrop": ["MKNOD"],
     "RestartPolicy": { "Name": "", "MaximumRetryCount": 0 },
     "NetworkMode": "bridge",
     "Devices": []
}
```

### Response
#### Success Response (204)
No content returned.

#### Status Codes
- **204** – no error
- **304** – container already started
- **404** – no such container
- **500** – server error
```


--------------------------------

### Get image history with GET /images/(name)/history

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.18.md

Retrieves the creation history and layers of the specified image.

```http
GET /v1.18/images/ubuntu/history HTTP/1.1
```

```http
HTTP/1.1 200 OK
Content-Type: application/json

[
    {
        "Id": "b750fe79269d",
        "Created": 1364102658,
        "CreatedBy": "/bin/bash"
    },
    {
        "Id": "27cf78414709",
        "Created": 1364068391,
        "CreatedBy": ""
    }
]
```


--------------------------------

### Get default username and email (GET /auth)

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.0.md

Retrieve the default Docker registry username and email configuration.

```http
GET /auth HTTP/1.1
```

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
     "username":"hannibal",
     "email":"hannibal@a-team.com"
}
```


--------------------------------

### Debug agent configuration, skills, and authentication

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/features/cli/index.md

Examples demonstrating how to inspect resolved configurations, toolsets, skills, session titles, authentication tokens, and MCP OAuth logins.

```bash
# Examples
$ docker agent debug config agent.yaml
$ docker agent debug toolsets agent.yaml
$ docker agent debug skills agent.yaml
$ docker agent debug title agent.yaml "How do I configure a fallback model?"
$ docker agent debug auth --json
$ docker agent debug oauth list
$ docker agent debug oauth login agent.yaml github
```


--------------------------------

### Start a container via POST /containers/(id or name)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.22.md

Starts the specified container. For backwards compatibility, the endpoint also accepts a JSON-encoded HostConfig in the request body.

```http
POST /v1.22/containers/e90e34656806/start HTTP/1.1
```

```http
HTTP/1.1 204 No Content
```


--------------------------------

### Join Swarm, Install Volume Plugin, and Create Volume on Worker Node

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/cli/docs/extend/plugins_services.md

Join node 2 to the swarm as a worker, install the sample volume plugin, and provision a named volume using that plugin driver.

```console
$ docker swarm join \
  --token SWMTKN-1-aabbccdd00112233aabbccdd00112233aabbccdd00112233aa-aabbccdd00112233... \
  192.168.99.100:2377
```

```console
$ docker plugin install tiborvass/sample-volume-plugin
latest: Pulling from tiborvass/sample-volume-plugin
eb9c16fbdc53: Download complete
Digest: sha256:00b42de88f3a3e0342e7b35fa62394b0a9ceb54d37f4c50be5d3167899994639
Status: Downloaded newer image for tiborvass/sample-volume-plugin:latest
Installed plugin tiborvass/sample-volume-plugin
```

```console
$ docker volume create -d tiborvass/sample-volume-plugin --name pluginVol
```


--------------------------------

### Create a volume with a driver and run a container mounting it

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/cli/docs/extend/plugins_volume.md

Creates a volume using a specified volume driver plugin, then mounts it into a container at /data using docker container run.

```console
$ docker volume create --driver=myplugin volumename

$ docker container run -it --volume volumename:/data busybox sh
```


--------------------------------

### GET /images/get

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.18.md

Get a tarball containing all images and metadata for one or more repositories. Returns a tarball binary data stream.

```APIDOC
## GET /images/get

### Description
Get a tarball containing all images and metadata for one or more repositories. For each value of the `names` parameter: if it is a specific name and tag (e.g. `ubuntu:latest`), then only that image (and its parents) are returned; if it is an image ID, similarly only that image (and its parents) are returned and there would be no names referenced in the 'repositories' file for this image ID.

### Method
GET

### Endpoint
/images/get

### Parameters
#### Query Parameters
- **names** (string) - Optional - Repository names or image IDs to include in the tarball

### Request Example
```http
GET /v1.18/images/get?names=myname%2Fmyapp%3Alatest&names=busybox
```

### Response
#### Success Response (200)
Content-Type: `application/x-tar`

Binary data stream

#### Status Codes
- **200** – no error
- **500** – server error
```


--------------------------------

### GET /images/get

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.16.md

Get a tarball containing all images and metadata for one or more repositories specified via the names query parameter.

```APIDOC
## GET /images/get

### Description
Get a tarball containing all images and metadata for one or more repositories. For each value of the `names` parameter: if it is a specific name and tag (e.g. ubuntu:latest), then only that image (and its parents) are returned; if it is an image ID, similarly only that image (and its parents) are returned and there would be no names referenced in the 'repositories' file for this image ID.

### Method
GET

### Endpoint
/images/get

### Parameters
#### Query Parameters
- **names** (string) - Optional - Repository name, image name and tag, or image ID to include in the tarball (can be specified multiple times)

### Request Example
```http
GET /images/get?names=myname%2Fmyapp%3Alatest&names=busybox
```

### Response
#### Success Response (200)
- Content-Type: `application/x-tar` (Binary data stream)

#### Status Codes
- **200** – no error
- **500** – server error
```


--------------------------------

### Create and start a container with port exposure and port binding

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.6.md

Two-step workflow that first creates a container exposing port 22/tcp and then starts the container using its returned ID to map port 22 to host port 11022.

```http
POST /containers/create HTTP/1.1
Content-Type: application/json

{
     "Cmd":[
             "/usr/sbin/sshd","-D"
     ],
     "Image":"image-with-sshd",
     "ExposedPorts":{"22/tcp":{}}
     }
```

```http
HTTP/1.1 201 OK
Content-Type: application/json

{
     "Id":"e90e34656806"
     "Warnings":[]
}
```

```http
POST /containers/e90e34656806/start HTTP/1.1
Content-Type: application/json

{
     "PortBindings": { "22/tcp": [{ "HostPort": "11022" }]}
     }
```

```http
HTTP/1.1 204 No Content
Content-Type: text/plain; charset=utf-8
Content-Length: 0
```


--------------------------------

### Start a container via POST /containers/(id or name)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.17.md

Start a defined container by ID or name. For backwards compatibility, the endpoint accepts an optional JSON-encoded HostConfig in the request body.

```http
POST /containers/e90e34656806/start HTTP/1.1
```

```http
HTTP/1.1 204 No Content
```


--------------------------------

### POST /exec/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.20.md

Starts a previously set up exec instance. If detach is set to true, it returns after starting the command; otherwise, it opens an interactive stream.

```APIDOC
## POST /exec/(id)/start

### Description
Starts a previously set up `exec` instance `id`. If `detach` is true, this API returns after starting the `exec` command. Otherwise, this API sets up an interactive session with the `exec` command.

### Method
POST

### Endpoint
`/exec/(id)/start`

### Parameters
#### Path Parameters
- **id** (string) - Required - Exec instance ID

#### Request Body
- **Detach** (boolean) - Optional - Detach from the `exec` command.
- **Tty** (boolean) - Optional - Allocate a pseudo-TTY.

### Request Example
```json
{
  "Detach": false,
  "Tty": false
}
```

### Response
#### Success Response (200 OK)
Content-Type: `application/vnd.docker.raw-stream`

#### Status Codes
- **200** – no error
- **404** – no such exec instance
```


--------------------------------

### List models and run with custom provider

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/getting-started/set-up-a-model/index.md

Commands to list available models and execute an agent using the configured custom provider.

```bash
$ docker agent models --provider myprovider
$ docker agent run --model myprovider/<model>
```


--------------------------------

### Clone, build, and run Docker Agent from source

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/community/contributing/index.md

Clone the repository, compile the binary using Task, export the required AI provider API keys, and execute a sample agent configuration.

```bash
# Clone and build
git clone https://github.com/docker/docker-agent.git
cd docker-agent
task build

# Set API keys
export OPENAI_API_KEY=your_key_here
export ANTHROPIC_API_KEY=your_key_here

# Run an example
./bin/docker-agent run examples/code.yaml
```


--------------------------------

### Start OpenAI-compatible chat server using docker agent serve chat

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/features/chat-server/index.md

Starts an HTTP server exposing agents at `/v1/chat/completions` and `/v1/models`. Demonstrates running single or multi-agent configurations, selecting specific agents, serving from registry images with custom listen addresses, and requiring authentication via `--api-key-env`.

```bash
# Single agent — exposed as the model `root`
$ docker agent serve chat agent.yaml

# Multi-agent config — every agent in the team becomes a model
$ docker agent serve chat ./team.yaml

# Pick a specific agent from a multi-agent config
$ docker agent serve chat ./team.yaml --agent reviewer

# Run an agent straight from the registry
$ docker agent serve chat myorg/agent:tag --listen 127.0.0.1:9090

# Require a Bearer token, sourced from an env var
$ docker agent serve chat agent.yaml --api-key-env CHAT_BEARER_TOKEN
```


--------------------------------

### Display system-wide information with GET /info

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.22.md

Send a GET request to `/v1.22/info` to retrieve system-wide information regarding architecture, container counts, storage drivers, and runtime settings. Returns HTTP 200 with system details in JSON format, or HTTP 500 on server error.

```http
GET /v1.22/info HTTP/1.1
```

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "Architecture": "x86_64",
    "ClusterStore": "etcd://localhost:2379",
    "Containers": 11,
    "ContainersRunning": 7,
    "ContainersStopped": 3,
    "ContainersPaused": 1,
    "CpuCfsPeriod": true,
    "CpuCfsQuota": true,
    "Debug": false,
    "DockerRootDir": "/var/lib/docker",
    "Driver": "btrfs",
    "DriverStatus": [[""]],
    "ExecutionDriver": "native-0.1",
    "ExperimentalBuild": false,
    "HttpProxy": "http://test:test@localhost:8080",
    "HttpsProxy": "https://test:test@localhost:8080",
    "ID": "7TRN:IPZB:QYBB:VPBQ:UMPP:KARE:6ZNR:XE6T:7EWV:PKF4:ZOJD:TPYS",
    "IPv4Forwarding": true,
    "Images": 16,
    "IndexServerAddress": "https://index.docker.io/v1/",
    "InitPath": "/usr/bin/docker",
    "InitSha1": "",
    "KernelVersion": "3.12.0-1-amd64",
    "Labels": [
        "storage=ssd"
    ],
    "MemTotal": 2099236864,
    "MemoryLimit": true,
    "NCPU": 1,
    "NEventsListener": 0,
    "NFd": 11,
    "NGoroutines": 21,
    "Name": "prod-server-42",
    "NoProxy": "9.81.1.160",
    "OomKillDisable": true,
    "OSType": "linux",
    "OperatingSystem": "Boot2Docker",
    "Plugins": {
        "Volume": [
            "local"
        ],
        "Network": [
            "null",
            "host",
            "bridge"
        ]
    },
    "RegistryConfig": {
        "IndexConfigs": {
            "docker.io": {
                "Mirrors": null,
                "Name": "docker.io",
                "Official": true,
                "Secure": true
            }
        },
        "InsecureRegistryCIDRs": [
            "127.0.0.0/8"
        ]
    },
    "ServerVersion": "1.9.0",
    "SwapLimit": false,
    "SystemStatus": [["State", "Healthy"]],
    "SystemTime": "2015-03-10T11:11:23.730591467-07:00"
}
```


--------------------------------

### Start a container

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.20.md

Start a container by ID or name. For backwards compatibility, the endpoint accepts an optional HostConfig in the JSON request body.

```http
POST /v1.20/containers/e90e34656806/start HTTP/1.1
```

```http
HTTP/1.1 204 No Content
```


--------------------------------

### Perform an HTTP GET request with HttpService.get

Source: https://github.com/docker/docs/blob/main/content/reference/api/extensions-sdk/HttpService.md

Performs an HTTP GET request to a specified backend service URL and returns a Promise.

```typescript
ddClient.extension.vm.service
 .get("/some/service")
 .then((value: any) => console.log(value)
```


--------------------------------

### GET /images/(name)/history

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.6.md

Get the history of an image. Returns the list of parent layers and commands used to build the image.

```APIDOC
## GET /images/(name)/history

### Description
Return the history of the image `name`.

### Method
GET

### Endpoint
/images/(name)/history

### Parameters
#### Path Parameters
- **name** (string) - Required - Image name or ID

### Request Example
```http
GET /images/base/history HTTP/1.1
```

### Response
#### Success Response (200)
Status Codes:
- **200** – no error
- **404** – no such image
- **500** – server error

#### Response Example
```json
[
     {
             "Id": "b750fe79269d",
             "Created": 1364102658,
             "CreatedBy": "/bin/bash"
     },
     {
             "Id": "27cf78414709",
             "Created": 1364068391,
             "CreatedBy": ""
     }
]
```
```


--------------------------------

### Get the history of an image (GET /images/(name)/history)

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.20.md

Return the layer history and creation metadata for a specified image name.

```http
GET /v1.20/images/ubuntu/history HTTP/1.1
```

```http
HTTP/1.1 200 OK
Content-Type: application/json

[
    {
        "Id": "3db9c44f45209632d6050b35958829c3a2aa256d81b9a7be45b362ff85c54710",
        "Created": 1398108230,
        "CreatedBy": "/bin/sh -c #(nop) ADD file:eb15dbd63394e063b805a3c32ca7bf0266ef64676d5a6fab4801f2e81e2a5148 in /",
        "Tags": [
            "ubuntu:lucid",
            "ubuntu:10.04"
        ],
        "Size": 182964289,
        "Comment": ""
    },
    {
        "Id": "6cfa4d1f33fb861d4d114f43b25abd0ac737509268065cdfd69d544a59c85ab8",
        "Created": 1398108222,
        "CreatedBy": "/bin/sh -c #(nop) MAINTAINER Tianon Gravi <admwiggin@gmail.com> - mkimage-debootstrap.sh -i iproute,iputils-ping,ubuntu-minimal -t lucid.tar.xz lucid http://archive.ubuntu.com/ubuntu/",
        "Tags": null,
        "Size": 0,
        "Comment": ""
    },
    {
        "Id": "511136ea3c5a64f264b78b5433614aec563103b4d4702f3ba7d4d2698e22c158",
        "Created": 1371157430,
        "CreatedBy": "",
        "Tags": [
            "scratch12:latest",
            "scratch:latest"
        ],
        "Size": 0,
        "Comment": "Imported from -"
    }
]
```


--------------------------------

### List containers via GET /containers/json

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.23.md

Send a GET request to the /v1.23/containers/json endpoint with query parameters to filter and inspect containers.

```http
GET /v1.23/containers/json?all=1&before=8dfafdbc3a40&size=1 HTTP/1.1
```


--------------------------------

### Get image history with GET /images/(name)/history

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.15.md

Returns the history layers and creation details for the specified image name.

```http
GET /images/ubuntu/history HTTP/1.1
```

```http
HTTP/1.1 200 OK
Content-Type: application/json

[
     {
             "Id": "b750fe79269d",
             "Created": 1364102658,
             "CreatedBy": "/bin/bash"
     },
     {
             "Id": "27cf78414709",
             "Created": 1364068391,
             "CreatedBy": ""
     }
]
```


--------------------------------

### Define base image with FROM syntax

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/buildkit/frontend/dockerfile/docs/reference.md

Initializes a new build stage and specifies the base image, with optional platform and stage name arguments.

```dockerfile
FROM [--platform=<platform>] <image> [AS <name>]
```


--------------------------------

### Start chat server with Bearer token authentication using --api-key-env

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/features/chat-server/index.md

Starts the chat server requiring a Bearer token specified by an environment variable. Clients must include an Authorization: Bearer <token> header for all requests to /v1/* endpoints.

```bash
$ docker agent serve chat agent.yaml --api-key-env CHAT_BEARER_TOKEN
```


--------------------------------

### Configure buildkitd daemon settings in buildkitd.toml

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/buildkit/docs/buildkitd.toml.md

Sample configuration file for the buildkitd daemon defining global settings, logging, networking, gRPC TLS, tracing, CDI, build history, and database compaction. Placed at /etc/buildkit/buildkitd.toml for rootful mode or ~/.config/buildkit/buildkitd.toml for rootless mode.

```toml
# root is where all buildkit state is stored.
root = "/var/lib/buildkit"
# insecure-entitlements allows insecure entitlements, disabled by default.
insecure-entitlements = [ "network.host", "security.insecure", "device" ]
# proxyNetwork enables proxy network enforcement for all builds, disabled by default.
# It can also be enabled with buildkitd --proxy-network.
proxyNetwork = true
# provenanceEnvDir is the directory where extra config is loaded that is added
# to the provenance of builds:
# slsa v0.2: invocation.environment.*
# slsa v1: buildDefinition.internalParameters.*
provenanceEnvDir = "/etc/buildkit/provenance.d"

[log]
  # log formatter: json or text
  format = "text"

  # log level (error/warn/info/debug/trace)
  level = "info"

[dns]
  nameservers=["1.1.1.1","8.8.8.8"]
  options=["edns0"]
  searchDomains=["example.com"]

[grpc]
  address = [ "tcp://0.0.0.0:1234" ]
  # debugAddress is address for attaching go profiles and debuggers.
  debugAddress = "0.0.0.0:6060"
  uid = 0
  gid = 0
  [grpc.tls]
    cert = "/etc/buildkit/tls.crt"
    key = "/etc/buildkit/tls.key"
    ca = "/etc/buildkit/tlsca.crt"

[otel]
  # OTEL collector trace socket path
  socketPath = "/run/buildkit/otel-grpc.sock"

[cdi]
  # Disables support of the Container Device Interface (CDI).
  disabled = true
  # List of directories to scan for CDI spec files. For more details about CDI
  # specification, please refer to https://github.com/cncf-tags/container-device-interface/blob/main/SPEC.md#cdi-json-specification
  specDirs = ["/etc/cdi", "/var/run/cdi", "/etc/buildkit/cdi"]

# config for build history API that stores information about completed build commands
[history]
  # maxAge is the maximum age of history entries to keep, in seconds.
  maxAge = 172800
  # maxEntries is the maximum number of history entries to keep. When the
  # history section is omitted, the default is 50. If only maxAge is set,
  # all entries older than maxAge are removed.
  # Setting this value to 0 prevents recording new build history, including
  # active-build events. Existing records remain available until normal GC.
  maxEntries = 50

[compaction]
  # Opt-in metadata database maintenance, independent of cache GC.
  enabled = false
  # Committed write transactions between automatic eligibility checks.
  writesPerCheck = 10000
  # Database size is sampled at most every five minutes after committed writes.
  # Initial minimum database size for growth-triggered eligibility checks.
  sizeWatermark = 134217728
  # After compaction, grow the next size watermark from the compacted size by
  # this percentage.
  sizeGrowthPercent = 100
  # Either threshold can trigger compaction, subject to the percentage floor.
  minReclaimBytes = 268435456
  # Percentage of the database file estimated to be reclaimable.
  minReclaimPercent = 30
  # Minimum reclaimable percentage, even when minReclaimBytes is reached.
  minReclaimPercentFloor = 10
  # Wait for no active transactions and this interval without database activity.
  idleTimeout = "1m"
  # Cancel this many attempts for arriving writers, then let the next copy finish.
  # Writers may wait for the full copy duration. Zero forces the first attempt.
  maxRetry = 3
```


--------------------------------

### Entrypoint wrapper script workaround

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/buildkit/frontend/dockerfile/docs/rules/json-args-recommended.md

Wraps multi-command startup logic into an executable shell script while invoking it using JSON exec form.

```dockerfile
FROM alpine
RUN apk add bash
COPY --chmod=755 <<EOT /entrypoint.sh
#!/usr/bin/env bash
set -e
my-background-process &
my-program start
EOT
ENTRYPOINT ["/entrypoint.sh"]

```


--------------------------------

### POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.1.md

Starts an existing, stopped container by ID or name.

```APIDOC
## POST /containers/(id)/start

### Description
Start the container `id`

### Method
POST

### Endpoint
/containers/(id)/start

### Parameters
#### Path Parameters
- **id** (string) - Required - Container ID or name

### Request Example
```http
POST /containers/e90e34656806/start HTTP/1.1
```

### Response
#### Status Codes
- **200** – no error
- **404** – no such container
- **500** – server error
```


--------------------------------

### Install Global Scoped Network Plugin

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/cli/docs/extend/plugins_services.md

Install a global scope network plugin on swarm nodes and grant the requested network capabilities.

```console
$ docker plugin install bboreham/weave2
Plugin "bboreham/weave2" is requesting the following privileges:
- network: [host]
- capabilities: [CAP_SYS_ADMIN CAP_NET_ADMIN]
Do you grant the above permissions? [y/N] y
latest: Pulling from bboreham/weave2
7718f575adf7: Download complete
Digest: sha256:2780330cc15644b60809637ee8bd68b4c85c893d973cb17f2981aabfadfb6d72
Status: Downloaded newer image for bboreham/weave2:latest
Installed plugin bboreham/weave2
```


--------------------------------

### Run a container using the Docker Go SDK

Source: https://github.com/docker/docs/blob/main/content/reference/api/engine/sdk/_index.md

Pulls an Alpine image, creates and starts a container to execute an echo command, waits for completion, and outputs logs to stdout using the Go SDK.

```go
package main

import (
	"context"
	"io"
	"os"

	"github.com/moby/moby/api/pkg/stdcopy"
	"github.com/moby/moby/api/types/container"
	"github.com/moby/moby/client"
)

func main() {
	ctx := context.Background()
	apiClient, err := client.New(client.FromEnv)
	if err != nil {
		panic(err)
	}
	defer apiClient.Close()

	reader, err := apiClient.ImagePull(ctx, "docker.io/library/alpine", client.ImagePullOptions{})
	if err != nil {
		panic(err)
	}
	io.Copy(os.Stdout, reader)

	resp, err := apiClient.ContainerCreate(ctx, client.ContainerCreateOptions{
		Image: "alpine",
		Config: &container.Config{
			Cmd: []string{"echo", "hello world"},
		},
	})
	if err != nil {
		panic(err)
	}

	if _, err := apiClient.ContainerStart(ctx, resp.ID, client.ContainerStartOptions{}); err != nil {
		panic(err)
	}

	wait := apiClient.ContainerWait(ctx, resp.ID, client.ContainerWaitOptions{})
	select {
	case err := <-wait.Error:
		if err != nil {
			panic(err)
		}
	case <-wait.Result:
	}

	out, err := apiClient.ContainerLogs(ctx, resp.ID, client.ContainerLogsOptions{ShowStdout: true})
	if err != nil {
		panic(err)
	}

	stdcopy.StdCopy(os.Stdout, os.Stderr, out)
}
```


--------------------------------

### Start a container

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.18.md

Starts an existing container by ID or name. For backwards compatibility, the endpoint also accepts a HostConfig as a JSON-encoded request body.

```http
POST /v1.18/containers/e90e34656806/start HTTP/1.1
```

```http
HTTP/1.1 204 No Content
```


--------------------------------

### POST /containers/(id or name)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.22.md

Starts the specified container. Can accept an optional host configuration for backwards compatibility and supports custom detach key sequences.

```APIDOC
## POST /containers/(id or name)/start

### Description
Start the container `id`

> **Note**: For backwards compatibility, this endpoint accepts a `HostConfig` as JSON-encoded request body. See create a container for details.

### Method
POST

### Endpoint
`/containers/(id or name)/start`

### Parameters
#### Path Parameters
- **id or name** (string) - Required - Container ID or name

#### Query Parameters
- **detachKeys** (string) - Optional - Override the key sequence for detaching a container. Format is a single character `[a-Z]` or `ctrl-<value>` where `<value>` is one of: `a-z`, `@`, `^`, `[`, `,` or `_`.

### Request Example
```http
POST /v1.22/containers/e90e34656806/start HTTP/1.1
```

### Response
#### Status Codes
- **204** – no error
- **304** – container already started
- **404** – no such container
- **500** – server error

#### Response Example
```http
HTTP/1.1 204 No Content
```
```


--------------------------------

### GET /images/(name)/get

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.8.md

Get a tarball containing all images and metadata for the specified repository name. Returns a binary tar stream.

```APIDOC
## GET /images/(name)/get

### Description
Get a tarball containing all images and metadata for the repository specified by `name`.

### Method
GET

### Endpoint
/images/(name)/get

### Parameters
#### Path Parameters
- **name** (string) - Required - Name of the repository

### Request Example
```http
GET /images/ubuntu/get
```

### Response
#### Success Response (200)
Content-Type: `application/x-tar`

Binary data stream

#### Status Codes
- **200** – no error
- **500** – server error
```


--------------------------------

### Display system-wide information via GET /info

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.20.md

Call GET /info to retrieve system-wide configuration and runtime information about the Docker host.

```http
GET /v1.20/info HTTP/1.1
```

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "Containers": 11,
    "CpuCfsPeriod": true,
    "CpuCfsQuota": true,
    "Debug": false,
    "DockerRootDir": "/var/lib/docker",
    "Driver": "btrfs",
    "DriverStatus": [[""]],
    "ExecutionDriver": "native-0.1",
    "ExperimentalBuild": false,
    "HttpProxy": "http://test:test@localhost:8080",
    "HttpsProxy": "https://test:test@localhost:8080",
    "ID": "7TRN:IPZB:QYBB:VPBQ:UMPP:KARE:6ZNR:XE6T:7EWV:PKF4:ZOJD:TPYS",
    "IPv4Forwarding": true,
    "Images": 16,
    "IndexServerAddress": "https://index.docker.io/v1/",
    "InitPath": "/usr/bin/docker",
    "InitSha1": "",
    "KernelVersion": "3.12.0-1-amd64",
    "Labels": [
        "storage=ssd"
    ],
    "MemTotal": 2099236864,
    "MemoryLimit": true,
    "NCPU": 1,
    "NEventsListener": 0,
    "NFd": 11,
    "NGoroutines": 21,
    "Name": "prod-server-42",
    "NoProxy": "9.81.1.160",
    "OomKillDisable": true,
    "OperatingSystem": "Boot2Docker",
    "RegistryConfig": {
        "IndexConfigs": {
            "docker.io": {
                "Mirrors": null,
                "Name": "docker.io",
                "Official": true,
                "Secure": true
            }
        },
        "InsecureRegistryCIDRs": [
            "127.0.0.0/8"
        ]
    },
    "SwapLimit": false,
    "SystemTime": "2015-03-10T11:11:23.730591467-07:00"
}
```


--------------------------------

### POST /exec/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.17.md

Starts a previously set up exec instance. If detach is true, returns immediately; otherwise sets up an interactive session.

```APIDOC
## POST /exec/(id)/start

### Description
Starts a previously set up exec instance `id`. If `detach` is true, this API returns after starting the `exec` command. Otherwise, this API sets up an interactive session with the `exec` command.

### Method
POST

### Endpoint
`/exec/(id)/start`

### Parameters
#### Path Parameters
- **id** (string) - Required - Exec instance ID

#### Request Body
- **Detach** (boolean) - Optional - Detach from the exec command.
- **Tty** (boolean) - Optional - Boolean value to allocate a pseudo-TTY.

### Request Example
```json
{
  "Detach": false,
  "Tty": false
}
```

### Response
#### Success Response (200)
Returns a raw stream `application/vnd.docker.raw-stream` with stream details similar to `POST /containers/(id or name)/attach`.

#### Status Codes
- **200** - no error
- **404** - no such exec instance
```


--------------------------------

### GET /images/(name)/get

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.18.md

Get a tarball containing all images and metadata for the repository specified by name. Returns binary data stream.

```APIDOC
## GET /images/(name)/get

### Description
Get a tarball containing all images and metadata for the repository specified by `name`. If `name` is a specific name and tag (e.g. ubuntu:latest), then only that image (and its parents) are returned. If `name` is an image ID, similarly only that image (and its parents) are returned, but with the exclusion of the 'repositories' file in the tarball, as there were no image names referenced.

### Method
GET

### Endpoint
/images/(name)/get

### Parameters
#### Path Parameters
- **name** (string) - Required - Repository name or image ID

### Request Example
```http
GET /v1.18/images/ubuntu/get
```

### Response
#### Success Response (200)
Content-Type: `application/x-tar`

Binary data stream

#### Status Codes
- **200** – no error
- **500** – server error
```


--------------------------------

### List containers using GET /containers/json

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.22.md

Send a GET request to /containers/json with query parameters such as all, before, and size to retrieve a JSON list of containers.

```http
GET /v1.22/containers/json?all=1&before=8dfafdbc3a40&size=1 HTTP/1.1
```

```http
HTTP/1.1 200 OK
Content-Type: application/json

[
     {
             "Id": "8dfafdbc3a40",
             "Names":["/boring_feynman"],
             "Image": "ubuntu:latest",
             "ImageID": "d74508fb6632491cea586a1fd7d748dfc5274cd6fdfedee309ecdcbc2bf5cb82",
             "Command": "echo 1",
             "Created": 1367854155,
             "Status": "Exit 0",
             "Ports": [{"PrivatePort": 2222, "PublicPort": 3333, "Type": "tcp"}],
             "Labels": {
                     "com.example.vendor": "Acme",
                     "com.example.license": "GPL",
                     "com.example.version": "1.0"
             },
             "SizeRw": 12288,
             "SizeRootFs": 0,
             "HostConfig": {
                     "NetworkMode": "default"
             },
             "NetworkSettings": {
                     "Networks": {
                             "bridge": {
                                      "IPAMConfig": null,
                                      "Links": null,
                                      "Aliases": null,
                                      "NetworkID": "7ea29fc1412292a2d7bba362f9253545fecdfa8ce9a6e37dd10ba8bee7129812",
                                      "EndpointID": "2cdc4edb1ded3631c81f57966563e5c8525b81121bb3706a9a9a3ae102711f3f",
                                      "Gateway": "172.17.0.1",
                                      "IPAddress": "172.17.0.2",
                                      "IPPrefixLen": 16,
                                      "IPv6Gateway": "",
                                      "GlobalIPv6Address": "",
                                      "GlobalIPv6PrefixLen": 0,
                                      "MacAddress": "02:42:ac:11:00:02"
                              }
                     }
             }
     },
     {
             "Id": "9cd87474be90",
             "Names":["/coolName"],
             "Image": "ubuntu:latest",
             "ImageID": "d74508fb6632491cea586a1fd7d748dfc5274cd6fdfedee309ecdcbc2bf5cb82",
             "Command": "echo 222222",
             "Created": 1367854155,
             "Status": "Exit 0",
             "Ports": [],
             "Labels": {},
             "SizeRw": 12288,
             "SizeRootFs": 0,
             "HostConfig": {
                     "NetworkMode": "default"
             },
             "NetworkSettings": {
                     "Networks": {
                             "bridge": {
                                      "IPAMConfig": null,
                                      "Links": null,
                                      "Aliases": null,
                                      "NetworkID": "7ea29fc1412292a2d7bba362f9253545fecdfa8ce9a6e37dd10ba8bee7129812",
                                      "EndpointID": "88eaed7b37b38c2a3f0c4bc796494fdf51b270c2d22656412a2ca5d559a64d7a",
                                      "Gateway": "172.17.0.1",
                                      "IPAddress": "172.17.0.8",
                                      "IPPrefixLen": 16,
                                      "IPv6Gateway": "",
                                      "GlobalIPv6Address": "",
                                      "GlobalIPv6PrefixLen": 0,
                                      "MacAddress": "02:42:ac:11:00:08"
                              }
                     }
             }
     },
     {
             "Id": "3176a2479c92",
             "Names":["/sleepy_dog"],
             "Image": "ubuntu:latest",
             "ImageID": "d74508fb6632491cea586a1fd7d748dfc5274cd6fdfedee309ecdcbc2bf5cb82",
             "Command": "echo 3333333333333333",
             "Created": 1367854154,
             "Status": "Exit 0",
             "Ports":[],
             "Labels": {},
             "SizeRw":12288,
             "SizeRootFs":0,
             "HostConfig": {
                         "NetworkMode": "default"
                 },
                 "NetworkSettings": {
                         "Networks": {
                                 "bridge": {
                                          "IPAMConfig": null,
                                          "Links": null,
                                          "Aliases": null,
                                          "NetworkID": "7ea29fc1412292a2d7bba362f9253545fecdfa8ce9a6e37dd10ba8bee7129812",
```


--------------------------------

### POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.9.md

Start a specific container by its ID. Allows configuring bind mounts, LXC parameters, port bindings, and privileges.

```APIDOC
## POST /containers/(id)/start

### Description
Start the container `id`.

### Method
POST

### Endpoint
`/containers/(id)/start`

### Parameters
#### Path Parameters
- **id** (string) - Required - Container ID or name

#### Request Body
- **Binds** (array) - Optional - Create a bind mount to a directory or file with [host-path]:[container-path]:[rw|ro]. If a directory "container-path" is missing, then docker creates a new volume.
- **LxcConf** (array) - Optional - Map of custom lxc options
- **PortBindings** (object) - Optional - Expose ports from the container, optionally publishing them via the HostPort flag
- **PublishAllPorts** (boolean) - Optional - 1/True/true or 0/False/false, publish all exposed ports to the host interfaces. Default false
- **Privileged** (boolean) - Optional - 1/True/true or 0/False/false, give extended privileges to this container. Default false

### Request Example
```json
{
  "Binds": ["/tmp:/tmp"],
  "LxcConf": [{"Key": "lxc.utsname", "Value": "docker"}],
  "PortBindings": { "22/tcp": [{ "HostPort": "11022" }] },
  "PublishAllPorts": false,
  "Privileged": false
}
```

### Response
#### Success Response (204)
- No Content

#### Response Example
```http
HTTP/1.1 204 No Content
Content-Type: text/plain
```

### Status Codes
- **204** – no error
- **404** – no such container
- **500** – server error
```


--------------------------------

### GET /events

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.16.md

Get container and image events from Docker, either in real time via streaming or via polling using timestamps.

```APIDOC
## GET /events

### Description
Get container events from docker, either in real time via streaming, or via polling (using since).

Docker containers will report the following events: `create`, `destroy`, `die`, `export`, `kill`, `pause`, `restart`, `start`, `stop`, `unpause`
Docker images will report: `untag`, `delete`

### Method
GET

### Endpoint
/events

### Parameters
#### Query Parameters
- **since** (integer/timestamp) - Optional - Timestamp used for polling
- **until** (integer/timestamp) - Optional - Timestamp used for polling
- **filters** (string) - Optional - A json encoded value of the filters (a map[string][]string) to process on the event list. Available filters: `event=<string>`, `image=<string>`, `container=<string>`

### Request Example
```http
GET /events?since=1374067924
```

### Response
#### Success Response (200)

```json
{"status": "create", "id": "dfdf82bd3881","from": "ubuntu:latest", "time":1374067924}
{"status": "start", "id": "dfdf82bd3881","from": "ubuntu:latest", "time":1374067924}
{"status": "stop", "id": "dfdf82bd3881","from": "ubuntu:latest", "time":1374067966}
{"status": "destroy", "id": "dfdf82bd3881","from": "ubuntu:latest", "time":1374067970}
```

#### Status Codes
- **200** – no error
- **500** – server error
```


--------------------------------

### GET /events

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.14.md

Get container and image events from Docker, either in real time via streaming or via polling using timestamps.

```APIDOC
## GET /events

### Description
Get container events from docker, either in real time via streaming, or via polling (using since). Container events include: create, destroy, die, export, kill, pause, restart, start, stop, unpause. Image events include: untag, delete.

### Method
GET

### Endpoint
/events

### Parameters
#### Query Parameters
- **since** (timestamp) - Optional - Timestamp used for polling
- **until** (timestamp) - Optional - Timestamp used for polling

### Request Example
```http
GET /events?since=1374067924
```

### Response
#### Success Response (200)
```json
{"status": "create", "id": "dfdf82bd3881", "from": "ubuntu:latest", "time": 1374067924}
{"status": "start", "id": "dfdf82bd3881", "from": "ubuntu:latest", "time": 1374067924}
{"status": "stop", "id": "dfdf82bd3881", "from": "ubuntu:latest", "time": 1374067966}
{"status": "destroy", "id": "dfdf82bd3881", "from": "ubuntu:latest", "time": 1374067970}
```

#### Status Codes
- **200** – No error
- **500** – Server error
```


--------------------------------

### Create a container with POST /containers/create

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.15.md

Send a POST request to initialize and create a new container instance.

```http
POST /containers/create HTTP/1.1
Content-Type: application/json
```


--------------------------------

### Configure Shared Todos for Multi-Agent Setups

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/tools/todo/index.md

Enables shared task lists across all agents in a multi-agent setup by setting `shared` to `true`.

```yaml
toolsets:
  - type: todo
    shared: true
```


--------------------------------

### Configure basic services with images, ports, and environment variables

Source: https://github.com/docker/docs/blob/main/content/reference/compose-file/services.md

Defines two simple services (web and db), mapping host ports and setting environment variables.

```yaml
services:
  web:
    image: nginx:latest
    ports:
      - "8080:80"

  db:
    image: postgres:18
    environment:
      POSTGRES_USER: example
      POSTGRES_DB: exampledb
```


--------------------------------

### Mount a volume with docker run syntax

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/cli/docs/reference/run.md

Demonstrates the basic syntax for attaching a volume using the --mount flag with source and target parameters. The target path inside the container must always be an absolute path starting with a forward slash.

```console
$ docker run --mount source=<VOLUME_NAME>,target=[PATH] [IMAGE] [COMMAND...]
```


--------------------------------

### Verify Docker Agent installation

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/getting-started/installation/index.md

Verify the installation by checking the Docker Agent version and running the default agent or an agent image from an OCI registry.

```bash
# Check the version
$ docker agent version

# Run the default agent
$ docker agent run

# Or run an agent from an OCI registry
$ docker agent run myorg/agent:tag
```


--------------------------------

### POST /exec/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.15.md

Starts a previously set up exec instance. Depending on the detach flag, it either returns immediately or sets up an interactive stream.

```APIDOC
## POST /exec/(id)/start

### Description
Starts a previously set up exec instance `id`. If `detach` is true, this API returns after starting the `exec` command. Otherwise, this API sets up an interactive session with the `exec` command.

### Method
POST

### Endpoint
`/exec/(id)/start`

### Parameters
#### Path Parameters
- **id** (string) - Required - Exec instance ID

#### Request Body
- **Detach** (boolean) - Optional - Detach from the exec command.
- **Tty** (boolean) - Optional - Boolean value to allocate a pseudo-TTY.

### Request Example
```json
{
  "Detach": false,
  "Tty": false
}
```

### Response
#### Success Response (200 OK)
Content-Type: `application/vnd.docker.raw-stream`

```
{{ STREAM }}
```

#### Status Codes
- **200** – no error
- **404** – no such exec instance
```


--------------------------------

### Verify installed plugin status using docker plugin ls

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/cli/docs/extend/_index.md

Lists installed plugins along with their ID, name, description, and enabled state.

```console
$ docker plugin ls

ID                    NAME                      DESCRIPTION                                ENABLED
aede66158353          rclone:latest             Rclone volume plugin for Docker            true
```


--------------------------------

### Execute docker agent models with filtering and format options

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/features/cli/index.md

Provides examples for listing all catalog models, filtering by a specific provider ID, and formatting output as JSON piped to jq.

```bash
# Examples
$ docker agent models                                 # only providers you can use
$ docker agent models --all                           # every provider the catalog knows about
$ docker agent models --provider openai
$ docker agent models --format json | jq
```


--------------------------------

### GET /containers/(id or name)/archive

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.20.md

Get a tar archive containing a filesystem resource from a container, along with resource metadata in response headers.

```APIDOC
## GET /containers/(id or name)/archive

### Description
Get a tar archive of a resource in the filesystem of container `id`.

### Method
GET

### Endpoint
`/containers/(id or name)/archive`

### Parameters
#### Path Parameters
- **id or name** (string) - Required - The container ID or name.

#### Query Parameters
- **path** (string) - Required - Resource in the container's filesystem to archive. If not an absolute path, it is relative to the container's root directory. The resource specified by path must exist. To assert that the resource is expected to be a directory, path should end in `/` or `/.`. If path ends in `/.` then this indicates that only the contents of the path directory should be copied. A symlink is always resolved to its target.

### Request Example
```http
GET /v1.20/containers/8cce319429b2/archive?path=/root HTTP/1.1
```

### Response
#### Success Response (200)
- **TAR STREAM** - Tar archive stream of the copied resource.
- **X-Docker-Container-Path-Stat** (header) - Base64-encoded JSON object with filesystem header info.

#### Response Example
```http
HTTP/1.1 200 OK
Content-Type: application/x-tar
X-Docker-Container-Path-Stat: eyJuYW1lIjoicm9vdCIsInNpemUiOjQwOTYsIm1vZGUiOjIxNDc0ODQwOTYsIm10aW1lIjoiMjAxNC0wMi0yN1QyMDo1MToyM1oiLCJsaW5rVGFyZ2V0IjoiIn0=

{{ TAR STREAM }}
```

Decoded `X-Docker-Container-Path-Stat` JSON structure:
```json
{
    "name": "root",
    "size": 4096,
    "mode": 2147484096,
    "mtime": "2014-02-27T20:51:23Z",
    "linkTarget": ""
}
```

#### Status Codes
- **200** - success, returns archive of copied resource
- **400** - client error, bad parameter, details in JSON response body (e.g. must specify path parameter, not a directory)
- **404** - client error, resource not found (e.g. no such container, no such file or directory)
- **500** - server error
```


--------------------------------

### GET /containers/(id or name)/logs

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.23.md

Get stdout and stderr logs from a container. This endpoint works only for containers with json-file or journald logging drivers.

```APIDOC
## GET /containers/(id or name)/logs

### Description
Get `stdout` and `stderr` logs from the container `id`. Note: This endpoint works only for containers with the `json-file` or `journald` logging drivers.

### Method
GET

### Endpoint
`/containers/(id or name)/logs`

### Parameters
#### Path Parameters
- **id or name** (string) - Required - Container ID or name

#### Query Parameters
- **follow** (boolean) - Optional - 1/True/true or 0/False/false, return stream. Default `false`.
- **stdout** (boolean) - Optional - 1/True/true or 0/False/false, show `stdout` log. Default `false`.
- **stderr** (boolean) - Optional - 1/True/true or 0/False/false, show `stderr` log. Default `false`.
- **since** (integer) - Optional - UNIX timestamp (integer) to filter logs. Specifying a timestamp will only output log-entries since that timestamp. Default: 0 (unfiltered).
- **timestamps** (boolean) - Optional - 1/True/true or 0/False/false, print timestamps for every log line. Default `false`.
- **tail** (string) - Optional - Output specified number of lines at the end of logs: `all` or `<number>`. Default `all`.

### Request Example
```http
GET /v1.23/containers/4fa6e0f0c678/logs?stderr=1&stdout=1&timestamps=1&follow=1&tail=10&since=1428990821 HTTP/1.1
```

### Response
#### Success Response (101 / 200)
Returns raw stream (`application/vnd.docker.raw-stream`).

#### Status Codes
- **101** – no error, hints proxy about hijacking
- **200** – no error, no upgrade header found
- **404** – no such container
- **500** – server error
```


--------------------------------

### GET /containers/(id or name)/logs

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.21.md

Get stdout and stderr logs from a container. Works only for containers configured with json-file or journald logging drivers.

```APIDOC
## GET /containers/(id or name)/logs

### Description
Get `stdout` and `stderr` logs from the container `id`. Works only for containers with the `json-file` or `journald` logging drivers.

### Method
GET

### Endpoint
/containers/(id or name)/logs

### Parameters
#### Path Parameters
- **id or name** (string) - Required - Container ID or name

#### Query Parameters
- **follow** (boolean) - Optional - 1/True/true or 0/False/false, return stream. Default `false`.
- **stdout** (boolean) - Optional - 1/True/true or 0/False/false, show `stdout` log. Default `false`.
- **stderr** (boolean) - Optional - 1/True/true or 0/False/false, show `stderr` log. Default `false`.
- **since** (integer) - Optional - UNIX timestamp to filter logs. Specifying a timestamp will only output log-entries since that timestamp. Default `0` (unfiltered).
- **timestamps** (boolean) - Optional - 1/True/true or 0/False/false, print timestamps for every log line. Default `false`.
- **tail** (string) - Optional - Output specified number of lines at the end of logs: `all` or `<number>`. Default `all`.

### Request Example
```http
GET /v1.21/containers/4fa6e0f0c678/logs?stderr=1&stdout=1&timestamps=1&follow=1&tail=10&since=1428990821 HTTP/1.1
```

### Response
#### Success Response (101 / 200)
Returns application/vnd.docker.raw-stream log output.

#### Response Example
```http
HTTP/1.1 101 UPGRADED
Content-Type: application/vnd.docker.raw-stream
Connection: Upgrade
Upgrade: tcp

{{ STREAM }}
```

#### Status Codes
- **101** - no error, hints proxy about hijacking
- **200** - no error, no upgrade header found
- **404** - no such container
- **500** - server error
```


--------------------------------

### GET /images/(name)/get

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.16.md

Get a tarball containing all images and metadata for the repository specified by name, image name and tag, or image ID.

```APIDOC
## GET /images/(name)/get

### Description
Get a tarball containing all images and metadata for the repository specified by `name`. If `name` is a specific name and tag (e.g. ubuntu:latest), then only that image (and its parents) are returned. If `name` is an image ID, similarly only that image (and its parents) are returned, but with the exclusion of the 'repositories' file in the tarball.

### Method
GET

### Endpoint
/images/(name)/get

### Parameters
#### Path Parameters
- **name** (string) - Required - Repository name, image name and tag, or image ID

### Request Example
```http
GET /images/ubuntu/get
```

### Response
#### Success Response (200)
- Content-Type: `application/x-tar` (Binary data stream)

#### Status Codes
- **200** – no error
- **500** – server error
```


--------------------------------

### Start gateway with custom host and port

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/model-runner/cmd/cli/docs/reference/model_gateway.md

Runs the gateway bound to a custom host interface and port number.

```console
$ docker model gateway --config config.yaml --host 127.0.0.1 --port 9000
```


--------------------------------

### GET /containers/(id)/logs

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.12.md

Get stdout and stderr logs from a specific container. Supports streaming, log filtering by stdout/stderr, and timestamp output.

```APIDOC
## GET /containers/(id)/logs

### Description
Get stdout and stderr logs from the container `id`.

### Method
GET

### Endpoint
`/containers/(id)/logs`

### Parameters
#### Path Parameters
- **id** (string) - Required - Container ID or name

#### Query Parameters
- **follow** (boolean) - Optional - 1/True/true or 0/False/false, return stream. Default false
- **stdout** (boolean) - Optional - 1/True/true or 0/False/false, if logs=true, return stdout log. Default false
- **stderr** (boolean) - Optional - 1/True/true or 0/False/false, if logs=true, return stderr log. Default false
- **timestamps** (boolean) - Optional - 1/True/true or 0/False/false, if logs=true, print timestamps for every log line. Default false

### Request Example
```http
GET /containers/4fa6e0f0c678/logs?stderr=1&stdout=1&timestamps=1&follow=1 HTTP/1.1
```

### Response
#### Success Response (200)
- Returns a raw stream of stdout/stderr logs (Content-Type: `application/vnd.docker.raw-stream`).

#### Response Example
```http
HTTP/1.1 200 OK
Content-Type: application/vnd.docker.raw-stream

{{ STREAM }}
```

#### Status Codes
- **200** - no error
- **404** - no such container
- **500** - server error
```


--------------------------------

### Configure API Toolset for GET Requests

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/tools/api/index.md

Defines an API toolset configuration using HTTP GET with parameters interpolated into the URL query string.

```yaml
toolsets:
  - type: api
    api_config:
      name: search_users
      method: GET
      endpoint: "https://api.example.com/users?q=${query}&limit=${limit}"
      instruction: Search for users by name
      args:
        query:
          type: string
          description: Search query
        limit:
          type: integer
          description: Maximum results (default 10)
      required: ["query"]
```


--------------------------------

### Retrieve system-wide details with GET /info

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.23.md

Returns comprehensive system and daemon configuration information including container counts, storage drivers, memory limits, and runtime plugins.

```http
GET /v1.23/info HTTP/1.1
```

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "Architecture": "x86_64",
    "ClusterStore": "etcd://localhost:2379",
    "CgroupDriver": "cgroupfs",
    "Containers": 11,
    "ContainersRunning": 7,
    "ContainersStopped": 3,
    "ContainersPaused": 1,
    "CpuCfsPeriod": true,
    "CpuCfsQuota": true,
    "Debug": false,
    "DockerRootDir": "/var/lib/docker",
    "Driver": "btrfs",
    "DriverStatus": [[""]],
    "ExecutionDriver": "native-0.1",
    "ExperimentalBuild": false,
    "HttpProxy": "http://test:test@localhost:8080",
    "HttpsProxy": "https://test:test@localhost:8080",
    "ID": "7TRN:IPZB:QYBB:VPBQ:UMPP:KARE:6ZNR:XE6T:7EWV:PKF4:ZOJD:TPYS",
    "IPv4Forwarding": true,
    "Images": 16,
    "IndexServerAddress": "https://index.docker.io/v1/",
    "InitPath": "/usr/bin/docker",
    "InitSha1": "",
    "KernelMemory": true,
    "KernelVersion": "3.12.0-1-amd64",
    "Labels": [
        "storage=ssd"
    ],
    "MemTotal": 2099236864,
    "MemoryLimit": true,
    "NCPU": 1,
    "NEventsListener": 0,
    "NFd": 11,
    "NGoroutines": 21,
    "Name": "prod-server-42",
    "NoProxy": "9.81.1.160",
    "OomKillDisable": true,
    "OSType": "linux",
    "OperatingSystem": "Boot2Docker",
    "Plugins": {
        "Volume": [
            "local"
        ],
        "Network": [
            "null",
            "host",
            "bridge"
        ]
    },
    "RegistryConfig": {
        "IndexConfigs": {
            "docker.io": {
                "Mirrors": null,
                "Name": "docker.io",
                "Official": true,
                "Secure": true
            }
        },
        "InsecureRegistryCIDRs": [
            "127.0.0.0/8"
        ]
    },
    "ServerVersion": "1.9.0",
    "SwapLimit": false,
    "SystemStatus": [["State", "Healthy"]],
    "SystemTime": "2015-03-10T11:11:23.730591467-07:00"
}
```


--------------------------------

### Configure agent session options with session.New

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/guides/go-sdk/index.md

Create a new agent session configured with a title, initial user message, and maximum iteration limits.

```go
import "github.com/docker/docker-agent/pkg/session"

sess := session.New(
    // Set a title for the session
    session.WithTitle("Code Review Task"),

    // Add user message
    session.WithUserMessage("Review this code for bugs"),

    // Limit iterations
    session.WithMaxIterations(20),
)
```


--------------------------------

### POST /containers/(id or name)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.14.md

Start a specific container by its ID or name. Allows passing optional host configuration parameters.

```APIDOC
## POST /containers/(id or name)/start

### Description
Start the container `id`.

### Method
POST

### Endpoint
`/containers/(id or name)/start`

### Parameters
#### Path Parameters
- **id or name** (string) - Required - Container ID or name

#### Request Body
- **hostConfig** (object) - Optional - The container's host configuration

### Request Example
```json
{
     "Binds":["/tmp:/tmp"],
     "Links":["redis3:redis"],
     "LxcConf":[{"Key":"lxc.utsname","Value":"docker"}],
     "PortBindings":{ "22/tcp": [{ "HostPort": "11022" }] },
     "PublishAllPorts":false,
     "Privileged":false,
     "Dns": ["8.8.8.8"],
     "VolumesFrom": ["parent", "other:ro"],
     "CapAdd": ["NET_ADMIN"],
     "CapDrop": ["MKNOD"]
}
```

### Response
#### Success Response (204)
- No Content

#### Status Codes
- **204** – no error
- **304** – container already started
- **404** – no such container
- **500** – server error
```


--------------------------------

### Install the rclone plugin with an alias

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/cli/docs/extend/_index.md

Pulls and installs the rclone plugin under the alias `rclone` and prompts to grant required network, mount, device, and capability permissions.

```console
$ docker plugin install rclone/docker-volume-rclone --alias rclone

Plugin "rclone/docker-volume-rclone" is requesting the following privileges:
 - network: [host]
 - mount: [/var/lib/docker-plugins/rclone/config]
 - mount: [/var/lib/docker-plugins/rclone/cache]
 - device: [/dev/fuse]
 - capabilities: [CAP_SYS_ADMIN]
Do you grant the above permissions? [y/N] 
```


--------------------------------

### Create plugin volume and observe log output

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/cli/docs/extend/_index.md

Creates a volume using a volume plugin and traces plugin execution steps such as path resolution and directory creation in the daemon logs.

```console
$ docker volume create -d tiborvass/sample-volume-plugin samplevol

INFO[0193] Create Called...  Ensuring directory /data/samplevol exists on host...  plugin=f52a3df433b9aceee436eaada0752f5797aab1de47e5485f1690a073b860ff62
INFO[0193] open /var/lib/docker/plugin-data/local-persist.json: no such file or directory  plugin=f52a3df433b9aceee436eaada0752f5797aab1de47e5485f1690a073b860ff62
INFO[0193]                   Created volume samplevol with mountpoint /data/samplevol  plugin=f52a3df433b9aceee436eaada0752f5797aab1de47e5485f1690a073b860ff62
INFO[0193] Path Called...    Returned path /data/samplevol  plugin=f52a3df433b9aceee436eaada0752f5797aab1de47e5485f1690a073b860ff62
```


--------------------------------

### POST /exec/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.23.md

Starts a previously set up exec instance. Can detach or run interactively with raw stream output.

```APIDOC
## POST /exec/(id)/start

### Description
Starts a previously set up `exec` instance `id`. If `detach` is true, this API returns after starting the `exec` command. Otherwise, this API sets up an interactive session with the `exec` command.

### Method
POST

### Endpoint
`/exec/(id)/start`

### Parameters
#### Path Parameters
- **id** (string) - Required - Exec instance ID.

#### Request Body
- **Detach** (boolean) - Optional - Detach from the `exec` command.
- **Tty** (boolean) - Optional - Allocate a pseudo-TTY.

### Request Example
```json
{
  "Detach": false,
  "Tty": false
}
```

### Response
#### Success Response (200 OK)
Content-Type: `application/vnd.docker.raw-stream`

Stream behavior is similar to `POST /containers/(id or name)/attach`.

#### Status Codes
- **200** - No error
- **404** - No such exec instance
- **409** - Container is paused
```


--------------------------------

### Render Docker Desktop installer links using desktop-install shortcode

Source: https://github.com/docker/docs/blob/main/_autodocs/api-reference/shortcodes-download.md

Calls the desktop-install shortcode in Markdown content to display download and checksum links across all platforms for a specific release version and build path.

```markdown
{{</* desktop-install
  all="true"
  version="4.45.0"
  build_path="/"
  win_arm_release="4.45.0"
*/>}}
```


--------------------------------

### Run a command without starting linked dependencies

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/compose/v5/docs/reference/compose_run.md

Use the `--no-deps` flag to execute the command without checking or starting any linked dependency services.

```console
$ docker compose run --no-deps web python manage.py shell
```


--------------------------------

### POST /containers/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.7.md

Start a container by ID. Allows passing host configuration options such as port bindings and volume mounts.

```APIDOC
## POST /containers/(id)/start

### Description
Start the container `id`.

### Method
POST

### Endpoint
/containers/(id)/start

### Parameters
#### Path Parameters
- **id** (string) - Required - Container ID or name

#### Request Body
- **hostConfig** (object) - Optional - The container's host configuration
  - **Binds** (array) - Optional - List of volume bindings (must reference volumes defined during container creation)
  - **LxcConf** (array) - Optional - LXC configuration key-value pairs
  - **PortBindings** (object) - Optional - Mapping of exposed ports to host ports
  - **Privileged** (boolean) - Optional - Give extended privileges to this container
  - **PublishAllPorts** (boolean) - Optional - Publish all exposed ports to the host

### Request Example
```http
POST /containers/(id)/start HTTP/1.1
Content-Type: application/json

{
     "Binds":["/tmp:/tmp"],
     "LxcConf":[{"Key":"lxc.utsname","Value":"docker"}],
     "PortBindings":{ "22/tcp": [{ "HostPort": "11022" }] },
     "Privileged":false,
     "PublishAllPorts":false
}
```

### Response
#### Success Response (204)
No Content

#### Error Responses
- **404** - no such container
- **500** - server error

#### Response Example
```http
HTTP/1.1 204 No Content
Content-Type: text/plain
```
```


--------------------------------

### GET /images/get

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.23.md

Get a tarball containing all images and metadata for one or more repositories. Accepts multiple repository names or image IDs via query parameters.

```APIDOC
## GET /images/get

### Description
Get a tarball containing all images and metadata for one or more repositories.

For each value of the `names` parameter: if it is a specific name and tag (e.g. `ubuntu:latest`), then only that image (and its parents) are returned; if it is an image ID, similarly only that image (and its parents) are returned and there would be no names referenced in the 'repositories' file for this image ID.

### Method
GET

### Endpoint
`/images/get`

### Parameters
#### Query Parameters
- **names** (string) - Optional - Image names or IDs to download.

### Request Example
```http
GET /v1.23/images/get?names=myname%2Fmyapp%3Alatest&names=busybox
```

### Response
#### Success Response (200)
- Binary data stream (`application/x-tar`)

#### Response Example
```http
HTTP/1.1 200 OK
Content-Type: application/x-tar

Binary data stream
```

#### Status Codes
- **200** – no error
- **500** – server error
```


--------------------------------

### Show Docker version information via GET /version

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.20.md

Call GET /version to retrieve version details for Docker, OS, kernel, Go, and the API.

```http
GET /v1.20/version HTTP/1.1
```

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
     "Version": "1.5.0",
     "Os": "linux",
     "KernelVersion": "3.18.5-tinycore64",
     "GoVersion": "go1.4.1",
     "GitCommit": "a8a31ef",
     "Arch": "amd64",
     "ApiVersion": "1.20",
     "Experimental": false
}
```


--------------------------------

### Get an image repository tarball with GET /images/(name)/get

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.10.md

Retrieves a tarball stream containing all images and metadata for the repository specified in the path parameter.

```http
GET /images/ubuntu/get
```

```http
HTTP/1.1 200 OK
Content-Type: application/x-tar

Binary data stream
```


--------------------------------

### Ping the Docker server with GET /_ping

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.23.md

Send a GET request to test connectivity and server availability. Returns a plain text 'OK' on HTTP 200 success.

```http
GET /v1.23/_ping HTTP/1.1
```

```http
HTTP/1.1 200 OK
Content-Type: text/plain

OK
```


--------------------------------

### Ping the Docker server via GET /_ping

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.20.md

Send a GET request to /_ping to check server responsiveness, returning a 200 OK with plain text response.

```http
GET /v1.20/_ping HTTP/1.1
```

```http
HTTP/1.1 200 OK
Content-Type: text/plain

OK
```


--------------------------------

### GET /images/(name)/get

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.22.md

Get a tarball containing all images and metadata for the repository specified by name. If name includes a specific tag, only that image and its parents are returned.

```APIDOC
## GET /images/(name)/get

### Description
Get a tarball containing all images and metadata for the repository specified by `name`. If `name` is a specific name and tag (e.g. `ubuntu:latest`), then only that image (and its parents) are returned. If `name` is an image ID, similarly only that image (and its parents) are returned, but with the exclusion of the 'repositories' file in the tarball.

### Method
GET

### Endpoint
`/images/(name)/get`

### Parameters
#### Path Parameters
- **name** (string) - Required - Image name or image ID

### Request Example
```http
GET /v1.22/images/ubuntu/get HTTP/1.1
```

### Response
#### Success Response (200)
- Returns binary data stream (`application/x-tar`)

#### Response Example
```http
HTTP/1.1 200 OK
Content-Type: application/x-tar

Binary data stream
```

#### Status Codes
- **200** – no error
- **500** – server error
```


--------------------------------

### Get a tarball containing all images in a repository

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.22.md

Send a GET request to export a tarball containing all images and metadata for a specific repository name and tag or image ID.

```http
GET /v1.22/images/ubuntu/get
```

```http
HTTP/1.1 200 OK
Content-Type: application/x-tar

Binary data stream
```


--------------------------------

### Get a tarball of repository images using GET /images/(name)/get

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.7.md

Download a tarball containing all images, tags, and metadata associated with the specified repository name.

```http
GET /images/ubuntu/get
```

```http
.. sourcecode:: http

   HTTP/1.1 200 OK
Content-Type: application/x-tar

Binary data stream
    :statuscode 200: no error
    :statuscode 500: server error
```


--------------------------------

### List containers with GET /containers/json

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.5.md

Send a GET request to list containers with optional query parameters for pagination, status, and sizing. By default, only running containers are returned.

```http
GET /containers/json?all=1&before=8dfafdbc3a40&size=1 HTTP/1.1
```

```http
HTTP/1.1 200 OK
Content-Type: application/json

[
  {
    "Id": "8dfafdbc3a40",
    "Image": "ubuntu:latest",
    "Command": "echo 1",
    "Created": 1367854155,
    "Status": "Exit 0",
    "Ports":[{"PrivatePort": 2222, "PublicPort": 3333, "Type": "tcp"}],
    "SizeRw":12288,
    "SizeRootFs":0
  },
  {
    "Id": "9cd87474be90",
    "Image": "ubuntu:latest",
    "Command": "echo 222222",
    "Created": 1367854155,
    "Status": "Exit 0",
    "Ports":[],
    "SizeRw":12288,
    "SizeRootFs":0
  },
  {
    "Id": "3176a2479c92",
    "Image": "centos:latest",
    "Command": "echo 3333333333333333",
    "Created": 1367854154,
    "Status": "Exit 0",
    "Ports":[],
    "SizeRw":12288,
    "SizeRootFs":0
  },
  {
    "Id": "4cb07b47f9fb",
    "Image": "fedora:latest",
    "Command": "echo 444444444444444444444444444444444",
    "Created": 1367854152,
    "Status": "Exit 0",
    "Ports":[],
    "SizeRw":12288,
    "SizeRootFs":0
  }
]
```


--------------------------------

### GET /containers/(id or name)/logs

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.14.md

Get stdout and stderr logs from a container. Supports streaming, log following, timestamps, and tailing a specific number of lines.

```APIDOC
## GET /containers/(id or name)/logs

### Description
Get stdout and stderr logs from the container `id`.

### Method
GET

### Endpoint
`/containers/(id or name)/logs`

### Parameters
#### Path Parameters
- **id or name** (string) - Required - Container ID or name

#### Query Parameters
- **follow** (boolean) - Optional - 1/True/true or 0/False/false, return stream. Default false
- **stdout** (boolean) - Optional - 1/True/true or 0/False/false, show stdout log. Default false
- **stderr** (boolean) - Optional - 1/True/true or 0/False/false, show stderr log. Default false
- **timestamps** (boolean) - Optional - 1/True/true or 0/False/false, print timestamps for every log line. Default false
- **tail** (string) - Optional - Output specified number of lines at the end of logs: `all` or `<number>`. Default all

### Request Example
```http
GET /containers/4fa6e0f0c678/logs?stderr=1&stdout=1&timestamps=1&follow=1&tail=10 HTTP/1.1
```

### Response
#### Success Response (200)
- Content-Type: `application/vnd.docker.raw-stream`
- Returns the log stream.

#### Status Codes
- **200** – no error
- **404** – no such container
- **500** – server error
```


--------------------------------

### Register custom themes with styles.RegisterBuiltinThemes

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/guides/go-sdk/index.md

Call styles.RegisterBuiltinThemes at startup before applying any persisted theme to embed custom themes. Validates eagerly and returns an error if the filesystem is nil or missing the themes directory.

```go
import (
    "embed"

    "github.com/docker/docker-agent/pkg/tui/styles"
)

//go:embed themes/*.yaml
var brandThemes embed.FS

// Call at startup, before applying any persisted theme:
if err := styles.RegisterBuiltinThemes(brandThemes); err != nil {
    return err
}
```


--------------------------------

### Define container healthcheck with interval and retry settings

Source: https://github.com/docker/docs/blob/main/content/reference/compose-file/services.md

Configures a container healthcheck command along with check intervals, timeout limits, retries, start period, and start interval.

```yml
healthcheck:
  test: ["CMD", "curl", "-f", "http://localhost"]
  interval: 1m30s
  timeout: 10s
  retries: 3
  start_period: 40s
  start_interval: 5s
```


--------------------------------

### GET /images/(name)/get

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.23.md

Get a tarball containing all images and metadata for the specified repository name or image ID. If a specific tag is provided, only that image and its parents are returned.

```APIDOC
## GET /images/(name)/get

### Description
Get a tarball containing all images and metadata for the repository specified by `name`.

If `name` is a specific name and tag (e.g. ubuntu:latest), then only that image (and its parents) are returned. If `name` is an image ID, similarly only that image (and its parents) are returned, but with the exclusion of the 'repositories' file in the tarball, as there were no image names referenced.

### Method
GET

### Endpoint
`/images/(name)/get`

### Parameters
#### Path Parameters
- **name** (string) - Required - Image name or ID.

### Request Example
```http
GET /v1.23/images/ubuntu/get
```

### Response
#### Success Response (200)
- Binary data stream (`application/x-tar`)

#### Response Example
```http
HTTP/1.1 200 OK
Content-Type: application/x-tar

Binary data stream
```

#### Status Codes
- **200** – no error
- **500** – server error
```


--------------------------------

### Get Docker version details with GET /version

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.23.md

Displays version and build information for the Docker daemon, including API version, Git commit, OS, and Go version.

```http
GET /v1.23/version HTTP/1.1
```

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
     "Version": "1.11.0",
     "Os": "linux",
     "KernelVersion": "3.19.0-23-generic",
     "GoVersion": "go1.4.2",
     "GitCommit": "e75da4b",
     "Arch": "amd64",
     "ApiVersion": "1.23",
     "BuildTime": "2015-12-01T07:09:13.444803460+00:00",
     "Experimental": true
}
```


--------------------------------

### Get a tarball containing multiple image repositories

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.22.md

Send a GET request with one or more names query parameters to export a tarball containing images and metadata across repositories.

```http
GET /v1.22/images/get?names=myname%2Fmyapp%3Alatest&names=busybox
```

```http
HTTP/1.1 200 OK
Content-Type: application/x-tar

Binary data stream
```


--------------------------------

### Get archive of filesystem resource (GET /containers/(id)/archive)

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.20.md

Retrieves a tar archive of a specified filesystem resource inside the container. Returns header metadata in X-Docker-Container-Path-Stat.

```http
GET /v1.20/containers/8cce319429b2/archive?path=/root HTTP/1.1
```

```http
HTTP/1.1 200 OK
Content-Type: application/x-tar
X-Docker-Container-Path-Stat: eyJuYW1lIjoicm9vdCIsInNpemUiOjQwOTYsIm1vZGUiOjIxNDc0ODQwOTYsIm10aW1lIjoiMjAxNC0wMi0yN1QyMDo1MToyM1oiLCJsaW5rVGFyZ2V0IjoiIn0=

{% raw %}
{{ TAR STREAM }}
{% endraw %}
```


--------------------------------

### Compliant all-uppercase Dockerfile instructions

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/buildkit/frontend/dockerfile/docs/rules/consistent-instruction-casing.md

Demonstrates consistent instruction casing using all-uppercase keyword letters.

```dockerfile
FROM alpine
RUN echo hello > /greeting.txt
ENTRYPOINT ["cat", "/greeting.txt"]
```


--------------------------------

### GET /containers/(id or name)/logs

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.18.md

Get stdout and stderr logs from a container by ID or name. Note that this endpoint works only for containers with json-file or journald logging drivers.

```APIDOC
## GET /containers/(id or name)/logs

### Description
Get stdout and stderr logs from a container. This endpoint works only for containers with the json-file or journald logging drivers.

### Method
GET

### Endpoint
`/containers/(id or name)/logs`

### Parameters
#### Path Parameters
- **id or name** (string) - Required - Container ID or name

#### Query Parameters
- **follow** (boolean) - Optional - Return stream (1/True/true or 0/False/false). Default `false`.
- **stdout** (boolean) - Optional - Show stdout log (1/True/true or 0/False/false). Default `false`.
- **stderr** (boolean) - Optional - Show stderr log (1/True/true or 0/False/false). Default `false`.
- **timestamps** (boolean) - Optional - Print timestamps for every log line (1/True/true or 0/False/false). Default `false`.
- **tail** (string) - Optional - Output specified number of lines at the end of logs: `all` or `<number>`. Default `all`.

### Response
#### Status Codes
- **101** - No error, hints proxy about hijacking
- **200** - No error, no upgrade header found
- **404** - No such container
- **500** - Server error
```


--------------------------------

### Get container logs via GET /containers/(id)/logs

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.13.md

Retrieves stdout and stderr log streams from a container by ID with optional follow, timestamp, and tail filtering.

```http
GET /containers/4fa6e0f0c678/logs?stderr=1&stdout=1&timestamps=1&follow=1&tail=10 HTTP/1.1
```

```http
HTTP/1.1 200 OK
Content-Type: application/vnd.docker.raw-stream

{{ STREAM }}
```


--------------------------------

### Run docker agent with custom sandbox template or --no-kit

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/docker/docker-agent/docs/configuration/sandbox/index.md

Demonstrates running an agent in sandbox mode using a custom template image or without staging skills and prompt files into the sandbox via --no-kit.

```bash
# Use a custom template image
docker agent run --sandbox --template myorg/custom-agent-template:latest agent.yaml

# Run without staging skills / prompt files into the sandbox
docker agent run --sandbox --no-kit agent.yaml
```


--------------------------------

### POST /exec/(id)/start

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.19.md

Starts a previously set up exec instance in either detached or interactive mode.

```APIDOC
## POST /exec/(id)/start

### Description
Starts a previously set up `exec` instance `id`. If `detach` is true, this API returns after starting the `exec` command. Otherwise, this API sets up an interactive session with the `exec` command.

### Method
POST

### Endpoint
/exec/(id)/start

### Parameters
#### Path Parameters
- **id** (string) - Required - Exec instance ID

#### Request Body
- **Detach** (boolean) - Detach from the `exec` command.
- **Tty** (boolean) - Allocate a pseudo-TTY.

### Request Example
```json
{
  "Detach": false,
  "Tty": false
}
```

### Response
#### Success Response (200)
- **200** – no error (`application/vnd.docker.raw-stream`)

#### Error Response (404)
- **404** – no such exec instance

#### Response Example
```http
HTTP/1.1 200 OK
Content-Type: application/vnd.docker.raw-stream

{{ STREAM }}
```
```


--------------------------------

### Create a container with POST /containers/create

Source: https://github.com/docker/docs/blob/main/_vendor/github.com/moby/moby/api/docs/v1.5.md

Send a POST request containing container configuration options like image, environment variables, and execution commands. Returns HTTP 201 with the container ID upon successful creation.

```http
POST /containers/create HTTP/1.1
Content-Type: application/json

{
  "Hostname":"",
  "User":"",
  "Memory":0,
  "MemorySwap":0,
  "AttachStdin":false,
  "AttachStdout":true,
  "AttachStderr":true,
  "PortSpecs":null,
  "Privileged": false,
  "Tty":false,
  "OpenStdin":false,
  "StdinOnce":false,
  "Env":null,
  "Cmd":[
    "date"
  ],
  "Dns":null,
  "Image":"ubuntu",
  "Volumes":{},
  "VolumesFrom":"",
  "WorkingDir":""
}
```

```http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "Id":"e90e34656806"
  "Warnings":[]
}
```
