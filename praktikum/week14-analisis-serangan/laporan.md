# Laporan Praktikum Kriptografi
Minggu ke-: 14
Topik: analisis serangan kriptografi 
Nama: Dhea Silvia
NIM: 230202742
Kelas:5ikrb  

---

## 1. Tujuan
1. Mengidentifikasi jenis serangan pada sistem informasi nyata.
2. Mengevaluasi kelemahan algoritma kriptografi yang digunakan.
3. Memberikan rekomendasi algoritma kriptografi yang sesuai untuk perbaikan keamanan.

## 2. Dasar Teori
Studi kasus yang dianalisis adalah penggunaan algoritma hash MD5
untuk penyimpanan password pengguna. MD5 merupakan algoritma hash
yang saat ini sudah tidak direkomendasikan karena rentan terhadap
serangan brute force dan dictionary attack. Penyerang dapat mencocokkan hash MD5 dengan database hash yang sudah
diketahui sehingga password dapat ditemukan dalam waktu singkat.

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
import hashlib

password = "admin123"
md5_hash = hashlib.md5(password.encode()).hexdigest()
sha256_hash = hashlib.sha256(password.encode()).hexdigest()

print("Password:", password)
print("MD5:", md5_hash)
print("SHA-256:", sha256_hash)


## 6. Hasil dan Pembahasan

<img width="1366" height="768" alt="Screenshot 2026-01-17 113446" src="https://github.com/user-attachments/assets/7ad2a5b3-1ab2-40b8-a19a-1d7fd96aa2a8" />

## 7. Jawaban Pertanyaan
. 1. Mengapa banyak sistem lama masih rentan terhadap brute force?**  
  = Karena masih menggunakan algoritma kriptografi lama yang sudah
   tidak aman dan belum diperbarui.

2. Apa perbedaan kelemahan algoritma dan implementasi?**  
  = Kelemahan algoritma berasal dari desain kriptografi, sedangkan
   kelemahan implementasi berasal dari kesalahan konfigurasi atau
   penggunaan algoritma.

3. Bagaimana memastikan sistem tetap aman di masa depan?**  
   = Dengan melakukan audit keamanan berkala, memperbarui algoritma
   kriptografi, dan mengikuti standar keamanan terbaru.


## 8. Kesimpulan
Analisis menunjukkan bahwa penggunaan algoritma kriptografi lemah
seperti MD5 dapat membahayakan keamanan sistem. Dengan mengganti
algoritma dan memperbaiki implementasi, risiko serangan kriptografi
dapat diminimalkan.

## 9. Daftar Pustaka
Stallings, W. (2017). Cryptography and Network Security. Pearson.

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2026-01-17

    week14- analisis serangan: analisis serangan dan laporan )
```
