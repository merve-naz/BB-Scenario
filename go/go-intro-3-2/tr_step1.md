#### Level: Orta
### Senaryo: Go Standard kütüphanesini kullanarak statik dosyalara hizmet veren bir web sunucusu oluşturma 
 
1. Go projeniz için go ve 
```
apk add go
```
nano yu yükleyelim.
```
apk add nano
```
2. Nano veya vim gibi bir metin editörü kullanarak main.go adında yeni bir dosya oluşturun:
```
nano main.go
```
3. main.go dosyasında, Go standart kütüphanesinden net/http paketini içe aktarın ve belirtilen bir dizindeki (bu durumda public dizini) statik dosyaları sunacak bir handler function tanımlayın:
```
package main

import (
    "fmt"
    "log"
    "net/http"
)

func main() {
    http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
        if r.URL.Path == "/" {
            http.ServeFile(w, r, "public/index.html")
            return
        }
        http.ServeFile(w, r, "public"+r.URL.Path)
    })

    fmt.Println("Starting server on http://localhost:8080")
    log.Fatal(http.ListenAndServe(":8080", nil))
}
```
4. Statik dosyalarınızı (ör. HTML, CSS, JavaScript) içerecek olan public adlı yeni bir dizin oluşturun:
```
mkdir public && cd public
```
5. public dizininde index.html adlı bir dosya oluşturun:
```
nano index.html
```

İsterseniz arkaplan rengini değiştirebilirsiniz
```
<table style="background-color:#33475b">
<tr>
<th>Name</th>
<th>Job Title</th> 
</tr>
<tr>
<td>Bulut Bilisimciler</td>
<td>Learner</td>
</tr>
</table>
```
Kaydet ve Çık -> Ctrl + x ve Y
7. Aşağıdaki komutu çalıştırarak sunucuyu başlatın:
```
go run main.go
```

8. Web tarayıcınızı açmak node un üstündeki kısayol ile port 8080 e gidin "Bulut Bilişimciler" mesajı mavi bir arka plan rengiyle görüntülenecektir.

Diğer statik dosyaları sunmaya yönelik testler yapmak için resim, JavaScript veya CSS dosyası gibi herhangi bir dosyayı public dizinine ekleyin ve tarayıcıda erişmeyi deneyin.

Tebrikler, Go standart kütüphanesini kullanarak bir web sunucusu oluşturmayı başardınız!
