# Lapres Praktikum Jarkom 2022 Modul 1 Kelompok F09

## Anggota Kelompok

<table>
    <tr>
        <th>NRP</th>
        <th>Nama</th>
    </tr>
    <tr>
        <td>Muhammad Lintang Panjerino</td>
        <td>5025201045</td>
    </tr>
    <tr>
        <td>Sayid Ziyad Ibrahim Alaydrus</td>
        <td>5025201147</td>
    </tr>
    <tr>
        <td>Wahyu Tri Saputro</td>
        <td>5025201217</td>
    </tr>
<table>

<br>

## NO 1.

### Sebutkan web server yang digunakan pada "monta.if.its.ac.id"!

### **Jawab:**

Untuk mengerjakan soal 1, Open file resource terlebih dahulu pada aplikasi _Wireshark_. File resource yang dimaksud adalah file pada **soal/soal1-2.pcapng**. Kemudian dilakukan _display filter_ dengan meng-apply **http.host**. Setelah itu, pilih salah satu hasil filter (di sini kami memilih hasil filter paling atas, No. 321), kemudian klik kanan --> Follow --> TCP Stream. Setelah itu, keluar sebuah window dan dapat dilihat isinya bahwa web server yang digunakan pada "monta.if.its.ac.id" adalah **nginx/1.10.3**

Wireshark filter expression: **http.host** <br>
**Server: nginx/1.10.3**

Screenshot bukti: [screenshot](https;//github.com/mlintang20/Jarkom-Modul-1-F09-2022/img/Screenshot Soal 1.png)

## NO 2.

### Ishaq sedang bingung mencari topik ta untuk semester ini , lalu ia datang ke website monta dan menemukan detail topik pada website “monta.if.its.ac.id” , judul TA apa yang dibuka oleh ishaq ?

### **Jawab:**

Untuk mengerjakan soal 2, Open file resource terlebih dahulu pada aplikasi _Wireshark_. File resource yang dimaksud adalah file pada **soal/soal1-2.pcapng**. Kemudian dilakukan _display filter_ dengan meng-apply **http.request.uri contains "detail"**. Setelah itu, muncul satu hasil filter, kemudian klik kiri --> lihat pada bagian tengah tampilan Wireshark --> klik _Hypertext Transfer Protocol_ --> klik _GET /index.php/topik/detailTopik/194 HTTP/1.1\r\n_ --> lihat pada bagian _Request URI_. Terlihat bahwa isinya adalah **/index.php/topik/detailTopik/194**. Setelah itu, buka web browser dan ketikkan **http://monta.if.its.ac.id/index.php/topik/detailTopik/194**, dan pada web tersebut dapat terlihat judul TA yang dimaksud

Wireshark filter expression: **http.request.uri contains "detail"** <br>
**Judul TA: Evaluasi unjuk kerja User Space Filesystem (FUSE) oleh WAHYU SUADI, Rabu 17 Maret 2021 pukul 05:13:50 WIB**

## NO 3.
### filter sehingga wireshark hanya menampilkan paket yang menuju port 80!

untuk menampilkan paket yang menuju port  80 kita dapat menggunakan command 

`tcp.dst port == 80`

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/650840aa-2117-4b42-ba87-dfa261ff9a32/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220924%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220924T061938Z&X-Amz-Expires=86400&X-Amz-Signature=79ad03fba2ad72b02b78c50cffa02b2b0f38e519100db2cd225ca791d1428e79&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

dari gambar diatas didapatkan paket-paket yang menuju port 80.

## NO 4.
## Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21!

untuk mengcapture paket yang berasal dari port 21 kita dapat menggunakan command

`tcp.srcport == 21`

sehingga didapatkan hasil sebagai berikut :

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/74fef641-9353-4eb4-87ee-73be40fcb2b3/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220924%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220924T062334Z&X-Amz-Expires=86400&X-Amz-Signature=8ec51a6702e677148640db192039780a4fc0525bbe3feb2ee034bae7bdf2e277&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)
## NO 5.
## Filter sehingga wireshark hanya mengambil paket yang berasal dari port 443!

sama seperti nomer sebelumnya ,untuk mengcapture paket yang berasal dari port 443 dapat menggunakan command:

`tcp.srcport==443`

sehingga didapatkan hasil sebagai berikut :

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/afaf9dc4-a0b5-4a3a-9a10-5e5f08f88483/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220924%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220924T081930Z&X-Amz-Expires=86400&X-Amz-Signature=c9418a286baf43c61ef74003472756a0b11eed60d2702ff1a39c3721b961cea8&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)
## NO 6.
## Filter sehingga wireshark hanya menampilkan paket yang menuju ke [lipi.go.id](http://lipi.go.id/) !

untuk mengetahui paket yang menuju lipi.go.id, pertama kita harus mengetahui ip destination nya.

dengan menggunakan command:

`http contains “lipi.go.id”`

setelah didapatkan ip dari website tersebut yaitu : 203.160.128.158, kita dapat menggunakan command `ip.dst` untuk menampilkan paket yang menuju ip tersebut.

hasil :

![Untitled](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/7ad37e78-525d-44ba-ade7-663108ce70e1/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220924%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220924T082558Z&X-Amz-Expires=86400&X-Amz-Signature=d99e54883f53972ca30b573d1d96d22f53cc2460c41157d35f5afbb37e8e38d6&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)
## NO 7.

### Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

### **Jawab:**

Pada soal ini kami menggunakan IP dari salah satu anggota kami, di mana IP nya adalah 192.168.43.89, yang dapat dilihat melalui Taskbar --> Wi-Fi network --> Properties --> IPv4 address. Pada aplikasi _Wireshark_ dipilih Capture Filter Wi-Fi, kemudian setelah masuk, apply perintah pada Display Filter, yaitu **ip.src == 192.168.43.89**. Setelah itu, keluar filter yang menampilkan paket yang berasal dari IP tersebut. Captured packet disave menjadi sebuah file .pcapng dan dapat dilihat pada **soal/soal7.pcapng**

Wireshark filter expression: **ip.src == 192.168.43.89**

## NO 8.
    
### Telusuri aliran paket dalam file .pcap yang diberikan, cari informasi berguna berupa percakapan antara dua mahasiswa terkait tindakan kecurangan pada kegiatan praktikum. Percakapan tersebut dilaporkan menggunakan protokol jaringan dengan tingkat keandalan yang tinggi dalam pertukaran datanya sehingga kalian perlu menerapkan filter dengan protokol yang tersebut.

Di dalam soal No. 8, kami mencoba - coba untuk menemukan sebuah pesan tersembunyi dengan cara memfilter ip source dari ip host 127.0.1.1 dengan menggunakan filter command : `ip.src_host = 127.0.1.1`. Kemudian kami melihat ternyata ada sebuah pesan tersembunyi dari ip tersebut.

SS

## Kendala

Kendala yang kami alami adalah pertama kami mencoba memfilter port, tetapi comman filter di wireshark tidak bekerja sehingga kami mengganti dengan cara mencoba memfilter ip source.

## NO 9.

### Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam percakapan yang diperoleh, carilah file yang dimaksud! Untuk memudahkan laporan kepada atasan, beri nama file yang ditemukan dengan format #[nama_kelompok].des3 dan simpan output file dengan nama #“flag.txt”..

## NO 10.
