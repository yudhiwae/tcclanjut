![](images/kubectl/1.png)

[**Katacoda**](https://www.katacoda.com/courses/kubernetes/kubectl-run-containers) Start containers using Kubectl

Menggunakan Kubectl untuk membuat dan menjalankan Deployment, Kontrol Replikasi, dan mengeksposnya melalui Service tanpa menulis definisi yaml. Sehingga container dapat dijalankan dengan cepat ke dalam kluster.

## 1. Memulai Cluster

	- minikube start : perintah untuk memulai minikube.

	- kubectl get nodes : digunakan untuk mengechek apakah node telah siap

	![](images/kubectl/2.png)
	![](images/kubectl/3.png)


## 2. Menjalankan Kubectl

	Untuk menjalankan Kubectl, digunakan perintah RUN. Syntak perintahnya adalah 
	**kubectl run <name of deployment> <properties>**

	![](images/kubectl/4.png)

	Untuk melihat status deploymentnya digunakan perintah : **kubectl get deployments**

	![](images/kubectl/5.png)

	Dan untuk melihat apa saja yang telah dibuat oleh Kubernetes, proses deployment ini dapat dideskripsikan dengan perintah **kubectl describe deployment http**

	![](images/kubectl/6.png)

	Dalam deskripsi tersebut menunjukkan berapa banyak replika yang tersedia, label dan event yang terkait.

## 3. Kubectl Expose

	Perintah kubectl expose digunakan untuk menentukan berbagai parameter layanan dan cara mengekspos penyebaran.

	![](images/kubectl/7.png)
	![](images/kubectl/8.png)

	- perintah ditas digunakan untuk mengekspos port kontainer 80 pada host 8000 yang mengikat ip eksternal host.

	- Perintah curl digunakan untuk melihat hasil dari service HTTP.

## 4. Kubectl Run dan Expose

	Dalam perintah kubectl run, bisa digunakan untuk membuat deployment dan mengeksposenya dengan satu perintah saja.

	![](images/kubectl/9.png)
	![](images/kubectl/10.png)
	![](images/kubectl/11.png)
	![](images/kubectl/12.png)

	- Perintah pertama dimaksudkan untuk membuat service kedua dan mengeksposenya pada port 8001.

	- Perintah *kubectl get svc* digunakan untuk melihat service yang terdaftar.

	- Perintah *docker ps | grep httpexposed* digunakan untuk melihat detail dari service. 

## 5. Skala Container

	Pengukuran jumlah replika dari deploymen ini akan meminta Kubernetes untuk meluncurkan Pod tambahan. Pod ini kemudian akan secara otomatis dimuat seimbang menggunakan service yang terbuka.

	![](images/kubectl/13.png)

	- Perintah *kubectl scale* digunakan untuk menyesuaikan jumlah Pods yang berjalan pada deployment atau replikasi tertentu.

	- Perintah *kubectl get pods* digunakan untuk melihat list dari semua pod yang berjalan.

	![](images/kubectl/14.png)
	![](images/kubectl/15.png)

	![](images/kubectl/16.png)
	- Perintah *kubectl describe svc http* digunakan untuk mendeskripsikan service dan melihat titik akhir dan pod-pod terkait lainnya.
	
 - << [BACK](README.md)