### Adım 1: Go Eşzamanlılığını Anlama
Go, eşzamanlı programlama yapmayı kolaylaştıran bir dildir ve aynı anda birden fazla görevi gerçekleştirmenize olanak tanır. Go'da, eşzamanlılık, gorutinler ve kanallar kullanılarak elde edilir.

### Goroutin
Goroutin ler, Go çalışma zamanı tarafından yönetilen hafif iş parçacıklarıdır. Her bir işlev için yeni bir iş parçacığı oluşturmadan fonksiyonları aynı anda yürütmeyi sağlarlar. Gorutinler, arka planda belirtilen işlevi çalıştıran go anahtar kelimesi kullanılarak oluşturulur.

Gorutin oluşturmak için bir işlev tanımlayabilir ve go anahtar kelimesini kullanarak başlatabilirsiniz:

```
package main
import "fmt"

func sayHello() {
    fmt.Println("Hello, world!")
}

func main() {
    go sayHello() // start a new goroutine
    fmt.Println("Main function")
}
```
Kaydet ve çık (Kısayol ESC + wq! )
Kodu çalıştırıken,
```go run goroutine.go``` "Hello, world!" mesajı, önceden başlatıldığı halde "Main Function" mesajından sonra yazdırılmaktadır. Bu, sayHello fonksiyonunun arka planda eşzamanlı olarak çalıştırılıyor olması nedeniyledir.