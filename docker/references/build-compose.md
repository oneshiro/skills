# Docker — Build & Compose

Sourced snippets (30 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Chain multiple sequential pre_start steps

Source: https://github.com/docker/docs/blob/main/content/manuals/compose/how-tos/init-containers.md

Executes multiple setup steps in declared sequence, ensuring the application starts only after both the migration and fixture loading exit with code 0.

```yaml
services:
  app:
    image: myapp:latest
    depends_on:
      db:
        condition: service_healthy
    pre_start:
      - command: ["./manage.py", "migrate"]
      - command: ["./manage.py", "loaddata", "fixtures.json"]

  db:
    image: postgres:18
```


--------------------------------

### Create a directory for the policy tutorial

Source: https://github.com/docker/docs/blob/main/content/manuals/build/policies/intro.md

Sets up and enters a dedicated directory for creating the tutorial Dockerfile and policy file.

```console
$ mkdir policy-tutorial
$ cd policy-tutorial
```


--------------------------------

### Configure one-shot setup service with service_completed_successfully

Source: https://github.com/docker/docs/blob/main/content/manuals/compose/how-tos/init-containers.md

Models startup setup tasks using a peer service with restart: "no" and service_completed_successfully dependency condition.

```yaml
services:
  migrate:
    image: myapp:latest
    command: ["./manage.py", "migrate"]
    restart: "no"

  app:
    image: myapp:latest
    depends_on:
      migrate:
        condition: service_completed_successfully
```


--------------------------------

### Initialize Compose SDK service and start a project

Source: https://github.com/docker/docs/blob/main/content/manuals/compose/compose-sdk.md

Initializes a Docker CLI client and Compose service instance, loads a project from compose.yaml, and starts the services using Up().

```go
package main

import (
    "context"
    "log"

	"github.com/docker/cli/cli/command"
	"github.com/docker/cli/cli/flags"
    "github.com/docker/compose/v5/pkg/api"
    "github.com/docker/compose/v5/pkg/compose"
)

func main() {
    ctx := context.Background()

	dockerCLI, err := command.NewDockerCli()
	if err != nil {
		log.Fatalf("Failed to create docker CLI: %v", err)
	}
	err = dockerCLI.Initialize(&flags.ClientOptions{})
	if err != nil {
		log.Fatalf("Failed to initialize docker CLI: %v", err)
	}
	
    // Create a new Compose service instance
    service, err := compose.NewComposeService(dockerCLI)
    if err != nil {
        log.Fatalf("Failed to create compose service: %v", err)
    }

    // Load the Compose project from a compose file
    project, err := service.LoadProject(ctx, api.ProjectLoadOptionsRestore{
        ConfigPaths: []string{"compose.yaml"},
        ProjectName: "my-app",
    })
    if err != nil {
        log.Fatalf("Failed to load project: %v", err)
    }

    // Start the services defined in the Compose file
    err = service.Up(ctx, project, api.UpOptions{
        Create: api.CreateOptions{},
        Start:  api.StartOptions{},
    })
    if err != nil {
        log.Fatalf("Failed to start services: %v", err)
    }

    log.Printf("Successfully started project: %s", project.Name)
}
```


--------------------------------

### Install and register QEMU using tonistiigi/binfmt

Source: https://github.com/docker/docs/blob/main/content/manuals/build/building/multi-platform.md

Installs QEMU binaries and registers non-native executable types on the host OS using binfmt_misc. Requires Linux kernel 4.8 or later and binfmt-support 2.1.7 or later.

```console
$ docker run --privileged --rm tonistiigi/binfmt --install all
```


--------------------------------

### Replace one-shot setup service with pre_start

Source: https://github.com/docker/docs/blob/main/content/manuals/compose/how-tos/init-containers.md

Converts a legacy one-shot setup service into a subordinate pre_start step on the main application service.

```yaml
services:
  app:
    image: myapp:latest
    pre_start:
      - command: ["./manage.py", "migrate"]
```


--------------------------------

### Install Docker Compose plugin on Ubuntu and Debian

Source: https://github.com/docker/docs/blob/main/content/manuals/compose/install/linux.md

Updates the apt package index and installs the latest docker-compose-plugin package. Requires Docker repository setup beforehand.

```console
$ sudo apt-get update
$ sudo apt-get install docker-compose-plugin
```


--------------------------------

### Create project directory

Source: https://github.com/docker/docs/blob/main/content/manuals/build/building/multi-platform.md

Initializes and navigates into an empty working directory for the Go server application.

```console
$ mkdir go-server
$ cd go-server
```


--------------------------------

### Uncached apt-get update issue example

Source: https://github.com/docker/docs/blob/main/content/manuals/build/building/best-practices.md

Demonstrates an anti-pattern where running apt-get update in a separate layer leads to stale cache issues on subsequent installs.

```dockerfile
# syntax=docker/dockerfile:1

FROM ubuntu:22.04
RUN apt-get update
RUN apt-get install -y --no-install-recommends curl
```


--------------------------------

### Verify Docker Compose plugin installation

Source: https://github.com/docker/docs/blob/main/content/manuals/compose/install/linux.md

Displays the installed Docker Compose version to verify successful repository installation.

```console
$ docker compose version
```


--------------------------------

### Verify Docker Compose standalone installation on Windows Server

Source: https://github.com/docker/docs/blob/main/content/manuals/compose/install/standalone.md

Checks the installed Docker Compose version to verify successful installation.

```console
$ docker-compose.exe version
Docker Compose version {{% param "compose_version" %}}
```


--------------------------------

### Start a specific profile using --profile flag

Source: https://github.com/docker/docs/blob/main/content/manuals/compose/how-tos/profiles.md

Starts services matching the debug profile along with any profile-less services.

```console
$ docker compose --profile debug up
```


--------------------------------

### Install Python package dependencies with pip using RUN

Source: https://github.com/docker/docs/blob/main/content/manuals/build/concepts/dockerfile.md

Installs the specified Flask version into the build container. Requires pip to already be installed by a prior step.

```dockerfile
RUN pip install flask==3.0.*
```


--------------------------------

### Set up SSH mount using docker/build-push-action

Source: https://github.com/docker/docs/blob/main/content/manuals/build/ci/github-actions/secrets.md

Sets up SSH authentication with `MrSquaare/ssh-setup-action` using secret `SSH_GITHUB_PPK` and passes `ssh: default` to `docker/build-push-action`. Uses `SSH_AUTH_SOCK` by default without needing an explicit ID or path.

```yaml
name: ci

on:
  push:

jobs:
  docker:
    runs-on: ubuntu-latest
    steps:
      - name: Set up SSH
        uses: MrSquaare/ssh-setup-action@2d028b70b5e397cf8314c6eaea229a6c3e34977a # v3.1.0
        with:
          host: github.com
          private-key: ${{ secrets.SSH_GITHUB_PPK }}
          private-key-name: github-ppk

      - name: Build and push
        uses: docker/build-push-action@{{% param "build_push_action_version" %}}
        with:
          ssh: default
          push: true
          tags: user/app:latest
```


--------------------------------

### Install system packages using RUN

Source: https://github.com/docker/docs/blob/main/content/manuals/build/concepts/dockerfile.md

Executes shell commands in the base image to update package indexes and install python3 and pip, preceded by a comment.

```dockerfile
# install app dependencies
RUN apt-get update && apt-get install -y python3 python3-pip
```


--------------------------------

### Build and push container image using individual GitHub Actions

Source: https://github.com/docker/docs/blob/main/content/manuals/build/ci/github-actions/github-builder/_index.md

Configures a conventional GitHub Actions job that explicitly defines individual steps for registry login, QEMU setup, Buildx setup, metadata generation, and image building/pushing.

```yaml
jobs:
  docker:
    runs-on: ubuntu-latest
    steps:
      - name: Login to Docker Hub
        uses: docker/login-action@{{% param "login_action_version" %}}
        with:
          username: ${{ vars.DOCKERHUB_USERNAME }}
          password: ${{ secrets.DOCKERHUB_TOKEN }}

      - name: Set up QEMU
        uses: docker/setup-qemu-action@{{% param "setup_qemu_action_version" %}}
      
      - name: Set up Docker Buildx
        uses: docker/setup-buildx-action@{{% param "setup_buildx_action_version" %}}
        
      - name: Docker meta
        uses: docker/metadata-action@{{% param "metadata_action_version" %}}
        id: meta
        with:
          images: name/app

      - name: Build and push
        uses: docker/build-push-action@{{% param "build_push_action_version" %}}
        with:
          push: ${{ github.event_name != 'pull_request' }}
          tags: ${{ steps.meta.outputs.tags }}
          labels: ${{ steps.meta.outputs.labels }}
          cache-from: type=gha
          cache-to: type=gha
```


--------------------------------

### List installed packages from SBOM using Go templates

Source: https://github.com/docker/docs/blob/main/content/manuals/build/metadata/attestations/sbom.md

Iterates through the SBOM package list to display installed package names and version identifiers.

```console
$ docker buildx imagetools inspect <namespace>/<image>:<version> \
    --format "{{ range .SBOM.SPDX.packages }}{{ .name }}@{{ .versionInfo }}{{ println }}{{ end }}"
adduser@3.118ubuntu2
apt@2.0.9
base-files@11ubuntu5.6
base-passwd@3.5.47
...
```


--------------------------------

### Recommended apt-get RUN pattern with cleanup

Source: https://github.com/docker/docs/blob/main/content/manuals/build/building/best-practices.md

Applies all apt-get best practices including cache busting, version pinning, multi-line listing, and removing /var/lib/apt/lists/*.

```dockerfile
RUN apt-get update && apt-get install -y --no-install-recommends \
    aufs-tools \
    automake \
    build-essential \
    curl \
    dpkg-sig \
    libcap-dev \
    libsqlite3-dev \
    mercurial \
    reprepro \
    ruby1.9.1 \
    ruby1.9.1-dev \
    s3cmd=1.1.* \
    && rm -rf /var/lib/apt/lists/*
```


--------------------------------

### View an SBOM attestation example in SPDX format

Source: https://github.com/docker/docs/blob/main/content/manuals/build/metadata/attestations/sbom.md

Example JSON structure of an in-toto SBOM attestation containing SPDX 2.2 document metadata, packages, and relationships.

```json
{
  "_type": "https://in-toto.io/Statement/v0.1",
  "predicateType": "https://spdx.dev/Document",
  "subject": [
    {
      "name": "pkg:docker/<registry>/<image>@<tag/digest>?platform=<platform>",
      "digest": {
        "sha256": "e8275b2b76280af67e26f068e5d585eb905f8dfd2f1918b3229db98133cb4862"
      }
    }
  ],
  "predicate": {
    "SPDXID": "SPDXRef-DOCUMENT",
    "creationInfo": {
      "created": "2022-12-16T15:27:25.517047753Z",
      "creators": ["Organization: Anchore, Inc", "Tool: syft-v0.60.3"],
      "licenseListVersion": "3.18"
    },
    "dataLicense": "CC0-1.0",
    "documentNamespace": "https://anchore.com/syft/dir/run/src/core/sbom-cba61a72-fa95-4b60-b63f-03169eac25ca",
    "name": "/run/src/core/sbom",
    "packages": [
      {
        "SPDXID": "SPDXRef-b074348b8f56ea64",
        "downloadLocation": "NOASSERTION",
        "externalRefs": [
          {
            "referenceCategory": "SECURITY",
            "referenceLocator": "cpe:2.3:a:org:repo:\\(devel\\):*:*:*:*:*:*:*",
            "referenceType": "cpe23Type"
          },
          {
            "referenceCategory": "PACKAGE_MANAGER",
            "referenceLocator": "pkg:golang/github.com/org/repo@(devel)",
            "referenceType": "purl"
          }
        ],
        "filesAnalyzed": false,
        "licenseConcluded": "NONE",
        "licenseDeclared": "NONE",
        "name": "github.com/org/repo",
        "sourceInfo": "acquired package info from go module information: bin/server",
        "versionInfo": "(devel)"
      },
      {
        "SPDXID": "SPDXRef-1b96f57f8fed62d8",
        "checksums": [
          {
            "algorithm": "SHA256",
            "checksumValue": "0c13f1f3c1636491f716c2027c301f21f9dbed7c4a2185461ba94e3e58443408"
          }
        ],
        "downloadLocation": "NOASSERTION",
        "externalRefs": [
          {
            "referenceCategory": "SECURITY",
            "referenceLocator": "cpe:2.3:a:go-chi:chi\\/v5:v5.0.0:*:*:*:*:*:*:*",
            "referenceType": "cpe23Type"
          },
          {
            "referenceCategory": "SECURITY",
            "referenceLocator": "cpe:2.3:a:go_chi:chi\\/v5:v5.0.0:*:*:*:*:*:*:*",
            "referenceType": "cpe23Type"
          },
          {
            "referenceCategory": "SECURITY",
            "referenceLocator": "cpe:2.3:a:go:chi\\/v5:v5.0.0:*:*:*:*:*:*:*",
            "referenceType": "cpe23Type"
          },
          {
            "referenceCategory": "PACKAGE_MANAGER",
            "referenceLocator": "pkg:golang/github.com/go-chi/chi/v5@v5.0.0",
            "referenceType": "purl"
          }
        ],
        "filesAnalyzed": false,
        "licenseConcluded": "NONE",
        "licenseDeclared": "NONE",
        "name": "github.com/go-chi/chi/v5",
        "sourceInfo": "acquired package info from go module information: bin/server",
        "versionInfo": "v5.0.0"
      }
    ],
    "relationships": [
      {
        "relatedSpdxElement": "SPDXRef-1b96f57f8fed62d8",
        "relationshipType": "CONTAINS",
        "spdxElementId": "SPDXRef-043f7360d3c66bc31ba45388f16423aa58693289126421b71d884145f8837fe1"
      },
      {
        "relatedSpdxElement": "SPDXRef-b074348b8f56ea64",
        "relationshipType": "CONTAINS",
        "spdxElementId": "SPDXRef-043f7360d3c66bc31ba45388f16423aa58693289126421b71d884145f8837fe1"
      }
    ],
    "spdxVersion": "SPDX-2.2"
  }
}
```


--------------------------------

### Create Kubernetes builder with qemu.install option

Source: https://github.com/docker/docs/blob/main/content/manuals/build/builders/drivers/kubernetes.md

Explicitly installs QEMU emulation using the qemu.install driver option when creating a Kubernetes builder.

```console
$ docker buildx create \
  --bootstrap \
  --name=kube \
  --driver=kubernetes \
  --driver-opt=namespace=buildkit,qemu.install=true
```


--------------------------------

### Create a docker-container builder with buildkitd config

Source: https://github.com/docker/docs/blob/main/content/manuals/build/buildkit/configure.md

Create and bootstrap a `docker-container` driver builder configured with `/etc/buildkitd.toml`.

```console
$ docker buildx create --use --bootstrap \
  --name mybuilder \
  --driver docker-container \
  --buildkitd-config /etc/buildkitd.toml
```


--------------------------------

### Bootstrap and import an Ubuntu base image with tar

Source: https://github.com/docker/docs/blob/main/content/manuals/build/building/base-images.md

Bootstraps an Ubuntu release filesystem, packages it into a tar stream, imports it as a Docker image, and verifies the OS release.

```dockerfile
$ sudo debootstrap noble noble > /dev/null
$ sudo tar -C noble -c . | docker import - noble

sha256:81ec9a55a92a5618161f68ae691d092bf14d700129093158297b3d01593f4ee3

$ docker run noble cat /etc/lsb-release

DISTRIB_ID=Ubuntu
DISTRIB_RELEASE=24.04
DISTRIB_CODENAME=noble
DISTRIB_DESCRIPTION="Ubuntu 24.04.2 LTS"
```


--------------------------------

### Create a Kubernetes builder with docker buildx create

Source: https://github.com/docker/docs/blob/main/content/manuals/build/builders/drivers/kubernetes.md

Bootstraps and configures a new Buildx builder using the Kubernetes driver inside the specified namespace.

```console
$ docker buildx create \
  --bootstrap \
  --name=kube \
  --driver=kubernetes \
  --driver-opt=namespace=buildkit
```


--------------------------------

### Reference image inputs in Dockerfile

Source: https://github.com/docker/docs/blob/main/content/manuals/build/policies/validate-images.md

Demonstrates how image inputs are introduced in Dockerfiles using FROM instructions and COPY --from references.

```dockerfile
# FROM instructions
FROM alpine:3.22
FROM golang:1.25-alpine AS builder

# COPY --from references
COPY --from=builder /app /app
COPY --from=nginx:latest /etc/nginx/nginx.conf /nginx.conf
```


--------------------------------

### Create and build using a multi-node builder with --append

Source: https://github.com/docker/docs/blob/main/content/manuals/build/building/multi-platform.md

Creates a builder named mybuild from context node-amd64, appends context node-arm64, and builds for both platforms. Assumes the specified Docker contexts already exist.

```console
$ docker buildx create --use --name mybuild node-amd64
mybuild
$ docker buildx create --append --name mybuild node-arm64
$ docker buildx build --platform linux/amd64,linux/arm64 .
```


--------------------------------

### Modified apt-get install demonstrating cache reuse

Source: https://github.com/docker/docs/blob/main/content/manuals/build/building/best-practices.md

Shows how modifying a subsequent RUN apt-get install layer reuses the stale cached apt-get update layer.

```dockerfile
# syntax=docker/dockerfile:1

FROM ubuntu:22.04
RUN apt-get update
RUN apt-get install -y --no-install-recommends curl nginx
```


--------------------------------

### Build a multi-platform image using QEMU emulation

Source: https://github.com/docker/docs/blob/main/content/manuals/build/building/multi-platform.md

Create, build, and test a multi-platform image targeting linux/amd64 and linux/arm64 using QEMU emulation. Requires Docker Desktop or Docker Engine with QEMU installed.

```console
$ mkdir multi-platform
$ cd multi-platform
```

```dockerfile
# syntax=docker/dockerfile:1
FROM alpine
RUN uname -m > /arch
```

```console
$ docker build --platform linux/amd64,linux/arm64 -t multi-platform .
```

```console
$ docker run --rm multi-platform cat /arch
```


--------------------------------

### Install Docker Compose plugin on RPM-based distributions

Source: https://github.com/docker/docs/blob/main/content/manuals/compose/install/linux.md

Updates the yum package repository and installs the docker-compose-plugin package. Requires Docker repository configuration for CentOS, RHEL, or Fedora.

```console
$ sudo yum update
$ sudo yum install docker-compose-plugin
```


--------------------------------

### Start stack with docker compose up and verify health status

Source: https://github.com/docker/docs/blob/main/content/manuals/compose/gettingstarted.md

Starts the Compose stack to confirm container startup ordering and verify that the redis container reports a healthy status.

```console
$ docker compose up
```

```text
[+] Running 2/2
✔ Container compose-demo-redis-1  Healthy                       0.0s
```


--------------------------------

### Create a new builder using docker buildx create

Source: https://github.com/docker/docs/blob/main/content/manuals/build/builders/manage.md

Creates a new builder instance. Buildx defaults to using the docker-container driver if the --driver flag is omitted.

```console
$ docker buildx create --name=<builder-name>
```
