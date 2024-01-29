# The Go Programming Language

## Installation

https://go.dev/doc/install

### Initializing a Project

`go mod tidy` - add missing and remove unused modules

### Environment Variables

~/.zshrc

```
export GOPATH=~/workspace/go
export PATH=$PATH:/usr/local/go/bin
```

## Go Workspace Directories

- bin - compiled executables
- pkg - compiled packages
- src - source code

## CLI tools
- go
    - fmt
        - code formater
    - run
        - execute prog
    - build
        - create executable
        - requires path to directory relative to Go's workspace dir
        - looks also for package main with main function
    - get
        - download code from URI to go workspace src directory
    - doc
        - read package documentation
        - simple comments specify docs in a file
    - install
        - compile packages
        - compile executables
    - mod
        - `init project-name` initializes and writes a new go.mod file in the current directory for creating the module
        - `tidy` adds any missing modules necessary to build the current module's packages and dependencies
    - test
        - test packages
        - args:
            - `-c` compile the test binary to pkg.test
            - `-v` shows each test name and status (verbose)
            - `-run NAME` run tests with NAME in the function name

## Example for Creating a New Module

 1. `go mod init project-name`
 1. `go mod tidy`
 1. `go test -c test.go`

## Naming Conventions

- camelCase
- functions
    - local - not exported!
        - `func whatEver()`
    - exported outside of the package
        - `func DoSomething()`

## Packages

### Structure

#### Import Path

- nested by / in import path e.g. `math/rand`
- use URL where a package is located e.g. `github.com/headfirstgo/greeting`

#### Package Name

- one word
- lower case

For instance: `strconv`

## Declarations

- variables
    - full variable declaration
        - `var name type = value`
    - short variable declaration
        - `name := value`
- constants
    - const keyword
    - `const name = value`
    - `const name type = value`
- functions
    - `func name(type param) retName retType`
        - pass-by-value for parameter
    - `func example() (float64, error)`
- methods
    - `func (m MyType) methodName() {}`
        - m as reciever name
            - optional
            - similar to self/this
            - should  be one lower letter that start with first letter from TypeDef
            - can be also a pointer
            - is a copy
                - as a poiner its values can be modified
        - MyType
            - reciever type
            - Relevant for accessing the method
    - same method name can be used with different types
    - use pointer consistent for reciecer types

## Type Definition
- type keyword
- `type MyStruct struct {}`

## General Purpose Functions

### Make

Creates a slice with type and size n:  
- `make([]type, n)`

### Append

Override mySlice variable to not generate multiple unused variables:  
- `mySlice = append(mySlice, elements)`
- frees resources
- prevents inconsistencies

### Delete 
`delete(container, "key")`

## Varadic Functions

- takes varying number of arguments
- `func myFunc(param ...type) {}`
- argument passed into the function is a slice

## Data Structures

### Array

- fixed size
- for...range loop
    - `for index, value := range array {}`
    - `for _, value := range array {}`
        - ignores the index with _
- one particular type
- declaration
    - `var name [n]type`
    - creates an array with n elements
- initialization with literal
    - `myarray := [n]type{x,y,z}`
    - `var myarray = [n]type{x,y,z}`

### Slice

- based on array it's like a view
- variable size
- for...range loop
    - `for index, value := range array {}`
    - `for _, value := range array {}`
        - ignores the index with _
- one particular type
- declaration
    - `var name []type`
- initialization with literal
    - `mySlice := []type{x,y,z}`
    - `var mySlice = []type{x,y,z}`
- initialization with size
    - `var mySlice = make([]type, n)`
- passing a slice to a varadic function requires ellipsis (e.g. `mySlice...`)
- adding a value with append() e.g. `mySlice = append(mySlice, item)`

### Map

- key/value binding
- key is one type
- declaration
    - `var myMap map[keyType]valueType`
- initialization
    - `myMap = make(map[keyType]valueType)`
- initialization with literal
    - `myMap := map[string]int{"a":1, "b":2}`
    - create an empty map
        - `myMap := map[string]int{}`
- zero maps
    - non existing key will return empty value
        - `myMap[string]int`
            - myMap[foo] returns 0
- check for key
    - `_, ok := myMap["key"]`
