# Laporan Praktikum Kriptografi
Minggu ke-: V  
Topik: Chiper Klasik  
Nama: Dimas Riyan Hidayat  
NIM: 230202746 
Kelas: 5IKRB 

---

## 1. Tujuan
1. Menerapkan algoritma Caesar Cipher untuk enkripsi dan dekripsi teks.
2. Menerapkan algoritma Vigenère Cipher dengan variasi kunci.
3. Mengimplementasikan algoritma transposisi sederhana.
4. Menjelaskan kelemahan algoritma kriptografi klasik.

---

## 2. Dasar Teori
Kriptografi klasik terdiri dari berbagai teknik penyandian yang pada dasarnya berfokus pada transformasi huruf dalam plaintext agar tidak dapat dibaca oleh pihak yang tidak berwenang. Salah satu teknik paling awal adalah Caesar Cipher, yaitu metode substitusi monoalfabetik yang menggantikan setiap huruf dengan huruf lain yang digeser sejumlah tetap dalam alfabet. Sifat pergeseran yang konstan membuat hubungan antara plaintext dan ciphertext tetap terjaga sehingga pola bahasa tidak sepenuhnya tersembunyi. Sebagai pengembangan dari teknik tersebut, Vigenère Cipher diperkenalkan sebagai cipher polialfabetik yang menggunakan kata kunci untuk menentukan pergeseran huruf secara berbeda-beda, sehingga dianggap lebih kuat. Namun, karakteristik kunci yang berulang tetap meninggalkan jejak pola yang dapat dianalisis menggunakan metode seperti Kasiski atau Friedman, menjadikannya masih rentan dibongkar.

Kelemahan utama dari cipher klasik muncul karena algoritma-algoritma tersebut tidak menghilangkan struktur statistik bahasa, sehingga mudah diserang dengan analisis frekuensi. Dalam bahasa alami, huruf tertentu muncul lebih sering daripada huruf lain, dan distribusi ini tetap terbawa ke ciphertext selama proses enkripsi tidak mengubah frekuensi kemunculan huruf secara signifikan. Dengan membandingkan frekuensi huruf pada ciphertext dengan frekuensi huruf umum suatu bahasa, penyerang dapat menebak huruf, menemukan pola substitusi, dan secara bertahap memulihkan isi pesan. Teknik kriptanalisis ini menjadi senjata utama dalam membongkar berbagai cipher substitusi maupun cipher berbasis kunci pendek.

Dalam kriptografi klasik sendiri terdapat dua pendekatan utama, yaitu cipher substitusi dan cipher transposisi. Cipher substitusi melakukan penggantian huruf plaintext dengan huruf lain menurut aturan tertentu, baik secara monoalfabetik maupun polialfabetik. Meskipun ciphertext tampak berubah, pola frekuensi huruf tidak terhapus, sehingga rentan terhadap analisis statistik. Sementara itu, cipher transposisi tidak mengganti huruf, tetapi mengacak posisi huruf sehingga struktur kata berubah namun frekuensi huruf tetap sama. Perubahan urutan ini membuat cipher transposisi relatif lebih sulit ditebak secara langsung, namun tetap dapat diserang melalui analisis pola pengacakan, panjang kunci, atau bentuk blok yang dihasilkan. Kedua jenis cipher ini menjadi fondasi penting dalam sejarah kriptografi, namun secara keamanan modern keduanya dianggap tidak cukup kuat karena masih mempertahankan karakteristik bahasa yang mudah diidentifikasi.

## 3. Alat dan Bahan
- Python 3.11
- Visual Studio Code 
- Git dan akun GitHub  

---

## 4. Langkah Percobaan  
1. Membuat file `caesar_cipher.py`, Vigenere Chiper.py, dan Transposisi.py di folder `praktikum/week5-chiper-klasik/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py, Vigenere Chiper.py, dan Transposisi.py`.)
4. Memasukan semua source code dan hasil code ke github

---

## 5. Source Code
1. Caesar Klasik

<img width="703" height="507" alt="Screenshot 2025-11-07 205852" src="https://github.com/user-attachments/assets/4edee4d6-6e02-447d-850b-62c394155c4d" />

2. Vigenere Chiper

<img width="845" height="936" alt="Screenshot 2025-11-09 115831" src="https://github.com/user-attachments/assets/2b30d6b3-531d-4957-8522-92075e1599bf" />

3. Trasposisi

