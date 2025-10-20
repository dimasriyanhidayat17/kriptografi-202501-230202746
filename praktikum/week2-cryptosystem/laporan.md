# Laporan Praktikum Kriptografi
Minggu ke-: 2  
Topik: Komponen, Enkripsi & Dekripsi, Simetris & Asimetris  
Nama: Dimas Riyan Hidayat  
NIM: 230202746  
Kelas: 5IKRB 

---

## 1. Tujuan
-Menganalisis struktur dasar sistem kriptografi, termasuk peran esensial dari Plaintext, Ciphertext, Kunci, dan Algoritma.
-Mendemonstrasikan alur kerja (workflow) lengkap untuk mengubah data menjadi bentuk terenkripsi dan memulihkannya kembali.
-Membandingkan dan membedakan dua kategori utama kriptosistem (Simetris vs. Asimetris) berdasarkan mekanisme penggunaan kuncinya.



## 2. Dasar Teori
Kriptografi adalah metode untuk mengamankan pesan menggunakan sandi. Inti dari setiap sistem sandi (kriptosistem) adalah mengubah pesan biasa (Plaintext) menjadi pesan acak yang tidak dapat dibaca (Ciphertext) melalui proses Enkripsi. Proses ini dikontrol oleh Algoritma (aturan matematis, misalnya AES atau Caesar Cipher) dan Kunci (kode rahasia). Agar penerima dapat membaca pesan, proses Dekripsi membalikkan operasi tersebut, menggunakan Algoritma dan Kunci yang benar untuk mengembalikan Ciphertext menjadi Plaintext.

Kriptosistem terbagi dua: Simetris dan Asimetris. Kriptografi Simetris menggunakan satu Kunci yang Sama untuk enkripsi dan dekripsi; keuntungannya adalah kecepatan, tetapi kuncinya harus dibagikan secara rahasia. Sebaliknya, Kriptografi Asimetris menggunakan pasangan kunci: Kunci Publik untuk enkripsi dan Kunci Privat untuk dekripsi. Sistem asimetris lebih lambat tetapi unggul dalam pertukaran kunci yang aman dan digunakan untuk sistem seperti RSA. Algoritma yang mendasari sandi-sandi ini, terutama yang klasik, sering kali memanfaatkan Aritmetika Modular untuk memetakan dan menggeser huruf atau angka secara berulang.

---

## 3. Alat dan Bahan
(- Python 3.12  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Draw Io )
- 

---

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `caesar_cipher.py` di folder `praktikum/week2-cryptosystem/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)
4. membuat diagram menggunakan draw io
5. 

---

## 5. Source Code
# file: praktikum/week2-cryptosystem/src/simple_crypto.py

def encrypt(plaintext, key):
    result = ""
    for char in plaintext:
        if char.isalpha():
            shift = 65 if char.isupper() else 97
            result += chr((ord(char) - shift + key) % 26 + shift)
        else:
            result += char
    return result

def decrypt(ciphertext, key):
    result = ""
    for char in ciphertext:
        if char.isalpha():
            shift = 65 if char.isupper() else 97
            result += chr((ord(char) - shift - key) % 26 + shift)
        else:
            result += char
    return result

if __name__ == "__main__":
    message = "230202749 Fajar Saputro"
    key = 5

    enc = encrypt(message, key)
    dec = decrypt(enc, key)

    print("Plaintext :", message)
    print("Ciphertext:", enc)
    print("Decrypted :", dec)

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
1. Komponen Utama Kriptosistem
Sebuah kriptosistem didefinisikan oleh enam komponen inti yang bekerja sama untuk menjamin kerahasiaan data. Komponen-komponen ini meliputi Plaintext, yaitu pesan yang belum disandikan; Ciphertext, yaitu pesan yang telah diacak dan tidak dapat dibaca; Algoritma, yaitu serangkaian aturan matematis formal yang menentukan proses enkripsi dan dekripsi; dan Kunci, yaitu nilai rahasia yang mengontrol operasi Algoritma. Kedua proses krusial yang menghubungkan komponen-komponen ini adalah Enkripsi (mengubah Plaintext menjadi Ciphertext) dan Dekripsi (memulihkan Ciphertext menjadi Plaintext).

2. Kelebihan dan Kelemahan Sistem Simetris dibandingkan Asimetris
Kriptosistem terbagi menjadi dua kelas utama yang memiliki kelebihan dan kelemahan kontras. Sistem Simetris memiliki keunggulan signifikan dalam kecepatan dan efisiensi pemrosesan data, menjadikannya pilihan ideal untuk enkripsi data dalam volume besar karena ia hanya menggunakan satu kunci rahasia. Sebaliknya, Sistem Asimetris jauh lebih lambat karena membutuhkan daya komputasi yang lebih besar; namun, keunggulan utamanya terletak pada kemampuannya memecahkan masalah distribusi kunci dengan menggunakan pasangan kunci Publik dan Privat, dan juga secara inheren mendukung Tanda Tangan Digital.

3. Mengapa Distribusi Kunci Menjadi Masalah Utama dalam Kriptografi Simetris
Distribusi kunci merupakan masalah utama dalam kriptografi simetris karena seluruh keamanan sistem bergantung pada kerahasiaan satu kunci bersama yang digunakan oleh kedua belah pihak. Kunci ini harus dikirimkan dari pengirim ke penerima melalui saluran yang sudah dijamin keamanannya sebelum komunikasi terenkripsi dapat dimulai. Jika kunci dicegat oleh pihak ketiga selama proses distribusi, seluruh komunikasi yang dienkripsi menggunakan kunci tersebut akan terkompromi. Selain itu, masalah ini menjadi tidak praktis dan sulit dikelola (non-scalable) ketika jumlah pengguna dalam jaringan meningkat, karena setiap pasangan pengguna memerlukan kunci rahasia unik tersendiri.

## 8. Kesimpulan
Berdasarkan percobaan dan analisis yang dilakukan, dapat disimpulkan bahwa kriptosistem berfungsi melalui dua proses berlawanan, yaitu Enkripsi dan Dekripsi, yang keduanya bergantung pada kombinasi spesifik Algoritma dan Kunci untuk mengubah Plaintext menjadi Ciphertext dan sebaliknya. Perbandingan antara sistem simetris yang cepat namun bermasalah dalam distribusi kunci, dengan sistem asimetris yang lambat namun aman dalam pertukaran kunci, menegaskan bahwa pemilihan kriptosistem harus disesuaikan dengan kebutuhan kecepatan dan mekanisme pertukaran kunci yang diinginkan.

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
commit cryptosystem
Author: Dimas Riyan Hidayat <dimasriyanhidayat01@gmail.com>
Date:   2025-10-12

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
