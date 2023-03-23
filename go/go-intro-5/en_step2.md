
### Step 2: Error types in Go

In Go, errors are represented by the error interface, which has a single method, Error() string, that returns a string describing the error. There are also several built-in error types in Go, such as fmt.Errorf, which allows you to create custom error messages.

To see an example of how to create and return a custom error in Go, run the following command:
```nano error2.go```

```
package main
import "errors"
import "fmt"

func main() {
	err := myFunc()
	if err != nil {
    	fmt.Println(err)
	}
}
func myFunc() error {
    return errors.New("something went wrong")
}
```
You should see the following output:

- something went wrong

This code defines a myFunc function that returns a custom error message using the errors.New function. The main function then calls myFunc and prints the returned error message.
