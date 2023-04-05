
## Adım 3: Go'da Hata Yakalama

Go'da hatalar genellikle if err != nil patterni kullanılarak ele alınır. Bu pattern, bir hata nil olmadığında, yani bir hata meydana geldiğinde kontrol eder ve uygun bir işlem yapar, örneğin hatayı kaydeder veya çağıran tarafa bir hata değeri döndürür.

Golang'de hataları ele almanın örneğini görmek için aşağıdaki komutu çalıştırın:

```nano error3.go```

```
package main
import "fmt"
import "os"

func main() {
	file, err := os.Open("nonexistent-file.txt")
	if err != nil {
    fmt.Println("error opening file:", err)
    return
}
defer file.Close()
// process file...
}
```

Bu kod, mevcut olmayan bir dosya açmaya çalışır ve hata oluşursa, bir hata mesajı yazdırır ve geri döner \
Dosyayı go run dediğinizde,şu çıktıyı alırsınız: \
-error opening file: open nonexistent-file.txt: no such file or directory 

Dosya başarıyla açılırsa, defer ifadesi kullanılarak işlenir ve kapatılır.

### Sonuç

Bu bölümde, Golang'da hataları ele almak için temel kavramlar ve teknikler, hata türleri, hata ele alma kalıpları ve hata mesajları ele alındı. Bu becerileri öğrenerek, çeşitli hata koşulları ve hatalarla başa çıkabilen daha güvenilir ve sağlam Golang kodu yazabileceksiniz. Devam edelim..