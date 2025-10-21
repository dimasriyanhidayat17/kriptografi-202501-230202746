# Laporan Praktikum Kriptografi
Minggu ke-: 3
Topik: Modular Math  
Nama: Dhea Silvia  
NIM: 230202742 
Kelas: 5IKRB 

---

## 1. Tujuan
1. Menyelesaikan operasi aritmetika modular.
2. Menentukan bilangan prima dan menghitung GCD (Greatest Common Divisor).
3. Menerapkan logaritma diskrit sederhana dalam simulasi kriptografi.

---

## 2. Dasar Teori
hasil pembagian terhadap suatu bilangan tertentu yang disebut modulus. Dalam sistem ini, setiap hasil operasi seperti penjumlahan, pengurangan, perkalian, maupun perpangkatan akan dikembalikan menjadi sisa pembagian terhadap modulus tersebut, sehingga nilainya selalu berada di antara 0 hingga 𝑛−1. Konsep ini banyak diterapkan dalam bidang kriptografi, misalnya pada algoritma RSA dan Diffie–Hellman, karena sifat periodiknya mampu menjaga hasil perhitungan tetap berada dalam rentang tertentu.
GCD (Greatest Common Divisor) atau faktor persekutuan terbesar adalah bilangan bulat terbesar yang dapat membagi habis dua bilangan tanpa menyisakan sisa. Nilai GCD dapat dihitung menggunakan algoritma Euclidean dengan prinsip bahwa GCD(a, b) sama dengan GCD(b, a mod b). Konsep GCD penting dalam kriptografi, terutama untuk menentukan apakah dua bilangan relatif prima dan dalam proses pencarian invers modular.

---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  


---

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file modular_math.py di folder `praktikum/week3-modmath/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python modular_math.py`.)

---

## 5. Source Code
**1. langkah 1 - Aritmatika Modular**

   def mod_add(a, b, n): return (a + b) % n
   def mod_sub(a, b, n): return (a - b) % n
   def mod_mul(a, b, n): return (a * b) % n
   def mod_exp(base, exp, n): return pow(base, exp, n) # eksponensiasi modular
print("7 + 5 mod 12 =", mod_add(7, 5, 12)) print("7 * 5 mod 12 =", mod_mul(7, 5, 12)) print("7^128 mod 13 =", mod_exp(7, 128, 13))

**2. langkah 2 -GCD & Algoritma Euclidean**

   def gcd(a, b): while b != 0: a, b = b, a % b return a
print("gcd(54, 24) =", gcd(54, 24))

