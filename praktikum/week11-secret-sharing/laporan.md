# Laporan Praktikum Kriptografi
Minggu ke-: 11
Topik:Secret Sharing (Shamir’s Secret Sharing)
Nama: Dhea Silvia 
NIM: 230202742
Kelas: 5IKRB

---

## 1. Tujuan
1. Menjelaskan konsep **Shamir Secret Sharing** (SSS).  
2. Melakukan simulasi pembagian rahasia ke beberapa pihak menggunakan skema SSS.  
3. Menganalisis keamanan skema distribusi rahasia.
---

## 2. Dasar Teori
Shamir Secret Sharing (SSS) adalah teknik kriptografi yang digunakan untuk membagi suatu informasi rahasia menjadi beberapa bagian yang disebut share, lalu mendistribusikannya kepada sejumlah pihak. Metode ini dikembangkan oleh Adi Shamir dengan memanfaatkan konsep polinomial dalam matematika. Dalam skema SSS, sebuah rahasia dipecah menjadi n share, namun hanya dapat direkonstruksi kembali apabila minimal k share berhasil dikumpulkan. Jika jumlah share yang tersedia kurang dari nilai ambang tersebut, maka informasi rahasia tidak dapat diketahui, sehingga tidak ada satu pihak pun yang memiliki kendali penuh atas rahasia tersebut.

Pada proses pembagian rahasia menggunakan SSS, nilai rahasia dimasukkan sebagai konstanta dalam sebuah polinomial berderajat k−1. Polinomial ini kemudian dihitung pada beberapa nilai tertentu untuk menghasilkan share yang berbeda bagi setiap pihak. Untuk memperoleh kembali rahasia awal, diperlukan minimal k share yang digabungkan menggunakan teknik interpolasi Lagrange. Dengan mekanisme ini, dapat dipahami bahwa kepemilikan satu share saja tidak cukup untuk mengungkap informasi rahasia.

Dari segi keamanan, Shamir Secret Sharing memiliki keunggulan karena tidak bergantung pada kemampuan komputasi pihak penyerang. Pihak yang hanya memiliki share di bawah batas threshold tidak akan mendapatkan informasi apa pun mengenai rahasia yang dilindungi. Oleh sebab itu, skema ini banyak digunakan dalam sistem yang memerlukan tingkat keamanan tinggi, seperti manajemen kunci kriptografi, sistem pengendalian bersama, serta penyimpanan data sensitif. Dengan demikian, SSS merupakan solusi yang efektif untuk mendistribusikan rahasia secara aman dan terkendali.

---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

---

## 4. Source Code
from secretsharing import SecretSharer

# Rahasia yang ingin dibagi
secret = "KriptografiUPB2025"

# Bagi menjadi 5 shares, ambang batas 3 (minimal 3 shares untuk rekonstruksi)
shares = SecretSharer.split_secret(secret, 3, 5)
print("Shares:", shares)

# Rekonstruksi rahasia dari 3 shares
recovered = SecretSharer.recover_secret(shares[:3])
print("Recovered secret:", recovered)

## 6. Hasil dan Pembahasan
(- Lampirkan screenshot hasil eksekusi program (taruh di folder `screenshots/`).  
- Berikan tabel atau ringkasan hasil uji jika diperlukan.  
- Jelaskan apakah hasil sesuai ekspektasi.  
- Bahas error (jika ada) dan solusinya. 

Hasil eksekusi program Caesar Cipher:

<img width="1366" height="768" alt="Capture 2" src="https://github.com/user-attachments/assets/9ddf1957-7946-4120-9370-e6e0b6b471c0" />/output.png)
)

---<img width="1366" height="768" alt="capture 1" src="https://github.com/user-attachments/assets/7f5c5652-26ac-4329-b762-3b1e0f707b3f" />
<img width="1366" height="768" alt="Capture 3" src="https://github.com/user-attachments/assets/29275393-b0ac-471e-abcb-e799bb980c33" />


## 7. Jawaban Pertanyaan
1. Apa keuntungan utama Shamir Secret Sharing dibanding membagikan salinan kunci secara langsung?

Keuntungan utama Shamir Secret Sharing adalah tidak ada satu pihak pun yang memegang kunci secara utuh. Berbeda dengan pembagian salinan kunci secara langsung yang berisiko bocor jika satu pihak disusupi, pada SSS satu share saja tidak memberikan informasi apa pun tentang rahasia. Dengan demikian, risiko kebocoran atau penyalahgunaan kunci dapat diminimalkan.

2. Apa peran threshold (k) dalam keamanan secret sharing?

Threshold (k) berfungsi sebagai batas minimum jumlah share yang harus dikumpulkan untuk merekonstruksi rahasia. Jika jumlah share kurang dari k, rahasia tidak dapat diketahui sama sekali. Semakin besar nilai k, semakin tinggi tingkat keamanan karena semakin banyak pihak yang harus bekerja sama untuk mengungkap rahasia.

3. Berikan satu contoh skenario nyata di mana SSS sangat bermanfaat.

Salah satu contoh penerapan SSS adalah pada pengelolaan kunci enkripsi data perusahaan. Kunci enkripsi dibagi ke beberapa administrator sistem, dan kunci tersebut hanya dapat digunakan apabila minimal sejumlah administrator (misalnya 3 dari 5 orang) menyetujui dan menggabungkan share mereka. Hal ini mencegah penyalahgunaan kunci oleh satu orang serta meningkatkan keamanan data penting perusahaan.

## 8. Kesimpulan
Shamir Secret Sharing merupakan metode kriptografi yang efektif untuk mendistribusikan rahasia secara aman dengan membaginya ke dalam beberapa share dan menggunakan mekanisme threshold. Skema ini memastikan bahwa tidak ada satu pihak pun yang memiliki akses penuh terhadap rahasia, sehingga risiko kebocoran dapat diminimalkan. Dengan tingkat keamanan yang tidak bergantung pada kemampuan komputasi, SSS sangat cocok diterapkan pada sistem yang membutuhkan perlindungan data dan kunci kriptografi tingkat tinggi.

## 9. Daftar Pustaka
Shamir, A. (1979). How to Share a Secret. Communications of the ACM, 22(11), 612–613.

Stinson, D. R. (2006). Cryptography: Theory and Practice (3rd ed.). Boca Raton: CRC Press.

Menezes, A. J., van Oorschot, P. C., & Vanstone, S. A. (1996). Handbook of Applied Cryptography. Boca Raton: CRC Press.

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit week 11 -secret sharing
Author: Dhea Silvia <dheasilvia5151@gmail.com>
Date:   2025-12-26

    week11-cryptosystem: secret sharing 
```
