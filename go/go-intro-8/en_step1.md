
### Step 1: Arrays
An array is a fixed-size collection of elements of the same type. In Go, you can create an array using the following syntax:


var numbers [5]int
This creates an array numbers of type int with a length of 5. You can access the elements of the array using their index, which starts at 0:

go
Copy code
numbers[0] = 10
numbers[1] = 20
numbers[2] = 30
numbers[3] = 40
numbers[4] = 50
You can also use a short syntax to create and initialize an array:

go
Copy code
numbers := [5]int{10, 20, 30, 40, 50}
To print the elements of an array, you can use a loop:

go
Copy code
for i := 0; i < len(numbers); i++ {
    fmt.Println(numbers[i])
}
This will print the numbers 10, 20, 30, 40, and 50 on separate lines.
