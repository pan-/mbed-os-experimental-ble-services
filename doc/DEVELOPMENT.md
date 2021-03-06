# Development

New services, enhancements and bug fixes are welcome. To contribute to this 
repository you should set up a development environment. 

## Minimum Requirements 

It is possible to develop services in your native environment and IDE of
choice (including VSCode!). 

The following software packages are required to build and run the unit tests from this 
repository: 
- CMake
- Git
- A host toolchain 
- Ninja

From an environment standpoint, an `mbed-os` folder should be present in the 
`tests` folder. It can be a symbolic link to a local Mbed OS version or a plain 
clone. Running the command `bootstrap.sh` will ensure Mbed OS is available in the 
environemnt. 

## Getting started 

### Setup

To facilitate the development experience, a Visual studio code configuration is 
available out of the box as well as a ready to use docker image. 

1. Download and install [VSCode](https://code.visualstudio.com/)
and [docker](https://www.docker.com/products/docker-desktop). If you're using a
Linux host, make sure to [configure](https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user) 
your system to run docker with your local user. 

1. Start the docker daemon

1. Open VSCode and install the [Remote - Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension. 

1. Open the local version of this repository in VSCode and VSCode will propose you to 
reopen the folder in a container. 

![Open in container toast](./img/vscode-open-in-container.png)

If you miss the VSCode toast, you can open the 
[command palette](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette)
and search for `Open folder in container...` ([reference](https://code.visualstudio.com/docs/remote/containers#_quick-start-open-an-existing-folder-in-a-container))

When the container is started, it will download the development image of this 
repository and set it up.

That's it you're all set to develop and debug new and exciting services!

### Commands

Most of the compilation and build commands are accessible through the UI: 

![Cmake toolbar](./img/vscode-cmake-toolbar.png)

Commands are accessible through the Command palette too: 
- Cmake configuration: `Cmake: Configure`
- Build: `Cmake: Build`
- Select build target: `CMake: Set Build Target`
- Execute test: `Cmake: Run Test` 
- Debug target: `CMake: Debug`


### Troubleshooting

- Autocompletion: The autocompletion engine takes a significant amount of time to 
start. When it is ready, the database icon at the bottom of the IDE should disappear. 
- Speed: I/O can be **really** slow when docker is run on Window or MacOS systems. You can 
clone this repository in a docker volume using the command [`Clone Repository in Container Volume`](https://code.visualstudio.com/docs/remote/containers#_quick-start-open-a-git-repository-or-github-pr-in-an-isolated-container-volume) .
