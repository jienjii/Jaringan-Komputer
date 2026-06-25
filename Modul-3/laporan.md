**Nama: Angeli Thie**

**Kelas: IF-04-04**

**NIM: 103072400032**

# Modul 3 HTTP
## Basic HTTP GET/Response Interaction
1. Browser web dijalankan, kemudian Wireshark dijalankan dan filter `http` diketikkan pada *display-filter-specification window*, sehingga hanya pesan HTTP yang ditampilkan pada jendela daftar paket.

2. Setelah menunggu sesaat, pengambilan paket Wireshark dimulai (*Start Capture*).

3. URL `http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file1.html` dimasukkan ke browser, menampilkan file HTML satu baris yang sederhana.

4. Pengambilan paket Wireshark dihentikan (*Stop Capture*).

5. Pada jendela daftar paket, ditemukan dua pesan HTTP yang tertangkap, yaitu pesan **GET** dari browser ke server `gaia.cs.umass.edu`, dan pesan **respons** dari server kembali ke browser. Detail pesan HTTP OK diperiksa pada jendela isi-paket, dengan informasi Frame, Ethernet, IP, dan TCP diminimalkan, sementara informasi HTTP dimaksimalkan.

## HTTP Conditional GET/Response Interaction

6. Cache dan history browser dibersihkan terlebih dahulu, kemudian pengambilan paket Wireshark dimulai.

7. URL `http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file2.html` dimasukkan ke browser, menampilkan file HTML lima baris yang sederhana.

8. URL yang sama dimasukkan kembali dengan cepat (atau tombol *refresh* ditekan), untuk memicu mekanisme *conditional GET* pada browser.

9. Pengambilan paket Wireshark dihentikan, dan filter `http` diterapkan pada jendela spesifikasi filter tampilan.

## Retrieving Long Documents

10. Cache dan history browser dibersihkan kembali, kemudian pengambilan paket Wireshark dimulai.

11. URL `http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file3.html` dimasukkan ke browser, menampilkan dokumen *Bill of Rights* AS yang relatif panjang.

12. Pengambilan paket Wireshark dihentikan, dan filter `http` diterapkan agar hanya pesan HTTP yang ditampilkan.

13. Pada jendela daftar paket, terlihat pesan HTTP GET diikuti oleh respons TCP multi-paket. Hal ini terjadi karena ukuran file HTML (sekitar 4500 byte) terlalu besar untuk dimuat dalam satu paket TCP, sehingga respons HTTP terfragmentasi menjadi beberapa paket TCP yang ditandai dengan keterangan **"TCP segment of a reassembled PDU"** pada kolom Info.

## HTML Documents dengan Embedded Objects

14. Cache dan history browser dibersihkan, kemudian pengambilan paket Wireshark dimulai.

15. URL `http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file4.html` dimasukkan ke browser, menampilkan file HTML pendek yang berisi dua gambar. Kedua gambar tersebut tidak disertakan langsung dalam file HTML, melainkan hanya direferensikan melalui URL, sehingga browser perlu mengambil gambar tersebut secara terpisah dari situs `gaia.cs.umass.edu`.

16. Pengambilan paket Wireshark dihentikan, dan filter `http` diterapkan agar hanya pesan HTTP yang ditampilkan.

## HTTP Authentication

17. Cache dan history browser dibersihkan, kemudian pengambilan paket Wireshark dimulai.

18. URL `http://gaia.cs.umass.edu/wireshark-labs/protected_pages/HTTP-wireshark-file5.html` dimasukkan ke browser. Username `wireshark-students` dan password `network` dimasukkan pada kotak pop-up autentikasi yang muncul.

19. Pengambilan paket Wireshark dihentikan, dan filter `http` diterapkan agar hanya pesan HTTP yang ditampilkan.

20. Pada pesan HTTP GET yang dikirim klien, ditemukan header **"Authorization: Basic"** yang berisi string `d2lyZXNoYXJrLXN0dWRlbnRzOm5ldHdvcms=`. String tersebut merupakan hasil enkode Base64 dari kombinasi username dan password, bukan hasil enkripsi.

21. String Base64 tersebut didekode melalui `motobit.com/util/base64-decoder-encoder.asp`, menghasilkan kembali username dan password dalam bentuk teks ASCII biasa. Hal ini menunjukkan bahwa autentikasi HTTP dasar tanpa enkripsi tambahan tidak aman, karena siapa pun yang menangkap paket dapat menerjemahkan kembali Base64 ke ASCII dengan mudah.
