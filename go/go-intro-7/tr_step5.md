### Adım 5: Docker imajı oluşturma
Artık Dockerfile'ımız var, bu yüzden mikroservisimiz için bir Docker imajı oluşturabiliriz.

Bir terminal açın ve projenizin kök dizinine gidin.

Aşağıdaki komutu kullanarak Docker imajını oluşturun:

```
docker build -t my-go-microservice .
```
Bu komut, my-go-microservice etiketiyle bir Docker imajı oluşturur. . Docker'a, mevcut dizini derleme bağlamı olarak kullanmasını söyler.

Derlemenin tamamlanmasını bekleyin. Bu, internet bağlantınıza ve projenizin boyutuna bağlı olarak birkaç dakika sürebilir.

Adım 6: Docker konteynerının çalıştırılması
Artık bir Docker imajımız var, bu imajdan bir Docker konteynerı çalıştırabiliriz.

Aşağıdaki komutu kullanarak Docker konteynerını başlatın:

```
docker run -p 8080:8080 my-go-microservice
```
Bu komut, my-go-microservice imajından yeni bir Docker konteynerı başlatır ve konteynerdaki 8080 numaralı bağlantı noktasını yerel makinenizdeki 8080 numaralı bağlantı noktasına eşler.

Port kısayolu ile 8080 adresine gidin. "Hello, World!" mesajını görmelisiniz.
[!go_port_icon.PNG](https://gitlab.bulutbilisimciler.com/bb-public/scenarios/-/raw/master/go/Assets/go_port_icon.PNG)

Tebrikler! Go ile bir mikroservis oluşturdunuz ve Docker konteynerında dağıttınız. Bir sonraki adımda, bu konteynerı bir bulut platformuna nasıl dağıtacağımızı öğreneceğiz.