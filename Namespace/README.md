## 🧑 Ders: Namespace

### 📗Bu bölümde YAML dosyası üzerinden Namespace Pod Yönetim işlemlerini bulacaksınız📗

#### Pod içerisindeki container1 bash üzerine bağlanma
***
```
default
kube-system
kube-public
Kube-node-lease
```
***
#### name=myLabel etiketine sahip Pod içerisindeki my-container loglarını listeleme
```
# kubectl create namespace dev
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
apiVersion: v1
kind: Namespace
metadata:
  name: dev
```
***
#### Pod içerisindeki my-container root dizini listeleme
```
kubectl run nginx --image=nginx --namespace=<insert-namespace-name-here>
```
***
#### Pod içerisindeki my-container loglarını listeleme
```
kubectl get pods --namespace=<insert-namespace-name-here>
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
# kubectl create -f  proje.yaml --namespace=dev
```
***
#### Multi-Container içerisindeki containerın 80 portuna yönlendirme
```
# kubectl exec -it proje --namespace=dev -- /bin/bash
```
