### CTF 2.Senaryo

1. Projeyi ilgili adresten çekin.
```
https://github.com/merve-naz/BB-Senaryo-Dockerfile-Go.git 
```
2. Projeyi Senaryo klasörümüze çektikten sonra listeleyerek içindekileri görebilirsiniz.

3. Burada " BB-Senaryo-Dockerfile-Go" adında bir klasör olacaktır. Bu github'dan cektigimiz projenin adıdır. Şimdi bu klasöründe içine gidiniz.

Bu çıktıyı görüyorsanız,devam edebilirsiniz.
- Dockerfile                  go.mod       main.go 
- docker-compose.yaml         go.sum       public

4. Dockerfile dosyasındaki talimatları ve yönergeleri kullanarak bir Docker imajı oluşturmamız gerekiyor fakat burada verilen Dockerfile dosyasında eksik kısımlar var. İlk olarak bunu düzeltmelisiniz.

5- Bunun için Dockerfile dosyasını metin editöründe açalım.(default olarak vi editörü ile bunu yapabiliriz.)

6. Dockerfile dosyasını düzelttikten sonra artık docker build alabiliriz.Aşagıdaki gibi bir komut kullanabilir.

docker build -t <image_name>:<tag> <Dockerfile_directory>

Burada  bulundugumuz dizinde Dockerfile oldugu için "." ve tag olarak 'da latest diyerek düzenleyebiliriz yani 

docker build -t <yeni_image_name>:latest . 


7.Aşagıdaki komutta  gerekli kısımları doldurarak  Docker konteynerini çalıştırın.(İpucu: Github'dan çekilen go projesinde main.go'ya bakarsak host_port:8080 olduguna görecegiz.)

docker run -p  <host_port>:<container_port>  --name <container_name> <image-ismi>:latest

8. Uygulamamız başarılı bir şekilde ayağa kalktıktan sonra containerın çalışıp çalışmadığını ve hangi portlara bağlandığını gözden geçirin.Bunun için " docker ps " komutunu kullanabilirsiniz.


9. Image içerisindeki dosyaları değiştirmek için ilgili komutu kullanarak çalışan bir Docker konteynerinin içine girebilirsiniz.

docker exec -it <container_id> /bin/bash

Not: <container_id> yerine  <container_name> 'de olabilri.

10. Dosya ve klasörleri gözden geçiriniz daha sonra public klasörüne gidiniz.

11. Public klasörünün içinde yer alan index.html dosyasını metin editörü (vi editör) ile açarak değiştirelim. "Hoşgeldiniz BB" yazısını "HOŞGELDİNİZ " olarak düzeltiniz.

- "exit" komutunu çalıştırarak container içinden çıkalım. 

12. Image içerisindeki dosyalar değiştirildiğinde, Docker container da  durdurması ve yeni değişikliklerin image'e yansıması için image'in baştan build edilmesi  gerekmektedir.Bunun için aşagıdaki komutları kendi degerlerinize göre uygulayın.

docker stop <container_name_or_id>
docker rmi <image_name_or_id>

* Not:Image id ogrenmek için de docker ımages komutunu kullanabilirsiniz.

13. Yeni Docker imajını oluşturun.Burada  olusturacagınız ımage'ın Docker Hub hesabınızda  yer alacaktır.Bu yuzden aşagıdaki komutu olarak  ımage olusturun.

docker build -t <Docker_Hub_Kullanıcı_Adı>/<Image_Adı>:latest .

Eger docker hub hesabınız yoksa aşagıdaki komutu kullanara daha sonra docker hub'a atarken de ımajı etiketleyebilirisiniz.

docker build -t /<Image_Adı>:latest .

14. Yeni image ile docker container'ı ayağa kaldırın.

docker run -d --name <container_name> -p 8080:<container_port> <yeni_image_name>:latest

Docker ps yazarak uygulamanızın ayaga kalkıp kalmadıgı  kontrol edebilirsiniz.

15. DockerHub'a olusturduğumuz bu imajı atmak için ilk olarak dockerhub websitesinden profil oluşturun.

16. Terminal ekranına asağıdaki komutu girin. Komut çalıstığı zaman üye oldugunuz kullanıcı adı ve şifreyi soracaktır.
``` 
docker login
```
17. Docker imajınızı Docker Hub'a yüklemek için, öncelikle imajınıza Docker Hub kullanıcı adınızı etiketlemeniz gerekir.( Eğer image olustururken bunu yaptıysanız buna gerek yoktur )


docker tag <image_id> <Docker_Hub_Kullanıcı_Adı>/<Image_Adı>:latest


18. Docker image'ını Docker Hub'a push edin.
docker push <Docker_Hub_Kullanıcı_Adı>/<Image_Adı>:latest
