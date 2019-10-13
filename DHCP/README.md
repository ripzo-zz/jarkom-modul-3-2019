## 1. Dynamic Host Configuration Protocol (DHCP)
## Outline
+ [1. Dynamic Host Configuration Protocol (DHCP)]()
	+ [Outline]()
	+ [1.1 Konsep]()
		+ [1.1.1 Pendahuluan]()
		+ [1.1.2 Apa itu DHCP?]()
		+ [1.1.3 Bootstrap Protocol dan DHCP]()
		+ [1.1.4 DHCP Message Header]()
		+ [1.1.5 Cara Kerja DHCP]()
	+  [1.2 Implementasi](https://github.com/yogamahottama/jarkom-modul-3/tree/master/DHCP-Server#12-implementasi)
		+ [1.2.1 Instalasi ISC-DHCP-Server](https://github.com/yogamahottama/jarkom-modul-3/tree/master/DHCP-Server#121-instalasi-isc-dhcp-server)
	    + [1.2.2 Konfigurasi DHCP Server](https://github.com/yogamahottama/jarkom-modul-3/tree/master/DHCP-Server#122-konfigurasi-dhcp-server)
	   + [1.2.3 Konfigurasi DHCP Client](https://github.com/yogamahottama/jarkom-modul-3/tree/master/DHCP-Server#123-konfigurasi-dhcp-client)
	   + [1.2.4 Fixed Address](https://github.com/yogamahottama/jarkom-modul-3/tree/master/DHCP-Server#124-fixed-address)
	   + [1.2.5 Testing](https://github.com/yogamahottama/jarkom-modul-3/tree/master/DHCP-Server#125-testing)
	+ [1.3 Soal Latihan](https://github.com/yogamahottama/jarkom-modul-3/tree/master/DHCP-Server#13-soal-latihan)
	+ [1.4 Referensi](https://github.com/yogamahottama/jarkom-modul-3/tree/master/DHCP-Server#14-referensi)

## 1.1 Konsep
### 1.1.1 Pendahuluan
Pada modul-modul sebelumnya, kita telah mempelajari cara mengonfigurasi IP, nameserver, gateway, dan subnetmask pada UML secara manual. Metode manual ini oke-oke saja saat diimplementasikan pada jaringan yang memiliki sedikit host. Tapi bagaimana jika jaringan tersebut memiliki banyak host? Jaringan WiFi umum misalnya. Apakah Administrator Jaringannya harus mengonfigurasi setiap host-nya satu per satu? Membayangkannya saja mengerikan, ya.

Di sinilah peran DHCP sangat dibutuhkan.

### 1.1.2 Apa itu DHCP?
__Dynamic Host Configuration Protocol (DHCP)__  adalah protokol berbasis arsitektur _client-server_ yang dipakai untuk memudahkan pengalokasian alamat IP dalam satu jaringan. DHCP secara otomatis akan meminjamkan alamat IP kepada host yang memintanya.

![cara kerja DHCP](images/cara-kerja.png)

Tanpa DHCP, administrator jaringan harus memasukkan alamat IP masing-masing komputer dalam suatu jaringan secara manual. Namun jika DHCP dipasang di jaringan, maka semua komputer yang tersambung ke jaringan akan mendapatkan alamat IP secara otomatis dari DHCP server.

### 1.1.3 Bootstrap Protocol dan Dynamic Host Configuration Protocol
Selain DHCP, terdapat protokol lain yang juga memudahkan pengalokasian alamat IP dalam suatu jaringan, yaitu Bootstrap Protocol (BOOTP). Perbedaan BOOTP dan DHCP terletak pada proses konfigurasinya.

| BOOTP | DHCP |
| --- | --- |
|Administrator jaringan melakukan konfigurasi mapping MAC Address client dengan IP tertentu. | Server akan melakukan peminjaman IP Address dan konfigurasi lainnya dalam rentang waktu tertentu. Protokol ini dibuat berdasarkan cara kerja BOOTP |

### 1.1.4 DHCP Message Header

![DHCP header]()

![DHCP header legend]()

### 1.1.5 Cara Kerja DHCP
DHCP bekerja dengan melibatkan dua pihak yakni __Server__ dan __Client__:
	1. __DHCP Server__ memberikan suatu layanan yang dapat memberikan alamat IP dan parameter lainnya kepada semua client yang memintanya.
	2. __DHCP Client__ adalah mesin client yang menjalankan perangkat lunak client yang memungkinkan mereka untuk dapat berkomunikasi dengan DHCP server.
DHCP Server umumnya memiliki sekumpulan alamat IP yang didistribusikan yang disebut DHCP Pool. Setiap client akan meminjamnya untuk rentan waktu yang ditentukan oleh DHCP sendiri (dalam konfigurasi). Jika masa waktu habis, maka client akan meminta alamat IP yang baru atau memperpanjangnya. Itulah sebabnya alamat IP client menjadi dinamis.

![DHCP Architecture]()

Terdapat 4 tahapan yang dilakukan dalam proses peminjaman alamat IP pada DHCP:
	1. __DHCPDISCOVER__: Client menyebarkan request secara broadcast untuk mencari DHCP Server yang aktif. DHCP Server menggunakan UDP port 67 untuk menerima broadcast dari client melalui port 68.
	2. __DHCPOFFER__: DHCP server menawarkan alamat IP (dan konfigurasi lainnya apabila ada) kepada client. Alamat IP yang ditawarkan adalah salah satu alamat yang tersedia dalam DHCP Pool pada DHCP Server yang bersangkutan.
	3. __DHCPREQUEST__: Client menerima tawaran dan menyetujui peminjaman alamat IP tersebut kepada DHCP Server.
	4. __DHCPACK__: DHCP server menyetujui permintaan alamat IP dari client dengan mengirimkan paket ACKnoledgment berupa konfirmasi alamat IP dan informasi lain. Kemudian client melakukan inisialisasi dengan mengikat (binding) alamat IP tersebut dan client dapat bekerja pada jaringan tersebut. DHCP Server akan mencatat peminjaman yang terjadi.
	5. __DHCPRELEASE__: Client menghentikan peminjaman alamat IP (apabila waktu peminjaman habis atau menerima DHCPNAK).

![]
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc4NDkwMDY3NywtMTEyMDU4ODc5MSwxMz
c4MTk4ODA3LDExMzAzNzMyNDUsMjEzMDAyNzg2NCwtMjA3Nzgz
MjMxNCwtNTYxMDIxODQyLDIwOTAzMjkxNDhdfQ==
-->