
## Adım 4: Go dilinde Debugging (Hata Ayıklama) 

Golang'da kod hata ayıklama, print ifadeleri, hata ayıklayıcılar ve profil araçları gibi çeşitli teknikler kullanılarak gerçekleştirilebilir. Go'da fmt paketi, hata ayıklama bilgilerini konsola yazdırmak için basit bir yöntem sağlarken, Delve gibi hata ayıklayıcılar kodu adım adım takip etmek ve değişkenleri incelemek için kullanılabilir.

Golang'da fmt paketini hata ayıklama için nasıl kullanacağınızın örneğini görmek için aşağıdaki komutu çalıştırın:

```nano error4.go```

```
package main
import "fmt"

func main() {
	myFunc()
}
func myFunc() {
    for i := 0; i < 10; i++ {
        fmt.Println("i =", i)
	}
}
```
Şu çıktıyı almalısınız:

i = 0
i = 1
i = 2
i = 3
i = 4
i = 5
i = 6
i = 7
i = 8
i = 9

Bu kod, fmt.Println işlevini kullanarak döngü değişkeni i'nin değerini konsola yazdıran myFunc fonksiyonunu tanımlar. Main func. daha sonra myFunc'ı çağırır ve i'nin 0'dan 9'a kadar olan değerlerini yazdırır.