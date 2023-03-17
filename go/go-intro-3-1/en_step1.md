### Scenario: Creating a simple web server using the Go standard library
  

Firstly, we need to install Go.
```
apk add go
```
## Steps

1. Create a new directory for your Go project and navigate into it: 
```
mkdir go-webserver && cd go-webserver
```
2. Create a new file called main.go using a text editor such as nano or vim:
```vim main.go```
3. In the main.go file, import the net/http package from the Go standard library and define a handler function that will handle incoming requests:

4.Define a main function that will start the server on a specified port (in this case, port 8080):
```
package main

import (
    "fmt"
    "net/http"
)

func main() {
    http.HandleFunc("/", handler)
    http.ListenAndServe(":8080", nil)
}
func handler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintf(w, "Hello, World!")
}

```

5. Save and close the main.go file ( Click Esc + :wq )

6. Run Go main.go file:
```go run main.go```


7.Open a web browser and navigate to http://localhost:8080 to see the "Hello, World!" message displayed in your browser.
Congratulations, you have successfully created a simple web server using the Go standard library!

