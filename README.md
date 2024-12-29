# Atelier

A ready-to-code Docker workspace with pre-configured development tools and environments.

> ⚠️ **Note:** 
> - This environment is meant for development purposes only and should not be used in production.
> - The Docker image size is approximately 1.5GB. Initial build process will take some time and consume considerable network data.

## Features

- 🐳 Docker-based development environment
- 💻 Pre-configured VSCode settings and extensions
- 🔧 Built-in compiler toolchains
- 🐞 Debug configurations for multiple languages
- 🚀 Fast project bootstrapping


## Prerequisites

- 🐳 Docker installed on your system
- 🔌 VSCode with [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension (if using VSCode)

## Quick Start 

- Clone the repository:
    ```bash
    git clone https://github.com/rishabhkhemka/atelier
    cd atelier
    ```

- Build the Docker image:
    ```bash
    docker build -f ./atelier_dockerfile -t atelier .
    ```

- Setup your workspace (vscode users):
    - Copy `.devcontainer.json` to your desired workspace folder
    - Copy / Replace / Merge the .vscode directory in the folder
    - Open VSCode in that folder
    - Click the icon in the bottom-left corner
    - Select "Reopen in Container" from the menu
    Your development environment will now start in the container. Ignore tasks issue popup. It gets resolved after the extensions get installed.

- Setup your workspace (terminal users):
    ```bash
    # From the project folder
    docker run -it --rm \
        -v "$(pwd):/home/dev/workspace" \
        atelier
    ```

## Included Tools

- GCC/G++ compiler suite
- Golang
- Git and common CLI tools

## VSCode Debug Configurations

Preconfigured debugging for:
- C/C++ applications


### Extending the Container

- Edit `atelier_dockerfile` and/or `.devcontainer.json` file to point to your own modified scripts and docker image.
- Build the image instead of pointing to a dockerfile.


### Modifying VSCode Settings

- Workspace settings are in `.vscode/settings.json`
- Debug configurations are in `.vscode/launch.json`

## Contributing

1. Fork the repository
2. Create your feature branch
3. Submit a pull request
