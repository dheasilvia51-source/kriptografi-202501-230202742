# Laporan Praktikum Kriptografi
Minggu ke-: 10  
Topik: Public Key Infrastructure (PKI & Certificate Authority)  
Nama: Dhea Silvia
NIM: 230202742 
Kelas: 5IKRB  

## 1. Tujuan
1. Membuat sertifikat digital sederhana.
2. Menjelaskan peran Certificate Authority (CA) dalam sistem PKI.
3. Mengevaluasi fungsi PKI dalam komunikasi aman (contoh: HTTPS, TLS).

## 2. Dasar Teori
PKI pada dasarnya adalah mesin kepercayaan yang dibangun di atas kriptografi kunci publik. Sistem ini memanfaatkan pasangan kunci public key dan private key, lalu menambahkan struktur otoritas tepercaya (CA), sertifikat digital, dan proses validasi agar dua pihak bisa saling percaya walaupun tidak saling kenal. Inti kerjanya: memastikan identitas, menjaga kerahasiaan data, dan menjamin integritas komunikasi. PKI bekerja dengan konsep sertifikat digital yang mengikat public key dengan identitas pemiliknya, dan sertifikat itu diverifikasi menggunakan tanda tangan digital dari CA yang sudah dipercaya oleh browser atau OS. Karena itulah PKI jadi pondasi utama pada HTTPS/TLS, email terenkripsi, tanda tangan digital, dan banyak sistem otentikasi modern.

## 3. Alat dan Bahan
- Python 
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
  

## 4. Langkah Percobaan
1. Membuat file `pki.py` di folder `praktikum/week10-pki/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python pki.py`.)
4. mengerjakan kuis

## 5. Source Code
from cryptography import x509
from cryptography.x509.oid import NameOID
from cryptography.hazmat.primitives import hashes, serialization
from cryptography.hazmat.primitives.asymmetric import rsa
from datetime import datetime, timedelta

# Generate key pair
key = rsa.generate_private_key(public_exponent=65537, key_size=2048)

# Buat subject & issuer (CA sederhana = self-signed)
subject = issuer = x509.Name([
    x509.NameAttribute(NameOID.COUNTRY_NAME, u"ID"),
    x509.NameAttribute(NameOID.ORGANIZATION_NAME, u"UPB Kriptografi"),
    x509.NameAttribute(NameOID.COMMON_NAME, u"example.com"),
])

# Buat sertifikat
cert = (
    x509.CertificateBuilder()
    .subject_name(subject)
    .issuer_name(issuer)
    .public_key(key.public_key())
    .serial_number(x509.random_serial_number())
    .not_valid_before(datetime.utcnow())
    .not_valid_after(datetime.utcnow() + timedelta(days=365))
    .sign(key, hashes.SHA256())
)

# Simpan sertifikat
with open("cert.pem", "wb") as f:
    f.write(cert.public_bytes(serialization.Encoding.PEM))

print("Sertifikat digital berhasil dibuat: cert.pem")

## 6. Hasil dan Pembahasan


