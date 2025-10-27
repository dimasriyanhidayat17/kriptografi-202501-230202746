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
1. Membuat file modular math.py di folder praktikum/week 3-modmath/src/modularmath.py
2. Menyalin kode program dari panduan praktikum
3. Menjalankan program dengan perintah python modular math.py
4. Screenshoot hasil program dan ditaruh didalam folder praktikum/week3-modmath-gcd/screenshoot/hasil.png

## 5. Source Code
<img width="868" height="980" alt="Screenshot 2025-10-27 150056" src="https://github.com/user-attachments/assets/80d472d5-11a6-4a51-b6e9-e049d300d3c7" />

## 6. Hasil dan Pembahasan
<img width="332" height="442" alt="Screenshot 2025-10-27 150149" src="https://github.com/user-attachments/assets/60a01b6b-96be-4c11-87e1-19de758e4579" />

## 7. Jawaban Pertanyaan
Soall
1. Apa peran aritmetika modular dalam kriptografi modern?
2. Mengapa invers modular penting dalam algoritma kunci publik (misalnya RSA)?
3. Apa tantangan utama dalam menyelesaikan logaritma diskrit untuk modulus besar?
   
Jawaban
1. Peran aritmetika modular dalam kriptografi modern
Aritmetika modular berperan penting dalam kriptografi modern karena menjadi dasar dari berbagai algoritma kunci publik seperti RSA, Diffie–Hellman, dan Elliptic Curve Cryptography (ECC). Dengan menggunakan operasi matematika yang dilakukan dalam sistem modulo, hasil perhitungan selalu berada dalam batas tertentu meskipun melibatkan bilangan yang sangat besar. Hal ini membuat proses enkripsi dan dekripsi dapat dilakukan dengan efisien serta menjaga keamanan data, karena operasi kebalikannya (misalnya mencari akar atau logaritma modular) sangat sulit diselesaikan tanpa kunci yang benar.

2. Mengapa invers modular penting dalam algoritma kunci publik (misalnya RSA)
Invers modular sangat penting dalam algoritma RSA karena digunakan untuk membalikkan proses enkripsi menjadi dekripsi. Dalam RSA, kunci publik terdiri dari pasangan , sedangkan kunci privat adalah . Nilai  diperoleh sebagai invers modular dari  terhadap , sehingga memenuhi persamaan . Hubungan ini memastikan bahwa hanya pemilik kunci privat yang dapat mengembalikan pesan terenkripsi ke bentuk aslinya. Tanpa invers modular, proses dekripsi tidak dapat dilakukan dengan benar, dan sistem RSA tidak akan berfungsi sebagaimana mestinya.

3. Tantangan utama dalam menyelesaikan logaritma diskrit untuk modulus besar
Tantangan utama dalam menyelesaikan logaritma diskrit untuk modulus besar terletak pada tingkat kesulitannya yang sangat tinggi secara komputasional. Masalah logaritma diskrit berarti mencari nilai  pada persamaan , dan hingga saat ini belum ada algoritma yang efisien untuk menyelesaikannya ketika modulus  berukuran besar. Waktu yang dibutuhkan meningkat secara eksponensial terhadap ukuran modulus, sehingga metode seperti Baby-step Giant-step, Pollard’s Rho, maupun Number Field Sieve menjadi tidak praktis. Kesulitan inilah yang menjadi dasar keamanan dari algoritma kriptografi seperti Diffie–Hellman dan ElGamal.

## 8. Kesimpulan
Aritmetika Modular merupakan cabang matematika yang mempelajari operasi hitung dengan menggunakan sistem modulo, yaitu sistem bilangan yang mengandalkan sisa hasil bagi. Konsep ini sering dianalogikan dengan “matematika jam”, di mana setelah mencapai batas tertentu, angka akan kembali ke awal. Aritmetika modular melibatkan operasi penjumlahan, pengurangan, perkalian, hingga perpangkatan dengan hasil yang disesuaikan berdasarkan modulus tertentu. Tujuan utama mempelajari aritmetika modular adalah untuk menyelesaikan operasi matematika dalam ruang terbatas, yang sangat berguna dalam bidang ilmu komputer dan kriptografi modern, seperti dalam algoritma RSA dan Diffie-Hellman.

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
commit
Author: Safira Dewi Rahmatika safiraa1026@gmail.com
Date:   2025-10-25

    week3-modular math : (Aritmetika Modular, GCD, Bilangan Prima, Logaritma Diskrit)
