Lesson 4: Functions
In Go, functions are first-class citizens, which means they can be assigned to variables, passed as arguments to other functions, and returned from functions. Functions are a key feature of Go and are used extensively throughout the language.

1. Function Definition
Functions are defined using the func keyword followed by the function name, a list of parameters enclosed in parentheses, and the function body enclosed in braces. The general syntax is as follows:

go
Copy code
func functionName(parameter1 type1, parameter2 type2) returnType {
    // function body
    return value
}
Here's an example function that takes two integers and returns their sum:

go
Copy code
func add(x int, y int) int {
    return x + y
}
2. Function Call
To call a function, you simply use its name followed by the argument list enclosed in parentheses. Here's an example:

go
Copy code
sum := add(5, 7) // sum is now 12
3. Multiple Return Values
Go functions can return multiple values, which is useful in many situations. To return multiple values, simply list them separated by commas in the function signature. Here's an example function that returns both the minimum and maximum values in a slice of integers:

go
Copy code
func minMax(nums []int) (int, int) {
    min := nums[0]
    max := nums[0]
    for _, num := range nums {
        if num < min {
            min = num
        }
        if num > max {
            max = num
        }
    }
    return min, max
}
To call this function and get the minimum and maximum values, you would use the following code:

go
Copy code
nums := []int{1, 5, 3, 9, 2}
min, max := minMax(nums)
fmt.Println("Minimum:", min) // prints "Minimum: 1"
fmt.Println("Maximum:", max) // prints "Maximum: 9"
4. Variadic Functions
Go functions can also be defined to take a variable number of arguments, known as variadic functions. To define a variadic function, use the ... syntax before the type of the last parameter. Here's an example function that takes a variable number of integers and returns their sum:

go
Copy code
func sum(nums ...int) int {
    total := 0
    for _, num := range nums {
        total += num
    }
    return total
}
To call this function with a variable number of arguments, you simply pass them separated by commas:

go
Copy code
sum := sum(1, 2, 3, 4, 5) // sum is now 15
5. Anonymous Functions
Go also supports anonymous functions, which are functions without a name. Anonymous functions are defined inline and can be assigned to variables, passed as arguments to other functions, and returned from functions. Here's an example of an anonymous function that doubles an integer:

go
Copy code
double := func(x int) int {
    return x * 2
}
To call this anonymous function, you simply use the variable name followed by the argument list enclosed in parentheses:

go
Copy code
result := double(5) // result is now 10
6. Higher-Order Functions
Higher-order functions are functions that take other functions as arguments or return functions as their result. They are a powerful programming technique that can be used to create reusable code. Here's an example of a higher-order function that takes a function as an argument and applies it to every element in a slice of integers: