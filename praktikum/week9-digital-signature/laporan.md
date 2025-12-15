# Laporan Praktikum Kriptografi
Minggu ke-: 9
Topik: Digital Signature (RSA/DSA) 
Nama:dhea silvia
NIM: 230202742
Kelas: 5IKRB

---

## 1. Tujuan
1. Mengimplementasikan tanda tangan digital menggunakan algoritma RSA/DSA.  
2. Memverifikasi keaslian tanda tangan digital.  
3. Menjelaskan manfaat tanda tangan digital dalam otentikasi pesan dan integritas data.  
---

## 2. Dasar Teori
  Tanda tangan digital berbasis RSA bekerja dengan prinsip kriptografi kunci publik. Tahap awalnya adalah menghasilkan nilai hash dari pesan yang akan dikirim, lalu hash tersebut dienkripsi menggunakan kunci privat milik pengirim sebagai tanda tangan digital. Ketika pesan diterima, penerima dapat melakukan verifikasi dengan memanfaatkan kunci publik pengirim dan membandingkannya dengan hash pesan yang dihitung ulang. Salah satu keunggulan RSA terletak pada konsepnya yang relatif mudah dipahami serta penerapannya yang telah luas di berbagai sistem keamanan.

Di sisi lain, DSA (Digital Signature Algorithm) menggunakan pendekatan matematis yang berbeda, yaitu logaritma diskret dalam aritmetika modular. Algoritma ini umumnya lebih efisien pada proses pembangkitan tanda tangan, meskipun waktu verifikasinya cenderung sedikit lebih lambat dibandingkan RSA. Keamanan DSA sangat bergantung pada penggunaan bilangan acak (nonce) yang unik setiap kali proses penandatanganan dilakukan, karena pengulangan nilai tersebut dapat menyebabkan kebocoran kunci.

Pada akhirnya, baik RSA maupun DSA memiliki tujuan yang sama, yaitu menjamin keaslian pesan, menjaga integritas data, serta mencegah penyangkalan dalam komunikasi digital. Perbedaan utama keduanya terletak pada dasar matematis dan karakteristik kinerjanya, namun kedua algoritma ini tetap memegang peranan penting dalam pengembangan dan pembelajaran teknologi keamanan modern.

## 3. Alat dan Bahan
- Python 3.x  
- Visual Studio Code 
- Git dan akun GitHub  
- Google Chrome

---

## 4. Langkah Percobaan
1. Membuat file `signature.py` di folder `praktikum/week9-digital-signature/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python signtaure

---

## 5. Source Code
Langkah 1 - Generate Key dan Buat Tanda Tangan
```
from Crypto.PublicKey import RSA
from Crypto.Signature import pkcs1_15
from Crypto.Hash import SHA256

# Generate pasangan kunci RSA
key = RSA.generate(2048)
private_key = key
public_key = key.publickey()

# Pesan yang akan ditandatangani
message = b"Hello, ini pesan penting."
h = SHA256.new(message)

# Buat tanda tangan dengan private key
signature = pkcs1_15.new(private_key).sign(h)
print("Signature:", signature.hex())
```

```
Langkah 2 — Verifikasi Tanda Tangan
```
try:
    pkcs1_15.new(public_key).verify(h, signature)
    print("Verifikasi berhasil: tanda tangan valid.")
except (ValueError, TypeError):
    print("Verifikasi gagal: tanda tangan tidak valid.")
```
Hasilnya :
```
Verifikasi berhasil: tanda tangan valid.
```
Langkah 3 — Uji Modifikasi Pesan
```
# Modifikasi pesan
fake_message = b"Hello, ini pesan palsu."
h_fake = SHA256.new(fake_message)

try:
    pkcs1_15.new(public_key).verify(h_fake, signature)
    print("Verifikasi berhasil (seharusnya gagal).")
except (ValueError, TypeError):
    print("Verifikasi gagal: tanda tangan tidak cocok dengan pesan.")
```
Hasilnya :
```
Verifikasi gagal: tanda tangan tidak cocok dengan pesan.
```

Signature :
```
from Crypto.PublicKey import RSA
from Crypto.Signature import pkcs1_15
from Crypto.Hash import SHA256

# Generate pasangan kunci RSA
key = RSA.generate(2048)
private_key = key
public_key = key.publickey()

# Pesan yang akan ditandatangani
message = b"Hello, ini pesan penting."
h = SHA256.new(message)

# Buat tanda tangan dengan private key
signature = pkcs1_15.new(private_key).sign(h)
print("Signature:", signature.hex())

try:
    pkcs1_15.new(public_key).verify(h, signature)
    print("Verifikasi berhasil: tanda tangan valid.")
except (ValueError, TypeError):
    print("Verifikasi gagal: tanda tangan tidak valid.")
```
Hasilnya :
```
Signature: 6bf5ea2a5dee7297c0ac6ae2c5c847bfd45194e94567f408835204499e3be947f3b6b96707e2340945b18763cdc5581b3a02085cc30e90c5425bf1f352abf65bb22a9426beb3a243685a94560705f65cd4129851fe62f28b42dcc1a39859f4c4f3121f789cd3b222de9cdf77a8dd145c1a47b7ca611e4e88be6d3b85c4078f132c25828cfc995f4274172c43b33ef4af29dbfca3c609771f5a5a06209ed6850f8ed3e5fd26fbe6842260bbe1736e5ca609a6e1840afe58e5ee3ea68572a0cd4e73904ef803dd65a4ad29882950f71678793a189387659947df7fffdfc1fed64387ffaeacc3c3eff4c6921b37dede8cdc970e5dae714876730109545ccdfc59d4
Verifikasi berhasil: tanda tangan valid.
```

Signature Modifikasi :
```
from Crypto.PublicKey import RSA
from Crypto.Signature import pkcs1_15
from Crypto.Hash import SHA256

# Generate pasangan kunci RSA
key = RSA.generate(2048)
private_key = key
public_key = key.publickey()

# Pesan yang akan ditandatangani(
message = b"Hello, ini pesan penting."
h = SHA256.new(message)

# Buat tanda tangan dengan private key
signature = pkcs1_15.new(private_key).sign(h)
print("Signature:", signature.hex())

# Modifikasi pesan
fake_message = b"Hello, ini pesan palsu."
h_fake = SHA256.new(fake_message)

try:
    pkcs1_15.new(public_key).verify(h_fake, signature)
    print("Verifikasi berhasil (seharusnya gagal).")
except (ValueError, TypeError):
    print("Verifikasi gagal: tanda tangan tidak cocok dengan pesan.")
```

Hasilnya :
```
Signature: 16c9261c372ab9a0220a8f5f368394e72defe0178371e4f23b0ae1a4f1e8c1ffbfc691ecf256b8464a9a9b98883ab5e8b6ec476a67f73a5b42db77462ed40017b491ddaa23183349d17813028f736b9a47921c186e2ac174e87a6a5a4391cba23c559c23e363e3c48f8384e538d7b50c9fa5ceb1dee1c7f3e4c174b544e8aed623f92ffadd4baa4eda2e106ca2d0a266081aaa9fc8d6f569d93225b907c6065d2783ef6d54d816aae72b76d2ba492db200259a16233243926405422e06ccd0469ea623b8c12c58aebac0201e5313f60bd64f559445900a961298527407be7d5106a083070873db3c79f9858b3885027610d1ffb542edb77e33127c2d5f1aa27c
Verifikasi gagal: tanda tangan tidak cocok dengan pesan.
```

---

## 6.hasil dan pembahasan

![IMG-20251215-WA0013](https://github.com/user-attachments/assets/a88b0acd-3a55-4c49-b248-1ea71affc276)
![IMG-20251215-WA0013](https://github.com/user-attachments/assets/aab9cf61-7bd3-4e2e-b3e8-089e820e0905)

---

## 7. Jawaban Pertanyaan
1. Apa perbedaan utama antara enkripsi RSA dan tanda tangan digital RSA?
2. Mengapa tanda tangan digital menjamin integritas dan otentikasi pesan?
3. Bagaimana peran Certificate Authority (CA) dalam sistem tanda tangan digital modern?

Jawaban : 

1. Perbedaan Utama Enkripsi RSA dan Digital Signature RSA ada pada tujuan serta arah penggunaan kunci yang berbeda:

    a. Enkripsi RSA

     1. Penerima membuka pesan dengan private key miliknya.
       
     2. Tujuan utama: menjaga kerahasiaan pesan (confidentiality).

    b. Tanda Tangan Digital RSA
   
     1. Pengirim menandatangani pesan menggunakan private key miliknya.
     
     2. Penerima memverifikasi tanda tangan menggunakan public key pengirim.
       
     3. Tujuan: menjamin keaslian (authenticity) dan integritas pesan.

2. Karena tanda tangan digital memanfaatkan hashing untuk membuat sidik jari pesan. Ketika pesan diubah sedikit saja, nilai hash akan berubah total sehingga proses verifikasi langsung gagal. Karena tanda tangan hanya dapat dibuat menggunakan private key pemiliknya, siapa pun yang memverifikasi tanda tangan dengan public key pengirim dapat memastikan: Pesan tidak diubah integrity,Pesan benar dari pengirim yang sah → authenticity

3. Peran Certificate Authority (CA) dalam sistem digital signature adalah sebagai pihak ketiga yang berfungsi untuk:

    1. Memverifikasi identitas pemilik kunci publik

    2. Menerbitkan digital certificate yang menghubungkan identitas seseorang/organisasi dengan public key

    3. Menjadi dasar trust dalam sistem keamanan modern seperti HTTPS, email secure, dan dokumen bertanda tangan digital
---

## 8. Kesimpulan
Berdasarkan hasil praktikum, dapat disimpulkan bahwa tanda tangan digital hanya dapat dinyatakan sah apabila pesan yang diverifikasi benar-benar identik dengan pesan saat proses penandatanganan dilakukan. Perubahan sekecil apa pun pada isi pesan akan menyebabkan verifikasi gagal karena nilai hash yang dihasilkan menjadi berbeda. Hal ini membuktikan bahwa mekanisme digital signature sangat andal dalam menjamin keaslian, integritas, serta keamanan data selama proses pengiriman
---

## 9. Daftar Pustaka 

---

## 10. Commit Log

```
commit week9-digital-signature
Author dhea silvia <dheasilvia51@gmail.com>
Date:   2025-12-13

  week9-digital-signature:  Digital Signature (RSA/DSA) 
```
