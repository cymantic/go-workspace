# Go Workspace Configuration
Based on instruction from [Golang GithubCodeLayout][golang-github].

## Set $GOPATH
$GOPATH must be set to this directory

## Layout
Projects are located under `src/github.com/<username>/<package>`

### Library
Package name is the same as the repository name.

So for a library `greeter`
```go
package greeter

func Greeting() string {
  return "Hello, world!"
}
```

### Application
Package name is `main`.

So for an application `greeterd`
```go
package main

import (
  "fmt"
  "github.com/<username>/greeter"
)

func main() {
  fmt.Printf(greeter.Greeting())
}
```

## Dependencies
To get all dependencies for the workspace use `cd $GOPATH; go get -v ./...`.

To get dependencies from within a project just use `go get` from the project directory.

## Install
To install an application use `cd $GOPATH; go install ...<application>`.

This will install the executable to `$GOPATH/bin/<application>`.


## Build
To build within the project use `go build` and it will create the executable in that directory.

[golang-github]: https://github.com/golang/go/wiki/GithubCodeLayout
