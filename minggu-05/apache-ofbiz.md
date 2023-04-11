### Install Apache OFBiz
###### 1. Memastikan bahwa Java sudah terinstall
Sebelum melakukan installasi Apache OFBiz terlebih dahulu perlu dilakukan pengecekan apakah java sudah terinstall dengan command line seperti dibawah ini :</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-05/ofbiz-01.PNG"/></br>

###### 2. Melakukan Download Apache OFBiz</br>
Unduh versi terbaru Apache OFBiz dari situs unduhan resminya atau menggunakan mirror.</br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-05/ofbiz-02.PNG"/></br>

Setelah download selesai, lakukan extract file yang telah berhasil didownload denggan perintah :</br>
<blockquote>unzip apache-ofbiz-18.12.05.zi</br> 
mv apache-ofbiz-18.12.05 /usr/local/apache-ofbiz</br>
rm -f apache-ofbiz-18.12.05.zip</blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-05/ofbiz-03.PNG"/></br>

###### 3. Installing Apache OFBiz</br>
Untuk melakukan installasi jalankan command line berikut :</br>
<blockquote>cd /usr/local/apache-ofbiz</br>
./gradle/init-gradle-wrapper.sh</blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-05/ofbiz-04.PNG"/></br>

Sekarang bersihkan sistem dan muat data OFBiz lengkap menggunakan perintah gradlew berikut.</br>
<blockquote>./gradlew cleanAll loadAll </blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-05/ofbiz-05.PNG"/></br>