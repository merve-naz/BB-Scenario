
### Adım 4: Go'da İşaretçi Kullanımı

İşaretçiler, başka değişkenlerin bellek adreslerini depolayan değişkenlerdir. Go'da, işaretçi bir değişkeni * sembolü kullanarak tanımlayabilirsiniz. İşte bir örnek:

```
package main

import "fmt"

func main() {
    var x int = 42
    var ptr *int = &x
    fmt.Println(*ptr)
}
```
Bu programda, bir tamsayı değişkeni (x) tanımlarız ve 42 değerini atarız. Ardından, bir işaretçi değişkeni (ptr) tanımlarız ve & sembolünü kullanarak bellek adresini x değişkenine atarız. Son olarak, işaretleyiciyi indirgeme sembolü (*) kullanarak x değerini konsola yazdırırız.