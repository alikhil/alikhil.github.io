---
layout: post
title:  "Go Quickstart"
date:   2018-04-06 15:56:57 +0300
categories: Go Tutuorial vscode
comments: true
---

Hi folks! 
It's been a long time since I have publish last post, but now I came back with short quickstart guide in **Go**.

In this tutorial we will configure Go environment in VS Code and write our first program in Go.

### Install Go

First thing that you need to do it's to install Go into your computer. To do so, dowload installer for your operating system from  [here](https://golang.org/dl/) and then run installer.


### Configure GOPATH

By language convention Go developers store all their code in single place called *workspace*. Go also puts dependency packages in workspace. So, in order to Go perform correctly we need to set `GOPATH` variable with path to workspace. 

#### MacOS and Linux

Set the `GOPATH` envar with workspace

```bash
export GOPATH=$HOME/go
```

Also we need to add `GOPATH/bin` to `PATH` in order to run compiler Go programs:

```bash
export PATH=$PATH:$GOPATH/bin
```

### Configure VS Code

Install [official Go extension](https://github.com/Microsoft/vscode-go).

Install delve debugger:

```bash
go get -u github.com/derekparker/delve/cmd/dlv
```

I reccomend you to add following lines to your VS Code user settings:

```json
{
    "go.autocompleteUnimportedPackages": true,
    "go.formatTool": "gofmt"
}
```

#### Windows

Create `GOPATH` envar:

```sh
set GOPATH=c:\Users\%USERNAME%\go
```

Also we need to add `GOPATH\bin` to `PATH` in order to run compiler Go programs:

```sh
set PATH=%PATH%;%GOPATH%\bin
```

### Create project

Move to your `GOPATH/src` directory. Create directory for your project:

```bash
cd $GOPATH/src
mkdir -p github.com/alikhil/hello-world-with-go
```

Open it using vscode:

```bash
code github.com/alikhil/hello-world-with-go
```

### Hello World!

Let's create file named `program.go` and put following code there:

```go
package main

import "fmt"

func main() {
    fmt.Println("¡Hola, mundo!")
}

```

### Run the program

Finally, to run the program by pressing F5 button in VS Code and you should see message printed to *Debuge Console*.

That's all! My congratulations, you have just written your first program in Go! 

### Troubleshouting

If you fail to run your program and there is some message like **"Cannot find path to `go`"**.
Try to add to your `PATH` envar with path directory where `go` binary is stored.

For example in MacOS I have added following line to my `~/.bash_profile`:

```bash
export PATH=/usr/local/go/bin:$PATH
```