# Laporan Praktikum Kriptografi
Minggu ke-: 5 
Topik: cipher klasik  
Nama: Safira Dewi Rahmatika 
NIM: 230202784
Kelas: 5IKRB

## 1. Tujuan
1. Menerapkan algoritma Caesar Cipher untuk enkripsi dan dekripsi teks.
2. Menerapkan algoritma Vigenère Cipher dengan variasi kunci.
3. Mengimplementasikan algoritma transposisi sederhana.
5. Menjelaskan kelemahan algoritma kriptografi klasik.

## 2. Dasar Teori
Caesar Cipher adalah algoritma substitusi sederhana yang menggeser huruf alfabet sebanyak kunci tertentu, dengan enkripsi menggunakan rumus (P + K) mod 26 dan dekripsi (C - K) mod 26, mudah diimplementasikan tetapi rentan brute force dan analisis frekuensi. Vigenère Cipher meningkatkan kompleksitas dengan shift variabel berdasarkan kata kunci yang diulang, menggunakan rumus serupa per huruf, namun tetap rentan terhadap teknik Kasiski untuk menentukan panjang kunci dan analisis frekuensi pada posisi shift. Kedua cipher ini cocok untuk pendidikan tetapi tidak aman untuk penggunaan modern karena ruang kunci terbatas.

Transposisi sederhana, seperti columnar transposition, mengatur ulang urutan huruf dalam grid berdasarkan urutan kolom tanpa mengubah huruf itu sendiri, dengan enkripsi melibatkan pengisian baris dan pembacaan kolom, serta dekripsi sebaliknya. Implementasinya melibatkan perhitungan grid dan panjang kolom untuk menangani teks tidak merata, lebih tahan analisis frekuensi daripada substitusi tetapi rentan brute force jika kunci dapat ditebak.

Secara umum, algoritma kriptografi klasik seperti Caesar, Vigenère, dan transposisi memiliki kelemahan utama berupa kerentanan terhadap analisis frekuensi, brute force, dan serangan komputasional karena tidak memiliki keamanan matematis yang kuat, sehingga mudah dipecahkan dengan alat modern dan telah digantikan oleh cipher seperti AES atau RSA untuk aplikasi keamanan yang se

## 3. Alat dan Bahan
- Python 3.x  
- Visual Studio Code 
- Git dan akun GitHub  

## 4. Langkah Percobaan
1. Membuat file `cipher_klasik.py` di folder `praktikum/week5-cipher_klasik/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)

## 5. Source Code


## 6. Hasil dan Pembahasan

## 7. Jawaban Pertanyaan
Soal 
1. Apa kelemahan utama algoritma Caesar Cipher dan Vigenère Cipher?
2. Mengapa cipher klasik mudah diserang dengan analisis frekuensi?
3. Bandingkan kelebihan dan kelemahan cipher substitusi vs transposisi.

Jawaban
1. Kelemahan Utama Caesar Cipher dan Vigenère Cipher
Caesar Cipher sangat lemah karena hanya bergantung pada pergeseran alfabet sederhana, sehingga mudah dipecahkan dengan brute force (hanya 25 kemungkinan kunci) dan analisis frekuensi, di mana pola huruf seperti 'e' yang sering muncul tetap terlihat. Vigenère Cipher lebih kuat dengan shift variabel berdasarkan kata kunci, tetapi rentan terhadap teknik Kasiski untuk menentukan panjang kunci dan analisis frekuensi pada setiap posisi shift, terutama jika kunci pendek atau dapat ditebak.
2. Mengapa Cipher Klasik Mudah Diserang dengan Analisis Frekuensi
Cipher klasik seperti substitusi monoalfabetik mudah diserang analisis frekuensi karena mereka mempertahankan distribusi frekuensi huruf dari bahasa asli, seperti 'e' yang muncul sekitar 12-13% dalam bahasa Inggris, sehingga pemecah kode dapat menghitung frekuensi dalam ciphertext dan membandingkannya untuk menebak substitusi huruf tanpa kunci, teknik yang dikembangkan sejak abad ke-9 dan efektif karena bahasa manusia memiliki pola statistik konsisten.
3. Perbandingan Kelebihan dan Kelemahan Cipher Substitusi vs Transposisi
Cipher substitusi, yang mengganti huruf dengan huruf lain, mudah diimplementasikan secara manual dan mempertahankan struktur serta panjang teks, tetapi sangat rentan terhadap analisis frekuensi karena frekuensi huruf tidak berubah. Sebaliknya, cipher transposisi, yang mengatur ulang urutan huruf tanpa mengubahnya, lebih tahan analisis frekuensi karena hanya mengubah posisi, namun lebih kompleks untuk diimplementasikan dan rentan terhadap brute force atau analisis pola jika kunci dapat ditebak.

## 8. Kesimpulan

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
commit abc12345
Author: safira dewi rahmatika safiraa1026@gmail.com
Date:   2025-11-07

    week5- implementasi Caesar Cipher Klasik dan laporan
