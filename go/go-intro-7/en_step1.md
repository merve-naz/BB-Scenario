## Microservices architecture with Go
### Step 1: Introduction to Microservices architecture
Overview
Microservices architecture is a software design pattern that structures an application as a collection of small, independent services that communicate with each other over the network. Each service is responsible for a single, specific task, and can be developed, deployed, and scaled independently.

Microservices architecture can bring many benefits, such as increased flexibility, agility, scalability, and resilience. However, it also introduces some challenges, such as increased complexity, coordination, and testing.

### Why Go is a good fit for Microservices architecture ?
Go is a modern, statically-typed programming language that was designed to build fast, efficient, and scalable systems. Go's built-in concurrency support, lightweight processes (goroutines), and low-level control over the network stack make it an ideal choice for building Microservices architecture.

Go's simplicity, readability, and maintainability also make it easy to write, test, and deploy Microservices architecture. Go's static typing and compile-time checks help catch errors before runtime, and its standard library and third-party packages provide many useful tools and frameworks for building Microservices architecture.

### Example: Building a simple Microservice in Go
To demonstrate how to build a Microservice in Go, let's create a simple HTTP server that returns the current time in UTC format.

Create a new directory for your project: `mkdir myservice`

Change into the new directory: `cd myservice`

Create a new file named main.go and open it in your favorite text editor: `nano main.go`

Copy and paste the following code into main.go:

```
package main

import (
    "fmt"
    "net/http"
    "time"
)

func main() {
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        fmt.Fprintf(w, "Current time: %s", time.Now().UTC().Format(time.RFC3339))
    })
    http.ListenAndServe(":8080", nil)
}
```
Save the changes to main.go and exit the editor(saving shortcut: ctrl + X and Y) 

Build and run the Microservice using the following command: `go run main.go`

You should now be able to access the Microservice by clicking port icon top of the shell and go the 8080 port
,continue the connection ignore warning and You should see the current time in UTC format displayed on the page.