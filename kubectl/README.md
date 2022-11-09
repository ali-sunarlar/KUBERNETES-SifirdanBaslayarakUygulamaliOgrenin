## 🧑 Ders: kubectl

### 📗Bu bölümde "kubectl" komut kullanımı bulacaksınız📗(murataksu.net)

#### Kubectl komut yazım şekli
***
```
kubectl [command] [TYPE] [NAME] [flags]
```
***
#### Kubectl versiyon bilgisini görüntüleme
```
kubectl version
```
***
#### Kubectl versiyon bilgisini kısa görüntüleme
```
kubectl version –short
```
***
#### Cluster detaylarını görüntüleme
```
kubectl cluster-info
```
***
#### Desteklenen API sürümlerini görüntüleme
```
kubectl api-versions
```
***
#### Cluster içerisindeki tüm nodeları listeme
```
kubectl get nodes
```
***
#### Default namespacedeki tüm podları listeleme
```
# kubectl get pods
Not: Demo ortamızda nesne yoksa test amaçlı deployment nesnesi oluşturabilirsiniz
kubectl create deployment my-dep-demo --image=nginx --scale=10
```
***
#### Default namespace’deki tüm replicasetleri listeleme
```
kubectl get replicaset
```
***
#### Default namespace’deki tüm deployment’ları listeleme
```
kubectl get deployment
```
#### Default namespace’deki tüm pod,replicaset ve deployment’ları tek komutla listeleme
```
kubectl get po,rs,deploy
```
***
#### Tüm namespace'lerde bulunan podları listeleme (--all-namespaces ifadesinin kısaltması -A'dır.Tüm namespace'ler anlamına gelir)
```
kubectl get pods --all-namespaces
```
***
#### Default namespace’deki tüm pod’ları ada göre sıralayarak listeleme
```
kubectl get pods --sort-by=.metadata.name
```
***
#### Default namespace’deki tüm pod’ları yeniden başlatma sayısına göre listeleme
```
kubectl get pods --sort-by=.status.containerStatuses[0].restartCount
```
***
#### --output parametresiyle (kısaltması -o 'dur) çıktı talep edilen farklı bir formatta döndürülebilir. 
```
Örn: Default namespace’deki tüm pod’ların sadece isimlerini listeleme
kubectl get pods --output name

-o yaml Yaml formatında çıktı döndürür.
-o json Json formatinda çıktı döndürür.
-o wide Plain-text fakat daha çok bilgi içerir.
-o jsonpath=<template> Jsonpath ifadesinde tanımlanan alanları döndürür.
-o name Sadece isimleri döndürür.
-o custom-columns=<spec> Comma-seperated olarak belirtilen kolonlardan bir table döndürür.
```
***
#### Default namespace’deki tüm pod’ları ek bilgilerle listeleme (IP adresi,node ismi vb)
```
kubectl get pods --output wide
```
