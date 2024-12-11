# Rangkuman Jarkom Lanjut - Imam Mulyana

**Nama**: Imam Mulyana  
**NIM**: 20210801234  
**Matkul**: Jarkom Lanjut

---

## Definisi IP

**IP Address (Internet Protocol Address)** adalah sebuah alamat unik yang diberikan kepada setiap perangkat yang terhubung ke jaringan komputer berbasis Internet Protocol. IP Address berfungsi untuk mengidentifikasi perangkat dalam jaringan dan memungkinkan perangkat-perangkat tersebut berkomunikasi satu sama lain.

---

## Jenis IP Address

1. **Public IP Address**: Alamat IP yang dapat diakses secara global melalui internet dan digunakan untuk mengidentifikasi perangkat di jaringan publik.
2. **Private IP Address**: Alamat IP yang digunakan dalam jaringan lokal (LAN) dan tidak dapat diakses langsung dari internet.
3. **Static IP Address**: Alamat IP tetap yang tidak berubah dan biasanya digunakan untuk server.
4. **Dynamic IP Address**: Alamat IP yang berubah setiap kali perangkat terhubung ke jaringan yang diberikan oleh server DHCP.

---

## Versi IP Address

1. **IPv4 (Internet Protocol Version 4)**: Protokol internet 32-bit yang ditulis dalam format desimal seperti 192.168.1.1.
2. **IPv6 (Internet Protocol Version 6)**: Protokol internet 128-bit yang ditulis dalam format heksadesimal seperti 2001:0db8:85a3:0000:0000:8a2e:0370:7334.

---

## Cara Setting IP

### A. Static (Manual)

1. Dalam **WinBox** → **IP** → **Addresses**.
2. Tambahkan IP Address baru → Contohnya `192.168.10.1/24` → Sesuaikan interface dengan ether dari sambungan kabel LAN → **Apply** → **Ok**.
3. Buka **Control Panel** untuk mengatur IP Laptop:
   - **Control Panel** → **Network and Internet** → **Network and Sharing Center** → **Ethernet** → **Properties**.
4. Ubah **IPv4** dengan double click → **Use the following IP Address** → Isi dengan `192.168.10.2` (2 karena 1 sudah digunakan MikroTik) → **Tab** untuk kolom yang lain → **Ok**.
5. Lakukan **Ping** terhadap IP Laptop dalam Terminal WinBox.

### B. DHCP (Otomatis)

1. Dalam **WinBox** → **IP** → **Addresses**.
2. Tambahkan IP Address baru → Contohnya `192.168.10.1/24` → Sesuaikan interface dengan ether dari sambungan kabel LAN → **Apply** → **Ok**.
3. Buka **Control Panel** untuk mengatur IP Laptop:
   - **Control Panel** → **Network and Internet** → **Network and Sharing Center** → **Ethernet** → **Properties**.
4. Ubah **IPv4** dengan double click → **Obtain an IP Address automatically** → **Ok**.
5. Dalam **WinBox** → **IP** → **DHCP Server**.
6. Tambahkan DHCP dengan **DHCP Setup** → Sesuaikan interface dengan ether yang digunakan → Klik **Next** sampai selesai.
7. Buka bagian **Leases** dalam **DHCP Server** → Lihat IP dalam bagian **Active Addresses**.
8. Lakukan **Ping** terhadap IP Address yang ada dalam **Leases** di Terminal WinBox.

### C. Bridge

1. Dalam **WinBox** → **Bridge**.
2. Tambahkan **Bridge** baru → **Apply** → **Ok**.
3. Tambahkan **Bridge Port** → Sesuaikan interface dengan ether yang digunakan → Sesuaikan Bridge dengan Bridge yang sudah dibuat → **Apply** → **Ok**.
4. Tambahkan IP Address → Ubah interface dengan Bridge yang sudah dibuat → **Apply** → **Ok**.
5. Tambahkan DHCP dengan **DHCP Setup** → Sesuaikan interface dengan Bridge yang sudah dibuat → Klik **Next** → Pada bagian **DNS Servers** ubah menjadi `8.8.8.8` → Klik **Next** sampai selesai.
6. Buka **Command Prompt** → **ipconfig** → Lihat **IPv4 Address** → Lakukan **Ping** terhadap sesama Laptop (Laptop A melakukan Ping terhadap IP Laptop B dan sebaliknya).
7. Buka **XAMPP** dan nyalakan → Salin **IP Address** Laptop satu sama lain untuk melihat web XAMPP jika sudah tersambung.

