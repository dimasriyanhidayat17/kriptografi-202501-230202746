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
SOAL!! 
1. 

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
commit abc12345
Author: Safira Dewi Rahmatika safiraa1026@gmail.com
Date:   2025-12-02

    
