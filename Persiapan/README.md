# Persiapan
## 1. Membuat Topologi Baru
Berikut adalah topologi jaringan yang akan digunakan pada modul 3 ini:

![topologi modul 3](images/topologiM3.png)

1. Hapus file UML lama bekas praktikum kemarin dengan perintah
```
rm PIKACHU MOLTRES MEWTWO ARTICUNO switch0 switch1 PSYDUCK SNORLAX
```
2. Sesuaikan script `topologi.sh` dengan gambar topologi baru di atas dengan tambahan ketentuan sebagai berikut:
	+ Memori _client_ __PSYDUCK__, __SNORLAX__, dan __CUBONE__ adalah __64M__.
	+ Memori router __PIKACHU__ adalah __256M__ karena akan menjadi DHCP Server.
	+ Memori server __ARTICUNO__ dan __MEWTWO__ adalah __128M__ karena akan menjadi DNS Server dan Proxy Server.
3. Langkah-langkah lengkapnya dapat dilihat pada [Modul Pengenalan UML](https://github.com/afrchmdi/Jarkom-Modul-Pengenalan-UML).

## 2. Konfigurasi Interface
Konfigurasi interface masih sama seperti [Modul Pengenalan UML](https://github.com/afrchmdi/Jarkom-Modul-Pengenalan-UML), dengan tambahan:
#### CUBONE (Sebagai Client)
```
auto eth0
iface eth0 inet static
address 192.168.0.4
netmask 255.255.255.0
gateway 192.168.0.1
```
## 3. Instalasi
Pada modul 3 kita akan menggunakan 3 aplikasi, yaitu:
+ __isc-dhcp-server__ (DHCP Server)
+ __squid3__ (Proxy Server)
+ __bind9__ (DNS Server)
Lakukan langkah-langkah berikut:
1. Lakukan update pada __PIKACHU__, __ARTICUNO__, dan __MEWTWO__.
```
apt-get update
```
2. Install __isc-dhcp-server__ pada router __PIKACHU__
```
apt-get install isc-dhcp-server
```
3. Install __squid3__ pada server __MEWTWO__
```
apt-get install squid3
```
4. Install __bind9__ pada server __ARTICUNO__
```
apt-get install bind9
```
# PENTING UNTUK DIINGAT!!!
Ada beberapa hal dasar yang harus dilakukan setiap kali UML dijalankan:
1. Menjalankan `iptables –t nat –A POSTROUTING –o eth0 –j MASQUERADE –s 192.168.0.0/16` pada router __PIKACHU__ agar client bisa terhubung dengan internet.
2. Menjalankan __export proxy__ pada __semua UML__ menggunakan akun VPN yang bisa didapatkan di [https://id.its.ac.id/otp/](https://id.its.ac.id/otp/).
```
export http_proxy="http://usernameVPN:passVPN@proxy.its.ac.id:8080";
export https_proxy="http://usernameVPN:passVPN@proxy.its.ac.id:8080";
export ftp_proxy="http://usernameVPN:passVPN@proxy.its.ac.id:8080";
```
Export proxy dilakukan supaya setiap UML bisa melewati proxy ITS dan bisa meng-_install_ sesuatu.

3. Melakukan `apt-get update` sebelum meng-_install_ sesuatu.

# Semoga lancar :)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ5NTgzMTA0NywtNjE3NTk2MzAsLTEzMT
AwNzA1NDIsMjE0NTAxMDUwOCw2MDcyNDIyNDJdfQ==
-->