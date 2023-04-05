#### Level: Elementary
### Scenario: Creating a web server that serves static files using the Go standard library
  
1. First install Go 
```
apk add go
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
```nano index.html```
Paste the codes
```
<table style="background-color:#33475b">
<tr>
<th>Name</th>
<th>Job Title</th> 
</tr>
<tr>
<td>Bulut Bilisimciler</td>
<td>Learner</td>
</tr>
</table>
```

6. Start the server by running the following command:
```go run main.go```

7. Start the server by running the following command:

![go_port_icon.PNG](https://gitlab.bulutbilisimciler.com/bb-public/scenarios/-/raw/master/go/Assets/go_port_icon.PNG)
Open navigate bar to connect 8080 port on node to see the "Bulut Bilisimciler" message displayed with a blue background color.

Test serving other static files by adding any file such as an image, javascript or css file to the public directory and try to access them on the browser.

Congratulations, you have successfully created a web server using the Go standard library that serves static files!

