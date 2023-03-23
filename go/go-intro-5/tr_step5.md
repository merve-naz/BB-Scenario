
## Adım 5: Go'da Debugging Araçları

Golang'da hata ayıklama için debugger ın yanı sıra, go test gibi kodun test edilmesi ve kapsama raporları oluşturulması için kullanılabilecek birkaç yerleşik araç ta bulunmaktadır. Ayrıca go pprof , CPU ve bellek kullanımını profillemek için kullanılabilir.

Golang'da hata ayıklama için go test komutunu nasıl kullanacağınızın örneğini görmek için, aşağıdaki kodu içeren main_test.go adlı yeni bir dosya oluşturun:

```main_test.go```

```
package main

import (
	"testing"
)

func TestMyFunc(t *testing.T) {
	result := 40 
	if result != 45 {
		t.Errorf("myFunc() returned %d, expected %d", result, 45)
	}
}
``` 
Bu kod, myFunc fonksiyonunu çağıran ve beklenen sonucu döndürdüğünü kontrol eden TestMyFunc adlı bir test fonksiyonu tanımlar. Testi çalıştırmak için bir terminal açın ve aşağıdaki komutu çalıştırın:


```go test```

Şu çıktıyı almalısınız:
PASS
ok      file    0.001s

Bu, testin başarıyla geçtiğini gösterir.

Test başarısız olursa, neyin yanlış gittiğini belirten bir hata mesajı yazdıracaktır.
result:=44'i şu şekilde değiştirin, böylece aşağıdakine benzer bir çıktı görebilirsiniz

--- FAIL: TestMyFunc (0.00s)
    main_test.go:10: result is 44, expected 45
FAIL
exit status 1
FAIL    file    0.003s


