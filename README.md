# Laporan Resmi Praktikum Jaringan Komputer - Modul 4 IT 20

> Annisa Rahmapuri - 5027211018
> 

> Abdul Zaki Syahrul Rahmat - 502721120
> 

## CPT *menggunakan VLSM*

### 1. Menentukan jumlah subnet pada topologi
Langkah pertama yang harus dilakukan adalah menentukan jumlah subnet dan juga nama subnet yang akan digunakan, kita akan menggunakan tabel berikut sebagai acuan

![Alt text](<image/Screenshot 2023-12-05 155105.png>)

Berdasarkan tabel tersebut, maka rangkaian subnet yang akan kita gunakan adalah sebagai berikut

| Rute | Subnet | Jumlah IP  | Length |
| --- | --- | --- | --- |
| Fern-Switch4-LaubHills-Switch4-AppetitRegion | A8  | 1023 | /21 |
| Fern-Flamme | A7 | 2 | /30 |
| Flamme-Switch5-RohrRoad | A6 | 1001 | /22 |
| Flamme-Himmel | A9 | 2 | /30 |
| Himmel-Switch6-SchwerMountains | A10 | 6 | /29 |
| Flamme-Frieren | A5 | 2 | /30 |
| Frieren-Switch3-LakeKorridor | A4 | 25 | /27 |
| Frieren-Aura | A3 | 2 | /30 |
| Aura-Denken | A1 | 2 | /30 |
| Denken-Switch2-RoyalCapital-Switch2-WileRegion | A2 | 127 | /24 |
| Aura-Eisen | A11 | 2 | /30 |
| Eisen-Switch1-Richter-Switch1-Revolte | A13 | 3 | /29 |
| Eisen-Switch0-Stark | A12 | 2 | /30 |
| Eisen-Lugner | A14 | 2 | /30 |
| Lugner-Switch10-TurkRegion | A15 | 1001 | /22 |
| Lugner-Switch9-GrobeForest | A16 | 251 | /24 |
| Eisen-Linie | A17 | 2 | /30 |
| Linie-Switch11-GranzChannel | A18 | 255 | /23 |
| Linie-Lawine | A19 | 2 | /30 |
| Lawine-Switch7-Heiter-Switch7-BredtRegion | A20 | 31 | /26 |
| Heiter-Switch8-Sein-Switch8-RiegelCanyon | A21 | 512 | /22 |
| Total Jumlah IP | | 4255 | /19 |

Sehingga untuk pembagian IP Addressnya adalah seperti ini

![Alt text](<image/Screenshot 2023-12-05 162932.png>)

Dan untuk tree nya adalah sebagai berikut

![Alt text](<image/Tree VLSM IT20.png>)

### 2. Membuat Topologi pada Cisco Packet Tracer

Langkah selanjutnya adalah membuat topologi sesuai dengan tabel yang kita pakai diatas, sehingga menjadi seperti ini

![Alt text](<image/Screenshot 2023-12-05 160152.png>)

Untuk Router jangan lupa untuk menambahkan modul **NM-2FE2W**

![Alt text](<image/Screenshot 2023-12-05 155850.png>)

Periksa kembali konfigurasi, dan pastikan semua router sudah dalam kondisi ON atau menyala

### 3. Melakukan Konfigurasi pada Cisco Packet Tracer
Untuk menghubungkan router dengan router lainnya, maupun dengan subnet, perlu dilakukan konfigurasi pada interface masing-masing komponen, untuk konfigurasinya adalah sebagai berikut 

### Aura
```
- FE0/1
IPv4    : 192.243.24.113
Netmask : 255.255.255.252

- FE1/0
IPv4    : 192.243.24.117
Netmask : 255.255.255.252

- FE1/1
IPv4    : 192.243.24.121
Netmask : 255.255.255.252
```

### Denken
```
- FE0/0
IPv4    : 192.243.24.114
Netmask : 255.255.255.252

- FE0/1
IPv4    : 192.243.23.1
Netmask : 255.255.255.0
```

### RoyalCapital
```
IPv4    : 192.243.23.2
Netmask : 255.255.255.0
Gateway : 192.243.23.1
```
### WilleRegion
```
IPv4    : 192.243.23.3
Netmask : 255.255.255.0
Gateway : 192.243.23.1
```

