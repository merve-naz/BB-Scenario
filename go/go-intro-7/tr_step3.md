
### Adım 3: Kullanıcı hizmeti için bir REST API oluşturma
Terminali açın ve projenin dizinine gidin.
Hizmet dizininde user.go adında yeni bir dosya oluşturun.
user.go dosyasını bir metin editörü ile açın.
Aşağıdaki kodu ekleyerek, kullanıcı listesi döndüren bir REST API oluşturun:

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
user.go dosyasını kaydedin ve kapatın.
Kullanıcı hizmetini başlatmak için aşağıdaki komutu çalıştırın:

```go run service/user.go```

Terminalde "Listening on :8080..." mesajını görmelisiniz.

Tebrikler! Kullanıcı hizmeti için basit bir REST API oluşturdunuz. Bir sonraki adımda, sipariş hizmeti için bir REST API oluşturacaksınız.