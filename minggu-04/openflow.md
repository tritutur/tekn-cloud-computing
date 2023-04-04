### BELAJAR OPENFLOW</br>

#### Installing required Software</br>
Untuk melakukan installasi Virtual Machine Image dapat didownload pada : </br>
https://github.com/mininet/mininet/releases/download/2.2.2/mininet-2.2.2-170321-ubuntu-14.04.4-server-amd64.zip </br>

#### Setup Virtual Machine</br>

###### Import Virtual Machine</br>
Setelah Anda mengunduh gambar .ovf, Jalankan VirtualBox, lalu pilih </br>
File->Import Appliance dan pilih image .ovf yang telah diunduh.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/openflow-1.png"/></br>

Selanjutnya, setelah klik import, lakukan setting pada network adapter 2 dengan memilih host-only adapter, seperti berikut :</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/openflow-2.png"/></br>

Kemudian jalankan virtualbox image dan login menggunakan username dan password **mininet**</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/openflow-3.png"/></br>

###### Setting up a Host-Only Network adapter</br>
Setting interface dengan perintah :</br>
<blockquote>sudo dhclient eth1</blockquote>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/openflow-4.png"/></br>

###### Setting up Port Forwarding</br>
Untuk menyiapkan Port Forwarding menggunakan GUI, pilih VM dan buka</br>
**Settings > Network > Adapter 1 > Advance > Port Forwarding** </ber>
dan kemudian tambahkan aturan untuk meneruskan port host TCP 2222 ke port guest 22, sebagai berikut :</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/openflow-5.png"/></br>

#### SSH Connections after set up Port Forwarding</br>
Pada windows jalankan perintah </br>
<blockquote> putty.exe -X -P 2222 -l <user name> localhost</blockquote></br>
Dari perintah diatas, pop up windows akan muncul jika berhasil</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/openflow-6.png"/></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-04/openflow-7.png"/></br>

