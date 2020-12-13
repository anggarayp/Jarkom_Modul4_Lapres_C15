# Jarkom_Modul4_Lapres_C15
Lapres Soal Shift Jarkom Modul 4

### Nama Anggota Kelompok :
### 1. Anggara Yuda Pratama (05111840000008)
### 2. Patrick (05111840000098)

![Soal Shift Modul 4](https://user-images.githubusercontent.com/61231385/101947041-69695f00-3c22-11eb-992b-3ddf0d5cae9c.png)

### Pembagian Subnetting

Pada Topologi CPT tersebut dibagi alamat IP-nya dengan metode Classful :

![image](https://github.com/anggarayp/Jarkom_Modul4_Lapres_C15/blob/main/Screenshots/Soal%20Shift%20C15%201.png)

### Metode VLSM

Metode Variable Length Subnet Masking kami gunakan untuk pengerjaan yang di CPT.

Menentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet dan lakukan labelling netmask berdasarkan jumlah IP yang dibutuhkan. Berikut merupakan hasilnya dalam bentuk **tabel** :

![image](https://github.com/anggarayp/Jarkom_Modul4_Lapres_C15/blob/main/Screenshots/tabel%20vlsm.png)

Selanjutnya hitung pembagian IP berdasarkan **tree** berikut :

![image](https://github.com/anggarayp/Jarkom_Modul4_Lapres_C15/blob/main/Screenshots/tree%20c15%20vlsm.png)

ss routing di cpt satu2 ???

### Metode CIDR

Perhitungan pada teknik Classless Inter Domain Routing juga didasarkan pada jumlah komputer/ host yang ada di dalam subnet. Kami menggunakan teknik ini untuk pengerjaan yang di UML.

Melakukan **labelling netmask** terhadap masing-masing subnet yang tahap-tahapnya sebagai berikut :

![image](https://github.com/anggarayp/Jarkom_Modul4_Lapres_C15/blob/main/Screenshots/a-b.png)

![image](https://github.com/anggarayp/Jarkom_Modul4_Lapres_C15/blob/main/Screenshots/c.png)

![image](https://github.com/anggarayp/Jarkom_Modul4_Lapres_C15/blob/main/Screenshots/d.png)

![image](https://github.com/anggarayp/Jarkom_Modul4_Lapres_C15/blob/main/Screenshots/e.png)

![image](https://github.com/anggarayp/Jarkom_Modul4_Lapres_C15/blob/main/Screenshots/f.png)

![image](https://github.com/anggarayp/Jarkom_Modul4_Lapres_C15/blob/main/Screenshots/g.png)

Dari proses penggabungan yang telah dilakukan, didapatkan sebuah subnet besar dengan netmask /16. Berikut pembagian NID serta lengthnya dalam bentuk **tabel** :

![image](https://github.com/anggarayp/Jarkom_Modul4_Lapres_C15/blob/main/Screenshots/tabel%20cidr.png)

Lalu hitung pembagian IP dengan **tree** berdasarkan penggabungan subnet yang telah dilakukan :

![image](https://github.com/anggarayp/Jarkom_Modul4_Lapres_C15/blob/main/Screenshots/tree%20cidr%20new%20new.png)

Buat file ```topologi.sh``` dan jalankan file tersebut dengan perintah ```bash topologi.sh```.
```
# Switch
uml_switch -unix switch1 > /dev/null < /dev/null &
uml_switch -unix switch2 > /dev/null < /dev/null &
uml_switch -unix switch3 > /dev/null < /dev/null &
uml_switch -unix switch7 > /dev/null < /dev/null &
uml_switch -unix switch11 > /dev/null < /dev/null &
uml_switch -unix switch13 > /dev/null < /dev/null &
uml_switch -unix switch15 > /dev/null < /dev/null &
uml_switch -unix switch16 > /dev/null < /dev/null &
uml_switch -unix switch17 > /dev/null < /dev/null &
uml_switch -unix switch18 > /dev/null < /dev/null &
uml_switch -unix switch19 > /dev/null < /dev/null &
uml_switch -unix switch21 > /dev/null < /dev/null &
uml_switch -unix switch20 > /dev/null < /dev/null &
uml_switch -unix switch22 > /dev/null < /dev/null &
uml_switch -unix switch25 > /dev/null < /dev/null &

# Router
xterm -T SURABAYA -e linux ubd0=SURABAYA,jarkom umid=SURABAYA eth0=tuntap,,,10.151.76.65 eth1=daemon,,,switch1 eth2=$
xterm -T PASURUAN -e linux ubd0=PASURUAN,jarkom umid=PASURUAN eth0=daemon,,,switch2 eth1=daemon,,,switch3 eth2=daemo$
xterm -T PROBOLINGGO -e linux ubd0=PROBOLINGGO,jarkom umid=PROBOLINGGO eth0=daemon,,,switch3 eth2=daemon,,,switch15 $
xterm -T BATU -e linux ubd0=BATU,jarkom umid=BATU eth0=daemon,,,switch7 eth1=daemon,,,switch11 eth2=daemon,,,switch2$
xterm -T MADIUN -e linux ubd0=MADIUN,jarkom umid=MADIUN eth0=daemon,,,switch22 eth1=daemon,,,switch25 mem=64M &
xterm -T KEDIRI -e linux ubd0=KEDIRI,jarkom umid=KEDIRI eth0=daemon,,,switch11 eth1=daemon,,,switch17 eth2=daemon,,,$
xterm -T BLITAR -e linux ubd0=BLITAR,jarkom umid=BLITAR eth0=daemon,,,switch17 eth1=daemon,,,switch20 mem=64M &

# Server
xterm -T MALANG -e linux ubd0=MALANG,jarkom umid=MALANG eth0=daemon,,,switch18 mem=64M &
xterm -T MOJOKERTO -e linux ubd0=MOJOKERTO,jarkom umid=MOJOKERTO eth0=daemon,,,switch13 mem=64M &

# Client
xterm -T SAMPANG -e linux ubd0=SAMPANG,jarkom umid=SAMPANG eth0=daemon,,,switch1 mem=64M &
xterm -T SIDOARJO -e linux ubd0=SIDOARJO,jarkom umid=SIDOARJO eth0=daemon,,,switch19 mem=64M &
xterm -T BANYUWANGI -e linux ubd0=BANYUWANGI,jarkom umid=BANYUWANGI eth0=daemon,,,switch16 mem=64M &
xterm -T JEMBER -e linux ubd0=JEMBER,jarkom umid=JEMBER eth0=daemon,,,switch16 mem=64M &
xterm -T BONDOWOSO -e linux ubd0=BONDOWOSO,jarkom umid=BONDOWOSO eth0=daemon,,,switch15 mem=64M &
xterm -T JOMBANG -e linux ubd0=JOMBANG,jarkom umid=JOMBANG eth0=daemon,,,switch22 mem=64M &
xterm -T BOJONEGORO -e linux ubd0=BOJONEGORO,jarkom umid=BOJONEGORO eth0=daemon,,,switch25 mem=64M &
xterm -T NGANJUK -e linux ubd0=NGANJUK,jarkom umid=NGANJUK eth0=daemon,,,switch21 mem=64M &
xterm -T LUMAJANG -e linux ubd0=LUMAJANG,jarkom umid=LUMAJANG eth0=daemon,,,switch17 mem=64M &
xterm -T TULUNGAGUNG -e linux ubd0=TULUNGAGUNG,jarkom umid=TULUNGAGUNG eth0=daemon,,,switch20 mem=64M &
```

Lakukan setting interface pada setiap UML dengan ```nano/etc/network/interfaces```. Lalu restart dengan ```service networking restart```. Jangan lupa uncomment ```net.ipv4.ip_forward=1``` pada ```nano /etc/sysctl.conf``` di semua router.

**SURABAYA**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 10.151.76.26
netmask 255.255.255.252
gateway 10.151.76.25
auto eth1
iface eth1 inet static
address   192.168.64.1
netmask 255.255.252.0
auto eth2
iface eth2 inet static
address 192.168.192.1
netmask 255.255.255.252
auto eth3
iface eth3 inet static
address 192.168.32.1
netmask 255.255.255.252
auto eth4
iface eth4 inet static
address 10.151.77.134
netmask 255.255.255.252
```

**PASURUAN**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.192.2
netmask 255.255.255.252
auto eth1
iface eth1 inet static
address 192.168.144.1
netmask 255.255.255.252
auto eth2
iface eth2 inet static
address 192.168.160.1
netmask 255.255.252.0
```

**PROBOLINGGO**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.144.2
netmask 255.255.255.252
auto eth2
iface eth1 inet static
address 192.168.136.1
netmask 255.255.255.128
auto eth3
iface eth2 inet static
address 192.168.128.1
netmask 255.255.248.0
```

**BATU**
```auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.32.2
netmask 255.255.255.252
auto eth1
iface eth1 inet static
address 192.168.8.1
netmask 255.255.255.252
auto eth2
iface eth2 inet static
address 192.168.20.1
netmask 255.255.252.0
auto eth3
iface eth3 inet static
address 192.168.18.1
netmask 255.255.255.240
```


**MADIUN**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.18.2
netmask 255.255.255.240
auto eth1
iface eth1 inet static
address 192.168.16.1
netmask 255.255.254.0
```


**KEDIRI**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.8.2
netmask 255.255.255.252
auto eth1
iface eth1 inet static
address 192.168.4.1
netmask 255.255.255.0
auto eth2
iface eth2 inet static
address 10.151.77.130
netmask 255.255.255.252
```


**BLITAR**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.4.2
netmask 255.255.255.0
auto eth1
iface eth1 inet static
address 192.168.0.1
netmask 255.255.252.0
```

**MALANG**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 10.151.77.130
netmask 255.255.255.252
gateway 10.151.77.129
```

**MOJOKERTO**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 10.151.77.134
netmask 255.255.255.252
gateway 10.151.77.133
```

**SAMPANG**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.64.2
netmask 255.255.252.0
gateway 192.168.64.1
```


**SIDOARJO**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.160.2
netmask 255.255.252.0
gateway 192.168.160.1
```

**BANYUWANGI**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.128.2
netmask 255.255.248.0
gateway 192.168.128.1
```

**JEMBER**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.128.3
netmask 255.255.248.0
gateway 192.168.128.1
```

**BONDOWOSO**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.136.2
netmask 255.255.255.128
gateway 192.168.136.1
```

**JOMBANG**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.18.3
netmask 255.255.255.240
gateway 192.168.18.1
```

**BOJONEGORO**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.16.2
netmask 255.255.254.0
gateway 192.168.16.1
```

**NGANJUK**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.20.2
netmask 255.255.252.0
gateway 192.168.20.1
```


**LUMAJANG**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.4.3
netmask 255.255.255.0
gateway 192.168.4.1
```

**TULUNGAGUNG**
```
auto lo
iface lo inet loopback
auto eth0
iface eth0 inet static
address 192.168.144.2
netmask 255.255.252.0
gateway 192.168.144.1
```

Setelah selesai melakukan setting interface, jalankan ```iptables –t nat –A POSTROUTING –o eth0 –j MASQUERADE –s 192.168.0.0/16``` pada uml SURABAYA agar terhubung ke internet. Lalu, lakukan routing dibawah ini dengan cara ```nano route.sh```. Ketika selesai menambahkan route, jalankan routing dengan ```bash route.sh```.


**SURABAYA**
```
route add -net 192.168.144.0 netmask 255.255.255.252 gw 192.168.192.2 
route add -net 192.168.136.0 netmask 255.255.255.128 gw 192.168.192.2
route add -net 192.168.160.0 netmask 255.255.252.0 gw 192.168.192.2
route add -net 192.168.128.0 netmask 255.255.248.0 gw 192.168.192.2

route add -net 192.168.8.0 netmask 255.255.255.252 gw 192.168.32.2
route add -net 192.168.20.0 netmask 255.255.252.0 gw 192.168.32.2
route add -net 192.168.18.0 netmask 255.255.255.240 gw 192.168.32.2
route add -net 192.168.16.0 netmask 255.255.254.0 gw 192.168.32.2
route add -net 192.168.4.0 netmask 255.255.255.0 gw 192.168.32.2
route add -net 192.168.0.0 netmask 255.255.252.0 gw 192.168.32.2
route add -net 10.151.77.128 netmask 255.255.255.252 gw 192.168.32.2
```

**BATU**
```
route add -net 192.168.4.0 netmask 255.255.255.0 gw 192.168.8.2
route add -net 192.168.0.0 netmask 255.255.252.0 gw 192.168.8.2
route add -net 10.151.77.128 netmask 255.255.255.252 gw 192.168.8.2
route add -net 192.168.16.0 netmask 255.255.255.240 gw 192.168.18.2
```

**KEDIRI**
```
route add -net 192.168.0.0 netmask 255.255.252.0 gw 192.168.4.2
```

**PASURUAN **
```
route add -net 192.168.128.0 netmask 255.255.248.0 gw 192.168.144.2
route add -net 192.168.136.0 netmask 255.255.255.128 gw 192.168.144.2
```