---

## Definisi Subnet

**Subnet Mask** adalah angka 32-bit yang digunakan dalam jaringan komputer untuk membagi alamat IP (Internet Protocol) menjadi dua bagian: alamat jaringan (network address) dan alamat host (host address). Subnet mask berfungsi untuk menentukan bagian dari alamat IP yang menunjukkan jaringan, serta bagian yang menunjukkan perangkat individu dalam jaringan tersebut.

Alamat IP (192.168.100.10) dan subnet mask (255.255.255.0) bekerja untuk membagi alamat IP menjadi Network Portion dan Host Portion menggunakan notasi biner. Subnet mask yang diwakili oleh angka 1 untuk bagian jaringan (Network Portion) dan 0 untuk bagian perangkat (Host Portion), memisahkan alamat IP menjadi dua bagian: 24 bit pertama (192.168.100) untuk mengidentifikasi jaringan, dan 8 bit terakhir (10) untuk mengidentifikasi perangkat dalam jaringan tersebut. Dengan demikian, router dapat menentukan jaringan tujuan data dan perangkat spesifik di dalam jaringan tersebut. Contoh ini menunjukkan bahwa alamat IP 192.168.100.10 berada dalam jaringan 192.168.100.0/24.

---

## IP Class

IP versi 4 dibagi menjadi beberapa kelas IP, setiap kelas memiliki jumlah host dan network yang berbeda. Pembagian kelas IP adalah sebagai berikut:

| Kelas   | Rentang IP                  | Jumlah Host | Jumlah Network | Kegunaan                                                              |
| ------- | --------------------------- | ----------- | -------------- | --------------------------------------------------------------------- |
| Kelas A | 0.0.0.0 - 127.255.255.255   | 16.777.216  | 128            | Jaringan komputer berskala besar                                      |
| Kelas B | 128.0.0.0 - 191.255.255.255 | 1.048.576   | 16.384         | Jaringan komputer berskala menengah                                   |
| Kelas C | 192.0.0.0 - 223.255.255.255 | 65.536      | 2.097.152      | Jaringan komputer berskala kecil                                      |
| Kelas D | 224.0.0.0 - 239.255.255.255 | Undefined   | Undefined      | Alamat IP multicast (untuk mengirim paket ke beberapa host yang sama) |
| Kelas E | 240.0.0.0 - 255.255.255.255 | Undefined   | Undefined      | Alamat IP untuk percobaan atau eksperimen                             |

---

## Definisi LAN

**LAN (Local Area Network)** adalah sebuah jaringan komputer yang menghubungkan perangkat-perangkat (seperti komputer, printer, router, dan perangkat lain) dalam area geografis yang terbatas, seperti rumah, kantor, sekolah, atau gedung. LAN dirancang untuk memungkinkan perangkat-perangkat tersebut saling berbagi sumber daya, seperti file, data, atau perangkat keras (misalnya printer).

---

## Routing

**Routing** adalah proses dalam jaringan komputer untuk menentukan jalur terbaik bagi data (paket) untuk berpindah dari satu perangkat ke perangkat lainnya melalui jaringan. Proses ini dilakukan oleh perangkat jaringan yang disebut router.

### 1. Static Routing

Static routing adalah salah satu jenis routing yang rutenya akan ditambahkan secara manual ke routing table.

### 2. Dynamic Routing

Dynamic routing memiliki proses otomatis. Rute yang ditentukan akan didasarkan pada situasi serta kondisi jalur routing table.

#### a. RIP (Routing Information Protocol):

RIP adalah protokol routing dinamis yang menggunakan jumlah hop sebagai metrik untuk menentukan jalur terbaik, namun hanya cocok untuk jaringan kecil karena keterbatasan maksimal 15 hop.

#### b. OSPF (Open Shortest Path First):

