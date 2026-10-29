# Docker — Desktop

Sourced snippets (47 entries). Search this file for the topic;
treat snippets as patterns and reconcile with the installed version.

### Install Docker Desktop using Windows Command Prompt

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/windows-install.md

Executes the installer from the Windows Command Prompt using `start /w` to wait for the installer to finish. Includes syntax for both per-user and all-users installation modes.

```sh
# Per-user installation (no admin required)
start /w "" "Docker Desktop Installer.exe" install --user
 
# All-users installation (run as administrator)
start /w "" "Docker Desktop Installer.exe" install
```


--------------------------------

### Install Docker Desktop using PowerShell Start-Process

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/windows-install.md

Executes the installer in PowerShell using `Start-Process` with the `-Wait` parameter to block until installation completes. Includes commands for both per-user and all-users installation modes.

```powershell
# Per-user installation (no admin required)
Start-Process 'Docker Desktop Installer.exe' -Wait -ArgumentList 'install', '--user'
 
# All-users installation (run as administrator)
Start-Process 'Docker Desktop Installer.exe' -Wait install
```


--------------------------------

### Install interactively without verbose logging

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/msi-install-and-configure.md

Starts the standard interactive MSI installation of Docker Desktop with the graphical user interface. Requires administrator rights.

```powershell
msiexec /i "DockerDesktop.msi"
```


--------------------------------

### Run Docker Desktop installer in PowerShell using Start-Process

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/windows-install.md

Pass installer flags using the ArgumentList parameter when invoking the installer from PowerShell.

```powershell
Start-Process 'Docker Desktop Installer.exe' -Wait -ArgumentList 'install', '--accept-license'
```


--------------------------------

### Install Docker Desktop RPM package using DNF

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/linux/fedora.md

Installs the downloaded Docker Desktop RPM package into `/opt/docker-desktop` and executes post-installation setup scripts automatically.

```console
$ sudo dnf install ./docker-desktop-x86_64.rpm
```


--------------------------------

### Install Docker Desktop on Mac from the command line

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/mac-install.md

Mounts the downloaded Docker.dmg image, runs the installer binary to install Docker Desktop into /Applications/Docker.app, and unmounts the disk image. Note that macOS security checks may cause the install command to take several minutes.

```console
$ sudo hdiutil attach Docker.dmg
$ sudo /Volumes/Docker/Docker.app/Contents/MacOS/install
$ sudo hdiutil detach /Volumes/Docker
```


--------------------------------

### Install interactively with verbose logging

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/msi-install-and-configure.md

Launches the Docker Desktop MSI installer user interface while capturing detailed logs in a specified file. Requires administrator rights.

```powershell
msiexec /i "DockerDesktop.msi" /L*V ".\msi.log"
```


--------------------------------

### Uninstall non-interactively using product code

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/msi-install-and-configure.md

Uninstalls Docker Desktop quietly using the retrieved product code GUID when the original MSI installer file is missing.

```powershell
msiexec /x {10FC87E2-9145-4D7D-B493-2E99E8D8E103} /L*V ".\msi.log" /quiet
```


--------------------------------

### Install Docker Desktop package using pacman

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/linux/archlinux.md

Installs the Docker Desktop Arch package on the system. By default, the application is installed to `/opt/docker-desktop`.

```console
$ sudo pacman -U ./docker-desktop-x86_64.pkg.tar.zst
```


--------------------------------

### Install Docker Desktop for all users via CLI

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/windows-install.md

Installs Docker Desktop for all users on the system. This installation mode prompts for elevation and requires administrator privileges.

```console
$ "Docker Desktop Installer.exe" install
```


--------------------------------

### Initialize Node.js project directory

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/features/mcp-catalog-and-toolkit/e2b-sandboxes.md

Creates a new project directory named `mcp-e2b-quickstart`, navigates into it, and generates a default `package.json` file.

```console
$ mkdir mcp-e2b-quickstart
$ cd mcp-e2b-quickstart
$ npm init -y
```


--------------------------------

### Install Docker Desktop via macOS installer CLI

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/pkg-install-and-configure.md

