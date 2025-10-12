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
(Jawab pertanyaan diskusi yang diberikan pada modul.  
- Pertanyaan 1: …  
- Pertanyaan 2: …  
)
---

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
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
