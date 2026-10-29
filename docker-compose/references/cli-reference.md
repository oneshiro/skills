# Docker Compose — CLI Reference

Sourced snippets (31 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Define services in compose.yaml

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_pull.md

Defines example services in compose.yaml, including an image-based database service and a buildable web application service.

```yaml
services:
  db:
    image: postgres
  web:
    build: .
    command: bundle exec rails s -p 3000 -b '0.0.0.0'
    volumes:
      - .:/myapp
    ports:
      - "3000:3000"
    depends_on:
      - db
```


--------------------------------

### Run a one-time command in a service container

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_run.md

Starts the web service and executes bash inside a new container. The command overrides the command defined in the service configuration.

```console
$ docker compose run web bash
```


--------------------------------

### Run a command without starting linked dependencies using --no-deps

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_run.md

Executes the command in the web service container without automatically starting any linked dependency containers.

```console
$ docker compose run --no-deps web python manage.py shell
```


--------------------------------

### Run an interactive command against a linked service container

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_run.md

Opens an interactive PostgreSQL shell in the db container. Automatically checks and starts any stopped linked services before running.

```console
$ docker compose run db psql -h db -U docker
```


--------------------------------

### Manage containers by project name using `-p`

Source: https://github.com/docker/compose/blob/main/docs/reference/compose.md

Use the `-p` flag to specify a custom project name when listing containers or viewing logs. Project names must contain only lowercase letters, decimal digits, dashes, and underscores, and must start with a lowercase letter or decimal digit.

```console
$ docker compose -p my_project ps -a
NAME                 SERVICE    STATUS     PORTS
my_project_demo_1    demo       running

$ docker compose -p my_project logs
demo_1  | PING localhost (127.0.0.1): 56 data bytes
demo_1  | 64 bytes from 127.0.0.1: seq=0 ttl=64 time=0.095 ms
```


--------------------------------

### Pull service image with docker compose pull

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_pull.md

Pulls the image associated with a specific service defined in compose.yaml from the current directory without starting the container.

```console
$ docker compose pull db
[+] Running 1/15
 ⠸ db Pulling                                                             12.4s
   ⠿ 45b42c59be33 Already exists                                           0.0s
   ⠹ 40adec129f1a Downloading  3.374MB/4.178MB                             9.3s
   ⠹ b4c431d00c78 Download complete                                        9.3s
   ⠹ 2696974e2815 Download complete                                        9.3s
   ⠹ 564b77596399 Downloading  5.622MB/7.965MB                             9.3s
   ⠹ 5044045cf6f2 Downloading  216.7kB/391.1kB                             9.3s
   ⠹ d736e67e6ac3 Waiting                                                  9.3s
   ⠹ 390c1c9a5ae4 Waiting                                                  9.3s
   ⠹ c0e62f172284 Waiting                                                  9.3s
   ⠹ ebcdc659c5bf Waiting                                                  9.3s
   ⠹ 29be22cb3acc Waiting                                                  9.3s
   ⠹ f63c47038e66 Waiting                                                  9.3s
   ⠹ 77a0c198cde5 Waiting                                                  9.3s
   ⠹ c8752d5b785c Waiting                                                  9.3s
```


--------------------------------

### Run a command with manual port mappings using --publish and -p

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_run.md

Manually maps container ports to host ports using --publish and -p options when executing a one-time command.

```console
$ docker compose run --publish 8080:80 -p 2022:22 -p 127.0.0.1:2021:21 web python manage.py shell
```


--------------------------------

### Inspect failed pre_start hook containers with docker ps and docker logs

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_up.md

Lists and inspects containers from failed pre_start lifecycle hooks. Compose retains these containers until the next compose up or compose down cleans them up.

```console
$ docker ps -a --filter label=com.docker.compose.hook=pre_start
$ docker logs <container-id>
```


--------------------------------

### Specify and merge multiple Compose files using -f

Source: https://github.com/docker/compose/blob/main/docs/reference/compose.md

Supplies multiple configuration files where subsequent files override matching fields and append new fields to preceding configurations. All relative paths resolve relative to the first configuration file specified with -f unless overridden by --project-directory.

```console
$ docker compose -f compose.yaml -f compose.admin.yaml run backup_db
```

```yaml
services:
  webapp:
    image: examples/web
    ports:
      - "8000:8000"
    volumes:
      - "/data"
```

```yaml
services:
  webapp:
    build: .
    environment:
      - DEBUG=1
```


--------------------------------

### Preview stack execution steps with docker compose --dry-run

Source: https://github.com/docker/compose/blob/main/docs/reference/compose.md

Use the `--dry-run` flag to test commands without modifying application stack state. It displays all steps Docker Compose will apply during execution. It cannot be used on commands that do not change state (such as ps, ls, or logs).

```console
$ docker compose --dry-run up --build -d
[+] Pulling 1/1
 ✔ DRY-RUN MODE -  db Pulled                                                                                                                                                                                                               0.9s
[+] Running 10/8
 ✔ DRY-RUN MODE -    build service backend                                                                                                                                                                                                 0.0s
 ✔ DRY-RUN MODE -  ==> ==> writing image dryRun-754a08ddf8bcb1cf22f310f09206dd783d42f7dd                                                                                                                                                   0.0s
 ✔ DRY-RUN MODE -  ==> ==> naming to nginx-golang-mysql-backend                                                                                                                                                                            0.0s
 ✔ DRY-RUN MODE -  Network nginx-golang-mysql_default                                    Created                                                                                                                                           0.0s
 ✔ DRY-RUN MODE -  Container nginx-golang-mysql-db-1                                     Created                                                                                                                                           0.0s
 ✔ DRY-RUN MODE -  Container nginx-golang-mysql-backend-1                                Created                                                                                                                                           0.0s
 ✔ DRY-RUN MODE -  Container nginx-golang-mysql-proxy-1                                  Created                                                                                                                                           0.0s
 ✔ DRY-RUN MODE -  Container nginx-golang-mysql-db-1                                     Healthy                                                                                                                                           0.5s
 ✔ DRY-RUN MODE -  Container nginx-golang-mysql-backend-1                                Started                                                                                                                                           0.0s
 ✔ DRY-RUN MODE -  Container nginx-golang-mysql-proxy-1                                  Started                                     Started
```


--------------------------------

### Run Compose file directly from an OCI registry

Source: https://github.com/docker/compose/blob/main/docs/reference/compose.md

Loads and runs a Compose configuration published as an OCI artifact using the oci:// prefix. Requires the artifact to contain a valid Compose file.

```console
$ docker compose -f oci://registry.example.com/my-compose-project:latest up
```


--------------------------------

### Format container list output as JSON Lines using --format json

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_ps.md

Outputs container information as one JSON object per line (JSON Lines), aligning with the output format of docker ps --format json.

```console
$ docker compose ps --format json
{"ID":"1553b0236cf4d2715845f053a4ee97042c4f9a2ef655731ee34f1f7940eaa41a","Name":"example-bar-1","Command":"/docker-entrypoint.sh nginx -g 'daemon off;'","Project":"example","Service":"bar","State":"exited","Health":"","ExitCode":0,"Publishers":null}
{"ID":"f02a4efaabb67416e1ff127d51c4b5578634a0ad5743bd65225ff7d1909a3fa0","Name":"example-foo-1","Command":"/docker-entrypoint.sh nginx -g 'daemon off;'","Project":"example","Service":"foo","State":"running","Health":"","ExitCode":0,"Publishers":[{"URL":"0.0.0.0","TargetPort":80,"PublishedPort":8080,"Protocol":"tcp"}]}
```


--------------------------------

### docker compose command syntax

Source: https://github.com/docker/compose/blob/main/docs/reference/compose.md

Syntax format for executing Docker Compose commands with options, subcommands, and arguments.

```text
docker compose [-f <arg>...] [options] [COMMAND] [ARGS...]
```


--------------------------------

### Format and pretty-print JSON container output with jq

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_ps.md

Pipes the JSON Lines output from docker compose ps into the jq utility to pretty-print each JSON object for easier readability and processing.

```console
$ docker compose ps --format json | jq .
{
  "ID": "1553b0236cf4d2715845f053a4ee97042c4f9a2ef655731ee34f1f7940eaa41a",
  "Name": "example-bar-1",
  "Command": "/docker-entrypoint.sh nginx -g 'daemon off;'",
  "Project": "example",
  "Service": "bar",
  "State": "exited",
  "Health": "",
  "ExitCode": 0,
  "Publishers": null
}
{
  "ID": "f02a4efaabb67416e1ff127d51c4b5578634a0ad5743bd65225ff7d1909a3fa0",
  "Name": "example-foo-1",
  "Command": "/docker-entrypoint.sh nginx -g 'daemon off;'",
  "Project": "example",
  "Service": "foo",
  "State": "running",
  "Health": "",
  "ExitCode": 0,
  "Publishers": [
    {
      "URL": "0.0.0.0",
      "TargetPort": 80,
      "PublishedPort": 8080,
      "Protocol": "tcp"
    }
  ]
}
```


--------------------------------

### Use Compose file from a Git repository over SSH

Source: https://github.com/docker/compose/blob/main/docs/reference/compose.md

Clones a remote Git repository using SSH authentication syntax to run Compose services.

```console
$ docker compose -f git@github.com:user/repo.git up
```


--------------------------------

### Run a command with service ports mapped using --service-ports

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_run.md

Creates and maps the service's configured ports to the host. By default, docker compose run does not create service ports to avoid collisions.

```console
$ docker compose run --service-ports web python manage.py shell
```


--------------------------------

### Display running processes with docker compose top

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_top.md

Displays the running processes across the containers managed by the Compose project.

```console
$ docker compose top
example_foo_1
UID    PID      PPID     C    STIME   TTY   TIME       CMD
root   142353   142331   2    15:33   ?     00:00:00   ping localhost -c 5
```


--------------------------------

### Combine a remote Git repository with a local Compose override file

Source: https://github.com/docker/compose/blob/main/docs/reference/compose.md

Merges a cloned Git repository Compose configuration with a local override YAML file.

```console
$ docker compose -f https://github.com/user/repo.git -f compose.override.yaml up
```


--------------------------------

### Use Compose file from a Git repository over HTTPS

Source: https://github.com/docker/compose/blob/main/docs/reference/compose.md

Clones a remote Git repository over HTTPS and executes commands using its Compose file.

```console
$ docker compose -f https://github.com/user/repo.git up
```


--------------------------------

### Run a command and remove the container on exit using --rm

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_run.md

Runs a one-time command and automatically removes the container upon completion. Overrides any restart policy defined in the service configuration.

```console
$ docker compose run --rm web python manage.py db upgrade
```


--------------------------------

### List retained pre-start hook containers

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_down.md

Lists containers retained after a failed pre_start lifecycle hook prior to running down. Compose automatically removes these hook containers during teardown.

```console
$ docker ps -a --filter label=com.docker.compose.hook=pre_start
```


--------------------------------

### Configure Compose services with target image registries

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_push.md

Specifies custom image names for services to push locally built images to either a local registry or Docker Hub.

```yaml
services:
  service1:
    build: .
    image: localhost:5000/yourimage  ## goes to local registry

  service2:
    build: .
    image: your-dockerid/yourimage  ## goes to your repository on Docker Hub
```


--------------------------------

### JSON event output format with --json

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_events.md

Demonstrates the single-line JSON object structure emitted for project container events when running docker compose events with the --json flag.

```json
{
    "time": "2015-11-20T18:01:03.615550",
    "type": "container",
    "action": "create",
    "id": "213cf7...5fc39a",
    "service": "web",
    "attributes": {
      "name": "application_web_1",
      "image": "alpine:edge"
    }
}
```


--------------------------------

### Specify path to a single Compose file using -f

Source: https://github.com/docker/compose/blob/main/docs/reference/compose.md

Points to a Compose configuration file located in an arbitrary directory when running CLI commands. Executes operations against the specified file without navigating into its parent directory.

```console
$ docker compose -f ~/sandbox/rails/compose.yaml pull db
```


--------------------------------

### Filter containers by status using --status

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_ps.md

Filters the list of containers based on their current execution status, such as running or exited.

```console
$ docker compose ps --status=running
NAME            IMAGE     COMMAND           SERVICE    CREATED         STATUS          PORTS
example-foo-1   alpine    "/entrypoint.…"   foo        4 seconds ago   Up 2 seconds    0.0.0.0:8080->80/tcp

$ docker compose ps --status=exited
NAME            IMAGE     COMMAND           SERVICE    CREATED         STATUS          PORTS
example-bar-1   alpine    "/entrypoint.…"   bar        4 seconds ago   exited (0)
```


--------------------------------

### Combine an OCI artifact with a local Compose override file

Source: https://github.com/docker/compose/blob/main/docs/reference/compose.md

Merges a remote OCI artifact Compose definition with a local override file using multiple -f flags.

```console
$ docker compose -f oci://registry.example.com/my-compose-project:v1.0 -f compose.override.yaml up
```


--------------------------------

### Specify a subdirectory path within a Git repository with -f

Source: https://github.com/docker/compose/blob/main/docs/reference/compose.md

Targets a Compose file located inside a subdirectory of a Git repository using the #branch:path syntax.

```console
$ docker compose -f https://github.com/user/repo.git#main:path/to/compose.yaml up
```


--------------------------------

### Specify a Git branch, tag, or commit ref with -f

Source: https://github.com/docker/compose/blob/main/docs/reference/compose.md

Targets specific Git branches, tags, or commit hashes using the @ref syntax in the repository URL.

```console
$ docker compose -f https://github.com/user/repo.git@main up
$ docker compose -f https://github.com/user/repo.git@v1.0.0 up
$ docker compose -f https://github.com/user/repo.git@abc123 up
```


--------------------------------

### Filter containers by status using --filter status=<status>

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_ps.md

Filters containers using the explicit filter key-value syntax. The --filter status=<status> option provides the underlying filter capability that --status aliases.

```console
$ docker compose ps --filter status=running
NAME            IMAGE     COMMAND           SERVICE    CREATED         STATUS          PORTS
example-foo-1   alpine    "/entrypoint.…"   foo        4 seconds ago   Up 2 seconds    0.0.0.0:8080->80/tcp
```


--------------------------------

### Send a custom signal with docker compose kill

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_kill.md

Sends a custom signal such as SIGINT to force running containers to stop instead of using the default SIGKILL.

```console
$ docker compose kill -s SIGINT
```


--------------------------------

### Remove stopped containers with docker compose rm

Source: https://github.com/docker/compose/blob/main/docs/reference/compose_rm.md

Runs docker compose rm without options to remove stopped containers and one-off containers created by docker compose run. Prompts for confirmation before proceeding with container removal.

```console
$ docker compose rm
Going to remove djangoquickstart_web_run_1
Are you sure? [yN] y
Removing djangoquickstart_web_run_1 ... done
```
