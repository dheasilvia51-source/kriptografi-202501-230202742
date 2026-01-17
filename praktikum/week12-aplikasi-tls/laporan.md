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
riptografi pada layanan surat elektronik serta protokol SSL/TLS berfungsi untuk menjamin aspek kerahasiaan, integritas, dan autentikasi data selama proses pertukaran informasi. Pada sistem email, mekanisme seperti PGP dan S/MIME menggunakan teknik enkripsi kunci publik, sehingga hanya penerima yang memiliki kunci privat yang sesuai yang dapat mengakses isi pesan. Selain itu, penggunaan tanda tangan digital memungkinkan verifikasi identitas pengirim serta menjaga pesan agar tidak mengalami pemalsuan atau perubahan. Di sisi lain, SSL/TLS berperan dalam mengamankan komunikasi antara klien dan server pada jaringan internet dengan cara mengenkripsi data yang dikirimkan, sehingga dapat melindungi dari ancaman penyadapan maupun serangan man-in-the-middle.

Dalam aktivitas transaksi e-commerce, enkripsi memiliki peranan yang sangat penting dalam melindungi data sensitif, seperti informasi kartu pembayaran, data pribadi pengguna, serta detail transaksi. Penerapan protokol HTTPS yang berbasis SSL/TLS memastikan bahwa data yang dipertukarkan antara pengguna dan server tetap aman dari upaya pembacaan maupun manipulasi oleh pihak yang tidak memiliki otorisasi. Selain itu, kriptografi juga mendukung proses autentikasi dan non-repudiation, sehingga dapat meningkatkan rasa aman dan kepercayaan antara pihak penjual dan pembeli dalam perdagangan elektronik.

Ditinjau dari sudut pandang etika dan privasi, kriptografi menjadi instrumen penting dalam menjaga hak privasi individu dengan mencegah akses tidak sah terhadap data pribadi. Meskipun demikian, muncul tantangan etis ketika enkripsi tingkat tinggi disalahgunakan untuk menyembunyikan aktivitas ilegal atau ketika pemerintah dan lembaga tertentu berupaya membatasi maupun mengakses informasi yang terenkripsi. Oleh karena itu, penerapan kriptografi perlu diimbangi dengan kebijakan yang adil dan bertanggung jawab agar tercapai keseimbangan antara keamanan, perlindungan privasi, dan kepentingan publik.
---

## 3. Alat dan Bahan
 - web browser
- Git dan akun GitHub  
- google chrome

---

## 4. Langkah Percobaan
Analisis SSL/TLS pada Website E-commerce
Website: Tokopedia

Hasil observasi sertifikat digital pada website Tokopedia menunjukkan bahwa:

Protokol: HTTPS

Certificate Authority (CA): DigiCert Inc

Masa Berlaku Sertifikat: (sesuai hasil observasi)

Algoritma Kriptografi:

Public Key: RSA

Enkripsi Simetris: AES

Hash: SHA-256

Sertifikat digital memastikan bahwa komunikasi antara browser pengguna dan server Tokopedia telah terenkripsi serta terverifikasi keasliannya.
---

## 5. Source Code


## 6. Hasil dan Pembahasan

<img width="1365" height="767" alt="Screenshot 2026-01-17 105827" src="https://github.com/user-attachments/assets/70246828-a720-4598-a05f-3de1b55bbf39" />

 Perbedaan utama antara HTTP dan HTTPS terletak pada aspek keamanan:
HTTP: Data dikirim dalam bentuk plaintext sehingga mudah disadap.
HTTPS: Data dienkripsi menggunakan TLS sehingga lebih aman dari serangan seperti sniffing dan Man-in-the-Middle (MITM).
Dengan demikian, HTTPS memberikan perlindungan yang lebih baik terhadap data pengguna.
**Analisis Enkripsi dalam Transaksi E-commerce
 Dalam transaksi e-commerce, TLS digunakan untuk:
Mengamankan proses login pengguna.
Melindungi data pembayaran seperti nomor kartu kredit atau e-wallet.
Menjamin integritas data agar tidak dimodifikasi selama transmisi.
Tanpa penggunaan TLS, transaksi e-commerce rentan terhadap:
 - Man-in-the-Middle Attack
 - Pencurian kredensial
 - Pemalsuan data transaksi
Oleh karena itu, TLS menjadi komponen wajib dalam sistem e-commerce modern.
Analisis Etika dan Privasi
- Privasi dalam Email Terenkripsi
 Teknologi seperti PGP dan S/MIME digunakan untuk mengenkripsi email sehingga hanya penerima yang berhak dapat membaca isi pesan. Hal ini meningkatkan privasi pengguna, namun juga menimbulkan tantangan dalam pengawasan komunikasi.
