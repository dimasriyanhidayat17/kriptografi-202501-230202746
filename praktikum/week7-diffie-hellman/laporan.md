# Laporan Praktikum Kriptografi
Minggu ke-: 7
Topik: Diffie Hellman
Nama: Safira Dewi Rahmatika 
NIM: 230202784
Kelas: 5IKRB

## 1. Tujuan
1. Melakukan simulasi protokol Diffie-Hellman untuk pertukaran kunci publik.
2. Menjelaskan mekanisme pertukaran kunci rahasia menggunakan bilangan prima dan logaritma diskrit.
3. Menganalisis potensi serangan pada protokol Diffie-Hellman (termasuk serangan Man-in-the-Middle / MITM).

## 2. Dasar Teori
Protokol Diffie-Hellman adalah metode untuk melakukan pertukaran kunci rahasia melalui saluran komunikasi yang tidak aman tanpa harus mengirimkan kunci itu sendiri. Mekanismenya dimulai dari dua pihak yang sepakat memilih sebuah bilangan prima besar  dan sebuah generator , yang keduanya bersifat publik. Masing-masing pihak kemudian memilih kunci privat, misalnya  untuk pihak pertama dan  untuk pihak kedua. Selanjutnya, mereka menghitung kunci publik dengan rumus  dan , lalu saling bertukar hasilnya. Dengan memanfaatkan sifat logaritma diskrit yang sulit dipecahkan, setiap pihak dapat menghitung kunci rahasia yang sama menggunakan kunci publik lawan: pihak pertama menghitung  dan pihak kedua menghitung . Hasilnya identik meskipun mereka tidak pernah mengirim kunci rahasia secara langsung.

Namun protokol Diffie-Hellman memiliki beberapa potensi kerentanan. Serangan paling dikenal adalah Man-in-the-Middle (MITM), yaitu ketika penyerang menyamar sebagai kedua belah pihak. Ketika pihak pertama mengirim kunci publiknya, penyerang mencegat dan menggantinya dengan kunci publik palsu, lalu melakukan hal yang sama kepada pihak kedua. Akibatnya, penyerang memiliki dua kunci rahasia terpisah dan dapat membaca, mengubah, atau memanipulasi pesan tanpa diketahui. Selain MITM, kelemahan lain adalah penggunaan bilangan prima kecil atau parameter yang tidak aman yang membuat logaritma diskrit lebih mudah dipecahkan. Untuk mencegah serangan, protokol biasanya dipadukan dengan autentikasi, seperti tanda tangan digital atau sertifikat, agar pihak yang bertukar kunci dapat memastikan identitas satu sama lain.

## 3. Alat dan Bahan
- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  

## 4. Langkah Percobaan
1. Membuat file diffie_hellman.py di folder praktikum/week7-diffie_hellman/src/.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah python diffie_hellman.py.

## 5. Source Code
<img width="1478" height="933" alt="image" src="https://github.com/user-attachments/assets/b88ec82f-1ef0-4ffe-9737-5d67dacf3460" />


## 6. Hasil dan Pembahasan
<img width="737" height="679" alt="image" src="https://github.com/user-attachments/assets/cddc2b2b-0006-4790-bcf4-93fc4941a526" />


## 7. Jawaban Pertanyaan
SOAL!! 
1. Mengapa Diffie-Hellman memungkinkan pertukaran kunci di saluran publik?
2. Apa kelemahan utama protokol Diffie-Hellman murni?
3. Bagaimana cara mencegah serangan MITM pada protokol ini?

JAWABAN!!
1. Karena protokol Diffie-Hellman memanfaatkan fungsi satu arah berbasis logaritma diskrit, yaitu operasi  yang mudah dihitung, tetapi sangat sulit dibalik untuk mencari nilai . Dengan sifat ini, dua pihak bisa bertukar nilai publik (yang aman diketahui siapa pun) namun tetap dapat menghasilkan kunci rahasia yang sama tanpa pernah mengirimkan kunci rahasianya secara langsung.
2. Kelemahan utamanya adalah tidak ada autentikasi, sehingga protokol ini tidak dapat memastikan bahwa pihak yang diajak bertukar kunci benar-benar pihak yang dimaksud. Tanpa autentikasi, protokol rentan terhadap serangan Man-in-the-Middle (MITM), di mana penyerang dapat menyusup dan membuat dua kunci terpisah dengan masing-masing pihak.
3.Untuk mencegah MITM, Diffie-Hellman harus dipadukan dengan mekanisme autentikasi. Metode umum meliputi:
Tanda tangan digital (misalnya menggunakan RSA, ECDSA) untuk menandatangani nilai publik DH.
Sertifikat digital dan PKI (HTTPS/SSL) untuk memverifikasi identitas server/pengirim.
Authenticated Diffie-Hellman seperti Station-to-Station (STS) atau Elliptic Curve Diffie-Hellman Ephemeral (ECDHE) yang menambahkan autentikasi.
Dengan autentikasi, penyerang tidak bisa lagi menyamar sebagai salah satu pihak dalam komunikasi.

## 8. Kesimpulan


## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
commit abc12345
Author: Safira Dewi Rahmatika safiraa1026@gmail.com
Date:   2025-12-02

    
