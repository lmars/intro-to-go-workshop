<!SLIDE>

# Introduction To Go

![Go](gopherbw.png)

<!SLIDE>

# Install Go

* OSX - https://golang.org/doc/install#osx

    (or via homebrew - `brew install go`)

* Linux - https://golang.org/doc/install#tarball

* Windows - https://golang.org/doc/install#windows

<!SLIDE>

# Workspace

## Go code must be kept inside a workspace containing these directories:

* `src` - Go source files organized into packages
* `pkg` - Package objects
* `bin` - Executables

<!SLIDE>

# Workspace

## The GOPATH environment variable specifies the location of your workspace:

    $ mkdir $HOME/go
    $ export GOPATH=$HOME/go

---

## Your code should (usually) go in:

    $GOPATH/src/github.com/USERNAME/PROJECT

    # e.g.
    $GOPATH/src/github.com/lmars/flynn

<!SLIDE>

# Hello, world!

    # $GOPATH/src/github.com/lmars/hello

    # main.go

    package main

    import "fmt"

    func main() {
        fmt.Println("Hello, world!")
    }
