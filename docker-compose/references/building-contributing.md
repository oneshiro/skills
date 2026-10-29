# Docker Compose — Building & Contributing

Sourced snippets (17 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Define multi-container services in compose.yaml

Source: https://github.com/docker/compose/blob/main/README.md

Example Compose configuration file defining web and redis services. Run docker compose up to create and run the application services together.

```yaml
services:
  web:
    build: .
    ports:
      - "5000:5000"
    volumes:
      - .:/code
  redis:
    image: redis
```


--------------------------------

### Run unit tests with make

Source: https://github.com/docker/compose/blob/main/BUILDING.md

Runs the full suite of unit tests for Docker Compose.

```console
make test
```


--------------------------------

### Build the relay image using Docker Buildx Bake

Source: https://github.com/docker/compose/blob/main/relay/README.md

Builds the static Go binary and scratch container image for compose-relay.

```console
$ docker buildx bake relay-image
```


--------------------------------

### Build CLI and run complete end-to-end test suite

Source: https://github.com/docker/compose/blob/main/BUILDING.md

Builds the Compose CLI binary before running both CLI and standalone e2e tests. Requires a running local Docker Engine.

```console
make build-and-e2e
```


--------------------------------

### Build CLI and run plugin end-to-end test suite

Source: https://github.com/docker/compose/blob/main/BUILDING.md

Builds the Compose CLI before executing the CLI plugin e2e tests. Requires a running local Docker Engine.

```console
make build-and-e2e-compose
```


--------------------------------

### Run complete end-to-end test suite

Source: https://github.com/docker/compose/blob/main/BUILDING.md

Executes both CLI and standalone e2e tests against an existing build. Requires a running local Docker Engine.

```console
make e2e
```


--------------------------------

### Build Docker Compose CLI plugin

Source: https://github.com/docker/compose/blob/main/BUILDING.md

Builds the docker-compose CLI plugin for the host machine into ./bin/build.

```console
make
```


--------------------------------

### Run plugin end-to-end test suite

Source: https://github.com/docker/compose/blob/main/BUILDING.md

Executes the CLI plugin e2e tests. Requires a running local Docker Engine.

```console
make e2e-compose
```


--------------------------------

### Define E2E Scenario and Compose Fixture with NewScenario

Source: https://github.com/docker/compose/blob/main/pkg/e2e/SCENARIO.md

Demonstrates pairing a standalone testdata/TestRestart/compose.yaml fixture with a Go scenario test using NewScenario. Each scenario locks a single behavior intent and runs ordered steps with command actions and state assertions.

```yaml
# testdata/TestRestart/compose.yaml
services:
  app:
    image: alpine
    init: true
    command: ash -c "if [[ -f /tmp/restart.lock ]] ; then sleep infinity; else touch /tmp/restart.lock; fi"
```

```go
func TestRestart(t *testing.T) {
	NewScenario(t, "restart must bring an exited service back up, restarting the same container").
		Step("up starts the service, whose first run exits at once",
			ComposeCmd("up", "-d"),
			Eventually(ServiceState("app", "exited"), 10*time.Second)).
		Step("restart brings the service back up, reusing the container",
			ComposeCmd("restart"),
			Eventually(ServiceState("app", "running"), 10*time.Second),
			NotRecreated("app"))
}
```


--------------------------------

### Build CLI and run standalone end-to-end test suite

Source: https://github.com/docker/compose/blob/main/BUILDING.md

Builds the Compose CLI before executing the standalone CLI e2e tests. Requires a running local Docker Engine.

```console
make build-and-e2e-compose-standalone
```


--------------------------------

### Run standalone end-to-end test suite

Source: https://github.com/docker/compose/blob/main/BUILDING.md

Executes the standalone CLI e2e test suite. Requires a running local Docker Engine.

```console
make e2e-compose-standalone
```


--------------------------------

### Configure a service with an external provider in Compose

Source: https://github.com/docker/compose/blob/main/relay/README.md

Delegates a service implementation to an external provider in a Compose configuration. Dependent services like web reference the provider service by name while the external resource resides outside the network.

```yaml
services:
  web:
    build: .
    depends_on:
      - database

  database:
    provider:
      type: awesomecloud
```


--------------------------------

### Specify relay routes using RELAY_ROUTES environment variable

Source: https://github.com/docker/compose/blob/main/relay/README.md

Defines the route mappings passed to the relay container via environment variables. The binary listens on each declared container port and forwards connections to the corresponding host address and port.

```text
RELAY_ROUTES=5432=localhost:49152[,<port>=<host>:<port>...]
```


--------------------------------

### Review Developer Certificate of Origin (DCO) 1.1

Source: https://github.com/docker/compose/blob/main/CONTRIBUTING.md

Certify patch ownership and open-source contribution rights under the Developer Certificate of Origin version 1.1 before signing off on commits.

```text
Developer Certificate of Origin
Version 1.1

Copyright (C) 2004, 2006 The Linux Foundation and its contributors.
660 York Street, Suite 102,
San Francisco, CA 94110 USA

Everyone is permitted to copy and distribute verbatim copies of this
license document, but changing it is not allowed.

Developer's Certificate of Origin 1.1

By making a contribution to this project, I certify that:

(a) The contribution was created in whole or in part by me and I
    have the right to submit it under the open source license
    indicated in the file; or

(b) The contribution is based upon previous work that, to the best
    of my knowledge, is covered under an appropriate open source
    license and I have the right under that license to submit that
    work with modifications, whether created in whole or in part
    by me, under the same open source license (unless I am
    permitted to submit under a different license), as indicated
    in the file; or

(c) The contribution was provided directly to me by some other
    person who certified (a), (b) or (c) and I have not modified
    it.

(d) I understand and agree that this project and the contribution
    are public and that a record of the contribution (including all
    personal information I submit with it, including my sign-off) is
    maintained indefinitely and may be redistributed consistent with
    this project or the open source license(s) involved.
```


--------------------------------

### Create a collapsible Markdown details section

Source: https://github.com/docker/compose/blob/main/AI_POLICY.md

Use collapsible sections in issue and PR descriptions to store extensive logs, reasoning, or alternatives without cluttering the main summary.

```markdown
<details>
<summary>Details</summary>

...supporting detail here...

</details>
```


--------------------------------

### Publish endpoint mapping from an external provider

Source: https://github.com/docker/compose/blob/main/relay/README.md

Declares where an external provider endpoint listens by emitting a publish-endpoint message per port. Compose uses this mapping to deploy a relay container and forward traffic from the container port to the host endpoint.

```json
{ "type": "publish-endpoint", "message": "5432=localhost:49152" }
```


--------------------------------

### Add Signed-off-by trailer to Git commit messages

Source: https://github.com/docker/compose/blob/main/CONTRIBUTING.md

Append a sign-off line with your real name and email address to the end of every commit message. Alternatively, sign commits automatically using the git commit -s command when user.name and user.email are set.

```text
Signed-off-by: Joe Smith <joe.smith@email.com>
```