### Frieren
```
- FE0/0
IPv4    : 192.243.24.118
Netmask : 255.255.255.252

- FE0/1
IPv4    : 192.243.24.65
Netmask : 255.255.255.252
```
### LakeKorridor
```
IPv4    : 192.243.24.66
Netmask : 255.255.255.224
Gateway : 192.243.24.65
```

### Flamme
```
- FE0/0
IPv4    : 192.243.24.126
Netmask : 255.255.255.252

- FE0/1
IPv4    : 192.243.24.129
Netmask : 255.255.255.252

- FE1/0
IPv4    : 192.243.24.133
Netmask : 255.255.255.252

- FE1/1
IPv4    : 192.243.8.1
Netmask : 255.255.252.0
```
### RohrRoad
```
IPv4    : 192.243.8.2
Netmask : 255.255.252.0
Gateway : 192.243.8.1
```

### Fern
```
- FE0/0
IPv4    : 192.243.24.130
Netmask : 255.255.255.252

- FE0/1
IPv4    : 192.243.0.1
Netmask : 255.255.248.0
```
### LaubHills
```
IPv4    : 192.243.0.2
Netmask : 255.255.248.0
Gateway : 192.243.0.1
```
### AppetitRegion
```
IPv4    : 192.243.0.3
Netmask : 255.255.248.0
Gateway : 192.243.0.1
```

### Himmel
```
- FE0/0
IPv4    : 192.243.24.134
Netmask : 255.255.255.252

- FE0/1
IPv4    : 192.243.24.97
Netmask : 255.255.255.248
```
### SchwerMountains
```
IPv4    : 192.243.24.98
Netmask : 255.255.255.248
Gateway : 192.243.24.97
```

### Eisen
```
- FE0/0
IPv4    : 192.243.24.122
Netmask : 255.255.255.252

- FE1/0
IPv4    : 192.243.24.105
Netmask : 255.255.255.248

- FE2/0
IPv4    : 192.243.24.141
Netmask : 255.255.255.252

- FE3/0
IPv4    : 192.243.24.145
Netmask : 255.255.255.252

- FE4/0
IPv4    : 192.243.24.137
Netmask : 255.255.255.252
```
### Stark
```
IPv4    : 192.243.24.138
Netmask : 255.255.255.252
Gateway : 192.243.24.137
```
### Richter
```
IPv4    : 192.243.24.106
Netmask : 255.255.255.248
Gateway : 192.243.24.105
```
### Revolte
```
IPv4    : 192.243.24.107
Netmask : 255.255.255.248
Gateway : 192.243.24.105
```

### Linie
```
- FE0/0
IPv4    : 192.243.24.146
Netmask : 255.255.255.252

- FE0/1
IPv4    : 192.243.20.1
Netmask : 255.255.254.0

- FE1/0
IPv4    : 192.243.24.149
Netmask : 255.255.255.252
```
### GranzChannel
```
IPv4    : 192.243.20.2
Netmask : 255.255.254.0
Gateway : 192.243.20.1
```

### Lawine
```
- FE0/0
IPv4    : 192.243.24.150
Netmask : 255.255.255.252

- FE0/1
IPv4    : 192.243.24.1
Netmask : 255.255.255.192
```
### BredtRegion
```
IPv4    : 192.243.24.2
Netmask : 255.255.255.192
Gateway : 192.243.24.1
```

### Heiter
```
- FE0/0
IPv4    : 192.243.24.3
Netmask : 255.255.255.192

- FE0/1
IPv4    : 192.243.16.1
Netmask : 255.255.252.0
```
### Sein
```
IPv4    : 192.243.16.2
Netmask : 255.255.252.0
Gateway : 192.243.16.1
```
### RiegelCanyon
```
IPv4    : 192.243.16.3
Netmask : 255.255.252.0
Gateway : 192.243.16.1
```

Kemudian kita akan melakukan testing dengan cara mengirim paket dari suatu **node** ke **node tetangga nya**

![Alt text](<image/Screenshot 2023-12-05 162702.png>)

