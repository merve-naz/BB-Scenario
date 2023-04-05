
### Adım 4: Bir Dockerfile oluşturun
Kodumuz hazır olduğuna göre, mikro servisimiz için bir Docker imajı oluşturmamıza izin verecek bir Dockerfile oluşturmamız gerekiyor.

Proje dizininin kökünde Dockerfile adında yeni bir dosya oluşturun.

Dockerfile'ı metin düzenleyicinizde açın ve aşağıdaki içeriği ekleyin:
```
FROM golang:alpine

WORKDIR /app

COPY go.mod .
COPY go.sum .
RUN go mod download

COPY . .

RUN go build -o main .

EXPOSE 8080

CMD ["./main"]
```
Bu Dockerfile, resmi golang:alpine imajını temel olarak kullanır. Çalışma dizinini /app olarak ayarlar, go.mod ve go.sum dosyalarını kopyalar ve bağımlılıkları indirmek için go mod download çalıştırır.

Ardından proje dosyalarının geri kalanını kopyalar ve ikili dosyayı oluşturmak için go build çalıştırır. EXPOSE yönergesi, konteynerin 8080 portunda dinleyeceğini Docker'a bildirir ve CMD yönergesi, konteyner başlatıldığında çalıştırılacak komutu belirtir.

Dockerfile'ı kaydedin ve kapatın.