#### Channels
Channels are used to communicate between goroutines. They allow you to send and receive values from one goroutine to another. Channels can be used to synchronize access to shared resources, or to pass data between different parts of a program.

To create a channel, you can use the make function:

ch := make(chan int) // create an integer channel

To send a value through a channel, you can use the <- operator:


ch <- 10 // send the value 10 through the channel
To receive a value from a channel, you can use the same operator:

x := <-ch // receive a value from the channel and store it in x
Here's an example of how you can use goroutines and channels together:

```
package main
import "fmt"
func sum(values []int, result chan int) {
    sum := 0
    for _, v := range values {
        sum += v
    }
    result <- sum // send the sum through the channel
}

func main() {
    values := []int{1, 2, 3, 4, 5}

    result := make(chan int)
    go sum(values[:len(values)/2], result) // run the sum function in a goroutine
    go sum(values[len(values)/2:], result) // run the sum function in a goroutine

    x, y := <-result, <-result // receive the sums from the channel
    fmt.Println(x + y) // prints 15
}
```
Save and exit (Shortcut ESC + :wq! )
When you run this code,
```go run gour.go```

In this example, the sum function calculates the sum of a slice of integers and sends the result through a channel. The main function creates two goroutines to run the sum function, each calculating the sum of half the slice. The results are then received from the channel and added together to get the final sum.