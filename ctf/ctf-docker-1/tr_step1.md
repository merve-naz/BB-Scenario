### CTF 2.Senaryo

1. Senaryomuz için bir klasör olusturalım.
```
mkdir Senaryo
```
2. Olusturduğumuz bu klasörün içine girip, git kullanarak GitHub'tan proje reposunu kopyalayın.
```
cd Senaryo
git clone https://github.com/merve-naz/BB-Senaryo-Dockerfile-Go.git 
```
2.Projeyi Senaryo klasörümüze çektikten sonra  ls komutunu çalıştıralım.
```
ls
```
3. Burada " BB-Senaryo-Dockerfile-Go" adında bir klasör  olacaktır. Bu github'dan cektigimiz projenin adıdır. Şimdi bu klasöründe içine girelim.

```
cd  BB-Senaryo-Dockerfile-Go
```

4. Ardından ls diyerek projenin içindeki dosyaları görelim.

```
ls 
```
Bunun sonucunda şu şekilde bir çıktı almamız gerekli
 
- Dockerfile                  go.mod       main.go 
- docker-compose.yaml         go.sum       public


5. Dockerfile dosyasındaki talimatları ve yönergeleri kullanarak bir Docker imajı oluşturmamız gerekiyor fakat burada verilen Dockerfile dosyasında eksik kısımlar var. İlk olarak bunu düzeltmelisiniz.

Bunun için Dockerfile dosyasını metin editöründe açalım.

```
vi Dockerfile
```

6. Dockerfile dosyasını düzelttikten sonra artık docker build alabiliriz. Bunun için aşağıdaki komutu kullanın.
```
docker build -t my-bb-scenario-image .
```

7. Docker konteynerini çalıştırın: Bir Docker imajı oluşturduktan sonra, bu imajı bir Docker container ında çalıştırmak için aşagıdaki komutu girin.
```
docker run -d --name my-container -p 8080:80  my-bb-scenario-image
```

8. Uygulamamız başarılı bir şekilde ayaga kalktı. Bunu kontrol etmek için de `docker ps ` komutunu kullanarak  uygulamamızı içeren container'ın çalışıp çalışmadığını ve hangi portlara bağlandığını görebilirsiniz. 

9. Image içerisindeki dosyaları değiştirmek için docker exec -it komutu kullanarak bir çalışan bir Docker konteynerinin içine girebilirsiniz. Aşagıdaki komutu çalıştırın.
```
docker exec -it   my-container /bin/sh 
```

10."ls" diyerek içinde dosya ve klasörleri görebilirsiniz. Burada `cd` diyerek public klasörüne girelim
```
cd public
```
11. Public klasörünün içinde yer alan index.html dosyasını vi editörü ile açarak değiştirelim. Örnegin "Hoşgeldiniz BB" yazısına "HOŞGELDİNİZ " olarak düzeltelim ve kaydedelim.
```
vi index.html
```

```exit``` yazarak container içinden çıkalım. 

12. Docker imajınızı güncelleyin:
```
docker commit my-container myimage
```

Burada, "myimage" güncellenmiş Docker imajınızın adıdır. Artık Docker imajınız, içindeki dosyaları değiştirerek güncellendi.

13. DockerHub'a olusturdugumuz bu imajı atmak için ilk önce bu siteye girerek bir "https://hub.docker.com/" bir hesap olusturun. Eğer hesabınız varsa, create  repository diyerek yeni alan oluşturun.

14. Terminal ekranına asağıdaki komutu girin. Komut çalıstığı zaman üye oldugunuz kullanıcı adı ve şifreyi soracaktır.
``` 
docker run
```

15. Yereldeki bir imajı bir Docker hub deposuna yüklemek istiyorsanız, önce bu imajı bir etiketle belirlemelisiniz.

```
docker tag <local-image> <dockerhub-repo>/<image-name>:<tag-name>
```

```docker ımages``` diyerek de image'nin versiyonunu bulabiliriz.

örnegin `docker tag myimage  mervenaz/myimage:latest`

16. Docker image'ını Docker Hub'a push edin:
```
docker push  mervenaz/myimage:latest
```