OSPF adalah protokol routing dinamis berbasis link-state yang menggunakan algoritma Dijkstra untuk menemukan jalur terpendek, ideal untuk jaringan menengah hingga besar.

#### c. BGP (Border Gateway Protocol):

BGP adalah protokol routing dinamis berbasis path-vector yang digunakan untuk routing antar jaringan besar (WAN), seperti antar ISP, dan mendukung kebijakan routing yang kompleks.

---

## Cara Setting Routing

### A. Dynamic Routing dengan RIP

1. Sambungkan Laptop dan MikroTik seperti sebelumnya:
   - Hubungkan MikroTik A → Laptop A → ether1.
   - Hubungkan MikroTik B → Laptop B → ether1.
   - Hubungkan kedua MikroTik → ether3.
2. Tambahkan IP Address di MikroTik:
   - Laptop A → 192.168.1.1/24.
   - Laptop B → 192.168.10.1/24.
   - MikroTik A → ether1: 192.168.1.254/24, ether3: 192.168.100.1/24.
   - MikroTik B → ether1: 192.168.10.254/24, ether3: 192.168.100.2/24.
3. Aktifkan RIP pada MikroTik:
   - Buka WinBox → Routing → RIP.
   - Tambahkan konfigurasi RIP:
     - MikroTik A:
       - Interface: `ether3`.
       - Redistribute Connected Routes: Centang.
     - MikroTik B:
       - Interface: `ether3`.
       - Redistribute Connected Routes: Centang.
4. Uji Konektivitas:
   - Buka Command Prompt pada Laptop A dan B.
   - Gunakan perintah `ping` untuk memastikan koneksi antara Laptop A dan Laptop B.

### B. Dynamic Routing dengan OSPF

1. Sambungkan Laptop dan MikroTik seperti sebelumnya.
2. Tambahkan IP Address di MikroTik:
   - Laptop A → 192.168.1.1/24.
   - Laptop B → 192.168.10.1/24.
   - MikroTik A → ether1: 192.168.1.254/24, ether3: 192.168.100.1/24.
   - MikroTik B → ether1: 192.168.10.254/24, ether3: 192.168.100.2/24.
3. Aktifkan OSPF pada MikroTik:
   - Buka WinBox → Routing → OSPF.
   - Buat Instance OSPF:
     - Name: OSPF-Instance.
     - Router ID: 192.168.100.1 (untuk MikroTik A), 192.168.100.2 (untuk MikroTik B).
   - Tambahkan Network:
     - MikroTik A: Network 192.168.1.0/24 dan 192.168.100.0/24.
     - MikroTik B: Network 192.168.10.0/24 dan 192.168.100.0/24.
4. Uji Konektivitas:
   - Gunakan perintah `ping` dan `tracert` untuk memastikan rute telah dipelajari oleh kedua MikroTik.

### C. Dynamic Routing dengan BGP

1. Sambungkan Laptop dan MikroTik seperti sebelumnya.
2. Tambahkan IP Address di MikroTik:
   - Laptop A → 192.168.1.1/24.
   - Laptop B → 192.168.10.1/24.
   - MikroTik A → ether1: 192.168.1.254/24, ether3: 192.168.100.1/24.
   - MikroTik B → ether1: 192.168.10.254/24, ether3: 192.168.100.2/24.
3. Aktifkan BGP pada MikroTik:
   - Buka WinBox → Routing → BGP.
   - Tambahkan Instance BGP:
     - MikroTik A:
       - AS Number: 65001.
       - Router ID: 192.168.100.1.
     - MikroTik B:
       - AS Number: 65002.
       - Router ID: 192.168.100.2.
   - Tambahkan Peers:
     - MikroTik A:
       - Peer Address: 192.168.100.2.
       - Remote AS: 65002.
     - MikroTik B:
       - Peer Address: 192.168.100.1.
       - Remote AS: 65001.
4. Tambahkan Network yang Akan Diumumkan:
   - MikroTik A: Tambahkan Network 192.168.1.0/24.
   - MikroTik B: Tambahkan Network 192.168.10.0/24.
5. Uji Konektivitas:
   - Gunakan `ping` untuk memastikan koneksi antar Laptop A dan Laptop B.
   - Gunakan `tracert` untuk melihat jalur routing berdasarkan BGP.
