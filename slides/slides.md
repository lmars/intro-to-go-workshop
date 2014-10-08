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

<!SLIDE>

# Hello, world!

    $ cd $GOPATH/src/github.com/lmars/hello

    $ go run main.go
    Hello, world!

<!SLIDE>

# Packages

    package main

* All Go code belongs to a package
* Acts as a namespace
* The `main` package is used for executables
* Other package names are libraries to be imported

<!SLIDE>

# Library

    # $GOPATH/src/github.com/lmars/greeter

    # greeter.go

    package greeter

    import "fmt"

    func PrintHello() {
      fmt.Println("Hello, world!")
    }

<!SLIDE>

# Library

    # $GOPATH/src/github.com/lmars/hello

    # main.go

    package main

    import "github.com/lmars/greeter"

    func main() {
      greeter.PrintHello()
    }
