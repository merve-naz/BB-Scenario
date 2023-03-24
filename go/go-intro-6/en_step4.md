
### Step 4: Using Pointers in Go

Pointers are variables that store the memory addresses of other variables. In Go, you can declare a pointer variable using the * symbol. Here's an example:

```
package main

import "fmt"

func main() {
    var x int = 42
    var ptr *int = &x
    fmt.Println(*ptr)
}
```
In this program, we declare an integer variable (x) and assign it a value of 42. We then declare a pointer variable (ptr) and assign it the memory address of x using the & symbol. Finally, we print the value of x using the * symbol to dereference the pointer.