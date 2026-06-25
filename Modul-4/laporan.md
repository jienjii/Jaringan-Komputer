**Nama: Angeli Thie**

**Kelas: IF-04-04**

**NIM: 103072400032**

# Modul 4 DNS
## Nslookup

1. Perintah `nslookup www.mit.edu` dijalankan melalui Command Prompt, menghasilkan informasi nama dan alamat IP server DNS yang memberikan jawaban, serta nama host dan alamat IP dari `www.mit.edu`.
<img width="1125" height="619" alt="image" src="https://github.com/user-attachments/assets/52d4ed20-cbac-4e00-a714-71e50398f3c7" />

2. Perintah `nslookup -type=NS mit.edu` dijalankan untuk meminta informasi server DNS otoritatif dari domain `mit.edu`. Hasilnya menunjukkan nama-nama server DNS otoritatif MIT beserta alamat IP-nya, meskipun jawaban yang diberikan bersifat non-otoritatif (berasal dari cache).
<img width="1130" height="619" alt="image" src="https://github.com/user-attachments/assets/c1d4d6e8-bb47-4045-99e5-a68bb987234b" />

3. Perintah `nslookup www.aiit.or.kr bitsy.mit.edu` dijalankan untuk mengirimkan permintaan langsung ke server DNS `bitsy.mit.edu`, menghasilkan alamat IP dari host `www.aiit.or.kr`.
<img width="1132" height="661" alt="image" src="https://github.com/user-attachments/assets/759dcc02-ff2e-46e0-a22c-abdf0cc6f9fa" />

4. Pengujian mandiri dilakukan dengan menjalankan `nslookup` untuk beberapa kasus:
   - Mencari alamat IP server web di Asia
   - Mencari server DNS otoritatif untuk universitas di Eropa
   - Mencari informasi server email Yahoo! Mail melalui salah satu server yang ditemukan sebelumnya
<img width="1128" height="661" alt="image" src="https://github.com/user-attachments/assets/203601e9-13f7-469f-952a-fdf686d14abc" />
<img width="1123" height="659" alt="image" src="https://github.com/user-attachments/assets/3772a49b-bb38-433a-acf1-616c696e27df" />

## Ipconfig

5. Perintah `ipconfig /all` dijalankan pada Command Prompt untuk menampilkan informasi TCP/IP host, termasuk alamat IP, alamat server DNS, dan jenis adaptor yang digunakan.
<img width="1130" height="661" alt="image" src="https://github.com/user-attachments/assets/86b7f286-0b63-4214-b6aa-5ebc7d7b43dd" />

6. Perintah `ipconfig /displaydns` dijalankan untuk melihat record DNS yang tersimpan di host beserta sisa *Time To Live* (TTL)-nya, kemudian perintah `ipconfig /flushdns` dijalankan untuk menghapus seluruh record DNS yang tersimpan.
<img width="1128" height="656" alt="image" src="https://github.com/user-attachments/assets/9bb4c76a-9e98-48f6-b678-7737fd5e60b8" />
<img width="1130" height="661" alt="image" src="https://github.com/user-attachments/assets/1b8887ce-1b7d-4f00-9897-74f0ba997c24" />

### Tracing DNS dengan Wireshark

7. Catatan DNS pada host dikosongkan menggunakan `ipconfig /flushdns`, dan cache browser dibersihkan terlebih dahulu sebelum pengambilan paket dimulai.

8. Filter `ip.addr == <alamat_IP_host>` diterapkan pada Wireshark untuk hanya menampilkan paket yang berasal dari atau ditujukan ke host yang digunakan.
<img width="1646" height="512" alt="image" src="https://github.com/user-attachments/assets/668cad48-7d12-410c-80bc-0892945db83c" />

9. Pengambilan paket dimulai, kemudian halaman `http://www.ietf.org` diakses melalui browser, dan pengambilan paket dihentikan setelah halaman selesai dimuat.