- Dilema Etika
Beberapa dilema etika dalam penggunaan kriptografi antara lain:
1. Apakah perusahaan berhak mendekripsi email karyawan untuk kepentingan audit?
2. Sejauh mana pemerintah boleh melakukan pengawasan terhadap komunikasi terenkripsi demi keamanan nasional?
Di satu sisi, kriptografi melindungi privasi individu, namun di sisi lain dapat menghambat proses penegakan hukum jika disalahgunakan.

## 7. Jawaban Pertanyaan
1. Apa perbedaan utama antara HTTP dan HTTPS?
    Perbedaan utama antara HTTP dan HTTPS terletak pada aspek keamanan komunikasi data. HTTP (Hypertext Transfer Protocol) tidak menggunakan mekanisme enkripsi sehingga data yang dikirimkan antara klien dan server dapat dibaca atau dimodifikasi oleh pihak yang tidak berwenang. Sebaliknya, HTTPS (Hypertext Transfer Protocol Secure) menggunakan protokol SSL/TLS untuk mengenkripsi data selama proses transmisi. Dengan adanya enkripsi, HTTPS mampu menjamin kerahasiaan, keutuhan, dan keamanan informasi, terutama pada aktivitas yang melibatkan data sensitif seperti proses login dan transaksi pembayaran, sehingga lebih dipercaya oleh pengguna dan browser.
   
2.  Mengapa sertifikat digital menjadi penting dalam komunikasi TLS?
   Sertifikat digital memiliki peran yang sangat penting dalam komunikasi berbasis TLS karena berfungsi sebagai identitas resmi suatu server atau website. Sertifikat ini diterbitkan oleh Certificate Authority (CA) yang dipercaya secara global dan digunakan untuk memverifikasi keaslian server yang diakses oleh pengguna. Melalui sertifikat digital, klien dapat memastikan bahwa kunci publik yang digunakan untuk proses enkripsi benar-benar milik server tujuan, sehingga mampu mencegah terjadinya serangan Man-in-the-Middle. Tanpa sertifikat digital, komunikasi TLS tidak dapat menjamin autentikasi server dan kepercayaan dalam pertukaran data.

3.   agaimana kriptografi mendukung privasi dalam komunikasi digital, tetapi sekaligus menimbulkan tantangan hukum dan etika?
   Kriptografi mendukung privasi dalam komunikasi digital dengan menyediakan mekanisme enkripsi, hashing, dan tanda tangan digital yang memungkinkan data hanya dapat diakses oleh pihak yang berwenang. Teknologi ini melindungi pengguna dari penyadapan, pencurian data, serta pemalsuan informasi dalam berbagai layanan digital seperti email, web, dan aplikasi pesan instan. Namun, di sisi lain, penggunaan kriptografi juga menimbulkan tantangan hukum dan etika karena menyulitkan proses pengawasan dan penegakan hukum oleh pihak berwenang. Dilema muncul ketika kebutuhan akan keamanan dan privasi individu harus diseimbangkan dengan kepentingan keamanan nasional dan kepatuhan hukum, sehingga diperlukan regulasi yang transparan dan proporsional agar kriptografi tidak disalahgunakan tetapi tetap melindungi hak privasi pengguna.

## 8. Kesimpulan
    Berdasarkan pembahasan yang telah dilakukan, dapat disimpulkan bahwa penggunaan HTTPS dengan dukungan SSL/TLS merupakan elemen penting dalam menjaga keamanan komunikasi digital dibandingkan HTTP yang tidak menyediakan mekanisme perlindungan data. Sertifikat digital berperan krusial dalam membangun kepercayaan dan autentikasi server, sehingga mencegah terjadinya penyadapan maupun pemalsuan identitas dalam pertukaran informasi. Selain itu, kriptografi secara umum memberikan perlindungan terhadap privasi pengguna melalui enkripsi dan mekanisme keamanan lainnya, namun juga menimbulkan tantangan hukum dan etika terkait pengawasan serta penegakan hukum. Oleh karena itu, diperlukan keseimbangan antara perlindungan privasi, keamanan sistem, dan kepatuhan terhadap regulasi agar pemanfaatan teknologi kriptografi dapat memberikan manfaat maksimal tanpa mengabaikan aspek etis dan hukum.

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
Author: Dhea Silvia <dheasilvia51@gmail.com>
Date:   2025-01-07

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
