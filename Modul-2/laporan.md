**Nama: Angeli Thie**

**Kelas: IF-04-04**

**NIM: 103072400032**
# Modul 2 Pengenalan Tools
1. Wireshark digunakan sebagai *packet sniffer* untuk mengamati pesan yang dipertukarkan antar entitas protokol. Tool ini bersifat pasif, hanya menerima salinan paket yang dikirim/diterima oleh aplikasi yang berjalan di komputer, tanpa pernah mengirim atau menerima paket secara langsung. Wireshark terdiri dari dua komponen utama, yaitu *Packet Capture Library* yang menangkap frame link layer, dan *Packet Analyzer* yang menampilkan isi dari setiap bidang pesan protokol.

2. Instalasi Wireshark dilakukan melalui halaman resmi `wireshark.org/download.html`, dengan memilih binary yang sesuai dengan sistem operasi yang digunakan.
<img width="1646" height="845" alt="image" src="https://github.com/user-attachments/assets/fdf47ce0-79ad-406c-aedf-7c0f7bad8c14" />

3. Wireshark dijalankan, menampilkan tampilan awal yang berisi daftar *interfaces* pada bagian Capture. Interface yang digunakan adalah Wi-Fi, karena seluruh paket data komputer melewati antarmuka tersebut.
<img width="1232" height="243" alt="image" src="https://github.com/user-attachments/assets/38e41798-4a62-47f7-ab8a-9ade0fceeebe" />

4. Browser web dijalankan terlebih dahulu sebagai langkah awal sebelum pengambilan paket dimulai.

5. Pengambilan paket dimulai melalui menu **Capture** → **Interfaces**, kemudian antarmuka Wi-Fi dipilih dan proses *Start Capture* dijalankan. Wireshark mulai menangkap seluruh paket yang dikirim/diterima oleh komputer.
<img width="1646" height="602" alt="image" src="https://github.com/user-attachments/assets/76bc2305-d41a-4f58-9db6-333e34962a83" />

6. Selama proses capture berjalan, URL `http://gaia.cs.umass.edu/wireshark-labs/INTRO-wireshark-file1.html` diakses melalui browser. Permintaan ini menghasilkan pertukaran pesan HTTP antara komputer dengan server `gaia.cs.umass.edu`, yang turut tertangkap oleh Wireshark.
<img width="880" height="358" alt="image" src="https://github.com/user-attachments/assets/f0aa22d3-4b07-400a-b562-01b3efa9654b" />

7. Setelah halaman berhasil ditampilkan, proses pengambilan paket dihentikan (*Stop Capture*). Pada jendela utama Wireshark, daftar paket yang tertangkap menampilkan berbagai jenis protokol, tidak hanya HTTP.
<img width="1646" height="925" alt="image" src="https://github.com/user-attachments/assets/cfc389cf-332c-470d-8218-10a77b70a21e" />

8. Filter `http` diketikkan pada kolom *display filter* di bagian atas jendela Wireshark, kemudian diterapkan dengan menekan **Enter**. Hasilnya, hanya paket dengan protokol HTTP yang ditampilkan pada jendela daftar paket.
<img width="1646" height="509" alt="image" src="https://github.com/user-attachments/assets/ece58d92-1a19-42c7-b224-c1870a77f028" />

9. Pesan **HTTP GET** yang dikirim dari komputer ke server `gaia.cs.umass.edu` diidentifikasi pada daftar paket. Paket tersebut dipilih untuk menampilkan detail frame Ethernet, datagram IP, segmen TCP, dan header pesan HTTP. Informasi pada lapisan Frame, Ethernet, IP, dan TCP diminimalkan, sementara informasi protokol HTTP dimaksimalkan agar lebih mudah diamati.

10. Setelah seluruh pengamatan selesai dilakukan, aplikasi Wireshark ditutup.