Runs the macOS installer command line utility to deploy the downloaded Docker.pkg package to the /Applications directory with administrator privileges.

```console
$ sudo installer -pkg "/path/to/Docker.pkg" -target /Applications
```


--------------------------------

### Enable CRB/EPEL and install pass on RHEL 9

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/linux/rhel.md

Use these commands if pass is not installed or cannot be installed on RHEL 9. Enables CodeReady Linux Builder and EPEL repositories before installing pass.

```console
$ sudo subscription-manager repos --enable codeready-builder-for-rhel-9-$(arch)-rpms
$ sudo dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-9.noarch.rpm
$ sudo dnf install pass

```


--------------------------------

### Enable CRB/EPEL and install pass on RHEL 10

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/linux/rhel.md

Use these commands if pass is not installed or cannot be installed on RHEL 10. Enables CodeReady Linux Builder and EPEL repositories before installing pass.

```console
$ sudo subscription-manager repos --enable codeready-builder-for-rhel-10-$(arch)-rpms
$ sudo dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-10.noarch.rpm
$ sudo dnf install pass

```


--------------------------------

### All-users .exe installation blocking message

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/faq.md

Output displayed when the MSI installer stops due to detecting an existing all-users .exe installation.

```text
You need to uninstall the previous Docker Desktop version in order to use the MSI installer.

```


--------------------------------

### Install MSI and remove existing installation

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/faq.md

Set REMOVEEXISTINGINSTALL=1 during silent MSI installation to automatically uninstall the existing .exe version using --keep-data.

```powershell
msiexec /i "DockerDesktop.msi" /L*V ".\msi.log" /quiet /norestart REMOVEEXISTINGINSTALL=1

```


--------------------------------

### Example admin-settings.json file template

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/hardened-desktop/settings-management/configure-json-file.md

A sample admin-settings.json template showing configuration options across proxy settings, ECI, Kubernetes, virtual machine configurations, Docker Scout, inference, and file sharing permissions.

```json
{
  "configurationFileVersion": 2,
  "exposeDockerAPIOnTCP2375": {
    "locked": true,
    "value": false
  },
  "proxy": {
    "locked": true,
    "mode": "system",
    "http": "",
    "https": "",
    "exclude": [],
    "windowsDockerdPort": 65000,
    "enableKerberosNtlm": false,
    "pac": "",
    "embeddedPac": ""
  },
  "containersProxy": {
    "locked": true,
    "mode": "manual",
    "http": "",
    "https": "",
    "exclude": [],
    "pac": "",
    "embeddedPac": "",
    "transparentPorts": ""
  },
  "enhancedContainerIsolation": {
    "locked": true,
    "value": true,
    "dockerSocketMount": {
      "imageList": {
        "images": [
          "docker.io/localstack/localstack:*",
          "docker.io/testcontainers/ryuk:*"
        ]
      },
      "commandList": {
        "type": "deny",
        "commands": ["push"]
      }
    }
  },
  "linuxVM": {
    "wslEngineEnabled": {
      "locked": false,
      "value": false
    },
    "dockerDaemonOptions": {
      "locked": false,
      "value": "{\"debug\": false}"
    },
    "vpnkitCIDR": {
      "locked": false,
      "value": "192.168.65.0/24"
    }
  },
  "kubernetes": {
    "locked": false,
    "enabled": false,
    "showSystemContainers": false,
    "imagesRepository": ""
  },
  "windowsContainers": {
    "dockerDaemonOptions": {
      "locked": false,
      "value": "{\"debug\": false}"
    }
  },
  "disableUpdate": {
    "locked": false,
    "value": false
  },
  "analyticsEnabled": {
    "locked": false,
    "value": true
  },
  "extensionsEnabled": {
    "locked": true,
    "value": false
  },
  "scout": {
    "locked": false,
    "sbomIndexing": true,
    "useBackgroundIndexing": true
  },
  "allowBetaFeatures": {
    "locked": false,
    "value": false
  },
  "blockDockerLoad": {
    "locked": false,
    "value": true
  },
  "filesharingAllowedDirectories": [
    {
      "path": "$HOME",
      "sharedByDefault": true
    },
    {
      "path": "$TMP",
      "sharedByDefault": false
    }
  ],
  "useVirtualizationFrameworkVirtioFS": {
    "locked": true,
    "value": true
  },
  "useVirtualizationFrameworkRosetta": {
    "locked": true,
    "value": true
  },
  "useGrpcfuse": {
    "locked": true,
    "value": true
  },
  "displayedOnboarding": {
    "locked": true,
    "value": true
  },
  "desktopTerminalEnabled": {
    "locked": false,
    "value": false
  },
  "enableInference": {
    "locked": false,
    "value": true
  },
  "enableInferenceTCP": {
    "locked": false,
    "value": true
  },
  "enableInferenceTCPPort": {
    "locked": true,
    "value": 12434
  },
  "enableInferenceCORS": {
    "locked": true,
    "value": ""
  },
  "enableInferenceGPUVariant": {
    "locked": true,
    "value": true
  },
  "portBindingBehavior": {
    "locked": true,
    "value": "default-port-binding"
  }
}
```


