### Senaryo: Go Standard Kütüphanesini Kullanarak Basit Bir Web Sunucusu Oluşturma
  
1. Yeni bir dizin oluşturun ve Go projeniz dizine gidin: 
```
mkdir go-webserver && cd go-webserver
```
2. nano veya vim gibi bir metin düzenleyicisi kullanarak main.go adında yeni bir dosya oluşturun:
```nano main.go```
3. main.go dosyasında, Go standart kütüphanesinden net/http paketini içe aktarın ve gelen istekleri işleyecek bir handler fonksiyonu tanımlayın:
```
package main

import (
    "fmt"
    "net/http"
)

func handler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintf(w, "Hello, World!")
}

```
4.Belirli bir bağlantı noktasında (bu durumda port 8080) sunucuyu başlatacak olan main fonksiyonunu tanımlayın:
```
func main() {
    http.HandleFunc("/", handler)
    http.ListenAndServe(":8080", nil)
}
```
5. main.go dosyasını kaydedin ve kapatın.

6. Aşağıdaki komutu kullanarak program için Go executable dosyasını oluşturun:
```go build```

/. Yeni odosyayı çalıştırarak sunucuyu başlatın:
```./go-webserver```

8. Web tarayıcınızı açın ve http://localhost:8080 adresine giderek "Merhaba, Dünya!" mesajını tarayıcınızda görüntüleyin.
Tebrikler, Go standart kütüphanesi kullanarak basit bir web sunucusu başarıyla oluşturdunuz!
