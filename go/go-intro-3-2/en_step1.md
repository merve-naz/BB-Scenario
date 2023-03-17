#### Level: Elementary
### Scenario: Creating a web server that serves static files using the Go standard library
  
1. Create a new directory for your Go project and navigate into it:
```
mkdir go-webserver && cd go-webserver
```
2. Create a new file called main.go using a text editor such as nano or vim:
But first we need to add nano 
```apk add nano```
Then,
```nano main.go```

3. In the main.go file, import the net/http package from the Go standard library and define a handler function that will serve static files from a specified directory (in this case, the public directory):
```
package main

import (
    "fmt"
    "log"
    "net/http"
)

func main() {
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        if r.URL.Path == "/" {
            http.ServeFile(w, r, "public/index.html")
            return
        }
        http.ServeFile(w, r, "public"+r.URL.Path)
    })

    fmt.Println("Starting server on http://localhost:8080")
    log.Fatal(http.ListenAndServe(":8080", nil))
}
```
Save shortcut ctrl + X and Y + enter
4. Create a new directory called public that will contain your static files (e.g. HTML, CSS, JavaScript):
```
mkdir public
```
5. Create an index.html file in the public directory:
```echo "<html><body><h1>Hello, World!</h1></body></html>" > public/index.html```
------
6. Create a style.css file in the public directory:
```echo "body { background-color: yellow; }" > public/style.css``
7. Start the server by running the following command:
```go run main.go```

8. Start the server by running the following command:

Open a web browser and navigate to http://localhost:8080 to see the "Hello, World!" message displayed with a yellow background color.

Test serving other static files by adding any file such as an image, javascript or css file to the public directory and try to access them on the browser.

Congratulations, you have successfully created a web server using the Go standard library that serves static files!

