
### Step 2: Garbage Collection in Go

At the core of Go's memory management system is its garbage collector, which periodically scans the program's memory to identify and deallocate memory that is no longer in use. The garbage collector runs concurrently with the program's execution, so it doesn't impact its performance.

To illustrate how the garbage collector works, let's create a simple Go program:

```
package main

import "fmt"

func main() {
    var x *int
    for i := 0; i < 10; i++ {
        x = new(int)
        *x = i
        fmt.Println(*x)
    }
}
```
In this program, we create a pointer to an integer variable (x) and use the new() function to allocate memory for the variable. We then assign the value of i to the variable and print it to the console.

When we run this program, we can see that the garbage collector deallocates the memory for the previous x variable before allocating new memory for the next one:

node1 # ```go run main.go ``` \
0 \
1 \
2 \
3 \
4 \
5 \
6 \
7 \
8 \
9