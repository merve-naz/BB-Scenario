
### Adım 2: Go'da Hata Tipleri

Go dilinde hatalar, bir metot olan Error() string ,error interface ile temsil edilir,hatayı gösteren bir string döndürür(return). Ayrıca, özel hata mesajları oluşturmanıza olanak tanıyan fmt.Errorf gibi birkaç yerleşik(built-in) hata türü de bulunmaktadır.

Golang'da özel bir hata oluşturup görmek için, ilk olarak aşağıdaki komutu çalıştırın:
```nano error2.go```

```
package main
import "errors"
import "fmt"

func main() {
	err := myFunc()
	if err != nil {
    	fmt.Println(err)
	}
}
func myFunc() error {
    return errors.New("something went wrong")
}
```
çalıştıralım ```go run error2.go``` \
Şu çıktıyı almalısınız:

- something went wrong

Bu kod, error.New fonksiyonunu kullanarak özel bir hata mesajı döndüren bir myFunc fonksiyonunu tanımlar. Main fonksiyonu daha sonra myFunc'u çağırır ve döndürülen hata mesajını yazdırır. Adım 3'e geçelim..
