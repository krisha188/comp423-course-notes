#  Go Tutorial :fontawesome-brands-golang:

Go, also known as Golang, is an open-source programming language created by Google in 2007 and released in 2009. It was designed with simplicity, performance, and ease of development in mind. Go combines the efficiency of compiled languages like C with the simplicity and readability of interpreted languages like Python, making it ideal for building scalable, high-performance applications. In this tutorial, we will guide you through setting up a development environment for Go using a Dev Container and build and run your first Go program within it. 

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

1.  In VS Code, open the go-project directory via: File > Open Folder

2.  Install the Dev Containers and Docker Extension for VS Code

3.  Create a .devcontainer directory in the root of your project, either through
    the VS Code GUI or with the command mkdir. Create a JSON file inside of this
    new directory called devcontainer.json. The path should be:

  
    .devcontainer/devcontainer.json

4.  The devcontainer.json file defines the configuration for your development environment. Here, we're specifying the following:

    * Name: a descriptive name for your dev container

    * Image: the Docker image to use, in this case, the latest version of a Go environment. Microsoft maintains a collection of base images for many programming language       environments, but you can also create your own!

    * Customizations: adds useful configurations to VS Code, Here we are using the Go VSCode plugin

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

## Creating a Go Basic Program

### Step 1. Create a "Hello COMP423" Program

(A) Initialize a Go Module. A go.mod file lists all external dependencies your project requires, along with their specific versions to ensure your project always uses the same version of each dependency. It will also declare your project as a Go module and assigns it a unique module path. This path acts as the module’s unique identifier, enabling other Go projects to reference your code when used as a dependency.

``` bash
  go mod init example.com/go-project
```
It should say ```go: creating new go.mod: module example.com/go-project`` after the command executes

!!! note
    the go.mod file is similar to the requirements.txt file found in python

(B) Create a .go file:
  1. In the Explorer tab, right-click on the folder and select New File
  2. Name the file hello-comp423.go

(C) Add the following code to print hello comp 423

``` go
  package main

  import "fmt"

  func main() {
    fmt.Println("Hello COMP423")
  }
```
(D) Save your changes (Ctrl + S or Cmd + S on Mac)

### Step 2: Run the Program 
Can run your file two different ways. 
1.  In the terminal of VS Code write

``` bash
  go run hello-comp423.go
```
  When it executes it will print "Hello COMP423" in your terminal
2. 
  (A) In your VS Code terminal write this command. It will create a executable binary file called hello-comp423.
    ``` bash
      go build -o hello-comp423 hello-comp423.go
    ```

  (B) Run the binary file.
    ``` bash
      ./hello-comp423
    ```
  This should give you the same output as before: "Hello COMP423"

!!! note "go build"
    The go build command compiles the source code and generates an executable binary file. This is similar to how the gcc (GNU Compiler Collection) command compiles C code into a binary in a typical C program. This is ideal when you want to distribute the program as an executable. The go run command compiles and runs the Go code in a single step. It doesn't produce a binary file. Instead, it compiles the source code in memory and immediately executes it. This is ideal for quick tests or development when you don't need the compiled binary file. 

You have now built and run your first Go program!

* Primary author: [Krisha Avula](https://github.com/krisha188)
* Reviewer: [Kevin Ma](https://github.com/Kevinofma)

This tutorial uses information from [Starting a Static Website Project with MkDocs by Kris Jordan](https://comp423-25s.github.io/resources/MkDocs/tutorial/)