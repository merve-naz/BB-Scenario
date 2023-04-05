## 1. Go dilinde hataların anlaşılması

### Adım 1: Go dilinde hatalar nelerdir?

Go'da hatalar, bir programın yürütülmesi sırasında meydana gelen anormal bir durumu veya durumu temsil eden değerlerdir. Hatalar genellikle başarısız olabilen işlevlerden döndürülür ve neyin yanlış gittiği ve neden olduğu hakkında bilgi sağlar.

İlk olarak go paketini yükleyelim
  ```apk add go``` \
dosya oluşturalım
 ```mkdir ./error``` \
dizine gidelim
```cd ./error``` \
nano editörü ekleyelim
 ```apk add nano```  \
go dosyası oluşturalım
 ```nano error.go``` 

Go 'da hataların nasıl döndürüldüğünü görmek için, aşağıdaki komutu yapıştırın:
```
package main
import "fmt"

func main() {
	fmt.Println(1 / 0)
}
```
Ctrl + x ile kayıt et,ardından Y ,enter
error dosyasını çalıştıralım ```go run error.go``` ,

Şu çıktıyı almalısınız:
-  command-line-arguments
- ./error.go:5:18: invalid operation: division by zero

### Sonuç

Bu hata mesajı size, main.go dosyasının 4. satırındaki fmt.Println işlev çağrısında sıfıra bölme hatası oluştuğunu söyler. Devam edebilirsiniz..