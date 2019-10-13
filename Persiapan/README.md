# Persiapan
## 1. Membuat Topologi Baru
Berikut adalah topologi jaringan yang akan digunakan pada modul 3 ini:

![topologi modul 3](img/topologiM3.png)

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
# PENTING UNTUK 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTUyMzMyNTU0NiwyMTQ1MDEwNTA4LDYwNz
I0MjI0Ml19
-->