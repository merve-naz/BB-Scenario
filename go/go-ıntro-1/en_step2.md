## First Exercise
Firstly, we need to install Go.
```
apk add go
```
We will use "Vim Editor" when creating pages. Let's take a quick look at shortcuts.

:q = Closes the Vim editor if the changes are saved. Otherwise, it will warn you.

:q! = Closes the editor directly without saving.

:w = Saves the changes made.

:wq = Saves the changes made and exits.

Then, let's create the first page named "hello.go" in the vim editor.

```
vim hello.go
```
To be able to work on the opened page, let's activate the "Insert Mode" by pressing the "i" key and write the code we want to run on the page.
Let's create a simple "Hello, World!" application with Golang.
```
package main
import "fmt"
 
func main() {
    fmt.Println("Hello, World!")
    //   // To save the operation and exit from hello.go, click "Esc" + ":" + "w" + "q" + "!" characters and then click "enter".
}
```
Then, let's run the hello.go page.
```
go run hello.go
```
Note: If you get the "bash: go: command not found" error at this step, you should try installing Go again.
Now, we can continue.