--------------------------------

### Install with passive display option and reboot suppression

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/msi-install-and-configure.md

Runs a non-interactive installation displaying only a progress bar without prompts or error messages. Prevents cancellation during installation and suppresses reboots.

```powershell
msiexec /i "DockerDesktop.msi" /L*V ".\msi.log" /passive /norestart
```


--------------------------------

### Run emulated HID keyboard example

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/features/usbip.md

Runs the emulated Human Interface Device (HID) keyboard example using cargo.

```console
$ env RUST_LOG=info cargo run --example hid_keyboard
```


--------------------------------

### Run MSI installer with verbose logging

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/faq.md

Executes the MSI installer with verbose logging to debug failed installations. Check the generated log for 'value 3' to find failure reasons.

```powershell
msiexec /i "DockerDesktop.msi" /L*V ".\msi.log"

```


--------------------------------

### Reproduce system context MSI installation with PsExec

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/faq.md

Executes the Docker Desktop MSI installer under the system account context using PsExec to simulate MDM installations where the docker-users group is not populated.

```powershell
psexec -i -s msiexec /i "DockerDesktop.msi"
```


--------------------------------

### Uninstall older Docker Desktop .exe installations while keeping data

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/faq.md

Use the --keep-data flag to uninstall older .exe installations while preserving resources such as container VMs. Commands are provided for both all-user and per-user installations.

```powershell
# For all-user installations
& 'C:\Program Files\Docker\Docker\Docker Desktop Installer.exe' uninstall --keep-data

# For per-user installations
& '%LOCALAPPDATA%\Programs\DockerDesktop\Docker Desktop Installer.exe' uninstall --keep-data

```


--------------------------------

### Install Docker Desktop DEB package using apt

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/linux/ubuntu.md

Updates apt package lists and installs the downloaded Docker Desktop package. The unsandboxed root permission denied warning shown at the end of installation can be safely ignored.

```console
$ sudo apt-get update
$ sudo apt install ./docker-desktop-amd64.deb
```

```text
N: Download is performed unsandboxed as root, as file '/home/user/Downloads/docker-desktop.deb' couldn't be accessed by user '_apt'. - pkgAcquire::Run (13: Permission denied)
```


--------------------------------

### Install Docker Desktop for current user via CLI

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/windows-install.md

Performs a per-user installation of Docker Desktop to `%LOCALAPPDATA%\Programs\DockerDesktop`. This mode does not require administrator privileges.

```console
$ "Docker Desktop Installer.exe" install --user
```


--------------------------------

### Suppress reboot during MSI installation

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/faq.md

Uses the /norestart switch with msiexec to prevent the installer from prompting for a system reboot.

```powershell
msiexec /i "DockerDesktop.msi" /L*V ".\msi.log" /norestart

```


--------------------------------

### Install Docker client binary on Linux

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/linux/archlinux.md

Downloads and extracts the static Docker client binary, copies it to `/usr/local/bin/`, and removes the temporary directory.

