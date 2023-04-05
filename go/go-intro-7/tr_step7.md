### Adım 7: Mikro servisi bir konteyner yönetim platformuna dağıtın
Mikro servisimizi yüksek kullanılabilirliğe ve ölçeklenebilirliğe sahip hale getirmek için Kubernetes veya Docker Swarm gibi bir konteyner yönetim platformuna dağıtabiliriz. Bu adımda, mikro servisimizi bir Kubernetes kümesine dağıtacağız.

İlk olarak, bir Kubernetes kümesine sahip olduğunuzdan emin olun. Google Cloud Platform veya Amazon Web Services gibi bir bulut sağlayıcısını kullanarak bir Kubernetes kümesi oluşturabilirsiniz.

Ardından, mikro servisimiz için bir Kubernetes dağıtımı oluşturmak için bir dağıtım YAML dosyası oluşturun. İşte bir YAML dosyası örneği:

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: hello-go
spec:
  replicas: 3
  selector:
    matchLabels:
      app: hello-go
  template:
    metadata:
      labels:
        app: hello-go
    spec:
      containers:
      - name: hello-go
        image: <sizin-docker-registry>/hello-go:v1
        ports:
        - containerPort: 8080
```
Bu YAML dosyası, mikro servisimizin 3 replikasından oluşan bir dağıtım oluşturur ve mikro servisimizin konteynerinin 8080 portunda dinlemesini belirtir.

Aşağıdaki komutu kullanarak dağıtım YAML dosyasını Kubernetes kümesine uygulayın:

```
kubectl apply -f deployment.yaml
```
Bu komut, Kubernetes kümesinde dağıtımı oluşturacaktır.

Aşağıdaki komutu kullanarak dağıtımı bir Kubernetes servisi olarak açığa çıkarın:
```
kubectl expose deployment hello-go --type=LoadBalancer --port=80 --target-port=8080
```
Bu komut, dağıtımı yük dengeleyicili bir servis olarak 80 portunda açığa çıkarır.

Aşağıdaki komutu kullanarak yük dengeleyicisinin harici IP adresini alın:

```
kubectl get services
```
Bu komut, yük dengeleyicisinin harici IP adresini çıktı olarak verir. Bu IP adresini, Kubernetes kümesi dışından mikro servise erişmek için kullanabilirsiniz.

Mikro servisi test etmek için HTTP istekleri göndererek yük dengeleyicisinin harici IP adresine gönderin. Mikro servisten yanıt almalısınız.
Bu adımları izleyerek, mikro servisinizi bir konteyner yönetim platformuna dağıttınız ve yüksek kullanılabilir ve ölçeklenebilir hale getirdiniz.