# Laporan Praktikum Kriptografi
Minggu ke-: 7
Topik: Diffie-hellman
Nama: Dhea Silvia 
NIM: 230202742 
Kelas: 5Ikrb

---

## 1. Tujuan
1. Melakukan simulasi protokol Diffie-Hellman untuk pertukaran kunci publik.
2. Menjelaskan mekanisme pertukaran kunci rahasia menggunakan bilangan prima dan logaritma diskrit.
3. Menganalisis potensi serangan pada protokol Diffie-Hellman (termasuk serangan Man-in-the-Middle / MITM).


## 2. Dasar Teori
Diffie–Hellman merupakan protokol pertukaran kunci yang memungkinkan dua pihak membentuk kunci rahasia bersama melalui jaringan yang tidak aman tanpa perlu membagikan kunci sebelumnya. Mekanisme ini bergantung pada aritmetika modular dan tingkat kesulitan Discrete Logarithm Problem (DLP), sehingga meskipun nilai publik dapat diketahui semua orang, kunci rahasianya tetap sulit untuk ditebak.

Prosesnya dimulai dengan kedua pihak menyepakati sebuah bilangan prima besar dan generator sebagai parameter publik. Masing-masing kemudian memilih kunci privat secara acak dan menghasilkan kunci publik. Setelah bertukar kunci publik, kedua pihak dapat menghitung kunci bersama yang identik melalui operasi perpangkatan modular. Pihak ketiga yang hanya melihat nilai publik tidak dapat menentukan kunci tersebut tanpa memecahkan DLP.

Namun, Diffie–Hellman tidak mencakup autentikasi, sehingga rentan terhadap serangan Man-in-the-Middle jika tidak dilengkapi mekanisme tambahan. Dalam penggunaan modern, protokol ini biasanya dipadukan dengan tanda tangan digital atau diimplementasikan dalam bentuk yang lebih efisien seperti Elliptic Curve Diffie–Hellman (ECDH) yang menyediakan tingkat keamanan tinggi dengan ukuran kunci yang lebih kecil.

## 3. Alat dan Bahan
- Python  
- Visual Studio Code  
- Git dan akun GitHub  


---

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `diffie- hellman.py` di folder `praktikum/week7-diffie-hellman/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python diffie-hellman.py`.)

---

## 5. Source Code
import random

# parameter umum (disepakati publik)
p = 23  # bilangan prima
g = 5   # generator

# private key masing-masing pihak
a = random.randint(1, p-1)  # secret Alice
b = random.randint(1, p-1)  # secret Bob

# public key
A = pow(g, a, p)
B = pow(g, b, p)

# exchange public key
shared_secret_A = pow(B, a, p)
shared_secret_B = pow(A, b, p)

print("Kunci bersama Alice :", shared_secret_A)
print("Kunci bersama Bob   :", shared_secret_B)  


## 6. Hasil dan Pembahasan


---<img width="1366" height="768" alt="diffiehellman" src="https://github.com/user-attachments/assets/d691e020-911f-49b8-8aea-894cc72a8def" />


## 7. Jawaban Pertanyaan
1. Mengapa Diffie-Hellman memungkinkan pertukaran kunci di saluran publik?
= Diffie-Hellman (DH) memungkinkan pertukaran kunci rahasia melalui saluran komunikasi yang tidak aman (publik) karena memanfaatkan kesulitan komputasi dari Masalah Logaritma Diskrit (Discrete Logarithm Problem - DLP).Protokol ini bekerja dengan cara di mana pihak-pihak yang berkomunikasi (misalnya, Alice dan Bob) menyepakati beberapa nilai publik terlebih dahulu, lalu masing-masing menghasilkan nilai rahasia mereka sendiri, dan akhirnya menggabungkan nilai-nilai ini untuk mendapatkan kunci rahasia bersama.Berikut adalah langkah kuncinya:Nilai Publik Bersama: Alice dan Bob menyepakati bilangan prima besar $p$ dan generator $g$ (keduanya diketahui publik).Kunci Rahasia Pribadi:Alice memilih bilangan rahasia $a$ (hanya Alice yang tahu).Bob memilih bilangan rahasia $b$ (hanya Bob yang tahu).Pertukaran Kunci Publik Parsial:Alice menghitung $A = g^a \pmod{p}$ dan mengirimkan $A$ ke Bob.Bob menghitung $B = g^b \pmod{p}$ dan mengirimkan $B$ ke Alice.Penting: Meskipun $A$ dan $B$ dipertukarkan secara publik, sangat sulit bagi penyadap (Eve) untuk mencari tahu $a$ atau $b$ dari $A$, $B$, $g$, dan $p$ karena DLP.Menghitung Kunci Rahasia Bersama:Alice menghitung $K = B^a \pmod{p} = (g^b)^a \pmod{p} = g^{ab} \pmod{p}$.Bob menghitung $K = A^b \pmod{p} = (g^a)^b \pmod{p} = g^{ab} \pmod{p}$.Kedua belah pihak mencapai kunci rahasia bersama yang sama, $K$, yang tidak pernah dikirimkan secara langsung melalui saluran publik, menjadikannya aman.

