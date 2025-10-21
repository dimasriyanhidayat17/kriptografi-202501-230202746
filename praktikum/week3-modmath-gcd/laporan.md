# Laporan Praktikum Kriptografi
Minggu ke-: 3
Topik: Modular Math (Aritmetika Modular, GCD, Bilangan Prima, Logaritma Diskrit)
Nama: Safira Dewi Rahmatika 
NIM: 230202784 
Kelas : 5IKRB 

## 1. Tujuan
1. Menyelesaikan operasi aritmetika modular.
2. Menentukan bilangan prima dan menghitung GCD (Greatest Common Divisor).
3. Menerapkan logaritma diskrit sederhana dalam simulasi kriptografi.

## 2. Dasar Teori
Aritmetika Modular merupakan cabang matematika yang mempelajari operasi hitung dengan menggunakan sistem modulo, yaitu sistem bilangan yang mengandalkan sisa hasil bagi. Konsep ini sering dianalogikan dengan “matematika jam”, di mana setelah mencapai batas tertentu, angka akan kembali ke awal. Aritmetika modular melibatkan operasi penjumlahan, pengurangan, perkalian, hingga perpangkatan dengan hasil yang disesuaikan berdasarkan modulus tertentu. Tujuan utama mempelajari aritmetika modular adalah untuk menyelesaikan operasi matematika dalam ruang terbatas, yang sangat berguna dalam bidang ilmu komputer dan kriptografi modern, seperti dalam algoritma RSA dan Diffie-Hellman.

Bilangan prima adalah bilangan bulat lebih besar dari satu yang hanya memiliki dua faktor pembagi, yaitu 1 dan dirinya sendiri. Bilangan ini memiliki peran penting dalam dunia kriptografi karena keunikannya dalam faktorisasi. Dalam pembelajaran matematika, menentukan apakah suatu bilangan merupakan bilangan prima sangat penting karena bilangan ini sering digunakan dalam pembuatan kunci rahasia. Tujuan dari mempelajari bilangan prima adalah untuk memahami sifat dasar dari bilangan tersebut dan bagaimana bilangan prima digunakan sebagai fondasi dalam algoritma keamanan komputer.

GCD (Greatest Common Divisor) atau Faktor Persekutuan Terbesar adalah bilangan bulat positif terbesar yang dapat membagi dua bilangan tanpa menyisakan sisa. GCD dapat dihitung dengan menggunakan algoritma Euclidean, yang merupakan metode efisien dan cepat. Dalam konteks kriptografi, GCD berguna untuk menentukan apakah dua bilangan saling relatif prima, yang merupakan syarat penting dalam pembuatan kunci enkripsi. Tujuan mempelajari GCD adalah untuk dapat menyelesaikan permasalahan matematika yang melibatkan pembagian serta memahami struktur dasar dari bilangan bulat.

Logaritma Diskrit adalah kebalikan dari perpangkatan dalam sistem modular, yaitu mencari eksponen x pada persamaan g^x ≡ y (mod p). Berbeda dengan logaritma biasa, logaritma diskrit sangat sulit dihitung, terutama ketika bilangan yang digunakan sangat besar. Kesulitan inilah yang menjadi dasar dari keamanan beberapa algoritma kriptografi, seperti Diffie-Hellman dan ElGamal. Tujuan dari mempelajari logaritma diskrit adalah untuk memahami bagaimana konsep ini digunakan dalam proses pertukaran kunci rahasia dan enkripsi data, serta menyadari pentingnya masalah matematika yang sulit diselesaikan sebagai dasar keamanan informasi.

## 3. Alat dan Bahan
- Visual Studio Code  
- Git dan akun GitHub  

## 4. Langkah Percobaan


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
