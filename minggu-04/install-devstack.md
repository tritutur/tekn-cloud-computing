## Install Devstack pada Ubuntu image 22.04
#### 1. Sebelum melakukan installasi, login pada ubuntu system dan melakukan update dengan beberapa command line berikut :</br>
<blockquote>sudo apt update</blockquote>
<blockquote>sudo apt -y upgrade</blockquote>
<blockquote>sudo apt -y dist-upgrade</blockquote>
Kemudin melakukan reboot setelah upgrade</br>

#### 2. Add Stack User</br>
Jalankan perintah di bawah ini untuk membuat pengguna penerapan DevStack :
<blockquote>sudo useradd -s /bin/bash -d /opt/stack -m stack</blockquote>
<blockquote>echo "stack ALL=(ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/stack</blockquote>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/img-1.png"/></br>

#### 3. Download DevStack
Download DevStack dilakukan dengan melakukan clone pada GitHub Devstack deployment dengan command line berikut : </br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/img-2.png"/></br>

Selanjutnya membuat file local.conf dalam direktori devstack sebagai berikut :</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/img-3.png"/></br>

#### 4. Start Openstack Deployment on Ubuntu
Installasi berjalan dengan command line :</br>
<blockquote>./stack.sh</blockquote>

<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/img-4.png"/></br>


Tunggu hingga proses installasi selesai, membutuhkan waktu sekitar 10 - 15 menit. </br>
Akan tetapi proses installasi saya mengalami error dan sampai saat ini masih belum solved. </br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/img-5.png"/></br>

Seharusnya jika installasi berhasil dan dashboard diakses maka akan mendapatkan tampilan sebagai beirkut : </br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/img-6.png"/></br>



