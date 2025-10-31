# Laporan Praktikum Kriptografi
Minggu ke-: 4
Topik: entrophy- unicity  
Nama: Dhea Silvia
NIM: 230202742  
Kelas: 5ikrb  

---

## 1. Tujuan
1. Menyelesaikan perhitungan sederhana terkait entropi kunci.
2. Menggunakan teorema Euler pada contoh perhitungan modular & invers.
3. Menghitung unicity distance untuk ciphertext tertentu.
4. Menganalisis kekuatan kunci berdasarkan entropi dan unicity distance.
5. Mengevaluasi potensi serangan brute force pada kriptosistem sederhana.

---

## 2. Dasar Teori
- Entropi kunci adalah ukuran derajat ketidakteraturan atau keacakan suatu sistem.Secara fundamental, konsep kunci entropi dalam Termodinamika berkaitan dengan:Ketidakteraturan (Disorder) atau Keacakan: Entropi ($S$) adalah besaran yang mengukur sejauh mana energi pada suatu sistem tersebar dan tingkat ketidakrapian atau kekacauan sistem tersebut. Semakin tinggi entropi, semakin tidak teratur sistemnya.Hukum Kedua Termodinamika: Hukum ini menyatakan bahwa entropi total suatu sistem terisolasi (misalnya alam semesta) cenderung selalu meningkat seiring waktu. Ini adalah kecenderungan alami proses menuju keadaan yang lebih kacau atau tidak teratur.Energi yang Tidak Tersedia untuk Kerja: Entropi juga dapat diartikan sebagai ukuran energi dalam sistem yang tidak dapat digunakan untuk melakukan kerja yang bermanfaat***.
---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code 
- Git dan akun GitHub  
- google gemini

---

## 4. Langkah Percobaan
1.Membuat file entropy_unicity.py di folder praktikum/week3_entropy_unicity/src/.
2.Menyalin kode program dari panduan praktikum.
- Langkah 1 — Perhitungan Entropi Gunakan rumus:
[ H(K) = \log_2 |K| ]
dengan (|K|) adalah ukuran ruang kunci.
- Langkah 2 — Menghitung Unicity Distance Gunakan rumus:
[ U = \frac{H(K)}{R \cdot \log_2 |A|} ]
dengan:
(H(K)): entropi kunci,
(R): redundansi bahasa (misal bahasa Inggris (R \approx 0.75)),
(|A|): ukuran alfabet (26 untuk A–Z). 6.
- Langkah 3 — Analisis Brute Force Simulasikan waktu brute force dengan asumsi kecepatan komputer tertentu.
Menjalankan program dengan perintah python entropy_unicity.py.)
---

## 5. Source Code
import math

def entropy(keyspace_size):
    return math.log2(keyspace_size)

print("Entropy ruang kunci 26 =", entropy(26), "bit")
print("Entropy ruang kunci 2^128 =", entropy(2**128), "bit")

def unicity_distance(HK, R=0.75, A=26):
    return HK / (R * math.log2(A))

HK = entropy(26)
print("Unicity Distance untuk Caesar Cipher =", unicity_distance(HK))

def brute_force_time(keyspace_size, attempts_per_second=1e6):
    seconds = keyspace_size / attempts_per_second
    days = seconds / (3600*24)
    return days

print("Waktu brute force Caesar Cipher (26 kunci) =", brute_force_time(26), "hari")
print("Waktu brute force AES-128 =", brute_force_time(2**128), "hari")


## 6. Hasil dan Pembahasan
Hasil:
Entropy ruang kunci 26 = 4.700439718141092 bit

Entropy ruang kunci 2^128 = 128.0 bit

Unicity Distance untuk Caesar Cipher = 1.3333333333333333

Waktu brute force Caesar Cipher (26 kunci) = 3.0092592592592593e-10 hari

Waktu brute force AES-128 = 3.938453320844195e+27 hari


