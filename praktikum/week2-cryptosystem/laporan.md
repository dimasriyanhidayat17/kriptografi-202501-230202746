# Laporan Praktikum Kriptografi
Minggu ke-: 2  
Topik: Komponen, Enkripsi & Dekripsi, Simetris & Asimetris  
Nama: Dimas Riyan Hidayat  
NIM: 230202746  
Kelas: 5IKRB 

## 1. Tujuan
1. Menganalisis struktur dasar sistem kriptografi, termasuk peran esensial dari Plaintext, Ciphertext, Kunci, dan Algoritma.
2. Mendemonstrasikan alur kerja (workflow) lengkap untuk mengubah data menjadi bentuk terenkripsi dan memulihkannya kembali.
3. Membandingkan dan membedakan dua kategori utama kriptosistem (Simetris vs. Asimetris) berdasarkan mekanisme penggunaan kuncinya.

## 2. Dasar Teori
Kriptografi adalah metode untuk mengamankan pesan menggunakan sandi. Inti dari setiap sistem sandi (kriptosistem) adalah mengubah pesan biasa (Plaintext) menjadi pesan acak yang tidak dapat dibaca (Ciphertext) melalui proses Enkripsi. Proses ini dikontrol oleh Algoritma (aturan matematis, misalnya AES atau Caesar Cipher) dan Kunci (kode rahasia). Agar penerima dapat membaca pesan, proses Dekripsi membalikkan operasi tersebut, menggunakan Algoritma dan Kunci yang benar untuk mengembalikan Ciphertext menjadi Plaintext.

Kriptosistem terbagi dua: Simetris dan Asimetris. Kriptografi Simetris menggunakan satu Kunci yang Sama untuk enkripsi dan dekripsi; keuntungannya adalah kecepatan, tetapi kuncinya harus dibagikan secara rahasia. Sebaliknya, Kriptografi Asimetris menggunakan pasangan kunci: Kunci Publik untuk enkripsi dan Kunci Privat untuk dekripsi. Sistem asimetris lebih lambat tetapi unggul dalam pertukaran kunci yang aman dan digunakan untuk sistem seperti RSA. Algoritma yang mendasari sandi-sandi ini, terutama yang klasik, sering kali memanfaatkan Aritmetika Modular untuk memetakan dan menggeser huruf atau angka secara berulang.

## 3. Alat dan Bahan
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Draw Io 

## 4. Langkah Percobaan
1. Membuat file `caesar_cipher.py` di folder `praktikum/week2-cryptosystem/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)
4. membuat diagram menggunakan draw io
5. menjawab quiz
6. merangkum materi

## 5. Source Code

<img width="1920" height="1080" alt="Screenshot 2025-10-20 210552" src="https://github.com/user-attachments/assets/a29b77b7-b3dc-46c6-b2e8-579c4b9497dc" />


## 6. Hasil dan Pembahasan
<img width="1043" height="368" alt="Screenshot 2025-10-20 010115" src="https://github.com/user-attachments/assets/1dcdd42d-2cad-4a8d-aacd-fecbd7e5ee34" />
<img width="1053" height="366" alt="Screenshot 2025-10-20 010445" src="https://github.com/user-attachments/assets/46724fd3-d3f9-4a3a-bc8c-07fdcccc9d00" />
<img width="581" height="303" alt="enkripsi drawio" src="https://github.com/user-attachments/assets/afd932b8-5a0f-49db-8570-e1e21c377713" />


## 7. Jawaban Pertanyaan
jawaban quiz :
1. Komponen Utama Kriptosistem
Sebuah kriptosistem didefinisikan oleh enam komponen inti yang bekerja sama untuk menjamin kerahasiaan data. Komponen-komponen ini meliputi Plaintext, yaitu pesan yang belum disandikan; Ciphertext, yaitu pesan yang telah diacak dan tidak dapat dibaca; Algoritma, yaitu serangkaian aturan matematis formal yang menentukan proses enkripsi dan dekripsi; dan Kunci, yaitu nilai rahasia yang mengontrol operasi Algoritma. Kedua proses krusial yang menghubungkan komponen-komponen ini adalah Enkripsi (mengubah Plaintext menjadi Ciphertext) dan Dekripsi (memulihkan Ciphertext menjadi Plaintext).

2. Kelebihan dan Kelemahan Sistem Simetris dibandingkan Asimetris
Kriptosistem terbagi menjadi dua kelas utama yang memiliki kelebihan dan kelemahan kontras. Sistem Simetris memiliki keunggulan signifikan dalam kecepatan dan efisiensi pemrosesan data, menjadikannya pilihan ideal untuk enkripsi data dalam volume besar karena ia hanya menggunakan satu kunci rahasia. Sebaliknya, Sistem Asimetris jauh lebih lambat karena membutuhkan daya komputasi yang lebih besar; namun, keunggulan utamanya terletak pada kemampuannya memecahkan masalah distribusi kunci dengan menggunakan pasangan kunci Publik dan Privat, dan juga secara inheren mendukung Tanda Tangan Digital.

3. Mengapa Distribusi Kunci Menjadi Masalah Utama dalam Kriptografi Simetris
Distribusi kunci merupakan masalah utama dalam kriptografi simetris karena seluruh keamanan sistem bergantung pada kerahasiaan satu kunci bersama yang digunakan oleh kedua belah pihak. Kunci ini harus dikirimkan dari pengirim ke penerima melalui saluran yang sudah dijamin keamanannya sebelum komunikasi terenkripsi dapat dimulai. Jika kunci dicegat oleh pihak ketiga selama proses distribusi, seluruh komunikasi yang dienkripsi menggunakan kunci tersebut akan terkompromi. Selain itu, masalah ini menjadi tidak praktis dan sulit dikelola (non-scalable) ketika jumlah pengguna dalam jaringan meningkat, karena setiap pasangan pengguna memerlukan kunci rahasia unik tersendiri.

## 8. Kesimpulan
Berdasarkan percobaan dan analisis yang dilakukan, dapat disimpulkan bahwa kriptosistem berfungsi melalui dua proses berlawanan, yaitu Enkripsi dan Dekripsi, yang keduanya bergantung pada kombinasi spesifik Algoritma dan Kunci untuk mengubah Plaintext menjadi Ciphertext dan sebaliknya. Perbandingan antara sistem simetris yang cepat namun bermasalah dalam distribusi kunci, dengan sistem asimetris yang lambat namun aman dalam pertukaran kunci, menegaskan bahwa pemilihan kriptosistem harus disesuaikan dengan kebutuhan kecepatan dan mekanisme pertukaran kunci yang diinginkan.

## 9. Daftar Pustaka


## 10. Commit Log
commit cryptosystem
Author: Dimas Riyan Hidayat <dimasriyanhidayat01@gmail.com>
Date:   2025-10-12
    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
