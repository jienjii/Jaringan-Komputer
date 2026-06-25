**Nama: Angeli Thie**

**Kelas: IF-04-04**

**NIM: 103072400032**

# Modul 5 UDP
1. Header UDP memiliki 4 *field*, yaitu **Source Port**, **Destination Port**, **Length**, dan **Checksum**.
<img width="822" height="773" alt="image" src="https://github.com/user-attachments/assets/279d4733-8b7d-4f70-ac84-a4341b9e8ad2" />

2. Setiap *field* pada header UDP memiliki panjang **2 byte (16 bit)**. Total keseluruhan header UDP adalah **8 byte**.

3. Nilai pada **Length** menyatakan panjang total segmen UDP (header UDP + data/payload), dalam satuan byte. Nilai ini dapat diverifikasi dengan menjumlahkan ukuran header (8 byte) dengan ukuran data pada paket yang dipilih.

4. Karena *field* **Length** berukuran 16 bit, nilai maksimumnya adalah 65.535. Dikurangi ukuran header UDP (8 byte), jumlah maksimum byte yang dapat disertakan dalam payload UDP adalah **65.527 byte**.

5. Karena *field* **Source Port** berukuran 16 bit, nomor port terbesar yang dapat menjadi port sumber adalah **65.535**.

6. Nomor protokol untuk UDP adalah **17 (desimal)** atau **0x11 (heksadesimal)**, dapat dilihat pada bagian *Protocol* di datagram IP yang membawa segmen UDP tersebut.

7. Pada pasangan paket UDP request-balasan, nomor port sumber pada paket pertama menjadi port tujuan pada paket kedua (balasan), dan sebaliknya, port tujuan pada paket pertama menjadi port sumber pada paket kedua. Nomor port pada kedua paket tersebut saling bertukar/terbalik.
