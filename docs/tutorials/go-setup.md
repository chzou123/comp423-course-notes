# Setting up a dev container for Go

* Primary author: [Chris Zou](https://github.com/chzou123)
* Reviewer: [Shanyu Gowdu](https://github.com/gowdu0)

## Prerequisites
- VS Code with Dev Containers extension
- Docker installed and running
- Git installed
- Knowledge of terminal

## Project Initialization
```bash
# Create Project Directory
mkdir comp423-go
cd comp423-go

# Initialize Git Repository
git init
```

## Dev Container Configuration
Create `.devcontainer/devcontainer.json`:
```json
{
  "name": "Go Dev Container",
  "image": "mcr.microsoft.com/devcontainers/go:0-1.20", 
  "customizations": {
    "vscode": {
      "extensions": [
        "golang.go"
      ]
    }
  }
}
```

## Create Go Project
Initialize the Go module
```bash
go mod init hello-comp423
```

## Implement Hello World
Create a file `main.go` in the root of your project.
```go
package main

import "fmt"

func main() {
    fmt.Println("Hello COMP423")
}
```

## Run Subcommand
By typing in the command below, it will compile the file and run the program.
```bash
go run main.go
```

## Build Subcommand
By typing in the first command below, it will create an executable in your project directory. Then, typing in the second command, you will be able to run the program
```bash
go build -o hello main.go
./hello
```