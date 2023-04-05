### Senaryo: Go Standard Kütüphanesini Kullanarak Basit Bir Web Sunucusu Oluşturma
  
İlk olarak Go paketini yükleyelim.
```
apk add go
```  
1. Yeni bir dizin oluşturun ve Go projeniz dizine gidin: 
```
mkdir go-webserver && cd go-webserver
```
2. Vim metin düzenleyicisi kullanarak main.go adında yeni bir dosya oluşturun:
```vim main.go```
3. main.go dosyasında, Go standart kütüphanesinden net/http paketini içe aktarın ve gelen istekleri işleyecek bir handler fonksiyonu tanımlayın:

4.Belirli bir bağlantı noktasında (bu durumda port 8080) sunucuyu başlatacak olan main fonksiyonunu tanımlayın:
```
package main

import (
    "fmt"
    "net/http"
)
func main() {
    http.HandleFunc("/", handler)
    http.ListenAndServe(":8080", nil)
}

func handler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintf(w, "Hello, World!")
}

```

5. main.go dosyasını kaydedin ve kapatın (Kısayol Esc + :wq )

6. main.go yu çalıştıralım.
``` 
go run main.go
```

7. Shell'in üstünde bulunan porta git ikonu ile 8080 adresine giderek "Merhaba, Dünya!" mesajını tarayıcınızda görüntüleyin.
Tebrikler, Go standart kütüphanesi kullanarak basit bir web sunucusu başarıyla oluşturdunuz!
