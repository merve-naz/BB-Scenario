## İlk Egzersiz

İlk olarak Go'yu yüklemeliyiz.
```
apk add go
```
Sayfaları oluşturuken "Vim Editörü" kullanacağız.Kısayollara hızlı bir göz atalım.

:q = Eğer yapılan değişiklikler kaydedilmişse Vim editörünü kapatır. Aksi durumda uyarı verecektir.

:q! = Editörü kaydetmeden direk olarak kapatır.

:w = Yapılan değişiklikleri kaydeder.

:wq = Yapılan değişiklikleri kaydeder ve çıkar. 

Ardından vim editöründe "hello.go" adlı ilk sayfayı oluşturalım.

```
vim hello.go
```
Açılan sayfada işlem yapabilmek için "i" harfine basarak "Insert Mode" u aktif hale getirelim ve sayfaya çalıştırmak istediğimiz kodu atalım.
Golang ile basit bir "Hello,World!" uygulaması yapalım
```
package main
import "fmt"
 
func main() {
    fmt.Println("Hello, World!")
    // İşlemi kaydedip hello.go 'dan çıkmak için "Esc" + ":" + "w" + "q" + "!" karakterlerine basıp "enter" diyelim
}
```
Ardından hello.go sayfasını çalıştıralım
```
go run hello.go
```
Not:Eğer bu adımda "bash: go: command not found" hatası aldıysanız,Go'nun yüklemeyi tekrar denemelisiniz.
Şimdi devam edebiliriz.