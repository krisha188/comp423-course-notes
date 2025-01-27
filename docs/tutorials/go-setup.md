#  Go Tutorial :fontawesome-brands-golang:

## Prerequisites
Before completing this tutorial make sure you have:

1.  A GitHub account: Make a github account if you do not already have one

2.  Install git: If its not installed, then install [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

3.  Visual Studio: If its not installed, then install [VS Code](https://code.visualstudio.com)

4.  Docker: This is needed to run your dev container. Install [Docker here](https://www.docker.com/products/docker-desktop/)

!!! note

    If you do not plan on creating a remote repository or would like to use a remote other than Github, then a Github account is not strictly required. However,
    for the purposes of this tutorial, we will be using Github.

## How to Setup Your Dev Container

### Step 1: Initial Setup

1.  Open your terminal or command prompt

2.  Create a new directory for your project

    ``` bash
    mkdir go-project
    cd go-project
    ```

3.  Initalize a new Git Repository

    ``` bash
    git init
    ```

!!! example "GitHub Repositories"

    If you would like, you can now create a new repository page on Github so that
    you can link your local repository to Github

    1.  Log in to your GitHub account and navigate to the Create a New Repository page.

    2.  Fill in the details as you would like

    3.  Do not initialize the repository with a README, .gitignore, or license.

    4.  Click Create Repository.

    5.  Add the GitHub repository as a remote with:

    ```
    git remote add origin https://github.com/<your-username>/<your-repository-name>.git
    ```
    

4.  Ensure Docker and VS Code are installed before proceeding

### Step 2: Setting up the Development Environment

1.  In VS Code, open the rust-project directory via: File > Open Folder

2.  Install the Dev Containers and Docker Extension for VS Code

3.  Create a .devcontainer directory in the root of your project, either through
    the VS Code GUI or with the command mkdir. Create a JSON file inside of this
    new directory called devcontainer.json. The path should be:

  
    .devcontainer/devcontainer.json

4.  The devcontainer.json file defines the configuration for your development environment. Here, we're specifying the following:

    * Name: a descriptive name for your dev container

    * Image: the Docker image to use, in this case, the latest version of a Rust environment. Microsoft maintains a collection of base images for many programming language       environments, but you can also create your own!

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

### Step 3: Reopen the Project in a VSCode Dev Container

1.  Reopen the project in the container by pressing Ctrl+Shift+P (or Cmd+Shift+P on Mac), then typing "Dev Containers: Reopen in Container," and selecting the option. This may take a few minutes while the image is downloaded and the requirements are installed.

2.  Once your dev container setup completes, close the current terminal tab (trash can), open a new terminal pane within VSCode, and try running go version to see your dev container is running a recent version of go without much effort!-

!!! note Go Version
    As of this writing: go version go1.23.4 should be the current version as of Janurary 26, 2025

!!! tip Docker
    In your Docker application, you can view your current running containers and images as well as in the Remote Explorer tab in VS Code.

Congratulations! You have created your first go dev container.


* Primary author: [Krisha Avula](https://github.com/krisha188)
* Reviewer: [Kevin Ma](https://github.com/Kevinofma)