**3. langkah 3 - extend euclidean algorthm**

   def egcd(a, b):
    if a == 0:
        return b, 0, 1
    g, x1, y1 = egcd(b % a, a)
    return g, y1 - (b // a) * x1, x1

def modinv(a, n):
    g, x, _ = egcd(a, n)
    if g != 1:
        return None
    return x % n

print("Invers 3 mod 11 =", modinv(3, 11))  # hasil: 4

**4. langkah 4 - discrete log**

    def discrete_log(a, b, n):
    for x in range(n):
        if pow(a, x, n) == b:
            return x
    return None

print("3^x ≡ 4 (mod 7), x =", discrete_log(3, 4, 7))  # hasil: 4

**source code seluruhnya:**

def mod_add(a, b, n): return (a + b) % n
def mod_sub(a, b, n): return (a - b) % n
def mod_mul(a, b, n): return (a * b) % n
def mod_exp(base, exp, n): return pow(base, exp, n)  # eksponensiasi modular

print("7 + 5 mod 12 =", mod_add(7, 5, 12))
print("7 * 5 mod 12 =", mod_mul(7, 5, 12))
print("7^128 mod 13 =", mod_exp(7, 128, 13))
def gcd(a, b):
    while b != 0:
        a, b = b, a % b
    return a

print("gcd(54, 24) =", gcd(54, 24))
def egcd(a, b):
    if a == 0:
        return b, 0, 1
    g, x1, y1 = egcd(b % a, a)
    return g, y1 - (b // a) * x1, x1

def modinv(a, n):
    g, x, _ = egcd(a, n)
    if g != 1:
        return None
    return x % n

print("Invers 3 mod 11 =", modinv(3, 11))  # hasil: 4
def discrete_log(a, b, n):
    for x in range(n):
        if pow(a, x, n) == b:
            return x
    return None

print("3^x ≡ 4 (mod 7), x =", discrete_log(3, 4, 7))  # hasil: 4

    Hasil:
7 + 5 mod 12 = 0
7 * 5 mod 12 = 11
7^128 mod 13 = 3
gcd(54, 24) = 6
Invers 3 mod 11 = 4
3^x ≡ 4 (mod 7), x = 4
   
## 6. Hasil dan Pembahasan

Hasil eksekusi program modmath:

<img width="1366" height="728" alt="dhea silvia py - Visual Studio Code 21_10_2025 14_46_07" src="https://github.com/user-attachments/assets/31579686-f9a2-44b9-839f-dbf6b7eac009" />
penje;lasan : program berjalan sesuai instruksi tanpa adanya bug.

## 7. Jawaban Pertanyaan

**Pertanyaan 1** : Apa peran aritmetika modular dalam kriptografi modern

Aritmetika modular berperan sangat penting dalam kriptografi modern karena menjadi dasar dalam berbagai algoritma enkripsi dan dekripsi yang mengandalkan operasi matematika dengan modulus besar.    
    Dalam sistem kriptografi seperti RSA, Diffie–Hellman, dan Elliptic Curve Cryptography (ECC), aritmetika modular digunakan untuk:
1.Membatasi hasil perhitungan dalam rentang tertentu — operasi seperti perpangkatan atau perkalian besar akan dikembalikan ke sisa hasil pembagiannya terhadap modulus, sehingga menjaga data tetap dalam ukuran yang dapat dikelola.
2.Menjamin keamanan enkripsi — sifat sulitnya membalik operasi modular (misalnya mencari akar modulo atau invers modulo besar) membuat algoritma tersebut tahan terhadap serangan brute force.
3. Mendukung sifat periodik dan deterministik — setiap hasil selalu berulang dalam pola tertentu yang teratur, penting untuk memastikan konsistensi dalam proses enkripsi dan dekripsi.
4. Mendefinisikan kunci publik dan privat — misalnya dalam RSA, operasi perpangkatan modular digunakan untuk mengenkripsi dan mendekripsi pesan menggunakan pasangan kunci tersebut.
**Pertanyaan 2 :** Mengapa invers modular penting dalam algoritma kunci publik (misalnya RSA)?

Invers modular berperan sebagai komponen kunci privat yang memungkinkan proses dekripsi bekerja dengan benar dan aman dalam sistem kriptografi kunci publik seperti RSA. Tanpa invers modular, pesan yang terenkripsi tidak akan bisa dikembalikan ke bentuk semula.
**Pertanyaan 3 :** Apa tantangan utama dalam menyelesaikan logaritma diskrit untuk modulus besar?

Tantangan utama dalam menyelesaikan logaritma diskrit (discrete logarithm) untuk modulus besar terletak pada tingkat kesulitannya yang sangat tinggi secara komputasional artinya, tidak ada algoritma efisien yang dapat menghitungnya dengan cepat ketika bilangan yang digunakan sangat besar.


## 8. Kesimpulan

Berdasarkan hasil yang telah dilakukan , dapat disimpulkan bahwa aritmetika modular, algoritma Euclidean, invers modular, dan logaritma diskrit memiliki hubungan yang sangat erat serta menjadi fondasi utama dalam kriptografi modern.
Aritmetika modular berfungsi untuk memastikan hasil operasi matematika tetap berada dalam batas nilai tertentu, algoritma Euclidean digunakan untuk menentukan bilangan yang relatif prima, invers modular berperan penting dalam proses dekripsi pada sistem kunci publik, sedangkan logaritma diskrit menjadi sumber keamanan utama karena tingkat kesulitannya yang tinggi ketika modulus bernilai besar.
Secara keseluruhan, keempat konsep tersebut saling melengkapi dan menjadi komponen inti dalam membangun sistem keamanan data digital, seperti pada algoritma RSA dan Diffie–Hellman.

---

## 9. Daftar Pustaka
---

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit week3-modmath-gcd
Author: Dhea Silvia <dheasilvia51@gmail.com>
Date:   2025-10-21

    week3-modmath-gcd: implementasi modular math
```
