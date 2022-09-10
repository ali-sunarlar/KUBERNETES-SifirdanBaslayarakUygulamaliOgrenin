## 🧑 Ders: Affinity

### 📗Bu bölümde Affinity Yönetim işlemlerini bulacaksınız📗

#### Nedir ?
***
```
Affinity, Nodeselector yerine daha karmaşık ifadeler yazarak podları dilediğimiz nodelar üzerine yönlendirmenin bir diğer yoludur. 
```
#### Affinity Türleri
***
```
  Node Affinity
  Node Anti-Affinity
```
***
#### Seçim İşlemi
```
Zorunluluk:
requiredDuringSchedulingIgnoredDuringExecution
Tercih:
preferredDuringSchedulingIgnoredDuringExecution
```
***
#### Node üzerinde standart eklenen label bilgileri
```
kubernetes.io/hostname
failure-domain.beta.kubernetes.io/zone
failure-domain.beta.kubernetes.io/region
beta.kubernetes.io/instance-type
beta.kubernetes.io/os
beta.kubernetes.io/arch

```
***
#### Örn: POD'u Linux işletim sistemi üzerinde yönlendirme - Zorunlu
```
  affinity:
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
        nodeSelectorTerms:
        - matchExpressions:
          - key: kubernetes.io/os
            operator: In
            values:
            - linux
```
***
#### Örn: POD'u Linux işletim sistemlerinden -Ubuntu veya Centos - üzerine yönlendirme - Tercih
```
  affinity:
    nodeAffinity:
      preferredDuringSchedulingIgnoredDuringExecution:
      - weight: 1
        preference:
          matchExpressions:
          - key: kubernetes.io/os
            operator: In
            values:
            - ubuntu
      - weight: 50
        preference:
          matchExpressions:
          - key: kubernetes.io/os
            operator: In
            values:
            - centos
```
***
#### Örn: POD'u Linux işletim sistemi üzerinde yönlendirme 
```
  affinity:
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
        nodeSelectorTerms:
        - matchExpressions:
          - key: kubernetes.io/os
            operator: In
            values:
            - linux
```
***
#### Örn: POD'u Linux işletim sistemi üzerinde yönlendirme 
```
  affinity:
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
        nodeSelectorTerms:
        - matchExpressions:
          - key: kubernetes.io/os
            operator: In
            values:
            - linux
```
