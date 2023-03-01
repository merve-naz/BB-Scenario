## 2. Egzersiz
Let's create a new page.

```
vim variables.go
```
Let's add 1 more variable to the following code and save ( Esc :wq ) and run it.

```
Copy code
package main
import "fmt"

func main() {

	// `var` declares 1 or more variables.
	var a = "initial"
	fmt.Println(a)

	// You can declare multiple variables at once.
	var b, c int = 1, 2
	fmt.Println(b, c)

	// Go will infer the type of initialized variables.
	var d = true
	fmt.Println(d)

	// Variables declared without a corresponding initialization are zero-valued. For example, the zero value for an `int` is `0`.
	var e int
	fmt.Println(e)

	// The `:=` syntax is shorthand for declaring and initializing a variable, e.g. for `var f string = "apple"` in this case.
	// We omitted the variable type and `:=` inferred the type and initialized f.
	f := "apple"
	fmt.Println(f)

    // Let g be 10 and printed like the examples above with fmt.Println().
}
```
Çalıştırmak için,
```
go run variables.go
```
If we can see the output of the variables on the screen, let's continue.