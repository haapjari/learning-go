# Learning Go

Hello! This is my personal notebook of resources, I've used to accumulate some knowledge of being Software Engineer, utilizing `Go` as tool. This aims or claims not to be a comprehensive list, but just a minor help to get started. 

---
## Table of Contents

1. [Introduction to Go](#introduction-to-go)
2. [Environment Setup](#environment-setup)
3. [Language Basics](#language-basics)
4. [Control Structures](#control-structures)
5. [Functions](#functions)
6. [Packages and Modules](#packages-and-modules)
7. [Structs and Interfaces](#structs-and-interfaces)
8. [Pointers](#pointers)
9. [Generics](#generics)
10. [Concurrency](#concurrency)
11. [Error Handling](#error-handling)
12. [Testing and Benchmarking](#testing-and-benchmarking)
13. [Standard Library](#standard-library)
14. [Best Practices](#best-practices)
15. [Example Projects](#example-projects)
16. [Useful Resources](#useful-resources)
17. [References](#references)

---

## Introduction to Go

- History and motivation
- Go's main features and advantages
- Use cases

## Environment Setup

- Installing Go
- Setting up the workspace
- Understanding GOPATH and GOROOT
- Basic command-line tools (go build, go run, go get, etc.)
- IDEs and text editors for Go development.

## Language Basics

- Variables, constants, and data types
- Operators and expressions
- Comments and documentation

## Control Structures

- Conditional statements (if, else, switch)
- Loops (for, range)
- Loop control statements (break, continue, goto)

## Functions

- Function declarations and parameters
- Multiple return values
- Anonymous functions and closures
- Variadic functions
- Defer, panic, and recover

## Packages and Modules

- Creating and using packages
- Importing packages
- Go modules and versioning
- Dependency management

## Structs and Interfaces

- Defining and using structs
- Methods and receivers
- Interfaces and their implementation
- Embedding and composition

## Pointers

TBD

## Generics

TBD

## Concurrency

- Goroutines
- Channels and channel operations
- Select statement
- WaitGroup and sync.Mutex
- Best practices for concurrency patterns

## Error Handling

- Error handling principles in Go
- Creating custom error types
- Handling and propagating errors
- Best practices for error handling

## Testing and Benchmarking

- Writing unit tests
- Table-driven tests
- Test coverage
- Benchmarking and performance testing
- Testing packages and tool

## Standard Library

- Commonly used packages (fmt, os, io, net, time, etc.)
- Working with files and directories
- Networking and web development
- Regular expressions and string manipulation
- JSON, XML, and other data formats

## Best Practices

- Code organization and style
- Naming conventions
- Effective logging and debugging
- Performance optimization techniques
- Security considerations

## Example Projects

### Simple Task Manager (command-line application)

#### Features

- **Add tasks**: Users can add new tasks with a description and deadline.
- **List tasks**: Users can view a list of all tasks, along with their status (completed or pending).
- **Complete tasks**: Users can mark tasks as completed.
- **Delete tasks**: Users can delete tasks from the task manager.

#### Implementation Steps

1. Define a Task struct with fields for description, deadline, and completion status.
2. Implement a storage mechanism to save and retrieve tasks (e.g., in-memory data structures or a JSON file).
3. Create commands for each feature: add, list, complete, and delete tasks.
4. Set up the command-line interface, for example with [cobra](https://github.com/spf13/cobra) library, or write your own and wire up the commands.

#### Skills

1. **Go programming**: Understanding Go language basics, including structs, slices, and maps.
2. **Command-line applications**: Creating command-line applications using the cobra library in Go.
3. **Data storage**: Implementing different storage mechanisms, such as in-memory data structures or working with JSON files.
4. **Error handling**: Handling application errors and returning appropriate error messages.
5. **Testing**: Writing tests for the application to ensure correct functionality and behavior.

---

### Simple Note-Taking API (rest api)

#### Features

1. **Create notes**: Users can create new notes with a title and content.
2. **List notes**: Users can view a list of all notes, with options to filter by keyword, sort by date or title and paginate results.
3. **Update notes**: Users can update the title and content of existing notes.
4. **Delete notes**: Users can delete notes from the system.
5. **Authentication**: Implementing a basic authentication mechanism to secure the API endpoints.

#### Implementation Steps

1. Choose a web framework for building the REST API, such as `net/http` from the standard library or a third-party library like `gin-gonic/gin`. 
2. Define a `Note` struct with fields for the title, content, and creation date.
3. Implement a storage mechanism to save and retrieve notes (e.g., in-memory data structures, a JSON file, or a database like SQLite, PostgreSQL, or MongoDB).
3. Create handlers for each API endpoint: create, list, update, and delete notes.
4. Set up routes and middleware for the API using the chosen web framework.
5. Optionally, implement a simple authentication mechanism using JSON Web Tokens (JWT) or API keys to secure the endpoints.

#### Skills

1. **Web development concepts**: Understanding HTTP methods, request and response handling, and the basics of RESTful API design.
2. **Go web frameworks**: Working with a Go web framework, such as net/http, gin-gonic/gin, or gorilla/mux, to create API endpoints and handle HTTP requests.
3. **Structs and JSON**: Defining custom data structures (e.g., the Note struct) and working with JSON for request and response payloads.
4. **Data storage**: Implementing different storage mechanisms, ranging from in-memory data structures to databases, which helps learn about Go's database/sql package, ORMs, and database drivers.
5. **Middleware**: Implementing middleware functions for request processing, such as authentication, logging, or input validation.
6. **Error handling**: Handling API errors and returning appropriate HTTP status codes and error messages.
7. **Authentication**: Securing the API using authentication techniques like JWT or API keys (optional).
8. **Testing**: Writing tests for the API endpoints to ensure correct functionality and behavior.

---

### Simple Chat Server and Client (web server and client)

#### Features

1. **Server**: Chat server that listens for incoming client connections, broadcasts messages to connected clients, and handles client disconnections.
2. **Client**: Implement a chat client that connects to the server, sends messages, and receives messages from other clients.
3. **Concurrency**: Use goroutines and channels to handle multiple clients concurrently and manage message broadcasting.
4. **Commands**: Support basic chat commands, such as changing the client's display name or listing connected users.

#### Implementation Steps

1. Use the `net` package to create a TCP server that listens for incoming client connections.
2. When a new client connects, start a goroutine to handle the client's communication (sending and receiving messages).
3. Use a channel to broadcast messages received from clients to all connected clients.
4. Implement a chat client using the `net` package to connect to the server, send messages, and receive messages from other clients.
5. Use goroutines and channels in the client to handle sending and receiving messages concurrently.
6. Support basic chat commands, such as changing the client's display name or listing connected users, by parsing and handling specific message patterns.

#### Skills

1. **Networking**: Understanding basic networking concepts and working with `net` package to create TCP servers and clients.
2. **Concurrency**: Using goroutines and channels to handle multiple client connections concurrently and manage communications between clients.
3. **Communication Patterns**: Implementing simple communication patterns, such as broadcasting messages to all aconnected clients, and handling chat commands.
4. **Error Handling**: Handling networking errors, client disconnections, and edge cases in the communication process.
5. **Command Parsing**: Parsing and handling chat commands by analyzing message content.
6. **Client-Server Architecture**: Understanding the client-server model and implementing a simple chat application based on this architecture.

---

## Useful Resources

### Official Resources

- [Official Go Documentation](https://go.dev/doc/) 
- [Official Go Tour](https://go.dev/tour/welcome/1)
- [Official Go Wiki](https://github.com/golang/go/wiki/)
- [Official Go Book, Effective Go](https://go.dev/doc/effective_go)
- [Go Style Guide](https://google.github.io/styleguide/go/decisions)

### Cheatsheets

- [Go Cheatsheet](https://quickref.me/go)
- [DevHints, Go Cheatsheet](https://devhints.io/go)
- [Go by Example](https://gobyexample.com/)

### Video and Online Courses

- [Video Course, from Matthew Holiday](https://www.youtube.com/playlist?list=PLoILbKo9rG3skRCj37Kn5Zj803hhiuRK6)
    - [Slides](https://github.com/matt4biz/go-class-slides/tree/trunk/xmas-2020)
- [Video Course, from freeCodeCamp](https://www.youtube.com/watch?v=YS4e4q9oBaU)
- [Online Course, from Coursera](https://www.coursera.org/specializations/google-golang)

### Books

- [Book: Go Programming Language](https://www.amazon.com/dp/0134190440?th=1&psc=1&linkCode=sl1&language=en_US&ref_=as_li_ss_tl)
    - Beginner
- [Book: Network Programming with Go](https://www.amazon.com/Network-Programming-Go-Adam-Woodbeck/dp/1718500882)
    - Intermediate
- [Book: Efficient Go](https://www.amazon.com/Efficient-Go-Data-Driven-Performance-Optimization/dp/1098105710)
    - Intermediate

### Miscellaneous

- [Awesome Go](https://awesome-go.com/)

---

## References

TBD
