### Step 3: Maps
Maps are another important data structure in Go that allow you to store key-value pairs. To create a map, you can use the following syntax:

go
Copy code
ages := map[string]int{
    "Alice": 25,
    "Bob":   30,
    "Carol": 35,
}
This creates a map ages that maps string keys to int values. You can access the value associated with a key using the index operator:

go
Copy code
fmt.Println(ages["Bob"]) // Output: 30
You can also add new key-value pairs to a map:

go
Copy code
ages["Dave"] = 40
To delete a key-value pair from a map, you can use the delete function:

go
Copy code
delete(ages, "Carol")
You can iterate over the keys and values of a map using a range loop:

go
Copy code
for name, age := range ages {
    fmt.Printf("%s is %d years old\n", name, age)
}
This will print out each name and age in the map on separate lines.