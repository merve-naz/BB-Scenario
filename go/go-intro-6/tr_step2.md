
### Adım 2: Go'da Çöp Toplama

Go'nun bellek yönetim sisteminin temelinde, programın belleğini düzenli olarak tarayan ve artık kullanılmayan belleği belirleyip serbest bırakan çöp toplayıcısı bulunur. Çöp toplayıcısı programın yürütülmesiyle eşzamanlı olarak çalıştığı için performansı etkilemez.

Çöp toplayıcısının nasıl çalıştığını göstermek için, basit bir Go programı oluşturalım:

```
package main

import "fmt"

func main() {
    var x *int
    for i := 0; i < 10; i++ {
        x = new(int)
        *x = i
        fmt.Println(*x)
    }
}
```
Bu programda, bir tamsayı değişkeni (x) için bir işaretçi oluştururuz ve değişken için bellek tahsis etmek için new() işlevini kullanırız. Daha sonra i değerini değişkene atarız ve değeri konsola yazdırırız.

Bu programı çalıştırdığımızda, çöp toplayıcısının her bir sonraki x değişkeni için belleği serbest bıraktığını görebiliriz:

node1 # ```go run main.go ``` \
0 \
1 \
2 \
3 \
4 \
5 \
6 \
7 \
8 \
9