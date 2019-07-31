![](images/yaml/1.png)

[**Katacoda**](https://www.katacoda.com/courses/kubernetes/creating-kubernetes-yaml-definitions) Deploy Containers Using YAML

# Membangun Container menggunakan YAML

Objek Deployment mendefinisikan spesifikasi container yang diperlukan, bersama dengan nama dan label yang digunakan oleh bagian lain dari Kubernetes untuk menemukan dan menghubungkannya ke aplikasi.

## 1. Membuat Deployment

- Menambahkan definisi object deployment pada file deployment.yaml
Apllikasi yang dijalankan bernana webapp1 menggunakan docker image katacoda/docker-http-server yang berjalan pada port 80.
   
![](images/yaml/2.png)

![](images/yaml/3.png)

- kubectl create -f deployment.yaml : digunakan untuk mendeploy file deployment.yaml ke dalam cluster

- kubectl get deployment : digunakan untuk menunjukkan list semua deployment object

![](images/yaml/5.png)

- kubectl describe deployment webapp1 : digunakan untuk menunjukkan detail dari deployment

## 2. Membuat Service

Kubernetes memiliki kemampuan jaringan yang kuat yang mengontrol bagaimana cara aplikasi berkomunikasi. Konfigurasi jaringan ini juga dapat dikontrol melalui YAML.

![](images/yaml/5.png)

- Service membuat aplikasi tersedia melalui NodePort.

![](images/yaml/6.png)

- perintah tersebut digunakan untuk mendeploy file service.yaml

![](images/yaml/7.png)

- perintah ini digunakan untuk melihat deskripsi objek, sehingga didapatkan informasi lebih detail tentang konfigurasinya.

![](images/yaml/8.png)

## 3. Mengukur Deployment

Rincian dari YAML dapat diubah karena konfigurasi yang berbeda diperlukan dalam deployment.
   
![](images/yaml/9.png)

Pada file deployment.yaml nilai replicas diganti menjadi 4 untuk meningkatkan jumlah instance yang berjalan.

![](images/yaml/10.png)

- Perintah *kubectl apply* digunakan untuk menerapkan pembaruan definisi yang dilakukan.

- Perintah *kubectl get deployment* digunakan untuk melihat status dari kluster yang telah diubah.
   
- << [BACK](README.md)