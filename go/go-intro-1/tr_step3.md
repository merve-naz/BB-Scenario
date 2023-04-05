## 2. Egzersiz
Yeni bir sayfa oluşturalım
```
vim variables.go
```
Aşağıdaki koda 1 değişken daha ekleyelim ve kaydedip ( Esc :wq ) çalıştıralım.
```
package main
import "fmt"

func main() {

	// `var` 1 veya 1 den fazla değişkeni tanımlar
	var a = "başlangıç değeri "
	fmt.Println(a)

	// 1 seferde 1 den fazla değişken tanımlayabilirsiniz.
	var b, c int = 1, 2
	fmt.Println(b, c)

	// Go başlatılan değişkenlerin tipini algılar
	var d = true
	fmt.Println(d)

	// Değer atanmadan tanımlanan değişkenler 0 değerlidir
	var e int
	fmt.Println(e)

	// The `:=` syntax bir değişkene "initial" değeri vermek için kullanılır
	var f string = "elma"
	fmt.Println(f)

    // Aşağıda g değeri 10 olsun,fmt.Println() ile yukarıdaki örnekler gibi bastırılsın


	// İşlemi kaydedip hello.go 'dan çıkmak için "Esc" + ":" + "w" + "q" + "!" karakterlerine basıp "enter" diyelim
}
```
Çalıştırmak için,
```
go run variables.go
```
Ekranda değişkenlerin çıktısını görüyorsak devam..
