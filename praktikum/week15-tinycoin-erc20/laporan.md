# Laporan Praktikum Kriptografi
Minggu ke-: 15
Topik: tinycoin
Nama: Dhea Silvia
NIM: 230202742
Kelas: 5ikrb

---

## 1. Tujuan
1. Mengembangkan proyek sederhana berbasis algoritma kriptografi.
2. Mendokumentasikan proses implementasi proyek ke dalam repository Git.
3. Menyusun laporan teknis hasil proyek akhir.


---

## 2. Dasar Teori
Pengembangan proyek sederhana yang menerapkan algoritma kriptografi bertujuan untuk mengimplementasikan konsep keamanan informasi secara langsung dalam sebuah sistem. Pada proyek ini, kriptografi digunakan untuk melindungi data penting dengan menjaga kerahasiaan, keutuhan, serta keaslian informasi. Penerapan algoritma keamanan tersebut juga membantu dalam memahami prinsip kerja kriptografi sekaligus mengenali berbagai tantangan yang muncul saat diimplementasikan pada sistem informasi.
Seluruh tahapan pengembangan proyek didokumentasikan secara terstruktur menggunakan sistem kontrol versi Git dan disimpan pada repositori daring seperti GitHub. Dokumentasi ini meliputi kode sumber, catatan perubahan, serta penjelasan teknis terkait mekanisme kerja sistem. Dengan dokumentasi yang lengkap, proses pengembangan menjadi lebih terorganisir, mudah dilacak, serta dapat dimanfaatkan sebagai bukti pelaksanaan proyek dan bahan evaluasi.
Output akhir dari proyek kemudian dituangkan dalam bentuk laporan teknis yang menggambarkan keseluruhan proses pengembangan dan hasil implementasi. Laporan tersebut mencakup latar belakang, tujuan, landasan teori kriptografi, metode pengembangan, hingga pengujian sistem. Penyusunan laporan ini bertujuan untuk memberikan pemahaman menyeluruh mengenai penerapan algoritma kriptografi serta menilai tingkat keamanan sistem yang dibangun, sehingga dapat dijadikan acuan untuk pengembangan dan penelitian di masa mendatang.

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
1. Apa fungsi utama ERC20 dalam ekosistem blockchain?

ERC20 adalah standar teknis untuk pembuatan dan pengelolaan token di blockchain Ethereum. Fungsi utamanya adalah menyediakan aturan baku agar token dapat saling kompatibel dengan berbagai aplikasi seperti wallet, exchange, dan smart contract lainnya. Dengan adanya ERC20, pengembang tidak perlu membuat sistem token dari nol, sehingga mempercepat pengembangan aplikasi terdesentralisasi (dApp) dan memudahkan integrasi antar platform.

2. Bagaimana mekanisme transfer token bekerja dalam kontrak ERC20?
Mekanisme transfer token dalam kontrak ERC20 dilakukan melalui fungsi transfer() atau transferFrom() yang tersedia di dalam smart contract. Ketika pengguna melakukan transfer, kontrak akan memeriksa apakah saldo pengirim mencukupi, kemudian mengurangi saldo pengirim dan menambah saldo penerima sesuai jumlah token yang dikirim. Seluruh proses ini dicatat secara permanen di blockchain dan dieksekusi secara otomatis tanpa perantara, sehingga menjamin transparansi dan keandalan transaksi.

4. Apa risiko utama dalam implementasi smart contract dan bagaimana cara mitigasinya?
 Risiko utama dalam pengembangan smart contract mencakup kesalahan logika pemrograman, celah keamanan seperti serangan reentrancy, serta kelemahan dalam pengaturan hak akses. Mengingat smart contract tidak dapat dimodifikasi setelah diterapkan di blockchain, kesalahan sekecil apa pun berpotensi menimbulkan dampak kerugian yang besar. Oleh karena itu, diperlukan penerapan praktik pengembangan yang aman, seperti melakukan audit kode secara menyeluruh, pengujian sistem secara intensif, memanfaatkan library standar yang telah terpercaya, serta menerapkan kontrol akses dan pembatasan pada fungsi-fungsi krusial. Melalui langkah-langkah tersebut, tingkat keamanan dan keandalan smart contract dapat ditingkatkan secara signifikan.  

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
commit tinycoin
Author: dheasilvia < dheasilvia51@gmail.com>
Date:   2025-01-26

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