Seharusnya jika konfigurasi yang digunakan sudah benar, maka semua node dapat mengirim paket ke node yang berada tepat di sebelahnya atau di satu subnet yang sama.

#### 4. Menghubungkan satu subnet dengan subnet lainnya di Cisco Packet Tracer

Setelah semua node terhubung satu sama lain, selanjutnya kita akan menghubungkan semua subnet yang ada dalam topologi atau melakukan Routing. Untuk konfigurasi routingnya adalah sebagai berikut

### Aura
```
- A4
Network  : 192.243.24.64
Mask     : 255.255.255.224
Next Hop : 192.243.24.118

- A2
Network  : 192.243.23.0
Mask     : 255.255.255.0
Next Hop : 192.243.24.114

- A8
Network  : 192.243.0.0
Mask     : 255.255.248.0
Next Hop : 192.243.24.118

- A6
Network  : 192.243.8.0
Mask     : 255.255.252.0
Next Hop : 192.243.24.118

- A10
Network  : 192.243.24.96
Mask     : 255.255.255.248
Next Hop : 192.243.24.118

- A12
Network  : 192.243.24.136
Mask     : 255.255.255.252
Next Hop : 192.243.24.122

- A13
Network  : 192.243.24.104
Mask     : 255.255.255.248
Next Hop : 192.243.24.122

- A15
Network  : 192.243.12.0
Mask     : 255.255.252.0
Next Hop : 192.243.24.122

- A15
Network  : 192.243.12.0
Mask     : 255.255.252.0
Next Hop : 192.243.24.122

- A16
Network  : 192.243.22.0
Mask     : 255.255.255.0
Next Hop : 192.243.24.122

- A18
Network  : 192.243.20.0
Mask     : 255.255.254.0
Next Hop : 192.243.24.122

- A20
Network  : 192.243.24.0
Mask     : 255.255.255.192
Next Hop : 192.243.24.122

- A21
Network  : 192.243.16.0
Mask     : 255.255.252.0
Next Hop : 192.243.24.122

- A5
Network  : 192.243.24.124
Mask     : 255.255.255.252
Next Hop : 192.243.24.118

- A7
Network  : 192.243.24.128
Mask     : 255.255.255.252
Next Hop : 192.243.24.118

- A9
Network  : 192.243.24.132
Mask     : 255.255.255.252
Next Hop : 192.243.24.118

- A14
Network  : 192.243.24.140
Mask     : 255.255.255.252
Next Hop : 192.243.24.122

- A17
Network  : 192.243.24.144
Mask     : 255.255.255.252
Next Hop : 192.243.24.122

- A17
Network  : 192.243.24.148
Mask     : 255.255.255.252
Next Hop : 192.243.24.122
```
### Denken
```
- A2 > A1
Network  : 0.0.0.0
Mask     : 0.0.0.0
Next Hop : 192.243.24.113
```

### Frieren
```
- A4 > A3
Network  : 0.0.0.0
Mask     : 0.0.0.0
Next Hop : 192.243.24.117

- A8
Network  : 192.243.0.0
Mask     : 255.255.248.0
Next Hop : 192.243.24.126

- A6
Network  : 192.243.8.0
Mask     : 255.255.252.0
Next Hop : 192.243.24.126

- A10
Network  : 192.243.24.96
Mask     : 255.255.255.248
Next Hop : 192.243.24.126

- A7
Network  : 192.243.24.128
Mask     : 255.255.255.252
Next Hop : 192.243.24.126

- A9
Network  : 192.243.24.132
Mask     : 255.255.255.252
Next Hop : 192.243.24.126
```

### Flamme
```
- A6 > A5
Network  : 0.0.0.0
Mask     : 0.0.0.0
Next Hop : 192.243.24.125

- A8
Network  : 192.243.0.0
Mask     : 255.255.248.0
Next Hop : 192.243.24.130

- A10
Network  : 192.243.24.96
Mask     : 255.255.255.248
Next Hop : 192.243.24.134
```

### Fern
```
- A8 > A7
Network  : 0.0.0.0
Mask     : 0.0.0.0
Next Hop : 192.243.24.129
```

### Himmel
```
- A10 > A9
Network  : 0.0.0.0
Mask     : 0.0.0.0
Next Hop : 192.243.24.133
```

