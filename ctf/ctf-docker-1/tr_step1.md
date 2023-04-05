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

5- Bunun için Dockerfile dosyasını metin editöründe açalım.

6. Dockerfile dosyasını düzelttikten sonra artık docker build alabiliriz.(Docker imajı olustururken tag   verebilirsiniz. Bu senaryo için "latest" tagini kullanınız ) 

7. Docker konteynerini çalıştırın.

8. Uygulamamız başarılı bir şekilde ayağa kalktıktan sonra containerın çalışıp çalışmadığını ve hangi portlara bağlandığını gözden geçirin.

9. Image içerisindeki dosyaları değiştirmek için ilgili komutu kullanarak çalışan bir Docker konteynerinin içine girebilirsiniz.

10. Dosya ve klasörleri gözden geçiriniz daha sonra public klasörüne gidiniz.

11. Public klasörünün içinde yer alan index.html dosyasını metin editörü ile açarak değiştirelim. "Hoşgeldiniz BB" yazısını "HOŞGELDİNİZ " olarak düzeltiniz.

- container içinden çıkalım. 

12. Docker containerını durdurun ve yeni oluşan imaj ile containerı ayağa kaldırın.

13. DockerHub'a olusturduğumuz bu imajı atmak için ilk olarak dockerhub websitesinden profil oluşturun.

14. Terminal ekranına asağıdaki komutu girin. Komut çalıstığı zaman üye oldugunuz kullanıcı adı ve şifreyi soracaktır.
``` 
docker login
```
15. Docker imajınızı Docker Hub'a yüklemek için, öncelikle imajınıza Docker Hub kullanıcı adınızı etiketlemeniz gerekir.( Eğer 6.adımda image olustururken bunu yaptıysanız buna gerek yoktur )

16. Docker image'ını Docker Hub'a push edin.
