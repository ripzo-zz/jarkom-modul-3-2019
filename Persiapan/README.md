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
3. Langkah-langkah lengkapnya dapat dilihat meng
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNjU2MTU1NCw2MDcyNDIyNDJdfQ==
-->