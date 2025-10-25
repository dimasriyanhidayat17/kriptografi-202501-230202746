# Laporan Praktikum Kriptografi
Minggu ke-: 3  
Topik: [judul praktikum]  
Nama: Dimas Riyan Hidayat  
NIM: 230202746 
Kelas: 5IKRB  

---

## 1. Tujuan
1. Menyelesaikan operasi aritmetika modular.
2. Menentukan bilangan prima dan menghitung GCD (Greatest Common Divisor).
3. Menerapkan logaritma diskrit sederhana dalam simulasi kriptografi.


## 2. Dasar Teori
1. Aritmatika
   Aritmetika modular merupakan cabang dari matematika yang mempelajari operasi bilangan dengan sistem sisa bagi. Dalam sistem ini, dua bilangan dikatakan kongruen jika memiliki sisa yang sama ketika dibagi oleh suatu bilangan tertentu yang disebut modulus. Konsep ini banyak digunakan dalam kriptografi, sistem komputer, dan teori bilangan karena memungkinkan operasi aritmetika dilakukan secara efisien dan terbatas dalam ruang tertentu.
2. GCD
   Greatest Common Divisor (GCD) atau pembagi bersama terbesar adalah bilangan bulat positif terbesar yang dapat membagi dua bilangan tanpa meninggalkan sisa. Konsep GCD penting dalam menyederhanakan pecahan, menentukan koprimalitas dua bilangan, dan menjadi dasar dalam algoritma kriptografi seperti RSA. Proses pencarian GCD umumnya dilakukan menggunakan algoritma Euclidean yang efisien dan sederhana.
3. Bilangan Prima
   Bilangan prima adalah bilangan yang lebih besar dari satu dan hanya memiliki dua faktor, yaitu satu dan dirinya sendiri. Bilangan prima menjadi dasar penting dalam teori bilangan karena setiap bilangan bulat positif dapat diuraikan menjadi hasil kali bilangan-bilangan prima secara unik. Dalam kriptografi modern, bilangan prima digunakan untuk membangun sistem keamanan yang sulit dipecahkan, seperti dalam algoritma RSA yang memanfaatkan kesulitan faktorisasi bilangan besar.

## 3. Alat dan Bahan
- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub 


## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `caesar_cipher.py` di folder `praktikum/week2-cryptosystem/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)

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