Pembahasan:
Hasil perhitungan keamanan kriptografi membandingkan Caesar Cipher (sandi lemah) dan AES-128 (sandi kuat). Entropi Ruang Kunci menunjukkan ukuran ruang kunci: Caesar Cipher hanya memiliki 4.7004 bit entropi, sementara AES-128 memiliki 128.0 bit, menegaskan ruang kunci AES-128 jauh lebih besar dan aman. Lebih lanjut, Jarak Unicity Caesar Cipher yang hanya 1.333 karakter berarti sandi tersebut dapat dipecahkan secara teoritis hanya dengan menganalisis sedikit ciphertext. Perbandingan Waktu Brute Force memperjelas perbedaan ini: Caesar Cipher dapat dipecahkan hampir instan ($3 \times 10^{-10}$ hari), sedangkan AES-128 memerlukan waktu $3.9 \times 10^{27}$ hari, menjadikannya aman dari serangan brute-force pada teknologi saat ini.

![Hasil Eksekusi](screenshots/output.png)
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/c7fd09cf-a3a9-4903-9504-c7c73e6efe91" />


---

## 7. Jawaban Pertanyaan
1. Apa arti dari nilai entropy dalam konteks kekuatan kunci?
    jawab:Entropi dalam konteks kekuatan kunci adalah ukuran derajat keacakan dan ketidakpastian dari suatu kunci atau password. Nilai entropi diukur dalam satuan bit.Semakin tinggi nilai entropi suatu kunci, semakin kuat dan aman kunci tersebut.

2. Mengapa unicity distance penting dalam menentukan keamanan suatu cipher?
   jawab: Unicity Distance ($U$) adalah jumlah minimum ciphertext (teks tersandi) yang diperlukan agar kunci dekripsi yang benar menjadi unik secara statistik di mata         penyerang.Unicity Distance menentukan seberapa cepat cipher tersebut dapat dipecahkan menggunakan analisis linguistik (memanfaatkan redundansi bahasa) tanpa harus mencoba semua kunci.

3. Mengapa brute force masih menjadi ancaman meskipun algoritma sudah kuat?
   jawab: Serangan brute force adalah upaya sistematis untuk mencoba setiap kemungkinan kunci hingga kunci yang benar ditemukan. Serangan ini tetap menjadi ancaman karena dua alasan utama:

1. Peningkatan Kekuatan Komputasi: Hukum Moore dan kemajuan dalam komputasi paralel, terutama dengan GPU dan komputasi terdistribusi, secara konstan meningkatkan kecepatan hashing dan percobaan kunci. Apa yang sulit dipecahkan sepuluh tahun lalu mungkin menjadi mungkin hari ini.

2. Kelemahan Implementasi (Kunci Pendek/Lemah): Meskipun algoritma (misalnya AES) itu sendiri kuat, keamanan selalu tergantung pada kunci terlemah.

- Jika pengguna memilih kunci yang pendek (misalnya, hanya 40 bit) atau tidak acak (misalnya, password yang umum), entropi kunci menjadi rendah.

- Ketika entropi kunci rendah, ruang kunci menjadi kecil, dan waktu yang dibutuhkan untuk serangan brute force menjadi sangat singkat, membuat cipher tersebut rentan meskipun menggunakan algoritma terkuat.

## 8. Kesimpulan
Penggunaan kriptografi klasik seperti caesar cipher sudah sangat usang, terbukti dari entropy kunci yang sangat rendah sehingga sangat rentan terhadap serangan brute force dan ananlisis frekuensi. Sedangkan penggunaan kriptografi modern seperti AES-128 dengan keamanan entropy 128 bit membuat pemecahan kunci secara komputasi menjadi mustahil, meskipun ancaman brute force tetap ada dengan menyerang penggunaan kombinasi password yang lemah.2–3 kalimat) berdasarkan percobaan.  )

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
week4-entrophy-unicity
Author: Dhea Silvia <dheasilvia51@gmail.com>
Date:   2025-10-31

    week4-entrophy-unicity: entrophy-unicity distance
```
