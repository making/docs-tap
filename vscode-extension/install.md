# Installing Tanzu Dev Tools for VSCode

This topic explains how to install the VMware Tanzu Developer Tools for Visual Studio Code.

## Prerequisites

Before installing the Tanzu Developer Tools IDE extension, you must have:

- The Kubernetes command-line tool, [Kubernetes documentation](https://kubernetes.io/docs/tasks/tools/)
- [Tilt](https://docs.tilt.dev/install.html) v0.23.2
- The Tanzu CLI.
  See [Install the Tanzu CLI](../install-general.md#cli-and-plugin).
- The Tanzu CLI apps plug-in.
  See [Install the Tanzu CLI plug-ins](../install-general.md#install-the-tanzu-cli-plugins).
- A cluster with Tanzu Application Platform, the default Supply Chain, and their dependencies. Download these from Tanzu Network. For installation instructions, see [Installing part I: Prerequisites, EULA, and CLI](../install-general.md).
- [VSCode](https://code.visualstudio.com/download)

## Installation

To install VMware Tanzu Developer Tools for Visual Studio Code:

1. Download the extension from Tanzu Network [here](https://network.tanzu.vmware.com/products/tanzu-application-platform/).
1. Open VSCode. From the Command Palette (`cmd` + `shift` + `P`), run "Extensions: Install from VSIX...". Select the extension file, `tanzu-vscode-extension.vsix`.
1. When you do not already have a Java Development Kit(JDK) installed, the Java extension pack prompts you to install one.
   Accept the dialog box to install the [Extension Pack for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack)
   and the [YAML Language Support by Red Hat](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml).
   These are required to support debug and code snippets, respectively.
1. Ensure Language Support for Java is running in [Standard Mode](https://code.visualstudio.com/docs/java/java-project#_lightweight-mode).

When the JDK and Language Support for Java are configured correctly,
you see that the integrated development environment creates a directory "target" where the code is compiled.

## Configuration

1. Ensure that you are targeting the correct cluster. See [Configure Access to Multiple Clusters](https://kubernetes.io/docs/tasks/access-application-cluster/configure-access-multiple-clusters/).

2. Go to `Preferences` -> `Settings` -> `Extensions` -> `Tanzu` and set the following:
  - Source Image (required): Destination for an image containing source code to be published
  - Local Path (optional): Path on the local filesystem to a directory of source code to build (defaults to current directory)
  - Namespace (optional): Namespace that workloads will be deployed into (defaults to namespace set in kubeconfig)

## Quick start

To quickly get you started, we've created a sample application with all the necessary configuration files.

**Option 1: Application Accelerator**

1. Set up [Application Accelerator](https://docs.vmware.com/en/Application-Accelerator-for-VMware-Tanzu/index.html).

2. Search for the Tanzu Java Web App.

3. Add the required configuration information and generate the application.

4. Unzip and open in VSCode.

**Option 2: Sample repository**

1. Use `git clone` to clone the [tanzu-java-web-app](https://github.com/sample-accelerators/tanzu-java-web-app) repository from GitHub.

2. Go to the `Tiltfile` and replace all instances of `your-registry.io/project` with your registry server and repository.

**You're all set. Time to get developing!**

>**Note:** For getting started with existing applications, see [Code Snippets](usage-getting-started.md#snippets) in the Tanzu Dev Tools Usage documentation.

## Uninstall

To uninstall the Tanzu Dev Tools extension:

1. Navigate to the extensions menu.

2. Right-click on the Tanzu Dev Tools extension and select **Uninstall**.