2.Apa kelemahan utama protokol Diffie-Hellman murni?
=Kelemahan utama dari protokol Diffie-Hellman murni (anonim) adalah kerentanannya terhadap serangan Man-in-the-Middle (MITM).Dalam protokol DH murni, tidak ada otentikasi yang dilakukan. Artinya, Alice tidak tahu apakah dia benar-benar berkomunikasi dengan Bob, dan sebaliknya

3. Bagaimana Cara Mencegah Serangan MITM pada Protokol Ini?
   =Cara paling umum dan efektif untuk mencegah serangan MITM pada protokol Diffie-Hellman adalah dengan menggabungkan otentikasi ke dalam pertukaran kunci.Metode utamanya meliputi:Penggunaan Tanda Tangan Digital (Digital Signatures):Ini adalah metode yang paling umum, digunakan dalam protokol seperti TLS/SSL.Alice dan Bob menggunakan pasangan kunci publik/privat (asimetris) yang sudah ada sebelumnya (misalnya, berdasarkan RSA atau DSA).Daripada hanya mengirim nilai publik $A$ dan $B$ secara langsung, mereka menandatangani nilai-nilai tersebut dengan kunci privat mereka sebelum mengirimkannya.Penerima (misalnya Bob) dapat menggunakan kunci publik Alice yang sah (yang didapatkan melalui Sertifikat Digital yang dipercaya) untuk memverifikasi bahwa kunci publik DH ($A$) benar-benar berasal dari Alice dan tidak diubah oleh pihak ketiga.Diffie-Hellman Otentik (Authenticated Diffie-Hellman):Menggunakan informasi otentikasi yang sudah ada sebelumnya, seperti kata sandi atau kunci simetris yang dibagikan sebelumnya, untuk memverifikasi identitas pihak lain. Contoh protokol ini adalah SRP (Secure Remote Password), yang menggabungkan DH dengan verifikasi kata sandi.Sertifikat Digital (Public Key Infrastructure - PKI):Sertifikat digital berfungsi sebagai identitas tepercaya yang mengikat kunci publik seseorang (misalnya, kunci publik untuk verentifikasi tanda tangan) ke identitas aslinya. Dengan memverifikasi sertifikat yang dikeluarkan oleh Otoritas Sertifikat (CA) yang tepercaya, Alice dan Bob dapat yakin akan identitas pihak lain sebelum melanjutkan pertukaran kunci DH.

## 8. Kesimpulan
Diffie-Hellman adalah protokol kriptografi yang memungkinkan dua pihak untuk menentukan kunci rahasia bersama melalui saluran komunikasi yang tidak aman (publik).Inti Kekuatan: Keamanannya didasarkan pada kesulitan komputasi dari Masalah Logaritma Diskrit (DLP), yang membuat pihak ketiga tidak mungkin menghitung kunci rahasia hanya dari nilai-nilai yang dipertukarkan secara publik.Kelemahan Utama: Protokol Diffie-Hellman murni tidak memiliki otentikasi, sehingga sangat rentan terhadap serangan Man-in-the-Middle (MITM).Pencegahan MITM: Untuk digunakan secara aman, DH harus selalu digabungkan dengan otentikasi, paling umum melalui Tanda Tangan Digital dan Sertifikat Digital (seperti yang dilakukan dalam TLS/SSL).
Berdasarkan hasil eksekusi program diffie hellman yang telah saya lakukan menunjukan keberhasilan yang dapat dilihat hasilnya pada screenshoot.

---

## 9. Daftar Pustaka
- Menezes, A. J., Van Oorschot, P. C., & Vanstone, S. A. (1996). Handbook of applied cryptography. CRC Press.
- Stallings, W. (Biasanya edisi terbaru). Cryptography and network security: Principles and practice. Pearson.
---

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Dhea Silvia <dheasilvia51@gmail.com>
Date:   2025-11-17

    week7-diffie-hellman: implementasi diffie-hellman dan laporan )
```
