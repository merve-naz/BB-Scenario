### Understanding Go Concurrency
Go is designed to make it easy to write concurrent programs, allowing you to perform multiple tasks simultaneously. In Go, concurrency is achieved using goroutines and channels.

#### Goroutines
Goroutines are lightweight threads that are managed by the Go runtime. They allow you to execute functions concurrently without creating a new thread for each one. Goroutines are created using the go keyword, which starts a new goroutine and runs the specified function in the background.

First create a Go page
```vim goroutine.go```
To create a goroutine, you can define a function and use the go keyword to start it:

```
package main
import "fmt"

func sayHello() {
    fmt.Println("Hello, world!")
}

func main() {
    go sayHello() // start a new goroutine
    fmt.Println("Main function")
}
```
Save and exit (Shortcut ESC + wq! )
When you run this code,
```go run goroutine.go``` you'll see that the "Hello, world!" message is printed after the "Main function" message, even though it was started first. This is because the sayHello function is running concurrently in the background.