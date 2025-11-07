# Laporan Praktikum Kriptografi
Minggu ke-: 4
Topik: entropy unicity & brute force attack 
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
<img width="1051" height="523" alt="Screenshot 2025-11-02 150955" src="https://github.com/user-attachments/assets/b2c73a55-8ad3-4390-ba77-2add69cb24dd" />

## 6. Hasil dan Pembahasan
<img width="693" height="255" alt="Screenshot 2025-11-02 151012" src="https://github.com/user-attachments/assets/358fdab6-9671-4d2e-8337-e98eb1aba23d" />


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
Berdasarkan data output tersebut, terlihat perbedaan keamanan yang sangat signifikan antara algoritma klasik dan modern. Caesar Cipher, dengan entropi ruang kunci 26 yang hanya ~4.7 bit, dapat dipecahkan melalui brute force dalam waktu yang hampir seketika, yaitu 3.009e-10 hari. Sebaliknya, standar enkripsi modern seperti AES-128 menawarkan tingkat keamanan yang jauh berbeda; dengan entropi 128 bit, waktu yang dibutuhkan untuk serangan brute force diperkirakan mencapai 3.938e+27 hari. Perbandingan ini secara jelas mengilustrasikan mengapa enkripsi sederhana seperti Caesar Cipher sama sekali tidak aman untuk data sensitif, sementara AES-128 dianggap aman secara komputasi.

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
Author: Safira Dewi Rahmatika <email> safiraa1026@gmail.com
week3-entropy-unicity: entropy & uniciy distance 
