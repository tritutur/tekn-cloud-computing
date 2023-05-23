### Install Docker Engine on Ubuntu Using the apt Repository</br>
#### Set up the repository </br>
1. Update apt package index dan install packages untuk memungkinkan apt penggunaan repositori melalui HTTPS dengan perintah berikut :</br>
  <blockquote> sudo apt-get update</br>
  sudo apt-get install ca-certificates curl gnupg
  </blockquote></br>
  <img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-07/install-01.PNG"/></br>
2. Menambahkan official GPG key, dengan menjalankan beberapa perintah berikut</br>
<blockquote>sudo install -m 0755 -d /etc/apt/keyrings </br>
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg </br>
sudo chmod a+r /etc/apt/keyrings/docker.gpg
</blockquote></br>

Serta gunakan command berikut untuk melakukan set up pada repositori :
<blockquote>echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
</blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-07/install-02.PNG"/></br>

#### Install Docker Engine </br>
Untuk melakukan install docker engine, containered dan docker compose gunakan perintah sebagai berikut :
<blockquote>sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
</blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-07/install-03.PNG"/></br>

Setelah proses installasi selesai, jalankan perintah berikut untuk memastikan bahwa docker telah berjalan dengan baik :
<blockquote>sudo docker run hello-world</blockquote></br>
<img src="https://github.com/tritutur/tekn-cloud-computing/blob/main/minggu-07/install-04.PNG"/></br>
