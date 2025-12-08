# Laporan Praktikum Kriptografi
Minggu ke-: VII 
Topik: Diffie-Hellman Key Exchange 
Nama: Dimas Riyan Hidayat  
NIM: 230202746  
Kelas: 5IKRB  

---

## 1. Tujuan
1. Melakukan simulasi protokol Diffie-Hellman untuk pertukaran kunci publik.
2. Menjelaskan mekanisme pertukaran kunci rahasia menggunakan bilangan prima dan logaritma diskrit.
3. Menganalisis potensi serangan pada protokol Diffie-Hellman (termasuk serangan Man-in-the-Middle / MITM).

## 2. Dasar Teori
Dasar teori Diffie–Hellman berfokus pada mekanisme pertukaran kunci yang memungkinkan dua pihak membentuk kunci rahasia bersama tanpa pernah mengirimkan kunci itu sendiri. Protokol ini bekerja menggunakan bilangan prima besar p dan generator g, kemudian masing-masing pihak membuat private key dan menghasilkan public key melalui operasi perpangkatan modulo. Kekuatannya berasal dari Discrete Logarithm Problem, yaitu sulitnya menebak private key dari public key yang terlihat. Dengan pertukaran public key, kedua pihak dapat menghitung kunci yang sama, sementara penyadap tidak bisa menghitungnya. Namun, protokol DH murni tidak menyediakan autentikasi, sehingga rentan terhadap serangan Man-in-the-Middle ketika penyerang mengganti public key yang dikirim. Untuk mengamankan penggunaannya, DH harus dikombinasikan dengan mekanisme autentikasi seperti tanda tangan digital atau sertifikat.

## 3. Alat dan Bahan
- Python 3.14  
- Visual Studio Code / editor lain  
- Git dan akun GitHub

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `Diffie–Hellman.py` di folder `praktikum/week7-Diffie-Hellman Key Exchange/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)
4. mengerjakan pertanyaan diskusi

---

## 5. Source Code
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fd17a6c5-3173-436e-b0a8-a7fa28b7df53" />


## 6. Hasil dan Pembahasan
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4846753c-1bee-41f6-b563-41b3b34d4cfa" />


## 7. Jawaban Pertanyaan
1. Mengapa Diffie–Hellman bisa digunakan di saluran publik?
Karena protokol ini hanya menukar nilai publik seperti g^a dan g^b, sementara kunci rahasia akhirnya dibentuk dari private key masing-masing. Penyadap yang melihat nilai publik tersebut tetap tidak bisa menghitung kunci bersama karena harus memecahkan Discrete Logarithm Problem yang sangat sulit jika parameter cukup besar.

2. Apa kelemahan utama Diffie–Hellman murni?
Masalah terbesarnya adalah tidak adanya autentikasi. Alice dan Bob tidak punya cara untuk memastikan bahwa public key yang mereka terima benar berasal dari pihak yang dimaksud. Celah ini memungkinkan penyerang menyisip sebagai perantara dan melakukan serangan Man-in-the-Middle, sehingga mereka berdua membentuk kunci yang berbeda tanpa sadar.

3. Bagaimana mencegah serangan MITM pada protokol ini?
Serangan dapat dicegah dengan menambahkan lapisan autentikasi terhadap public key yang dipertukarkan. Caranya bisa melalui tanda tangan digital, sertifikat yang divalidasi oleh CA (PKI), public-key pinning, atau menggunakan versi Diffie–Hellman yang terautentikasi seperti yang dipakai di TLS, SSH, atau protokol modern lain yang menggabungkan DH dengan verifikasi identitas.
## 8. Kesimpulan
Kesimpulannya, Diffie–Hellman sangat efektif untuk membangun kunci rahasia di saluran publik karena hanya mengungkapkan nilai yang aman untuk dilihat siapa pun, sementara kunci sebenarnya dihitung dari informasi privat yang tidak pernah dikirim. Namun, tanpa autentikasi, protokol ini tetap rentan terhadap serangan penyisipan seperti Man-in-the-Middle, di mana penyerang bisa mengganti public key dan diam-diam menguasai dua kunci berbeda. Karena itu, Diffie–Hellman harus selalu dipadukan dengan mekanisme autentikasi—seperti tanda tangan digital, sertifikat, atau key pinning—agar pertukaran kunci benar-benar aman dan tidak bisa dimanipulasi pihak ketiga.

## 9. Daftar Pustaka


## 10. Commit Log
week7-diffie-hellman
Author: Dimas Riyan Hidayat <dimasriyanhidayat01@gmail.com>
Date:   2025-12-08