<img width="1097" height="792" alt="Screenshot 2025-11-09 115950" src="https://github.com/user-attachments/assets/6410d1c7-16e5-4e02-82e0-4e1599dc8ccf" />



## 6. Hasil dan Pembahasan
1. Caesar Klasik

<img width="448" height="106" alt="Screenshot 2025-11-07 205925" src="https://github.com/user-attachments/assets/f1ba6f33-bc85-4be0-8d7b-947b5b2e825f" />

2. Vigenere Chiper

<img width="484" height="195" alt="Screenshot 2025-11-09 115906" src="https://github.com/user-attachments/assets/1f37d140-2938-44f3-ac31-43aa80cf191f" />

3. Trasposisi

<img width="488" height="192" alt="Screenshot 2025-11-09 120013" src="https://github.com/user-attachments/assets/4d5fd309-15ff-41a2-9dc8-4547f717ffa0" />




## 7. Jawaban Pertanyaan
1. Apa kelemahan utama algoritma Caesar Cipher dan Vigenère Cipher?

Kelemahan utama Caesar Cipher adalah ruang kuncinya yang sangat kecil dan pola pergeseran huruf yang konsisten, sehingga cipher ini mudah dipecahkan dengan brute force maupun analisis frekuensi. Sementara itu, Vigenère Cipher yang dianggap lebih kuat tetap memiliki kelemahan ketika kunci yang digunakan pendek atau berulang. Dalam kondisi tersebut, panjang kunci dapat ditemukan dengan metode seperti Kasiski atau Friedman, sehingga ciphertext dapat dipecah menjadi beberapa bagian yang masing-masing dapat diperlakukan sebagai Caesar Cipher dan tetap rentan terhadap analisis frekuensi.

2. Mengapa cipher klasik mudah diserang dengan analisis frekuensi?

Cipher klasik mudah diserang dengan analisis frekuensi karena tidak menghilangkan pola statistik bahasa dari plaintext. Huruf yang sering muncul dalam bahasa tertentu, seperti “a” atau “e”, tetap mempertahankan frekuensinya dalam ciphertext meskipun telah disubstitusi atau diacak. Akibatnya, penyerang dapat membandingkan distribusi huruf pada ciphertext dengan frekuensi huruf bahasa yang digunakan, lalu menebak pemetaan huruf atau pola yang terbentuk sehingga mampu memulihkan plaintext secara bertahap.

3. Bandingkan kelebihan dan kelemahan cipher substitusi vs transposisi.

Cipher substitusi bekerja dengan cara mengganti setiap huruf dengan huruf lain, sehingga ciphertext tampak berbeda dari plaintext. Keunggulannya adalah mudah diterapkan dan dapat menghasilkan tampilan teks yang terlihat acak, namun kelemahannya adalah frekuensi huruf tetap terjaga sehingga sangat rentan terhadap analisis frekuensi. Sebaliknya, cipher transposisi mengacak posisi huruf tanpa menggantinya, sehingga frekuensi huruf tetap sama tetapi pola strukturnya berubah. Hal ini membuatnya lebih tahan terhadap serangan substitusi langsung, namun masih dapat dianalisis melalui pola pengacakan, panjang kunci, atau bentuk blok yang terbentuk. Kedua jenis cipher ini tetap dianggap lemah karena tidak mampu menutupi pola bahasa secara menyeluruh.

## 8. Kesimpulan
Cipher klasik seperti Caesar Cipher dan Vigenère Cipher pada dasarnya memiliki kelemahan mendasar karena masih mempertahankan pola bahasa asli dalam bentuk frekuensi huruf maupun struktur teks. Hal ini membuatnya mudah dibongkar menggunakan analisis frekuensi dan teknik kriptanalisis sederhana lainnya. Meskipun cipher substitusi dan transposisi menjadi fondasi perkembangan kriptografi, keduanya tidak mampu menyembunyikan karakteristik statistik bahasa secara sempurna sehingga tidak memberikan tingkat keamanan yang memadai untuk penggunaan modern. Oleh karena itu, cipher klasik hanya efektif sebagai pembelajaran dasar kriptografi dan tidak lagi sesuai untuk melindungi data sensitif di era komputasi saat ini.

## 9. Daftar Pustaka

## 10. Commit Log
```
commit abc12345
Author: Dimas Riyan Hidayat <dimasriyanhidayat01@gmail.com>
Date:   2025-11-09

    week5-Ciper Klasik:
```