### Eisen
```
- A12 & A13 > A11
Network  : 0.0.0.0
Mask     : 0.0.0.0
Next Hop : 192.243.24.121

- A15
Network  : 192.243.12.0
Mask     : 255.255.252.0
Next Hop : 192.243.24.142

- A16
Network  : 192.243.22.0
Mask     : 255.255.255.0
Next Hop : 192.243.24.142

- A18
Network  : 192.243.20.0
Mask     : 255.255.254.0
Next Hop : 192.243.24.146

- A20
Network  : 192.243.24.0
Mask     : 255.255.255.192
Next Hop : 192.243.24.146

- A21
Network  : 192.243.16.0
Mask     : 255.255.252.0
Next Hop : 192.243.24.146

- A14
Network  : 192.243.24.140
Mask     : 255.255.255.252
Next Hop : 192.243.24.142

- A17
Network  : 192.243.24.144
Mask     : 255.255.255.252
Next Hop : 192.243.24.146

- A19
Network  : 192.243.24.148
Mask     : 255.255.255.252
Next Hop : 192.243.24.146
```

### Lugner
```
- A15 & A16 > A14
Network  : 0.0.0.0
Mask     : 0.0.0.0
Next Hop : 192.243.24.141
```

### Linie
```
- A18 > A17
Network  : 0.0.0.0
Mask     : 0.0.0.0
Next Hop : 192.243.24.145

- A20
Network  : 192.243.24.0
Mask     : 255.255.255.192
Next Hop : 192.243.24.150

- A21
Network  : 192.243.16.0
Mask     : 255.255.252.0
Next Hop : 192.243.24.150

- A19
Network  : 192.243.24.148
Mask     : 255.255.255.252
Next Hop : 192.243.24.150
```

### Lawine
```
- A20 > A19
Network  : 0.0.0.0
Mask     : 0.0.0.0
Next Hop : 192.243.24.149

- A21
Network  : 192.243.16.0
Mask     : 255.255.252.0
Next Hop : 192.243.24.3
```

### Heiter
```
- A21 > A20
Network  : 0.0.0.0
Mask     : 0.0.0.0
Next Hop : 192.243.24.1
```

### 5. Testing Topologi
Setelah melakukan routing, langkah selanjutnya adalah testing untuk memeriksa apakah semua komponen di jaringan sudah terhubung dengan satu sama lain

Untuk testing yang digunakan di percobaan ini adalah sebagai berikut

```
Sein - Richter
GranzChannel - Turk Region
RiegelCanyon - Aura
Fern - Linie
RoyalCapital - LaubHills
Heiter - Denken
SchwerMountains - Lugner
```

Dan hasilnya adalah sebagai berikut
![Alt text](<image/Screenshot 2023-12-06 163044.png>)
![Alt text](<image/Screenshot 2023-12-06 163141.png>)
## *GNS menggunakan CIDR*

### *Penggabungan IP*

- Menentukan jumlah subnet awal pada topologi, seperti gambar berikut :
    
    ![Untitled](image/Untitled.png)
    
    | Rute | Subnet | Jumlah IP  | Lenght |
    | --- | --- | --- | --- |
    | Fern-Switch4-LaubHills-Switch4-AppetitRegion | A8  | 1023 | /21 |
    | Fern-Flamme | A7 | 2 | /30 |
    | Flamme-Switch5-RohrRoad | A6 | 1001 | /22 |
    | Flamme-Himmel | A9 | 2 | /30 |
    | Himmel-Switch6-SchwerMountains | A10 | 6 | /29 |
    | Flamme-Frieren | A5 | 2 | /30 |
    | Frieren-Switch3-LakeKorridor | A4 | 25 | /27 |
    | Frieren-Aura | A3 | 2 | /30 |
    | Aura-Denken | A1 | 2 | /30 |
    | Denken-Switch2-RoyalCapital-Switch2-WileRegion | A2 | 127 | /24 |
    | Aura-Eisen | A11 | 2 | /30 |
    | Eisen-Switch1-Richter-Switch1-Revolte | A13 | 3 | /29 |
    | Eisen-Switch0-Stark | A12 | 2 | /30 |
    | Eisen-Lugner | A14 | 2 | /30 |
    | Lugner-Switch10-TurkRegion | A15 | 1001 | /22 |
    | Lugner-Switch9-GrobeForest | A16 | 251 | /24 |
    | Eisen-Linie | A17 | 2 | /30 |
    | Linie-Switch11-GranzChannel | A18 | 255 | /23 |
    | Linie-Lawine | A19 | 2 | /30 |
    | Lawine-Switch7-Heiter-Switch7-BredtRegion | A20 | 31 | /26 |
    | Heiter-Switch8-Sein-Switch8-RiegelCanyon | A21 | 512 | /22 |
