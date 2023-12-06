# Jarkom-Modul-4-IT28-2023
**Praktikum Jaringan Komputer Modul 4 Tahun 2023**

## Anggota
| Nama | NRP |
|---------------------------|------------|
|Yoga Hartono| 5027211023| 
|Athallah Narda Wiyoga| 5027211041| 

# Laporan Resmi


## Soal
Berikut gambar topologi yang harus dibuat

![topologiCPT](https://cdn.discordapp.com/attachments/1067327620938747946/1181917906729193493/Screenshot_2023-12-06_at_18.19.39.png?ex=6582cdd3&is=657058d3&hm=b803d6359510e6c6f9bcbee2eb27cb8006e5786a5a96eac0854221a9f230274b&)


1. Soal shift dikerjakan pada Cisco Packet Tracer dan GNS3 menggunakan metode perhitungan CLASSLESS yang berbeda.
Keterangan: Bila di CPT menggunakan VLSM, maka di GNS3 menggunakan CIDR atau sebaliknya
2. Jika tidak ada pemberitahuan revisi soal dari asisten, berarti semua soal BERSIFAT BENAR dan DAPAT DIKERJAKAN.
Untuk di GNS3 CLOUD merupakan NAT1 jangan sampai salah agar bisa terkoneksi internet.
3. Pembagian IP menggunakan Prefix IP yang telah ditentukan pada modul pengenalan
4. Pembagian IP dan routing harus SE-EFISIEN MUNGKIN.

## Jawaban
### Metode VLSM Menggunakan CPT
Langkah pertama yaitu membuat tree IP seperti tabel berikut ini

![Screenshot 2023-11-28 235649](https://cdn.discordapp.com/attachments/1067327620938747946/1180540708927590410/Screenshot_2023-12-02_at_23.07.11.png?ex=657dcb36&is=656b5636&hm=b804b326fcf9502d14a7fd22ce55e469efdf974b762b14be93dd3cf25a31e2a2&)


Setelah dilakukannya pembuatan tree, maka buatlah perhitungan pembagian IP tersebut seperti gambar berikut ini

|Subnet	  |Rute Subnet	|Jumlah IP  |	Netmask| Network ID | IP Netmask | Broadcast |
|---------|---------|---------|---------|---------|---------|---------|
|A5|Aura-Frieren-Flamme-Fern-Switch4-LaubHills-Switch4-AppetittRegion |1023| /21| 192.247.0.0	| 255.255.248.0	| 192.247.7.255|
|A6|Aura-Frieren-Flamme-Switch5-RohrRoad |1001|	/22| 192.247.8.0 |	255.255.252.0 |	192.247.11.255|
|A13|	Aura-Eisen-LugnerSwitch10-TurkRegion |1001|	/22| 192.247.12.0 |	255.255.252.0	| 192.247.15.255 |
|A18|Aura-Eisen-Linie-Lawine-Heiter-Switch8-Sein-Switch8-RiegelCanyon |512|	/22| 192.247.16.0 | 255.255.252.0 |	192.247.19.255|
|A19|	Aura-Eisen-Linie-Switch11-GranzChannel |255|	/23| 192.247.20.0	 | 255.255.254.0	| 192.247.21.255| 
|A14|	Aura-Eisen-Lugner-Switch9-GrobeForest |251|	/24| 192.247.22.0 |	255.255.255.0	| 192.247.22.255|
|A21|	Aura-Denken-Switch2-RoyalCapital-Switch2-WilleRegion |127|	/24| 192.247.23.0 |	255.255.255.0 |	192.247.23.255|
|A17|	Aura-Eisen-Linie-Lawine-Heiter-Switch7-BredtRegion |31|	/26| 192.247.24.0	| 255.255.255.192 |	192.247.24.63|
|A2|	Aura-Frieren-Switch3LakeKorridor |25|	/27| 192.247.24.64	| 255.255.255.224 |	192.247.24.95|
|A8|	Aura-Frieren-Flamme-Himmel-Switch6-SchwerMountains |6|	/29| 192.247.24.96 |	255.255.255.248 |	192.247.24.103|
|A10|	Aura-Eisen-Switch1-Richter-Switch1-Revolte |3|	/29| 192.247.24.104 |	255.255.255.248 |	192.247.24.111|
|A1|	Aura-Frieren |2|	/30| 192.247.24.112	| 255.255.255.252 |	192.247.24.115|
|A3|	Aura-Frieren-Flamme	|2|	/30| 192.247.24.116	255.255.255.252	192.247.24.119|
|A4|	Aura-Frieren-Flamme-Fern	|2|	/30| 192.247.24.120	255.255.255.252	192.247.24.123|
|A7|	Aura-Frieren-Flamme-Himmel	|2|	/30| 192.247.24.124	255.255.255.252	192.247.24.127|
|A9|	Aura-Eisen	|2|	/30| 192.247.24.128	| 255.255.255.252	| 192.247.24.131|
|A11|	Aura-Eisen-Switch0-Stark	|2|	/30| 192.247.24.132 |	255.255.255.252	| 192.247.24.135|
|A12|	Aura-Eisen-Lugner	|2|	/30| 192.247.24.136 |	255.255.255.252	| 192.247.24.139|
|A15|	Aura-Eisen-Linie	|2|	/30| 192.247.24.140 |	255.255.255.252	| 192.247.24.143|
|A16|	Aura-Eisen-Linie-Lawine	|2|	/30| 192.247.24.144	| 255.255.255.252 |	192.247.24.147|
|A20|	Aura-Denken	|2|	/30| |192.247.24.148 |	255.255.255.252 |	192.247.24.151|

Setelah dilakukannya pembagian IP, maka mulai membuat topologi menggunakan Cisco Packet Tracer (CPT) seperti gambar berikut


[gampar cpt]

Selanjutnya melakukan subneting yang bergantung terhadap subnet yang akan dilalui, dengan contoh subnet A20 antara Aura (Eth 1/0) dan Denken (Fa 0/0) dan Subnet A21 antara Denken (Fa 0/1) dan PC RoyalCapital (Fa 0), seperti gambar berikut:

1. Subnetting pada Aura melalui Eth 1/0 pada Subnet A20

![aura_A20](https://cdn.discordapp.com/attachments/1067327620938747946/1181918997290164234/Screenshot_2023-12-06_at_18.24.00.png?ex=6582ced7&is=657059d7&hm=ed6ff70cf77defd59f52916c5d8136c8a4d8ab89dd342b83154d6b13b3677341&)


2. Subnetting pada Denken melalui Fa 0/0 pada Subnet A20

![denken_A20](https://cdn.discordapp.com/attachments/1067327620938747946/1181919426153549824/Screenshot_2023-12-06_at_18.25.44.png?ex=6582cf3e&is=65705a3e&hm=dcdbe197fb4cce47318bfaa98db3bafd6c5bfbef6b7c82bf2ca3e364ab26601f&)


3. Subnetting pada RoyalCapital melalui Fa 0 pada Subnet A21

![royalCapital_A21](https://cdn.discordapp.com/attachments/1067327620938747946/1181919656475361371/Screenshot_2023-12-06_at_18.26.36.png?ex=6582cf75&is=65705a75&hm=4a965ff09119da6abe8651de00accfd01d09dc37d5e9c365ea5543f7087306e6&)



Terkhusus pada Server dan PC, diperlukan konfigurasi tambahan yakni pada tab desktop dan opsi Ip Configuration untuk menambahkan Default Gateway dari IP router yang menyambungkannya yakni Denken melalui Fa 0/1, seperti gambar berikut

![royalCapital_A21](https://cdn.discordapp.com/attachments/1067327620938747946/1181919730630676490/Screenshot_2023-12-06_at_18.26.58.png?ex=6582cf86&is=65705a86&hm=da4b3e6d098542a5702d5ed52c5573bc3b53a54e4b6208fd961bcae0666c43dc&)



Kemudian dilakukannya routing  terhadap subnet yang ingin dituju dengan mengisi tab static, dengan contoh routing Aura dan Denken terhadap subnet A21

1. Routing pada Aura menuju Denken (routing maju)

![aura_static](https://cdn.discordapp.com/attachments/1067327620938747946/1181920820222758942/Screenshot_2023-12-06_at_18.31.16.png?ex=6582d08a&is=65705b8a&hm=645a327b71880de43cd1d3a231f1e195632071e952073488c73e886fdead4314&)



2. Routing pada Denken menuju Aura (routing mundur)

![denken_static](https://cdn.discordapp.com/attachments/1067327620938747946/1181921167964131379/Screenshot_2023-12-06_at_18.32.38.png?ex=6582d0dd&is=65705bdd&hm=7748a7b2f5e21d9d01bd958fbc8e7947b94aff82b56f2cb68f6f27a0641fda1d&)



Lakukan langkah subneting dan routing untuk seluruhnya sampai setiap PC atau Server dapat melakukan ping sampai ke Aura.

Kemudian untuk melakukan ping dari PC atau server atau bahkan router yang berasal dari percabangan subnet yang berbeda, diperlukan langkah tambahan pada routing maju terhadap subnet percabangan tersebut.

Disini diberikan contoh pada Router Aura menuju Royal Capital (semua routing memiliki sistem yang sama sehingga ini akan dijadikan satu contoh)

Lakukan langkah routing sehingga dapat melakukan ping pada client tersebut
![testPingPC](https://cdn.discordapp.com/attachments/1067327620938747946/1181923706600177785/Screenshot_2023-12-06_at_18.42.45.png?ex=6582d33a&is=65705e3a&hm=c107a519365f18c83d653da45eea40967b3fbf38b4b824934359beeeceec7c0c&)








### Metode CIDR Menggunakan GNS3
