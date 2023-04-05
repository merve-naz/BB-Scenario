
## Step 4: Debugging techniques in Go

Debugging Go code can be done using a variety of techniques, such as print statements, debuggers, and profiling tools. The fmt package in Go provides a simple way to print debug information to the console, while debuggers like Delve can be used to step through code and inspect variables.

To see an example of how to use the fmt package for debugging in Go, run the following command:
```nano error4.go```

```
package main
import "fmt"

func main() {
	myFunc()
}
func myFunc() {
    for i := 0; i < 10; i++ {
        fmt.Println("i =", i)
	}
}
```
You should see the following output:

i = 0 \
i = 1 \
i = 2 \
i = 3 \
i = 4 \
i = 5 \
i = 6 \
i = 7 \
i = 8 \
i = 9 

This code defines a myFunc function that prints the value of a loop variable i to the console using the fmt.Println function. The main function then calls myFunc and prints the values of i from 0 to 9.