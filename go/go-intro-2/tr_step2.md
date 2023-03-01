#### Kanallar(Channels)
Kanallar, gorutinler arasında iletişim kurmak için kullanılır. Bir gorutinden diğerine değer göndermenizi ve almanızı sağlar. Kanallar, paylaşılan kaynaklara erişimi senkronize etmek veya programın farklı bölümleri arasında veri aktarmak için kullanılabilir.

Kanal oluşturmak için make işlevi kullanılabilir:

ch := make(chan int) // bir tamsayı kanalı oluştur

Bir değeri kanaldan göndermek için <- operatörü kullanılabilir:

ch <- 10 // değeri kanaldan gönder
Bir kanaldan bir değer almak için aynı operatör kullanılabilir:

x := <-ch // kanaldan bir değer al ve x değişkenine kaydet
Gorutinleri ve kanalları birlikte nasıl kullanabileceğinize dair bir örnek çalıştıralım. İlk olarak yeni sayfa oluşturalım.
```vim channel.go```
Kodları atalım.
```
package main
import "fmt"
func sum(values []int, result chan int) {
    sum := 0
    for _, v := range values {
        sum += v
    }
    result <- sum // toplamı channel a gönder
}

func main() {
    values := []int{1, 2, 3, 4, 5}

    result := make(chan int)
    go sum(values[:len(values)/2], result) // sum ı gorutinde çalıştır
    go sum(values[len(values)/2:], result) // sum ı gorutinde çalıştır

    x, y := <-result, <-result // kanaldan toplamları al
    fmt.Println(x + y) 
}
```
Kaydet ve çık (Kısayol ESC + wq! )
Kodu çalıştırıken,
```go run channel.go```
Bu örnekte, sum fonksiyonu bir tam sayı dilimi toplamını hesaplar ve sonucu kanal aracılığıyla gönderir. Ana işlev, dilimin yarısını hesaplamak için iki gorutin çalıştıran sum işlevini çalıştırır. Sonuçlar daha sonra kanaldan alınır ve toplanarak son toplam elde edilir.Sonuç 15 se devam edebiliriz.