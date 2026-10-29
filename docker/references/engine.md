# Docker — Engine

Sourced snippets (49 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Install docker-ce-rootless-extras via apt-get

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/security/rootless/_index.md

Installs the rootless setup extras package manually if dockerd-rootless-setuptool.sh is missing.

```console
$ sudo apt-get install -y docker-ce-rootless-extras
```


--------------------------------

### Start rootless daemon with systemctl

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/security/rootless/tips.md

Starts the rootless Docker systemd user service. Use this when rootless Docker was installed with systemd support.

```console
$ systemctl --user start docker

```


--------------------------------

### Install Docker Engine from RPM package with dnf

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/install/fedora.md

Installs a manually downloaded Docker RPM package. Docker is installed but not started, and the docker group is created without users added.

```console
$ sudo dnf install /path/to/package.rpm
```


--------------------------------

### Set up rootless Docker using dockerd-rootless-setuptool.sh

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/security/rootless/_index.md

Runs the rootless setup tool as a non-root user when Docker is installed via RPM/DEB packages. Configures the systemd user service and sets the CLI context to rootless.

```console
$ dockerd-rootless-setuptool.sh install
[INFO] Creating /home/testuser/.config/systemd/user/docker.service
...
[INFO] Installed docker.service successfully.
[INFO] To control docker.service, run: `systemctl --user (start|stop|restart) docker.service`
[INFO] To run docker.service on system startup, run: `sudo loginctl enable-linger testuser`

[INFO] Creating CLI context "rootless"
Successfully created context "rootless"
[INFO] Using CLI context "rootless"
Current context is now "rootless"

[INFO] Make sure the following environment variable(s) are set (or add them to ~/.bashrc):
export PATH=/usr/bin:$PATH

[INFO] Some applications may require the following environment variable too:
export DOCKER_HOST=unix:///run/user/1000/docker.sock
```


--------------------------------

### Verify Docker installation with hello-world container

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/install/binaries.md

Downloads and runs the test image hello-world:nanoserver to verify that Docker is installed correctly.

```powershell
PS C:\> &$Env:ProgramFiles\Docker\docker run hello-world:nanoserver
```


--------------------------------

### Install apparmor package using apt-get

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/release-notes/23.0.md

Installs the apparmor package on Debian systems as a manual workaround for containers failing to start due to missing apparmor_parser.

```console
apt-get install apparmor
```


--------------------------------

### Populate a volume using container contents

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/storage/volumes.md

Starts an nginx container and copies files from /usr/share/nginx/html into the new nginx-vol volume. Provides interchangeable examples using --mount and -v syntax.

```console
$ docker run -d \
  --name=nginxtest \
  --mount source=nginx-vol,destination=/usr/share/nginx/html \
  nginx:latest
```

```console
$ docker run -d \
  --name=nginxtest \
  -v nginx-vol:/usr/share/nginx/html \
  nginx:latest
```


--------------------------------

### Install rootless Docker via installation script

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/security/rootless/_index.md

Downloads and executes the rootless installer script when package manager permissions are unavailable. Installs binaries to ~/bin; note that static packages are not supported on s390x.

```console
$ curl -fsSL https://get.docker.com/rootless | sh
...
[INFO] Creating /home/testuser/.config/systemd/user/docker.service
...
[INFO] Installed docker.service successfully.
[INFO] To control docker.service, run: `systemctl --user (start|stop|restart) docker.service`
[INFO] To run docker.service on system startup, run: `sudo loginctl enable-linger testuser`

[INFO] Creating CLI context "rootless"
Successfully created context "rootless"
[INFO] Using CLI context "rootless"
Current context is now "rootless"

[INFO] Make sure the following environment variable(s) are set (or add them to ~/.bashrc):
export PATH=/home/testuser/bin:$PATH

[INFO] Some applications may require the following environment variable too:
export DOCKER_HOST=unix:///run/user/1000/docker.sock
```


--------------------------------

### Install and configure lxc-user-nic helper

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/security/rootless/troubleshoot.md

Installs LXC and configures /etc/lxc/lxc-usernet to enable privileged networking helper for the current user.

```bash
sudo apt-get install -y lxc
sudo mkdir -p /etc/lxc
cat <<EOF | sudo tee /etc/lxc/lxc-usernet
# USERNAME TYPE BRIDGE COUNT
$USER veth lxcbr0 10
EOF
```


--------------------------------

### Start the Docker daemon

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/storage/drivers/overlayfs-driver.md

Start Docker to apply changes made to /etc/docker/daemon.json.

```console
$ sudo systemctl start docker
```


--------------------------------

### Enable and start Docker systemd service

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/install/fedora.md

Configures the Docker service to start immediately and automatically at boot time. Use 'sudo systemctl start docker' instead if automatic boot startup is not desired.

```console
$ sudo systemctl enable --now docker
```


--------------------------------

### Start container with specific logging driver using --log-driver

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/logging/configure.md

Overrides the default Docker daemon logging driver for a new container. In this example, logging is disabled by setting the driver to none.

```console
$ docker run -it --log-driver none alpine ash
```


--------------------------------

### Start container with a bind mount using --mount

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/storage/bind-mounts.md

Binds the host target/ directory to /app in the container using the --mount parameter. Run this command from within the source directory so $(pwd) resolves properly.

```console
$ docker run -d \
  -it \
  --name devtest \
  --mount type=bind,source="$(pwd)"/target,target=/app \
  nginx:latest
```


--------------------------------

### Start Notary Server with Docker Compose

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/security/trust/deploying_notary.md

Builds and starts the Notary Server in the background using sample certificates for local testing.

```console
$ docker compose up -d 
```


--------------------------------

### Verify installation using hello-world container

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/install/binaries.md

Downloads and executes the hello-world test image to verify Docker is working properly. The container prints a confirmation message and terminates.

```console
$ sudo docker run hello-world
```


--------------------------------

### Install rclone volume plugin with docker plugin install

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/storage/volumes.md

Installs the rclone/docker-volume-rclone plugin on the Docker host with all permissions granted and an alias set to rclone.

```console
$ docker plugin install --grant-all-permissions rclone/docker-volume-rclone --aliases rclone
```


--------------------------------

### Run container and create volume using --mount and rclone driver

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/storage/volumes.md

Starts a container and creates the rclone volume on the fly with driver options specified directly in the --mount flag.

```console
$ docker run -d \
  --name rclone-container \
  --mount type=volume,volume-driver=rclone,src=rclonevolume,target=/app,volume-opt=type=sftp,volume-opt=path=remote, volume-opt=sftp-host=1.2.3.4,volume-opt=sftp-user=user,volume-opt=-o "sftp-password=$(cat file_containing_password_for_remote_host)" \
  nginx:latest
```


--------------------------------

### Register and start Docker service on Windows

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/install/binaries.md

Registers dockerd as a Windows service and starts the Docker Engine.

```powershell
PS C:\> &$Env:ProgramFiles\Docker\dockerd --register-service
PS C:\> Start-Service docker
```


--------------------------------

### Set up Docker apt repository

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/install/ubuntu.md

Adds Docker's official GPG key and configures the apt sources repository list for Ubuntu before updating the package index.

```bash
# Add Docker's official GPG key:
sudo apt update
sudo apt install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL {{% param "download-url-base" %}}/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: {{% param "download-url-base" %}}
Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
Components: stable
Architectures: $(dpkg --print-architecture)
Signed-By: /etc/apt/keyrings/docker.asc
EOF

sudo apt update
```


--------------------------------

### Start container with a bind mount using -v

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/storage/bind-mounts.md

Binds the host target/ directory to /app in the container using the -v shorthand flag. Produces the same mount configuration as the --mount option.

```console
$ docker run -d \
  -it \
  --name devtest \
  -v "$(pwd)"/target:/app \
  nginx:latest
```


--------------------------------

### Run hello-world on a remote Docker daemon

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/install/binaries.md

Verifies the Docker client installation by connecting to an accessible remote Docker daemon at `<hostname>` and running the `hello-world` container.

```console
$ sudo docker -H <hostname> run hello-world
```


--------------------------------

### Start Docker Compose services

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/cli/otel.md

Starts the configured OpenTelemetry and Prometheus services defined in the Compose file.

```console
$ docker compose up
```


--------------------------------

### Install ca-certificates inside container using apt-get

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/network/ca-certs.md

Ensures the ca-certificates package is installed inside the Ubuntu-based container.

```console
# apt-get update && apt-get install -y ca-certificates
```


--------------------------------

### Demonstrate missing source path error with --mount

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/storage/bind-mounts.md

Attempting to bind-mount a non-existent host path with `--mount` fails with an error by default rather than creating the host directory.

```console
$ docker run --mount type=bind,src=/dev/noexist,dst=/mnt/foo alpine
docker: Error response from daemon: invalid mount config for type "bind": bind source path does not exist: /dev/noexist.
```


--------------------------------

### Start dockerd with --feature embedded-containerd

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/daemon/embedded-containerd.md

Enables the embedded containerd feature when starting dockerd manually from the command line.

```console
$ sudo dockerd --feature embedded-containerd
```


--------------------------------

### Remove Rootless Docker binaries from ~/bin

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/security/rootless/troubleshoot.md

Deletes installed Docker binaries under ~/bin when Docker was installed without package managers.

```console
$ cd ~/bin
$ rm -f containerd containerd-shim containerd-shim-runc-v2 ctr docker docker-init docker-proxy dockerd dockerd-rootless-setuptool.sh dockerd-rootless.sh rootlesskit rootlesskit-docker-proxy runc vpnkit
```


--------------------------------

### Install latest Docker Engine packages

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/install/ubuntu.md

Installs the latest release of Docker Engine, CLI, containerd, Buildx, and Compose plugins.

```console
$ sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```


--------------------------------

### Install bash-completion package

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/cli/completion.md

Installs the bash-completion package needed for Docker CLI completion functions across different package managers.

```bash
# Install using APT:
sudo apt install bash-completion

# Install using Homebrew (Bash version 4 or later):
brew install bash-completion@2
# Homebrew install for older versions of Bash:
brew install bash-completion

# With pacman:
sudo pacman -S bash-completion
```


--------------------------------

### Start containers on the default bridge network

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/network/drivers/bridge.md

Starts two detached, interactive Alpine containers connected by default to the bridge network.

```console
$ docker run -dit --name alpine1 alpine ash
$ docker run -dit --name alpine2 alpine ash
```


--------------------------------

### Start Docker daemon using systemctl

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/daemon/start.md

Starts the Docker daemon service on operating systems using systemd, such as Ubuntu and Debian.

```console
$ sudo systemctl start docker
```


--------------------------------

### Create IPvLAN network with custom-named 802.1Q sub-interface

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/network/drivers/ipvlan.md

Demonstrates creating an 802.1Q sub-interface with an arbitrary name (`foo`) and referencing it with `-o parent=foo`. Non-standard interface names are honored as long as the interface exists and is up before network creation.

```console
# create a new sub interface tied to dot1q vlan 40
$ ip link add link eth0 name foo type vlan id 40

# enable the new sub-interface
$ ip link set foo up

# now add networks and hosts as you would normally by attaching to the master (sub)interface that is tagged
$ docker network create -d ipvlan \
    --subnet=192.168.40.0/24 --gateway=192.168.40.1 \
    -o parent=foo ipvlan40

# in two separate terminals, start a Docker container and the containers can now ping one another.
$ docker run --net=ipvlan40 -it --name ivlan_test5 --rm alpine /bin/sh
$ docker run --net=ipvlan40 -it --name ivlan_test6 --rm alpine /bin/sh
```


--------------------------------

### Install specific version of Docker Engine

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/install/ubuntu.md

Lists available versions of docker-ce in the repository, assigns the target version to VERSION_STRING, and installs the matching packages.

```console
$ apt list --all-versions docker-ce

docker-ce/noble 5:{{% param "docker_ce_version" %}}-1~ubuntu.24.04~noble <arch>
docker-ce/noble 5:{{% param "docker_ce_version_prev" %}}-1~ubuntu.24.04~noble <arch>
...
```

```console
$ VERSION_STRING=5:{{% param "docker_ce_version" %}}-1~ubuntu.24.04~noble
$ sudo apt install docker-ce=$VERSION_STRING docker-ce-cli=$VERSION_STRING containerd.io docker-buildx-plugin docker-compose-plugin
```


--------------------------------

### Start Docker daemon in background

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/install/binaries.md

Starts the dockerd daemon process in the background. Custom configuration options can be passed as CLI arguments or configured in /etc/docker/daemon.json.

```console
$ sudo dockerd &
```


--------------------------------

### Create project directory for stack demo

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/swarm/stack-deploy.md

Creates and enters a new directory named stackdemo for the sample application files.

```console
$ mkdir stackdemo
$ cd stackdemo
```


--------------------------------

### Create a named database container

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/network/links.md

Starts a detached PostgreSQL container named db from the training/postgres image.

```console
$ docker run -d --name db training/postgres
```


--------------------------------

### Display dockerd help options

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/daemon/_index.md

Displays all available command-line flags and configuration options for the Docker daemon.

```console
$ dockerd --help
```


--------------------------------

### Build image with docker build

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/containers/start-containers-automatically.md

Builds the container image tagged as `startstop` from the Dockerfile in the current directory.

```console
$ docker build -t startstop .
```


--------------------------------

### Example ETW event message

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/logging/drivers/etwlogs.md

Shows an example of a formatted event message generated by the etwlogs logging driver, containing container metadata and the log message.

```yaml
container_name: backstabbing_spence,
image_name: windowsservercore,
container_id: f14bb55aa862d7596b03a33251c1be7dbbec8056bbdead1da8ec5ecebbe29731,
image_id: sha256:2f9e19bd998d3565b4f345ac9aaf6e3fc555406239a4fb1b1ba879673713824b,
source: stdout,
log: Hello world!
```


--------------------------------

### Configure client using docker context use

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/security/rootless/tips.md

Switches the active CLI context to rootless, directing subsequent docker commands to the rootless daemon instance.

```console
$ docker context use rootless
rootless
Current context is now "rootless"
$ docker run -d -p 8080:80 nginx

```


--------------------------------

### Back up a container volume using --volumes-from

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/storage/volumes.md

Creates a container with a data volume and then launches an ephemeral container to tar the volume contents into a host-mounted backup directory. When the second container stops, the tar archive is preserved on the host.

```console
$ docker run -v /dbdata --name dbstore ubuntu /bin/bash
```

```console
$ docker run --rm --volumes-from dbstore -v $(pwd):/backup ubuntu tar cvf /backup/backup.tar /dbdata
```


--------------------------------

### Install or update docker-scan-plugin on Debian and Ubuntu

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/release-notes/20.10.md

Updates repository package lists and installs or upgrades the docker-scan-plugin on .deb-based distributions. On Linux, docker scan is supported only on x86 architectures.

```console
$ apt-get update && apt-get install docker-scan-plugin
```


--------------------------------

### Initiate repository and add initial signer with docker trust signer add

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/security/trust/trust_delegation.md

Uploads the first delegation key and initiates trust data for the repository. Requires entering the passphrase for the local Notary Canonical Root Key and setting a new repository key passphrase.

```console
$ docker trust signer add --key cert.pem jeff registry.example.com/admin/demo

Adding signer "jeff" to registry.example.com/admin/demo...
Initializing signed repository for registry.example.com/admin/demo...
Enter passphrase for root key with ID f6c6a4b: 
Enter passphrase for new repository key with ID b0014f8: 
Repeat passphrase for new repository key with ID b0014f8: 
Successfully initialized "registry.example.com/admin/demo"
Successfully added signer: jeff to registry.example.com/admin/demo
```


--------------------------------

### Identify missing apparmor_parser error on container start

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/release-notes/23.0.md

Displays the daemon error message that occurs on Debian systems when containers fail to start because the apparmor_parser executable is missing from PATH.

```console
Error response from daemon: AppArmor enabled on system but the docker-default profile could not be loaded: running `apparmor_parser apparmor_parser --version` failed with output:
error: exec: "apparmor_parser": executable file not found in $PATH
Error: failed to start containers: somecontainer
```


--------------------------------

### Run container with specified IPv6 address and check dual-stack routes

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/network/drivers/ipvlan.md

Start a container assigned to the dual-stack IPvlan network with an explicit IPv6 address, then inspect the interface and both IPv4 and IPv6 routing tables.

```console
$ docker run --net=ipvlan140 --ip6=2001:db8:abc2::51 -it --rm alpine /bin/sh

$ ip a show eth0
78: eth0@if77: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UNKNOWN group default
    link/ether 00:50:56:2b:29:40 brd ff:ff:ff:ff:ff:ff
    inet 192.168.140.2/24 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 2001:db8:abc4::250:56ff:fe2b:2940/64 scope link
       valid_lft forever preferred_lft forever
    inet6 2001:db8:abc9::1/64 scope link nodad
       valid_lft forever preferred_lft forever

$$ ip route
default via 192.168.140.1 dev eth0
192.168.140.0/24 dev eth0  proto kernel  scope link  src 192.168.140.2

$$ ip -6 route
2001:db8:abc4::/64 dev eth0  proto kernel  metric 256
2001:db8:abc9::/64 dev eth0  proto kernel  metric 256
default via 2001:db8:abc9::22 dev eth0  metric 1024
```


--------------------------------

### Expose all available NVIDIA GPUs with --gpus all

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/containers/gpu.md

Run a container with access to all available host GPUs using the `--gpus all` flag and verify with `nvidia-smi`. Requires installed NVIDIA drivers and NVIDIA Container Toolkit.

```console
$ docker run -it --rm --gpus all ubuntu nvidia-smi
```

```text
+---------------------------------------------------------------------------------------+
| NVIDIA-SMI 535.288.01             Driver Version: 535.288.01   CUDA Version: 12.2     |
|-----------------------------------------+----------------------+----------------------+
| GPU  Name                 Persistence-M | Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp   Perf          Pwr:Usage/Cap |         Memory-Usage | GPU-Util  Compute M. |
|                                         |                      |               MIG M. |
|=========================================+======================+======================|
|   0  NVIDIA L4                      Off | 00000000:31:00.0 Off |                    0 |
| N/A   40C    P0              27W /  72W |      0MiB / 23034MiB |      4%      Default |
|                                         |                      |                  N/A |
+-----------------------------------------+----------------------+----------------------+

+---------------------------------------------------------------------------------------+
| Processes:                                                                            |
|  GPU   GI   CI        PID   Type   Process name                            GPU Memory |
|        ID   ID                                                             Usage      |
|=======================================================================================|
|  No running processes found                                                           |
+---------------------------------------------------------------------------------------+
```


--------------------------------

### Install or update docker-scan-plugin on CentOS or Fedora

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/release-notes/20.10.md

Installs or upgrades the docker-scan-plugin package on RPM-based Linux systems using yum. This allows updating docker scan independently of Docker Engine.

```console
$ yum install docker-scan-plugin
```


--------------------------------

### Create and enter trustsandbox directory

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/security/trust/trust_sandbox.md

Create a new directory named trustsandbox and change into it to begin configuring the sandbox environment.

```console
$ mkdir trustsandbox
$ cd trustsandbox
```


--------------------------------

### Start dockerd manually with flags

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/daemon/_index.md

Starts the Docker daemon manually with debug logging enabled, TLS certificates specified, and bound to a TCP host. Useful for troubleshooting daemon configurations.

```console
$ dockerd --debug \
  --tls=true \
  --tlscert=/var/docker/server.pem \
  --tlskey=/var/docker/serverkey.pem \
  --host tcp://192.168.59.3:2376
```


--------------------------------

### Create a basic single-replica service

Source: https://github.com/docker/docs/blob/main/content/manuals/engine/swarm/services.md

Starts an Nginx service on an available node with a randomly generated name and no published ports.

```console
$ docker service create nginx
```
