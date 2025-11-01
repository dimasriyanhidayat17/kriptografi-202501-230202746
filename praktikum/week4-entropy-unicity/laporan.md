# Laporan Praktikum Kriptografi
Minggu ke-: 4
Topik: entropy unicity
Nama: Safira Dewi Rahmatika 
NIM: 230202784
Kelas: 5IKRB 
## 1. Tujuan
1. Menyelesaikan perhitungan sederhana terkait entropi kunci.
2. Menggunakan teorema Euler pada contoh perhitungan modular & invers.
3. Menghitung unicity distance untuk ciphertext tertentu.
4. Menganalisis kekuatan kunci berdasarkan entropi dan unicity distance.
5. Mengevaluasi potensi serangan brute force pada kriptosistem sederhana.

## 2. Dasar Teori
Entropi kunci adalah ukuran tingkat ketidakpastian atau keacakan dari sebuah kunci dalam sistem kriptografi. Semakin tinggi nilai entropi, semakin sulit kunci tersebut ditebak atau diretas, karena kemungkinan kombinasi yang bisa digunakan semakin banyak. Entropi juga bisa diartikan sebagai seberapa kuat dan acak sebuah kunci yang digunakan dalam proses enkripsi.

Teorema Euler digunakan dalam kriptografi untuk membantu melakukan perhitungan pada operasi matematika berbasis modulus, seperti mencari nilai invers atau hasil pangkat dalam sistem bilangan modular. Teorema ini menjadi dasar penting bagi algoritma kriptografi modern seperti RSA, karena menjelaskan hubungan antara bilangan yang saling relatif prima dengan modulus tertentu.

Unicity distance atau jarak unisitas menunjukkan seberapa panjang sebuah ciphertext diperlukan agar hanya ada satu kunci yang mungkin digunakan untuk menghasilkan pesan asli yang bermakna. Konsep ini membantu menentukan kekuatan sebuah sistem kriptografi. Semakin besar nilai unicity distance, semakin sulit ciphertext dipecahkan. Analisis terhadap entropi kunci dan unicity distance juga berguna untuk menilai kemungkinan serangan brute force, yaitu upaya mencoba semua kunci secara acak hingga menemukan yang benar.

## 3. Alat dan Bahan
- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  

## 4. Langkah Percobaan
1. Merangkum materi terkait entropy unicity.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program.
4. Menjawab pertanyaan atau quiz 

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
Author: Safira Dewi Rahmatika <email> safiraa1026@gmail.com
week3-entropy-unicity: entropy & uniciy distance 