```console
$ wget https://download.docker.com/linux/static/stable/x86_64/docker-{{% param "docker_ce_version" %}}.tgz -qO- | tar xvfz - docker/docker --strip-components=1
$ sudo cp -rp ./docker /usr/local/bin/ && rm -r ./docker
```


--------------------------------

### Upgrade Docker Desktop using dnf

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/linux/rhel.md

Remove the existing Docker Desktop installation and install the newly downloaded RPM package.

```console
$ sudo dnf remove docker-desktop
$ sudo dnf install ./docker-desktop-<arch>-rhel.rpm
```


--------------------------------

### Upgrade Docker Desktop using DNF

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/linux/fedora.md

Removes the currently installed version of Docker Desktop and installs the updated RPM package.

```console
$ sudo dnf remove docker-desktop
$ sudo dnf install ./docker-desktop-x86_64.rpm
```


--------------------------------

### Install gnome-terminal on non-GNOME environments

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/linux/fedora.md

Installs gnome-terminal to enable terminal access from Docker Desktop when using desktop environments other than GNOME.

```console
$ sudo dnf install gnome-terminal
```


--------------------------------

### Install and run evtest to test the USB device

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/features/usbip.md

Installs evtest inside Alpine and captures input events from the attached device.

```console
$ apk add evtest
$ evtest /dev/input/event0
```

```console
Input driver version is 1.0.1
Input device ID: bus 0x3 vendor 0x0 product 0x0 version 0x111
...
Properties:
Testing ... (interrupt to exit)
Event: time 1717575532.881540, type 4 (EV_MSC), code 4 (MSC_SCAN), value 7001e
Event: time 1717575532.881540, type 1 (EV_KEY), code 2 (KEY_1), value 1
Event: time 1717575532.881540, -------------- SYN_REPORT ------------
...
```


--------------------------------

### Upgrade Docker Desktop using apt

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/linux/ubuntu.md

Upgrades an existing Docker Desktop installation by installing the newly downloaded DEB package with apt.

```console
$ sudo apt install ./docker-desktop-amd64.deb
```


--------------------------------

### Install gnome-terminal for non-GNOME desktop environments

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/linux/rhel.md

Installs gnome-terminal to enable terminal access from Docker Desktop when running a desktop environment other than GNOME.

```console
$ sudo dnf install gnome-terminal

```


--------------------------------

### Install E2B and dotenv dependencies

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/features/mcp-catalog-and-toolkit/e2b-sandboxes.md

Installs the required `e2b` and `dotenv` npm packages for interacting with E2B sandboxes and loading environment variables.

```console
$ npm install e2b dotenv
```


--------------------------------

### Install non-interactively with admin settings

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/msi-install-and-configure.md

Performs a silent installation configuring ADMINSETTINGS as a JSON string and assigning ALLOWEDORG. Requires administrator rights.

```powershell
msiexec /i "DockerDesktop.msi" /L*V ".\msi.log" /quiet /norestart ADMINSETTINGS="{""configurationFileVersion"":2,""enhancedContainerIsolation"":{""value"":true,""locked"":false}}" ALLOWEDORG="your-organization"
```


--------------------------------

### Install Docker Desktop DEB package using apt

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/linux/debian.md

Updates apt package indexes and installs the downloaded Docker Desktop deb package.

```console
$ sudo apt-get update
$ sudo apt-get install ./docker-desktop-amd64.deb
```


--------------------------------

### Install non-interactively and suppress reboots

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/msi-install-and-configure.md

Runs a silent installation of Docker Desktop while suppressing any automatic system reboots with /norestart. Requires administrator rights.

```powershell
msiexec /i "DockerDesktop.msi" /L*V ".\msi.log" /quiet /norestart
```


--------------------------------

### Per-user .exe installation blocking message

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/faq.md

Output shown in Docker Desktop version 4.84 and later when an existing per-user .exe installation is detected.

```text
Docker Desktop is installed per-user for one or more accounts on this machine: <usernames>.
Please have each affected user uninstall Docker Desktop first before running the MSI installer.

```


--------------------------------

### Start privileged Docker container with host PID namespace

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/features/usbip.md

