
### Adım 5: Go'da Yığın Bellek ve Yığın Dışı Bellek

Go'da, iki tür bellek tahsisi vardır: yığın ve yığın dışı bellek. Yığın belleği yerel değişkenler için kullanılır ve programın işlevlere girdiğinde ve çıktığında otomatik olarak tahsis edilir ve serbest bırakılır. Yığın dışı bellek, bir dilim oluştururken veya new() işlevi ile bellek tahsisi yaparken olduğu gibi dinamik bellek tahsisi için kullanılır.

Yığın ve yığın dışı bellek arasındaki farkı göstermek için bir örneğe bakalım:

```
package main

import "fmt"

func main() {
    var x int = 42
    fmt.Println("x değişkeninin değeri:", x)
    fmt.Println("x değişkeninin bellek adresi:", &x)

    var ptr *int = new(int)
    *ptr = 100
    fmt.Println("ptr işaretçisinin değeri:", *ptr)
    fmt.Println("ptr işaretçisinin bellek adresi:", ptr)
}
```
Bu programda, bir tamsayı değişkeni olan x tanımlarız ve 42 değerini atarız. fmt.Println() işlevini kullanarak x değerini ve bellek adresini konsola yazdırırız.

Daha sonra, bir işaretçi değişkeni olan ptr tanımlarız ve new() işlevini kullanarak bir tamsayı değişkeni için bellek tahsisi yaparız.İşaretçi aracılığıyla de düzgün bir şekilde bellek ayırarak, *ptr = 100 ile değişkenin değerini 100 olarak atarız. Son olarak, fmt.Println() işlevini kullanarak ptr değişkeninin bellek adresi ve değerini yazdırırız.

Bu programı çalıştırdığımızda, şu çıktıyı elde ederiz:

x değişkeninin değeri: 42 \
x değişkeninin bellek adresi: 0xc000018078 \
ptr işaretçisinin değeri: 100 \
ptr işaretçisinin bellek adresi: 0xc00000a0c0

Gördüğümüz gibi, x değişkeni yığın bellekte ayrılmıştır ve bellek adresi main() fonksiyonunun yığın çerçevesi içindedir. ptr değişkeni ise yığın dışı bellekte ayrılmıştır ve bellek adresi yığın çerçevesinin dışındadır.