
### Adım 3: Go'da Manuel Bellek Yönetimi

Go'nun çöp toplayıcısı oldukça etkili olsa da, make() ve delete() işlevlerini kullanarak manuel olarak bellek tahsis etmek ve serbest bırakmak mümkündür. Ancak, bu genellikle daha karmaşık ve hata eğilimli kodlara yol açabileceğinden önerilmez.

Bir dilim için bellek tahsisi yapmak için make() işlevini kullanmanın bir örneğini şöyle gösterebiliriz:

```
package main

import "fmt"

func main() {
    slice := make([]int, 5, 10)
    slice[0] = 1
    slice[1] = 2
    slice[2] = 3
    slice[3] = 4
    slice[4] = 5
    fmt.Println(slice)
    // Dilim için belleği serbest bırak
    slice = nil
}
```

Bu programda, 5 uzunluğunda ve 10 kapasiteli bir tam sayı dilimi için bellek tahsisi yapmak için make() işlevini kullanıyoruz. Ardından dilimin öğelerine değer atarız ve dilimin tamamını konsola yazdırırız. Son olarak, dilim için belleği serbest bırakırız, bunu nil ile yapabiliriz.