# Go Tutorial

Prerequisites
---
Before completing this tutorial make sure you have:

1. A GitHub account: Make a github account if you do not already have one

2. Install git: If its not installed, then install [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

3. Visual Studio: If its not installed, then install [VS Code](https://code.visualstudio.com)

4. Docker: This is needed to run your dev container. Install [Docker here](https://www.docker.com/products/docker-desktop/)

How to Setup Your Dev Container
---

Step 1: Initial Setup

(A) Open your terminal or command prompt

(B) Create a new directory for your project

``` bash
mkdir go-project
cd go-project
```

(C) Initalize a new Git Repository

``` bash
git init
```
(D) Ensure Docker and VS Code are installed before proceeding

Step 2: Setting up the Development Environment

(A) In VS Code, open the rust-project directory via: File > Open Folder

(B) Install the Dev Containers and Docker Extension for VS Code

(C) Create a .devcontainer directory in the root of your project, either through
    the VS Code GUI or with the command mkdir. Create a JSON file inside of this
    new directory called devcontainer.json. The path should be:

  
    .devcontainer/devcontainer.json

(D) The devcontainer.json file defines the configuration for your development environment. Here, we're specifying the following:

* Name: a descriptive name for your dev container

* Image: the Docker image to use, in this case, the latest version of a Rust environment. Microsoft maintains a collection of base images for many programming language environments, but you can also create your own!

* Customizations: adds useful configurations to VS Code, Here we are using the rust-analyzer VSCode plugin by the Rust Programming Language Group

``` JSON
{
  "name": "Go Dev Container",
  "image": "mcr.microsoft.com/devcontainers/go:latest",
  "customizations": {
    "vscode": {
      "settings": {},
      "extensions": ["golang.Go"]
    }
  }
}
```

Step 3: Reopen the Project in a VSCode Dev Container

(A) Reopen the project in the container by pressing Ctrl+Shift+P (or Cmd+Shift+P on Mac), then typing "Dev Containers: Reopen in Container," and selecting the option. This may take a few minutes while the image is downloaded and the requirements are installed.

(B) Once your dev container setup completes, close the current terminal tab (trash can), open a new terminal pane within VSCode, and try running go version to see your dev container is running a recent version of go without much effort! (As of this writing: go version go1.23.4 should be the current version as of Janurary 26, 2025)

Congratulations! You have created your first go dev container.


* Primary author: [Krisha Avula](https://github.com/krisha188)
* Reviewer: [Kevin Ma](https://github.com/Kevinofma)