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

![cara kerja DHCP](images/cara-ker)


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM3ODE5ODgwNywxMTMwMzczMjQ1LDIxMz
AwMjc4NjQsLTIwNzc4MzIzMTQsLTU2MTAyMTg0MiwyMDkwMzI5
MTQ4XX0=
-->