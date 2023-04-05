## 1. Understanding errors in Go

### Step 1: What are errors in Go?

In Go, errors are values that represent an abnormal condition or state that occurs during the execution of a program. Errors are typically returned from functions that can fail, and they provide information about what went wrong and why.
 
Create a folder  ```mkdir ./error``` ,
go the folder  ```cd ./error``` ,
add nano editor  ```apk add nano``` or you can use "vi","vim" it is up to you ,
make a go file  ```nano error.go``` ,

To see an example of how errors are returned in Go, paste the following command:
```
package main
import "fmt"

func main() {
	fmt.Println(1 / 0)
}
```
Ctrl + x for saving and Y
run the file ```go run error.go``` ,

You should see the following output:
-  command-line-arguments
- ./error.go:5:18: invalid operation: division by zero

### Conclusion

This error message tells you that a division by zero occurred in the fmt.Println function call on line 4 of the main.go file.
