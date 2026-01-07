# Laporan Praktikum Kriptografi
Minggu ke-: 13
Topik: TinyChain – Proof of Work (PoW)  
Nama: Dhea Silvia
NIM: 230202742
Kelas:5ikrb 

---

## 1. Tujuan
1. Menjelaskan peran hash function dalam blockchain.
2. Melakukan simulasi sederhana Proof of Work (PoW).
3. Menganalisis keamanan cryptocurrency berbasis kriptografi.


---

## 2. Dasar Teori
Blockchain merupakan sebuah struktur data terdistribusi yang tersusun atas kumpulan blok yang saling terhubung melalui mekanisme fungsi hash. Setiap blok berisi informasi transaksi, penanda waktu (timestamp), nilai hash dari blok sebelumnya, serta hash dari blok itu sendiri. Penggunaan fungsi hash kriptografis, seperti SHA-256, berperan penting dalam menjaga integritas data karena sifatnya yang satu arah dan sangat peka terhadap perubahan sekecil apa pun pada data masukan.

Proof of Work (PoW) adalah metode konsensus yang digunakan untuk memverifikasi dan menambahkan blok baru ke dalam jaringan blockchain. Pada mekanisme ini, penambang diwajibkan mencari nilai nonce tertentu yang mampu menghasilkan hash dengan karakteristik khusus, seperti memiliki sejumlah angka nol di bagian awal. Proses pencarian ini membutuhkan sumber daya komputasi yang besar, sehingga membuat upaya pemalsuan atau manipulasi data menjadi sangat sulit untuk dilakukan.

Keamanan blockchain dibangun dari kombinasi penerapan fungsi hash kriptografis dan mekanisme Proof of Work. Apabila terjadi perubahan data pada satu blok, maka nilai hash blok tersebut akan berubah dan menyebabkan ketidaksesuaian dengan blok-blok selanjutnya. Kondisi ini menjadikan blockchain memiliki ketahanan yang tinggi terhadap manipulasi data serta berbagai serangan, termasuk serangan double spending.

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
1. Mengapa fungsi hash sangat penting dalam blockchain?
   Fungsi hash memiliki peran yang sangat penting dalam blockchain karena digunakan untuk menjaga integritas dan keterkaitan antarblok. Setiap blok dalam blockchain menyimpan hash dari blok sebelumnya, sehingga membentuk rantai yang saling terhubung. Sifat fungsi hash yang satu arah dan sangat sensitif terhadap perubahan data menyebabkan setiap modifikasi kecil pada isi blok akan menghasilkan nilai hash yang berbeda. Dengan demikian, upaya perubahan data secara sepihak dapat dengan mudah terdeteksi karena akan merusak struktur rantai blok, sehingga blockchain menjadi lebih aman dan tahan terhadap manipulasi.
   
2. Bagaimana Proof of Work mencegah double spending?
   Proof of Work mencegah terjadinya double spending dengan mewajibkan penambang melakukan perhitungan kriptografis yang kompleks sebelum suatu transaksi dapat divalidasi dan dimasukkan ke dalam blok. Proses ini memastikan bahwa hanya satu versi transaksi yang sah yang dapat dicatat dalam blockchain berdasarkan rantai terpanjang yang memiliki kerja komputasi terbanyak. Karena setiap blok membutuhkan waktu dan sumber daya yang besar untuk dibuat, pelaku tidak dapat dengan mudah menggandakan atau mengubah transaksi yang telah dikonfirmasi, sehingga risiko double spending dapat diminimalkan.
   
3. Apa kelemahan dari PoW dalam hal efisiensi energi?
   Meskipun efektif dalam menjaga keamanan, Proof of Work memiliki kelemahan utama dari sisi efisiensi energi. Proses pencarian nonce yang tepat membutuhkan daya komputasi yang sangat tinggi dan berjalan secara kompetitif di antara banyak penambang. Akibatnya, konsumsi listrik menjadi sangat besar dan sering kali tidak sebanding dengan jumlah transaksi yang diproses. Kondisi ini menimbulkan kekhawatiran terkait dampak lingkungan serta mendorong pengembangan mekanisme konsensus alternatif yang lebih hemat energi, seperti Proof of Stake.


## 8. Kesimpulan
    TinyChain dengan mekanisme Proof of Work menggambarkan cara blockchain menjaga keamanan data melalui penerapan fungsi hash dan sistem konsensus. Walaupun memberikan tingkat keamanan yang tinggi, Proof of Work memiliki keterbatasan dalam hal efisiensi energi, sehingga diperlukan pertimbangan terhadap penggunaan mekanisme konsensus alternatif yang lebih efisien.

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
