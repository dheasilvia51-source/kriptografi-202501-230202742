# Laporan Praktikum Kriptografi
Minggu ke-:12
Topik:aplikasi-tls 
Nama: Dhea Silvia
NIM: 230202742
Kelas: 5ikrb

---

## 1. Tujuan
1. Menganalisis penggunaan kriptografi pada email dan SSL/TLS.
2. Menjelaskan enkripsi dalam transaksi e-commerce.
3. Mengevaluasi isu etika & privasi dalam penggunaan kriptografi di kehidupan sehari-hari.


## 2. Dasar Teori
Transport Layer Security (TLS) merupakan sebuah protokol keamanan yang dirancang untuk melindungi pertukaran data dalam jaringan komputer, terutama pada layanan berbasis internet. Protokol ini beroperasi pada lapisan transport dan bertujuan memastikan kerahasiaan data, menjaga keutuhan informasi, serta melakukan proses otentikasi antara pihak klien dan server. TLS adalah pengembangan lanjutan dari Secure Socket Layer (SSL) dan saat ini digunakan sebagai standar utama dalam komunikasi jaringan yang aman.

Dalam implementasinya, TLS menggabungkan teknik kriptografi asimetris dan simetris. Kriptografi asimetris dimanfaatkan pada tahap handshake untuk proses verifikasi identitas dan pertukaran kunci secara aman, umumnya melalui sertifikat digital yang dikeluarkan oleh Certificate Authority (CA). Setelah kunci sesi berhasil disepakati, TLS kemudian menggunakan kriptografi simetris yang lebih efisien untuk mengenkripsi data selama proses komunikasi berlangsung. TLS banyak diterapkan pada berbagai layanan jaringan seperti HTTPS pada web, layanan email (SMTPS, IMAPS), VPN, serta berbagai aplikasi client-server. Keberadaan TLS sangat penting karena mampu melindungi data yang dikirim melalui jaringan publik dari ancaman penyadapan, perubahan data, dan serangan Man-in-the-Middle (MITM), sehingga keamanan transaksi dan pertukaran informasi digital dapat terjaga.
---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

---

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `caesar_cipher.py` di folder `praktikum/week2-cryptosystem/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)

---

## 5. Source Code
(Salin kode program utama yang dibuat atau dimodifikasi.  
Gunakan blok kode:

```python
# contoh potongan kode
def encrypt(text, key):
    return ...
```
)

---

## 6. Hasil dan Pembahasan
(- Lampirkan screenshot hasil eksekusi program (taruh di folder `screenshots/`).  
- Berikan tabel atau ringkasan hasil uji jika diperlukan.  
- Jelaskan apakah hasil sesuai ekspektasi.  
- Bahas error (jika ada) dan solusinya. 

Hasil eksekusi program Caesar Cipher:

![Hasil Eksekusi](screenshots/output.png)
![Hasil Input](screenshots/input.png)
![Hasil Output](screenshots/output.png)
)

---

## 7. Jawaban Pertanyaan
(Jawab pertanyaan diskusi yang diberikan pada modul.  
- Pertanyaan 1: …  
- Pertanyaan 2: …  
)
---

## 8. Kesimpulan
(Tuliskan kesimpulan singkat (2–3 kalimat) berdasarkan percobaan.  )

---

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