Starts an Alpine container with full access to the host and shared host process namespace.

```console
$ docker run --rm -it --privileged --pid=host alpine
```


--------------------------------

### Install Docker Model Runner with vLLM backend and CUDA GPU

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/features/gpu.md

Installs the Docker Model Runner configured with the vLLM backend and CUDA GPU acceleration.

```console
$ docker model install-runner --backend vllm --gpu cuda
```


--------------------------------

### Per-user MSI installation unsupported message

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/faq.md

Output message shown in Docker Desktop version 4.92 and later when attempting to install the MSI using MSIINSTALLPERUSER.

```text
Docker Desktop does not support per-user installation with the MSI installer.

```


--------------------------------

### Install non-interactively with verbose logging

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/msi-install-and-configure.md

Performs a silent installation of Docker Desktop using the /quiet flag while logging verbose output. Requires administrator rights.

```powershell
msiexec /i "DockerDesktop.msi" /L*V ".\msi.log" /quiet
```


--------------------------------

### Ignorable apt installation warning for local DEB package

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/linux/debian.md

Harmless permission warning displayed at the end of installation when apt handles a locally downloaded deb package.

```text
N: Download is performed unsandboxed as root, as file '/home/user/Downloads/docker-desktop.deb' couldn't be accessed by user '_apt'. - pkgAcquire::Run (13: Permission denied)
```


--------------------------------

### Verify MCP gateway connection output

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/features/mcp-catalog-and-toolkit/e2b-sandboxes.md

Displays the expected console output after executing the quickstart script to verify the E2B sandbox creation and MCP gateway connection.

```console
Creating E2B sandbox with Notion and GitHub MCP servers...

Sandbox created successfully!
MCP Gateway URL: https://50005-xxxxx.e2b.app/mcp

Connecting Claude to MCP gateway...
Added HTTP MCP server e2b-mcp-gateway with URL: https://50005-xxxxx.e2b.app/mcp

Connection successful! Cleaning up...
```


--------------------------------

### Install Rosetta 2 on Apple silicon

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/mac-install.md

Installs Rosetta 2 from the command line on macOS with Apple silicon. Use this if you need support for optional command-line tools that require Darwin/AMD64.

```console
$ softwareupdate --install-rosetta
```


--------------------------------

### Install and enable AppIndicator GNOME extension on RHEL 10

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/setup/install/linux/rhel.md

Installs and enables AppIndicator and KStatusNotifierItem GNOME extensions on RHEL 10 with GNOME desktop environment. Requires EPEL to be enabled.

```console
$ # enable EPEL as described above
$ sudo dnf install gnome-shell-extension-appindicator
$ sudo gnome-extensions enable appindicatorsupport@rgcjonas.gmail.com

```


--------------------------------

### Install interactively specifying an embedded PAC script

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/enterprise/enterprise-deployment/msi-install-and-configure.md

Passes an inline JavaScript proxy auto-config script directly to OVERRIDEPROXYEMBEDDEDPAC during installation. Uses --% to preserve argument formatting in PowerShell.

```powershell
PowerShell
 msiexec --% /i "DockerDesktop.msi" /L*V ".\msi.log"  PROXYHTTPMODE="manual" OVERRIDEPROXYEMBEDDEDPAC="function FindProxyForURL(url,host) {return ""DIRECT"" ;; }"
```


--------------------------------

### Terminate Docker processes before installing patch for versions 4.32 to 4.36

Source: https://github.com/docker/docs/blob/main/content/manuals/desktop/cert-revoke-solution.md

Stops background helper services and terminates Docker processes prior to applying a version-specific patch installer on macOS.

```console
$ sudo launchctl bootout system/com.docker.vmnetd 2>/dev/null || true
$ sudo launchctl bootout system/com.docker.socket 2>/dev/null || true
 
$ sudo rm /Library/PrivilegedHelperTools/com.docker.vmnetd || true
$ sudo rm /Library/PrivilegedHelperTools/com.docker.socket || true

$ ps aux | grep docker | awk '{print $2}' | sudo xargs kill -9 2>/dev/null
```
