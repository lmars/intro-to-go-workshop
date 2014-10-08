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

<!SLIDE>

# Variables

## Declaration

    var i int

## Declaration + Allocation

    var i int = 10

    var i = 10

    i := 10

<!SLIDE>

# Types

* `int`, `int32`, `uint`, `byte` (alias for `uint8`)
* `float32`, `float64`
* `string` (e.g. `"Hello, world!"`)
* `bool` (`true` and `false`)

<!SLIDE>

# `struct`

    type Rectangle struct {
      Width  int
      Height int
    }

    rect := Rectangle{Width: 10, Height: 20}

    fmt.Println("rect.Width:", rect.Width)
    fmt.Println("rect.Height:", rect.Height)

<!SLIDE>

# Task

1. Define types representing the following shapes:

    * Rectangle

    * Circle

    * Square

2. Create an executable which prints their dimensions

<!SLIDE>

# Methods

    type Rectangle struct {
      Width  int
      Height int
    }

    func (r Rectangle) Area() float64 {
        return float64(r.Width * r.Height)
    }

    rect := Rectangle{Width: 10, Height: 20}
    fmt.Println("rect.Area:", rect.Area())

<!SLIDE>

# Interfaces

## Interfaces are types which contain a set of methods

    type Shape interface {
      Area() float64
    }

## Any type having those methods "implements" the interface

## Can be used as function arguments

<!SLIDE>

# Task

1. Make your shapes implement the `Shape` interface

2. Write a function which prints the area of any `Shape`