- for...range loop
    - `for key, value := range myMap{}`
    - access values only
        - `for _, value := range myMap{}`
    - access keys only
        - `for key := range myMap{}`
- unordered collection
    - keys have to be sorted and iterated on to access the sorted keys on the map

### Struct

- initialization with literal
    - `myStruct := myStructType{"X", 12}`
- modification within a function with pointer
    - auto dereference with . operator
    - otherwise reciever is a copy!
- exported files must be capatialized, to be accessable outside of the package
- can hold any type
- anonymous files
    - just declare the type without name in the struct
    - it also embedds the fields into the struct
        - myStruct.fieldFromOtherStruct
    - CapitalLetter so the field is exported
- to make fields private, the defintion of fields must be lower case and within a package
- getter method
    - Field()
- setter method
    - requires pointer to RecieverType
    - SetField(...)
- embedded Types
    - types with no variable name within the struct
    - fields then belong also to the struct type

### Data Encapsulation

Data encapsulation is accomplished within packages with unexported:  

- fields in structs
- functions
- methods

## Various Operator

### Pointer */&

- `*`
    - type declaration
    - dereference pointer to access its value
- `&`
    - address (ampersand) operator

### :

- `mySlice := myArray[1:3]`
- generates view on array/slice
- view can be used to change also the array/slice

### -
used for ignoring return value on assignment e.g. `myVal, _ = returnsTwoValues()`

## Interfaces

- defines methods that satisfy interface declaration
    - the method signatures must fit
- implicit implementation
- type creation on interface
    - `var interface Interface = MyType{}`
- error interface for custom errors
    - `type error interface { Error() string }`
- string representation interface e.g. toString() in Java
    - `type Stringer interface { String() string }`
- empty interface
    - used for accepting any value
        - fmt.Println accepts empty `interface{}`
        - type assertion used for converting to a specific type

## Type Assertion

- makes convertion possible between different types of interfaces
- creates a copy of value and assigns it no newValue with the asserted type AssertType
- `newValue, ok := value.(AssertType)`
- newValue is the new value with the asserted type on success, otherwise the variable should be nil
- ok is a bool variable that holds if the type assertion was successful or not

## Deferred Function

- keyword `defer`
- ensures a function is executed in any case within a given function
    - e.g. event or error occured
        - close opened files
        - recovering after a panic
    - it is also executed when program panics
        - if multiple deferred functions are defined they are all executed but vise-versa

## Error Handling

- `defer handleError()`
- panic
    - crashes the program
    - should be used for an impossible situation e.g. encountering a bug
    - prints stack trace
- recover
    - can resume after panic call
    - execution coninutes outside of the panic call
    - panic again on unanticipated panic
    - returns panic value on panic otherwise nil
    - can be used to report panic value
    - intercrepts any panic 
- missuse of panic/recover
    - do not user this mechanism like with exception handling
- prefered way for error handling should be a constructs of `if/return error`

Example with deferred function recovering after a panic:  

```go
func bug() { panic("data field x not found in package") }

func handlePanic() {
    panicVal := recover()
    // panicVal is a empty interface, so type assertion is required to get the error... 
    err, ok := panicVal.(myerror)
    if ok {
        fmt.Println(err.Error())
    } else {
        panic(panicVal)
    }
}

func main() {
    defer handlePanic()
    bug()
    // programm continues...
}
```

## Concurrency

- goroutines
    - declaration is `go myFunc()`
    - concurrent exection by a thread 
    - execution order is not predictable
    - no return value is supported
- channels
    - declaration is `var myChannel chan float64`
    - assignments:  
        - `myChannel = make(chan float64)`
        - `myChannel := make(chan float64)`
        - keyword for channels is `chan`
        - data type to hold must be specified
    - communication over goroutines only
    - send/receive
        - send
            - `myChannel <- value`
        - receive
            - `<- myChannel`
            - `myValue <- myChannel`
    - mode
        - buffered
            - defines the number of values the channel can hold before it blocks on the next operation
        - unbuffered
            - will block immediately if the value in the channel was not processed
    - deadlock situations are possible in main function e.g. when trying to get an item from an empty blocking channel

# Testing

- files should be named with `_test.go` in filename
- `import testing` package
- each test function should start with `Test`
- test function should accept a pointer to a `testing.T` value as parameter
- more detailed error messages can be printed with `Errorf()`
