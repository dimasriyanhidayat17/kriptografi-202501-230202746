    # Laporan Praktikum Kriptografi
Minggu ke-: 4  
Topik: [judul praktikum]  
Nama: Dimas Riyan Hidayat  
NIM: 230202746  
Kelas: 5IKRB 

## 1. Tujuan
1. Menyelesaikan perhitungan sederhana terkait entropi kunci.
2. Menggunakan teorema Euler pada contoh perhitungan modular & invers.
3. Menghitung unicity distance untuk ciphertext tertentu.
4. Menganalisis kekuatan kunci berdasarkan entropi dan unicity distance.
5. Mengevaluasi potensi serangan brute force pada kriptosistem sederhana.

## 2. Dasar Teori
(Ringkas teori relevan (cukup 2–3 paragraf).  
Contoh: definisi cipher klasik, konsep modular aritmetika, dll.  )

---

## 3. Alat dan Bahan 
- Python 3.11
- Git dan akun GitHub

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `caesar_cipher.py` di folder `praktikum/week2-cryptosystem/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)

---

## 5. Source Code
<img width="1051" height="523" alt="Screenshot 2025-11-02 150955" src="https://github.com/user-attachments/assets/a26ee09c-37db-45fe-9c15-7e2ae20dbcbd" />


## 6. Hasil dan Pembahasan
<img width="693" height="255" alt="Screenshot 2025-11-02 151012" src="https://github.com/user-attachments/assets/c8f49947-ae98-4c54-91cb-7242cdc10c6e" />


## 7. Jawaban Pertanyaan
1. Nilai Entropy dalam Kekuatan Kunci
Dalam konteks kekuatan kunci, nilai entropy menggambarkan tingkat keacakan atau ketidakpastian dari suatu kunci kriptografi. Semakin tinggi nilai entropi, semakin besar ruang kemungkinan kunci yang tersedia dan semakin sulit bagi penyerang untuk menebaknya melalui brute force. Entropy yang tinggi menunjukkan bahwa kunci sulit diprediksi dan memiliki keamanan yang lebih baik karena peluang untuk menebak kunci secara benar menjadi sangat kecil.

2. Pentingnya Unicity Distance dalam Keamanan Cipher
Unicity distance merupakan ukuran jumlah minimal ciphertext yang dibutuhkan agar kunci dapat ditentukan secara unik melalui analisis kriptografi. Nilai ini bergantung pada besarnya entropi kunci dan tingkat redundansi dalam plaintext. Jika jumlah ciphertext yang diperoleh lebih sedikit dari nilai unicity distance, maka kriptanalis tidak dapat memastikan kunci yang benar, sehingga cipher masih dianggap aman. Sebaliknya, jika ciphertext yang tersedia melebihi nilai tersebut, maka kemungkinan kunci dapat ditemukan secara pasti meningkat, dan keamanan cipher menjadi berkurang.

3. Brute Force sebagai Ancaman Meski Algoritma Sudah Kuat
Meskipun algoritma kriptografi modern seperti AES dan RSA memiliki dasar matematis yang sangat kuat, brute force tetap menjadi ancaman nyata. Ancaman ini muncul bukan karena kelemahan algoritmanya, tetapi karena faktor-faktor eksternal seperti penggunaan kunci yang lemah, kesalahan implementasi, kemajuan teknologi komputasi, serta pengelolaan kunci yang tidak aman. Dengan meningkatnya kemampuan perangkat keras seperti GPU dan komputer kuantum, waktu yang dibutuhkan untuk melakukan brute force dapat berkurang secara signifikan. Oleh karena itu, keamanan sistem kriptografi tidak hanya bergantung pada kekuatan algoritma, tetapi juga pada penerapan dan pengelolaan kunci yang benar.

## 8. Kesimpulan
(Tuliskan kesimpulan singkat (2–3 kalimat) berdasarkan percobaan.  )

---

## 9. Daftar Pustaka

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
