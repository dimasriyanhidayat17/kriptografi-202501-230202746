# Laporan Praktikum Kriptografi
Minggu ke-: 4
Topik: entropy unicity & brute force attack 
Nama: Safira Dewi Rahmatika 
NIM: 230202784
Kelas: 5IKRB 
## 1. Tujuan
1. Entropi kunci.
2. Unicity distance.
3. Estimasi brute force attack.
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
soal.
1. Apa arti dari nilai entropy dalam konteks kekuatan kunci?
2. Mengapa unicity distance penting dalam menentukan keamanan suatu cipher?
3. Mengapa brute force masih menjadi ancaman meskipun algoritma sudah kuat?
   
Jawaban.
1. Nilai entropi dalam konteks kekuatan kunci menunjukkan tingkat ketidakpastian atau kerandoman dari suatu kunci. Semakin tinggi nilai entropi, berarti kunci tersebut semakin acak dan sulit ditebak oleh pihak lain. Entropi yang tinggi menandakan bahwa ruang kemungkinan kunci sangat besar, sehingga peluang seseorang menebak kunci dengan benar menjadi sangat kecil. Dengan kata lain, entropi menjadi ukuran seberapa kuat kunci dapat melindungi pesan dari serangan yang mencoba menebaknya secara acak atau sistematis.

2. Unicity distance penting karena menunjukkan seberapa banyak ciphertext yang dibutuhkan untuk bisa menentukan kunci enkripsi secara unik. Jika unicity distance besar, maka penyerang membutuhkan lebih banyak data terenkripsi untuk menemukan kunci yang benar, sehingga sistem menjadi lebih aman. Sebaliknya, jika unicity distance kecil, maka dengan sedikit ciphertext saja penyerang mungkin sudah bisa menemukan kunci, membuat cipher lebih rentan. Jadi, unicity distance membantu menilai ketahanan cipher terhadap analisis kriptografi yang mencoba memecahkan kunci berdasarkan data yang tersedia.

3. Brute force masih menjadi ancaman meskipun algoritma kriptografi modern sangat kuat, karena metode ini tidak bergantung pada kelemahan algoritma, melainkan mencoba semua kemungkinan kunci hingga menemukan yang benar. Dengan meningkatnya kemampuan komputasi dan munculnya teknologi baru seperti komputasi paralel dan komputer kuantum, waktu yang dibutuhkan untuk melakukan brute force bisa semakin singkat. Oleh karena itu, meskipun algoritma sudah kuat, penggunaan panjang kunci yang memadai tetap penting agar brute force tetap tidak praktis untuk dilakukan.




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