![IMG-20251215-WA0015](https://github.com/user-attachments/assets/c0ef4c85-e7f0-4c38-972f-32139793edda)
![IMG-20251215-WA0014](https://github.com/user-attachments/assets/aa2f0c52-2259-4d30-a6e3-136947a97a5a)


1. Penggunaan public key untuk memverifikasi tanda tangan sertifikat

Tanda tangan digital pada sertifikat X.509 dihasilkan menggunakan private key milik pihak penerbit sertifikat, yang umumnya adalah Certificate Authority (CA) atau bersifat self-signed pada sistem tertentu. Untuk memastikan bahwa sertifikat tersebut valid dan tidak mengalami perubahan, proses verifikasi dilakukan dengan memanfaatkan public key milik penerbit. Verifikasi ini bertujuan mencocokkan tanda tangan digital dengan data sertifikat yang belum ditandatangani (TBS certificate). Apabila proses verifikasi berhasil, dapat dipastikan bahwa sertifikat masih utuh dan asli. Sebaliknya, jika verifikasi gagal, sertifikat dianggap tidak valid atau telah dimodifikasi. Dengan mekanisme ini, public key penerbit berfungsi sebagai sarana pembuktian keaslian dan integritas sertifikat.

2. Peran CA dalam menjamin keaslian sertifikat

Certificate Authority (CA) bertindak sebagai pihak tepercaya yang menjamin bahwa sertifikat digital benar-benar mewakili identitas pemiliknya. Sebelum menerbitkan sertifikat, CA akan melakukan proses verifikasi identitas pemohon, baik individu, organisasi, maupun pemilik domain, sesuai prosedur yang berlaku. Setelah identitas dinyatakan valid, CA menerbitkan sertifikat yang berisi identitas dan public key pemilik, kemudian menandatanganinya menggunakan private key CA. Karena CA telah terdaftar sebagai pihak tepercaya pada browser dan sistem operasi, sertifikat yang ditandatangani olehnya dapat diverifikasi dan dipercaya. Dengan demikian, CA menjadi elemen utama dalam membangun kepercayaan pada sistem keamanan digital.

3. Cara browser memverifikasi sertifikat HTTPS

Browser akan menerima sertifikat dari server dan memeriksa tanda tangan digitalnya menggunakan public key CA yang tersimpan dalam daftar trusted root. Selain itu, browser juga mengecek kesesuaian nama domain, masa berlaku sertifikat, serta status pencabutan. Jika seluruh pemeriksaan tersebut terpenuhi, browser akan menganggap koneksi aman dan melanjutkan komunikasi secara terenkripsi.

4. Dampak jika CA palsu menerbitkan sertifikat

Sertifikat yang diterbitkan oleh CA palsu umumnya akan langsung ditolak oleh browser karena tidak terdaftar sebagai CA tepercaya. Namun, apabila CA resmi berhasil diretas dan mengeluarkan sertifikat ilegal, penyerang dapat menyamar sebagai situs asli dan melakukan serangan man-in-the-middle. Oleh sebab itu, browser dan sistem keamanan akan segera mencabut kepercayaan terhadap CA yang terbukti bermasalah.

5. Alasan pentingnya PKI dalam komunikasi aman

Public Key Infrastructure (PKI) memiliki peran penting dalam menjamin keamanan komunikasi digital, terutama dalam memastikan identitas pihak yang berkomunikasi, menjaga integritas data, dan mendukung proses enkripsi. Dalam aktivitas seperti transaksi online, PKI memastikan bahwa pengguna terhubung ke situs yang sah serta melindungi data sensitif, seperti kata sandi dan informasi keuangan, dari penyadapan maupun manipulasi.


## 7. Jawaban Pertanyaan
1. Apa fungsi utama Certificate Authority (CA)?

Certificate Authority (CA) berfungsi sebagai pihak ketiga tepercaya yang memverifikasi identitas pemilik sertifikat dan kemudian menandatangani sertifikat digital mereka. Dengan adanya tanda tangan CA, browser dan sistem lain dapat yakin bahwa public key dalam sertifikat benar-benar milik pihak yang sah, sehingga identitas server atau organisasi dapat dibuktikan. CA menjadi fondasi kepercayaan dalam ekosistem keamanan internet.

2. Mengapa self-signed certificate tidak cukup untuk sistem produksi?

Self-signed certificate tidak diakui oleh browser atau perangkat pengguna karena tidak ada pihak ketiga tepercaya yang menjamin keasliannya. Akibatnya, koneksi akan dianggap tidak aman dan pengguna akan melihat peringatan “certificate not trusted.” Dalam lingkungan produksi, terutama untuk layanan publik seperti website, API, atau aplikasi online, sertifikat harus diterbitkan oleh CA resmi agar dipercaya otomatis dan tidak memicu peringatan keamanan.

3. Bagaimana PKI mencegah serangan MITM dalam komunikasi TLS/HTTPS?

PKI mencegah serangan Man-in-the-Middle dengan memastikan bahwa pengguna hanya bisa membangun koneksi terenkripsi dengan server yang memiliki sertifikat valid dari CA tepercaya. Browser memverifikasi tanda tangan digital sertifikat, memeriksa domain, dan memastikan sertifikat belum dicabut. Jika seorang penyerang mencoba menyisipkan server palsu atau memalsukan sertifikat, verifikasi akan gagal sehingga koneksi diblokir. Dengan begitu, PKI membuat MITM hampir tidak mungkin dilakukan jika sertifikat dan CA tidak diretas.

## 8. Kesimpulan
Singkatnya, PKI adalah fondasi kepercayaan di dunia digital. Dengan menggabungkan kriptografi kunci publik, sertifikat digital, dan otoritas tepercaya (CA), PKI memastikan bahwa identitas server valid, data tidak bisa diubah, dan komunikasi tetap aman dari penyadapan maupun manipulasi. Tanpa PKI, protokol seperti HTTPS atau transaksi online tidak akan punya jaminan keaslian maupun keamanan, sehingga risiko serangan—terutama MITM—jadi jauh lebih besar. PKI hadir untuk memastikan semua pihak bisa berkomunikasi dengan aman meskipun berada di jaringan yang tidak aman.

## 9. Daftar Pustaka

## 10. Commit Log
commit week10-pki
Author: Dhea Silvia <dheasilvia51@gmail.com>
Date:   2025-12-15