- Penggabungan Subnet
    - Penggabungan A → B
        
        ![Untitled](image/Untitled%201.png)
        
        ![Untitled](image/Untitled%202.png)
        
    - Penggabungan B → C
        
        ![Untitled](image/Untitled%203.png)
        
        ![Untitled](image/Untitled%204.png)
        
    - Penggabungan C → D
        
        ![Untitled](image/Untitled%205.png)
        
        ![Untitled](image/Untitled%206.png)
        
    - Penggabungan D → E
        
        ![Untitled](image/Untitled%207.png)
        
        ![Untitled](image/Untitled%208.png)
        
    - Penggabungan E → F
        
        ![Untitled](image/Untitled%209.png)
        
        ![Untitled](image/Untitled%2010.png)
        
    - Penggabungan F → G
        
        ![Untitled](image/Untitled%2011.png)
        
        ![Untitled](image/Untitled%2012.png)
        
    - Penggabungan G → H
        
        ![Untitled](image/Untitled%2013.png)
        
        ![Untitled](image/Untitled%2014.png)
        
    - Penggabungan H → I
        
        ![Untitled](image/Untitled%2015.png)
        
        ![Untitled](image/Untitled%2016.png)
        
        Berdasarkan total IP dan netmask yang dibutuhkan, Subnet besar yang dibentuk memiliki `NID 192.243.0.0` dengan `Netmask /14`. 
        

### *Perhitungan dan Pembagian IP  *****

Menghitung pembagian IP berdasarkan `NID` dan `Netmask` yang didapatkan : 

![Untitled](image/Untitled%2017.png)

Berdasarkan tree di atas serta perhitungan yang ada, dapat disimpulkan pembagian IP pada masing masing subnet sebagai berikut : 

![Untitled](image/Untitled%2018.png)

### *Routing*  ****

Untuk menghubungkan perangkat-perangkat dalam topologi jaringan, perlu dilakukan konfigurasi jaringan pada masing-mfv wasing interface perangkat. Konfigurasi jaringan ini meliputi pengaturan alamat IP, subnet mask, dan gateway.

![Untitled](image/Untitled%2019.png)

- Aura
    
    ```bash
    #Aura
    auto eth0
    iface eth0 inet dhcp
    
    #A11 Aura-Eisen
    auto eth1
    iface eth1 inet static
    	address 192.245.128.1
    	netmask 255.255.255.252
    
    #A1 Aura-Denken
    auto eth2
    iface eth2 inet static
    	address 192.244.1.1
    	netmask 255.255.255.252
    
    #A3 Aura-Frieren
    auto eth3
    iface eth3 inet static
    	address 192.243.128.1
    	netmask 255.255.255.252
    ```
    
    ```bash
    route add -net 192.244.0.0 netmask 255.255.255.0 gw 192.244.1.2
    route add -net 192.243.192.0 netmask 255.255.255.224 gw 192.243.128.2
    ```
    
- Denken
    
    ```bash
    #A1 Denken-Aura
    auto eth0
    iface eth0 inet static
    	address 192.244.1.2
    	netmask 255.255.255.252
    
    #A2 Denken-Switch-RoyalCapital-Switch-WileRegion
    auto eth1
    iface eth1 inet static
    	address 192.244.0.1
    	netmask 255.255.255.0
    ```
    
    ```bash
    route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.244.1.1
    ```
    
- Royal Capital
    
    ```bash
    #RoyalCapital
    auto eth0
    iface eth0 inet static
    	address 192.244.0.2
    	netmask 255.255.255.0
        gateway 192.244.0.1
    ```
    
