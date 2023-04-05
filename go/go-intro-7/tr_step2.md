
### Adım 2: Temel bir Go mikro servisi kurulumu
Mikro servislerin anlaşılmasını aldıktan sonra, temel bir Go mikro servisi oluşturalım. Bu adımda, yeni bir Go projesi kuracağız, bir HTTP sunucusu oluşturacağız ve basit bir uç nokta yazacağız.

Aşağıdaki komutu çalıştırarak projeniz için yeni bir dizin oluşturun:

```mkdir go-microservice && cd go-microservice```

Ardından aşağıdaki komutu çalıştırarak yeni bir Go modülü oluşturun:

```go mod init github.com/{kullanıcı-adınız}/go-microservice```

Bu, projenizin bağımlılıklarını takip edecek yeni bir go.mod dosyası oluşturacaktır.

main.go adında yeni bir dosya oluşturun ve tercih ettiğiniz metin düzenleyicide açın.

Gerekli paketleri içe aktararak main.go dosyanızın üstüne aşağıdaki kod satırlarını ekleyin:

```
package main

import (
    "fmt"
    "log"
    "net/http"
)
```
fmt paketi çıktı yazdırmak için kullanılır, log paketi kaydetmek için kullanılır ve net/http paketi bir HTTP sunucusu oluşturmak için kullanılır.

Mikro servisimiz için uç nokta olarak hizmet edecek bir işleyici işlevi ekleyin. Aşağıdaki kod, basit bir işleyici kurar ve "Merhaba Dünya!" mesajını döndürür:

```
func handler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintf(w, "Merhaba Dünya!")
}
```
Main fonksiyonunu oluşturun ve HTTP sunucusunu başlatmak için aşağıdaki kodu main.go dosyanıza ekleyin:

```
func main() {
    http.HandleFunc("/", handler)
    log.Fatal(http.ListenAndServe(":8080", nil))
}
```
Bu kod, HTTP sunucusuna istekleri root path (/) için handler fonksiyonunu kullanması söyler. Ayrıca sunucunun 8080 numaralı portta dinlemesi gerektiğini belirtir.

Artık "Merhaba Dünya!" mesajıyla yanıt veren temel bir Go mikro servisiniz var. Aşağıdaki komutu çalıştırarak mikro servisinizi çalıştırabilirsiniz:

```
go run main.go
```
Terminalinizde "Merhaba Dünya!" mesajının göründüğünü görmelisiniz. Mikro servisinizi test etmek için bir port kısayolu ile 8080 adresine gidin.