### Step 3: Create a REST API for the user service
Open the terminal and navigate to the project directory.
Create a new file named user.go in the service directory.
Open the user.go file with a text editor.
Add the following code to create a REST API that returns a list of users:
```
package main

import (
	"encoding/json"
	"log"
	"net/http"
)

type User struct {
	Name  string `json:"name"`
	Email string `json:"email"`
}

func main() {
	http.HandleFunc("/users", getUsers)
	log.Fatal(http.ListenAndServe(":8080", nil))
}

func getUsers(w http.ResponseWriter, r *http.Request) {
	users := []User{
		User{Name: "John Doe", Email: "johndoe@example.com"},
		User{Name: "Jane Doe", Email: "janedoe@example.com"},
	}

	json.NewEncoder(w).Encode(users)
}
```
Save and close the user.go file.
Run the following command to start the user service:

```go run service/user.go```

You should see the following message in the terminal: Listening on :8080...

Congratulations! You have created a simple REST API for the user service. In the next step, you will create a REST API for the order service.