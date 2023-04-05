### Adım 6: API Gateway'i Uygulayın
Mikro servis mimarisinde, API Gateway, tüm istekleri ve mikro servislere yanıt verirken ters vekil görevi görür. İstemcinin arka uç mikro servisleri ile iletişim kurmak için tek bir giriş noktası sağlar. Bu adımda, Go kullanarak mikro servislerimiz için bir API Gateway uygulayacağız.

Projelerinizin dizininde api-gateway adında yeni bir dizin oluşturun.

```
mkdir api-gateway
```
Dizin değiştirin ve api-gateway dizinine gidin.

```cd api-gateway
```
API Gateway için yeni bir Go modülü oluşturun.

```
go mod init api-gateway
```
API Gateway için gerekli paketleri yükleyin.

```
go get github.com/gorilla/mux
go get github.com/rs/cors
```
gorilla/mux paketi, Go için popüler bir HTTP yönlendirici ve dağıtıcısıdır ve rs/cors paketi, Go için basit bir CORS ara yazılımıdır.

api-gateway dizinine main.go adında yeni bir dosya oluşturun ve aşağıdaki kodları ekleyin:
```
package main

import (
    "github.com/gorilla/mux"
    "github.com/rs/cors"
    "net/http"
)

func main() {
    // Yeni bir yönlendirici oluştur
    r := mux.NewRouter()

    // Uç noktaları tanımla
    r.HandleFunc("/users", getUsers).Methods("GET")
    r.HandleFunc("/users/{id}", getUser).Methods("GET")
    r.HandleFunc("/users", createUser).Methods("POST")
    r.HandleFunc("/users/{id}", updateUser).Methods("PUT")
    r.HandleFunc("/users/{id}", deleteUser).Methods("DELETE")

    // CORS ara yazılımını yapılandır
    c := cors.New(cors.Options{
        AllowedOrigins: []string{"*"},
        AllowedMethods: []string{"GET", "POST", "PUT", "DELETE"},
    })
    handler := c.Handler(r)

    // Sunucuyu başlat
    http.ListenAndServe(":8080", handler)
}

func getUsers(w http.ResponseWriter, r *http.Request) {
    // Kullanıcı servisini çağırarak kullanıcı listesini alın
}

func getUser(w http.ResponseWriter, r *http.Request) {
    // Belirli bir kullanıcıyı almak için kullanıcı servisini çağırın
}

func createUser(w http.ResponseWriter, r *http.Request) {
    // Yeni bir kullanıcı oluşturmak için kullanıcı servisini çağırın
}

func updateUser(w http.ResponseWriter, r *http.Request) {
    // Belirli bir kullanıcıyı güncellemek için kullanıcı servisini çağırın
}

func deleteUser(w http.ResponseWriter, r *http.Request) {
    // Belirli bir kullanıcıyı silmek için kullanıcı servisini çağırın
}
```
Bu kodda, gorilla/mux paketini kullanarak API Gateway uç noktalarımızı tanımlıyoruz. Her uç noktayı işlemek için çağrılacak fonksiyonları da tanımlıyoruz. Son olarak, rs/c