- WillieRegion
    
    ```bash
    #WilleRegion
    auto eth0
    iface eth0 inet static
    	address 192.244.0.3
    	netmask 255.255.255.0
        gateway 192.244.0.1
    ```
    
- Eisen
    
    ```bash
    #Eisen
    #A11 Aura-Eisen
    auto eth0
    iface eth0 inet static
    	address 192.245.128.2
    	netmask 255.255.255.252
    
    #A17 Eisen-Linie
    auto eth1
    iface eth1 inet static
    	address 192.245.96.1
    	netmask 255.255.255.252
    
    #A12 Eisen-Switch0-Stark
    auto eth2
    iface eth2 inet static
    	address 192.245.16.1
    	netmask 255.255.255.252
    
    #A13 Eisen-Switch1-Richter-Switch1-Revolte
    auto eth3
    iface eth3 inet static
    	address 192.245.32.1
    	netmask 255.255.255.248
    
    #A14 Eisen-Lugner
    auto eth4
    iface eth4 inet static
    	address 192.245.8.1
    	netmask 255.255.255.252
    ```
    
    ```bash
    route add -net 192.245.0.0 netmask 255.255.255.0 gw 192.245.8.2
    ```
    
- Stark
    
    ```bash
    #Stark A12
    auto eth0
    iface eth0 inet static
    	address 192.245.16.2
    	netmask 255.255.255.252
    ```
    
- Lugner
    
    ```bash
    #A14 Eisien-Lugner
    auto eth0
    iface eth0 inet static
    	address 192.245.8.2
    	netmask 255.255.255.252
    
    #A15 Lugner-Switch10-TurkRegion
    auto eth1
    iface eth1 inet static
    	address 192.245.0.1
    	netmask 255.255.252.0
    
    #A16 Lugner-Switch9-GrobeForest
    auto eth2
    iface eth2 inet static
    	address 192.245.4.1
    	netmask 255.255.255.0
    ```
    
    ```bash
    route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.245.8.1
    ```
    
- TurkRegion
    
    ```bash
    #TurkRegion
    auto eth0
    iface eth0 inet static
    	address 192.245.0.2
    	netmask 255.255.252.0
        gateway 192.245.0.1
    ```
    
- GrabForest
    
    ```bash
    #GrobeForest
    auto eth0
    iface eth0 inet static
    	address 192.245.4.2
    	netmask 255.255.255.0
        gateway 192.245.4.1
    ```
    
- Ricther
    
    ```bash
    #Ritcher 
    auto eth0
    iface eth0 inet static
    	address 192.245.32.2
    	netmask 255.255.255.248
    ```
    
- Revolte
    
    ```bash
    #Revolte
    auto eth0
    iface eth0 inet static
    	address 192.245.32.3
    	netmask 255.255.255.248
    ```
    
- Frieren
    
    ```bash
    #Frieren 
    #A3 Frieren-Aura
    auto eth0
    iface eth0 inet static
    	address 192.243.128.2
    	netmask 255.255.255.252
    
    #A5 Flamme-Frieren
    auto eth1
    iface eth1 inet static
    	address 192.243.32.1
    	netmask 255.255.255.252
    
    #A4 Frieren-Switch3-LakeKorridor
    auto eth2
    iface eth2 inet static
    	address 192.243.192.1
    	netmask 255.255.255.224
    ```
    
    ```bash
    route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.243.128.1
    ```
    
- LaubHills
    
    ```bash
    #LaubHills A4
    auto eth0
    iface eth0 inet static
    	address 192.243.192.2
    	netmask 255.255.255.224
    ```
    

### *Testing*

Dilakukan beberapa testing sebagai berikut:

- `RoyalCapital` →  `Aura`
    
    ![Untitled](image/Untitled%2020.png)
    
- `Revolte` →  `Eisien`
    
    ![Untitled](image/Untitled%2021.png)
    
- `GrabForest` → `Lugner`
    
    ![Untitled](image/Untitled%2022.png)
    
- `HaLakeCoridor` → `Frieren`
    
    ![Untitled](image/Untitled%2023.png)
