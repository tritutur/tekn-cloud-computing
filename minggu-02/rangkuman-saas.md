## Rangkuman Materi Cloud Computing Minggu ke 02

### 1. Perbedaan IaaS, PaaS, SaaS
#### A. Infrastructure as a Service (IaaS)
IaaS merupakan tingkatan paling mendasar pada Cloud Computing. IaaS memungkinkan para pengguna untuk dapat memiliki akses peyimpanan maupun sumber daya dalam bentuk virtual mesin yang dapat diakses melalui terminal atau mekanisme remote desktop dengan menggunakan alamat pada IP. Pada Iass pengguna bertanggung jawab untuk mengelola dan memelihara server dan semua komponen didalamnya sehingga dapat sesuai dengan kebutuhan masing masing. Contoh dari IaaS ini seperti Amazon Web Services dan Google Cloud Platform. </br>

#### B. Platform as a Service (PaaS)
Platform as a service memungkinkan pengguna untuk mengembangkan, mengelola, dan menyebarkan hasil perangkat lunak pada infrastruktur cloud. Platform as a service menyediakan kumpulan data lengkap yang menghadirkan kerangka kerja dan sumberdaya yang diperlukan dalam pengembangan aplikasi. Keunggulan dari PaaS adalah High Availability, Monitoring, Scale/Descale deployment yang mudah, serta pengurangan biaya dan waktu pengembangan. Contoh Platform as a Service adalah Heroku. </br>

#### C. Software as a Service (SaaS)
SaaS merupakan model cloud computing yang paling populer. SaaS memungkinkan pengguna untuk mengakses aplikasi tanpa perlu menginstall pada perangkat yang dimilikinya. SaaS didasarkan pada aplikasi yang dijalankan dari jarak jauh yang disediakan oleh vendor dan diakses pelanggan melalui internet atau API. Contoh SaaS seperti Dropbox, Troop Messenger, Shopify dan sebagainya.</br>

### 2. SaaS Platform Arsitektur
SaaS merupakan layanan perangkat lunak yang dilisensikan berdasarkan langganan dan dihosting secara terpusaat yang dapat diakses dengan bantuan web browser. Dengan begitu, satu versi aplikasi dengan satu konfigurasi dapat digunakan oleh banyak pelanggan. Terdapat dua varietas utama SaaS adalah SaaS Vertikal yang menyediakan perangkat lunak untuk kebutuhan idustri tertentu seperti keseharan, pertanian dan keuangan. Sedangkan variasi kedua yakni SaaS Horisontal yang berfokus pada kategori perangkat lunak seperti untuk pemasaran, penjualan tetapi agnostik industri.</br>
Manfaat SaaS : </br>
Dengan memanfaatkan SaaS, sebuah perusahaan dapat menerapkan sistem perangkat lunak berskala besar kepada sistem yang lebih terpusat sehingga dapat menghemat dari segi biaya, waktu, dan sumber daya. Integrasi dapat direncanakan dan dilaksanakan dengan upaya minimal, menciptakan salah satu interval waktu tersingkat yang memungkinkan untuk investasi TI yang besar.</br>

Penambahan SaaS dapat menyebabkan perubahan mendasar dalam peran departemen TI sebagai penyedia layanan informasi karena kendali pusat data tidak harus sama dengan kendali atas seluruh lingkungan komputasi perusahaan.</br>

### 3. Struktur Platform SaaS
##### Apa itu Platform Arsitektur SaaS
SaaS merupakan salah satu pilar utama dalam cloud computing. SaaS mengirimkan perangkat lunak secara terpusat dan menghostingnya agar membuatnya tersedia untuk pelanggan melalui internet.</br>
##### Mengapa menggunakaan Arsitektur SaaS
**Dari Sudut pandang konsumen**, Saas merupakan cara termudah untuk menggunakan layanan produk digital karena cukup membayar dan dapat mengakses sumber daya yang disediakan sesuai kebutuhan. Selain itu pengguna tidak perlu membayar lagi untuk lisensi perangkat.</br>
**Dari Sudut pandang bisnis**, produk perangkat lunak dalam as a service memungkinkan bisnis untuk menawarkan produknya dalam skala besar dan global, serta terpusat sehingga memungkinkan untuk mempertahankan kontrol atas produk mereka.</br>
##### Fitur Utama dan Manfaat Platform Arsitektur SaaS
Beberapa manfaat yang diperoleh dari Platform arsitektur SaaS diantaranya :</br>
The simplicity of SaaS Architecture Apps</br>
Aplikasi dalam SaaS diakses melalui web dari berbagai perangkat, kemajuan bahasa pemrograman menghasilkan antarmuka yang intuitif sehingga semudah sebagaimana aplikasi desktop.</br>
Economical Value</br>
Kemudahan dan kemurahan biaya berlangganan membuat banyak perusahaan memiliki budget yang cukup, dan bahkan lebih menghemat dari metode yang sebelumnya.</br>
Security</br>
Keamanan dalam platform SaaS terjamin karena data tersimpan aman dalam cloud, sehingga pengguna tidak perlu mengkhawatirkan aspek terpenting ini.</br>
Compatibility</br>
Dengan penginstalan perangkat lunak tradisional, pembaruan dan tambalan terkadang membutuhkan banyak waktu dan uang. Ini terutama berlaku di perusahaan.</br>
##### Pertimbangan Desain untuk Platform Arsitektur SaaS</b>
**Scalability**
Arsitektur SaaS harus dapat menskalakan dan mengakomodasi banyak pengguna dalam waktu yang bersamaan. Hal ini dapat diperoleh dengan menggunakan perangkat keras seperti Network Load Balancers untuk mendistribusikan lalu lintas secara merata didalam server web.</br>
**Zero downtime and Service Level Agreements**
Pembangunan SaaS harus dapat mempertimbangkan kapan waktu yang tepat untuk pemutakhiran, debugging dan pemecahan masalah produksi kedalam aplikasi SaaS. Selain itu pengembang harus memastikan bahwa resource dapat menangani permintaan pengguna untuk membenahi masalah umum bahkan kompleks.</br>
**Multi-tenancy in SaaS architecture**
Agar aplikasi yang dibangun dapat dikirim sebagai produk SaaS harus mendukung multi-penyewa dengan arti bahwa produk dapat mengakomodasi banyak pengguna sekaligus dengan mempertimbangkan data dan privasi pengguna.