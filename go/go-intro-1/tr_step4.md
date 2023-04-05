## 3. Egzersiz
# Challenge Variables
Ekrana adınızı,soyadınızı,yaşınızı ve öğrenci olma durumunuzu yazdıran kodu yazınız.
ad        -> string
soyad     ->string
yaş       ->integer
öğrenci mi->boolean

Yeni bir sayfa oluşturalım
```
vim variables2.go
```
Örnek Kod:
```
package main
import "fmt"

func main() {
    age := 25
    name := "Alice"

    fmt.Println("Name:", name)
    fmt.Println("Age:", age)
}
```
Kodu yazalım ("i " insert mode için ) ve kaydedip çıkalım ( Esc + wq )
Çalıştıralım
```
go run variables2.go
```
Çıktı düzgünse başardınız demektir,Golang de değişken tanımlamak bu kadar kolay :)
