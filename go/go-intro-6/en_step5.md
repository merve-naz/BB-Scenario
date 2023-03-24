
### Step 5: Stack vs. Heap Memory in Go
In Go, there are two types of memory allocation: stack and heap. Stack memory is used for local variables and is automatically allocated and deallocated by the program as it enters and exits functions. Heap memory is used for dynamic memory allocation, such as when creating a slice or allocating memory with the new() function.

To illustrate the difference between stack and heap memory, let's take a look at an example:

```
package main

import "fmt"

func main() {
    var x int = 42
    fmt.Println("Value of x:", x)
    fmt.Println("Memory address of x:", &x)

    var ptr *int = new(int)
    *ptr = 100
    fmt.Println("Value of ptr:", *ptr)
    fmt.Println("Memory address of ptr:", ptr)
}
```
In this program, we declare an integer variable x and assign it a value of 42. We print the value of x and its memory address using the fmt.Println() function.

We then declare a pointer variable ptr and use the new() function to allocate memory for an integer variable. We assign a value of 100 to the variable using the dereferenced pointer (*ptr = 100). Finally, we print the value of ptr and its memory address.

When we run this program, we get the following output:


Value of x: 42
Memory address of x: 0xc000018078
Value of ptr: 100
Memory address of ptr: 0xc00000a0c0

As we can see, the variable x is allocated on the stack, and its memory address is within the stack frame of the main() function. The variable ptr is allocated on the heap, and its memory address is outside the stack frame.