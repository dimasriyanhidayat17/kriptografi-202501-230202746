# Laporan Praktikum Kriptografi
Minggu ke-: VI  
Topik: Chiper Modern(DES, AES, RSA)  
Nama: Safira Dewi Rahmatika 
NIM: 230202784 
Kelas: 5IKRB

## 1. Tujuan
1. Mengimplementasikan algoritma DES untuk blok data sederhana.
2. Menerapkan algoritma AES dengan panjang kunci 128 bit.
3. Menjelaskan proses pembangkitan kunci publik dan privat pada algoritma RSA.

## 2. Dasar Teori
DES (Data Encryption Standard) adalah algoritma kriptografi simetris yang menggunakan satu kunci yang sama untuk proses enkripsi dan dekripsi data. Algoritma ini bekerja pada blok data berukuran 64 bit dan menggunakan kunci sepanjang 56 bit untuk menghasilkan ciphertext. DES melakukan proses enkripsi melalui beberapa tahap, seperti permutasi awal, 16 ronde substitusi dan permutasi, serta permutasi akhir. Meskipun pernah menjadi standar enkripsi data yang banyak digunakan, DES kini dianggap kurang aman karena panjang kuncinya yang terlalu pendek sehingga rentan terhadap serangan brute force.

AES (Advanced Encryption Standard) merupakan algoritma kriptografi simetris yang dikembangkan sebagai pengganti DES dengan tingkat keamanan yang lebih tinggi. AES bekerja dengan blok data berukuran 128 bit dan mendukung panjang kunci 128, 192, atau 256 bit. Proses enkripsinya meliputi tahapan SubBytes, ShiftRows, MixColumns, dan AddRoundKey yang diulang beberapa kali tergantung panjang kunci yang digunakan. Karena struktur dan kompleksitasnya yang tinggi, AES menjadi algoritma enkripsi yang cepat, efisien, serta telah ditetapkan sebagai standar enkripsi global oleh NIST.

RSA (Rivest–Shamir–Adleman) adalah algoritma kriptografi asimetris yang menggunakan dua kunci berbeda, yaitu kunci publik untuk enkripsi dan kunci privat untuk dekripsi. RSA didasarkan pada konsep matematika bilangan prima besar dan operasi eksponensial modular. Proses pembangkitan kunci RSA dilakukan dengan memilih dua bilangan prima besar, menghitung hasil kali serta totiennya, lalu menentukan nilai kunci publik dan privat yang saling terkait. RSA banyak digunakan dalam keamanan data digital, seperti tanda tangan elektronik, autentikasi, serta pertukaran kunci secara aman di jaringan internet.

## 3. Alat dan Bahan
- Python 3.11 
- Visual Studio Code  
- Git dan akun GitHub  

## 4. Langkah Percobaan
1. Membuat file aes.py rsa.py des.py di folder praktikum/week6-cipher-modern/src/.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan kode program.

## 5. Source Code
1. Implementasi DES

<img width="611" height="436" alt="Screenshot 2025-11-11 114555" src="https://github.com/user-attachments/assets/6208d124-386e-4b03-91af-2d1f49c11f04" />

2. Implementasi AES

<img width="687" height="437" alt="Screenshot 2025-11-11 114649" src="https://github.com/user-attachments/assets/eed1858a-3327-4ab7-80f5-1f423eeedf12" />

3. Implementasi RSA

<img width="565" height="535" alt="Screenshot 2025-11-11 114740" src="https://github.com/user-attachments/assets/c7bf2c7a-f0bb-4ffc-afbf-a323b2470a68" />

## 6. Hasil dan Pembahasan
1. Implementasi DES

<img width="503" height="192" alt="Screenshot 2025-11-11 114622" src="https://github.com/user-attachments/assets/a1de1e7d-131d-4302-81f4-b72b13535243" />

2. Implementasi AES

<img width="823" height="199" alt="Screenshot 2025-11-11 114718" src="https://github.com/user-attachments/assets/809fa406-ebe1-4d82-a4f9-682014579de5" />

3. Implementasi RSA

<img width="1316" height="369" alt="Screenshot 2025-11-11 114804" src="https://github.com/user-attachments/assets/8d347e34-616d-4327-ad0f-fff7e6c01713" />


## 7. Jawaban Pertanyaan
soal
1. Apa perbedaan mendasar antara DES, AES, dan RSA dalam hal kunci dan keamanan?
2. Mengapa AES lebih banyak digunakan dibanding DES di era modern?
3. Mengapa RSA dikategorikan sebagai algoritma asimetris, dan bagaimana proses pembangkitan kuncinya?

jawaban
1. Perbedaan utama antara DES, AES, dan RSA terletak pada jenis kunci dan keamanannya. DES dan AES adalah algoritma simetris yang memakai satu kunci untuk enkripsi dan dekripsi, sedangkan RSA adalah asimetris yang menggunakan dua kunci, yaitu publik dan privat. DES memakai kunci 56-bit yang kini dianggap lemah, sementara AES lebih kuat dengan panjang kunci 128, 192, atau 256-bit. RSA lebih sering digunakan untuk pertukaran kunci dan tanda tangan digital karena sifat asimetrisnya.

2. AES lebih banyak digunakan dibanding DES karena lebih aman, cepat, dan efisien. DES dengan kunci 56-bit mudah dipecahkan dengan brute force, sedangkan AES memiliki struktur yang lebih kompleks dan mendukung panjang kunci lebih besar. Selain itu, AES telah diakui sebagai standar enkripsi internasional (FIPS 197) oleh NIST, sehingga menjadi pilihan utama di berbagai sistem keamanan modern.

3. RSA disebut algoritma asimetris karena memakai dua kunci berbeda: publik untuk enkripsi dan privat untuk dekripsi. Kuncinya dibentuk dengan memilih dua bilangan prima besar, menghitung hasil kali dan totiennya, lalu menentukan nilai  (publik) dan  (privat) yang saling berhubungan secara matematis. Dengan cara ini, pesan hanya bisa dibuka oleh pemilik kunci privat yang sesuai.
   
## 8. Kesimpulan
Dari ketiga algoritma tersebut, dapat disimpulkan bahwa DES, AES, dan RSA memiliki perbedaan mendasar dalam cara kerja dan tingkat keamanannya. DES merupakan algoritma simetris generasi awal yang kini dianggap kurang aman karena panjang kuncinya hanya 56 bit. AES hadir sebagai penggantinya dengan struktur yang lebih kompleks, panjang kunci yang lebih besar, dan tingkat keamanan yang jauh lebih tinggi sehingga menjadi standar enkripsi modern. Sementara itu, RSA termasuk algoritma asimetris yang menggunakan dua kunci berbeda, yaitu publik dan privat, dan banyak digunakan dalam sistem keamanan digital seperti enkripsi kunci, tanda tangan digital, dan autentikasi. Dengan kombinasi penggunaan algoritma simetris dan asimetris, sistem keamanan data saat ini dapat mencapai efisiensi sekaligus perlindungan yang kuat terhadap ancaman siber.
## 9. Daftar Pustaka

## 10. Commit Log
commit abc12345
Author: Safira Dewi Rahamatika (safiraa1026@gmail.com)
Date:   2025-11-11

    week6-Chiper Modern: implementasi DES, AES, RSA dan laporan
