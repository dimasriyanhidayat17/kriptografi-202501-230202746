# Laporan Praktikum Kriptografi
Minggu ke-: VI  
Topik: Chiper-Modern  
Nama: Dimas Riyan Hidayat
NIM: 230202746 
Kelas: 5IKRB

---

## 1. Tujuan
1. Mengimplementasikan algoritma DES untuk blok data sederhana.
2. Menerapkan algoritma AES dengan panjang kunci 128 bit.
3. Menjelaskan proses pembangkitan kunci publik dan privat pada algoritma RSA.

## 2. Dasar Teori
Kriptografi modern terbagi menjadi dua kategori utama, yaitu kriptografi simetris dan asimetris. Algoritma simetris seperti DES dan AES menggunakan satu kunci yang sama untuk proses enkripsi dan dekripsi, sehingga efisien untuk pengolahan data dalam jumlah besar. DES merupakan algoritma blok simetris berbasis struktur Feistel dengan panjang kunci 56 bit, namun kelemahannya pada ukuran kunci yang kecil membuatnya rentan terhadap brute force. Sebagai penerusnya, AES dikembangkan dengan panjang kunci 128, 192, dan 256 bit serta struktur Substitution–Permutation Network (SPN) yang lebih aman dan efisien, sehingga menjadi standar internasional dan menggantikan DES dalam berbagai aplikasi keamanan modern.

Berbeda dari DES dan AES, RSA adalah algoritma kriptografi asimetris yang menggunakan sepasang kunci berbeda, yaitu kunci publik untuk enkripsi dan kunci privat untuk dekripsi. Keamanan RSA bergantung pada kesulitan memfaktorkan bilangan komposit besar, sehingga proses pembangkitan kuncinya melibatkan pemilihan dua bilangan prima besar, perhitungan nilai modulus n, totient Eule 𝜑(𝑛)φ(n), serta penentuan eksponen publik dan privat. Penggunaan dua kunci yang berbeda memungkinkan RSA menyelesaikan masalah distribusi kunci, menjadikannya sangat penting untuk pertukaran kunci dan tanda tangan digital.

Secara keseluruhan, perbedaan mendasar antara DES, AES, dan RSA terletak pada jenis kunci serta tingkat keamanannya. AES lebih unggul dibanding DES karena panjang kunci yang jauh lebih besar, tingkat keamanan yang lebih tinggi, dan performa yang lebih baik. RSA, meskipun tidak efisien untuk enkripsi data dalam jumlah besar, memainkan peran penting dalam komunikasi aman karena kemampuannya menyediakan mekanisme autentikasi dan distribusi kunci yang tidak dapat dilakukan oleh algoritma simetris.
## 3. Alat dan Bahan
- Python 3.11
- Visual Studio Code 
- Git dan akun GitHub 

---

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `caesar_cipher.py` di folder `praktikum/week2-cryptosystem/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)

---

## 5. Source Code
1. Implementasi DES
   
<img width="611" height="436" alt="Screenshot 2025-11-11 114555" src="https://github.com/user-attachments/assets/4208b4aa-a843-473c-8376-3969f4ac355e" />

2. Implementasi AES

<img width="687" height="437" alt="Screenshot 2025-11-11 114649" src="https://github.com/user-attachments/assets/c9aed329-62ca-499f-a4b5-1dcae0e99fa6" />

3. Implementasi RSA

<img width="565" height="535" alt="Screenshot 2025-11-11 114740" src="https://github.com/user-attachments/assets/cde86b40-5ded-4fb5-a1be-97a60597a4c2" />

---

## 6. Hasil dan Pembahasan
1. Implementasi DES

<img width="503" height="192" alt="Screenshot 2025-11-11 114622" src="https://github.com/user-attachments/assets/fa1254b7-86f0-4755-890e-3881d639e5b2" />

2. Implementasi AES

<img width="823" height="199" alt="Screenshot 2025-11-11 114718" src="https://github.com/user-attachments/assets/38d79985-7c56-4951-8e5d-ea603e1fbc96" />

3. Implementasi RSA

<img width="1316" height="369" alt="Screenshot 2025-11-11 114804" src="https://github.com/user-attachments/assets/e175da6f-312c-4792-93f6-8d2cbd090423" />


## 7. Jawaban Pertanyaan
1. Perbedaan mendasar antara DES, AES, dan RSA dalam hal kunci dan keamanan

DES, AES, dan RSA menunjukkan perbedaan mendasar baik dari jenis kunci yang digunakan maupun tingkat keamanannya. DES dan AES termasuk dalam kategori algoritma kriptografi simetris, di mana proses enkripsi dan dekripsi menggunakan kunci yang sama. DES memiliki panjang kunci efektif sebesar 56 bit sehingga rentan terhadap serangan brute force pada sistem komputasi modern. Sebaliknya, AES menawarkan panjang kunci 128, 192, dan 256 bit serta menggunakan struktur desain yang lebih efisien dan aman, sehingga menjadi standar enkripsi yang lebih kuat dan relevan. RSA berbeda secara fundamental karena merupakan algoritma asimetris yang menggunakan sepasang kunci, yaitu kunci publik dan kunci privat. Keamanan RSA tidak bergantung pada panjang blok data, tetapi pada tingkat kesulitan matematis dalam memfaktorkan bilangan komposit besar menjadi faktor-faktor primanya. Dengan demikian, kunci RSA umumnya memiliki panjang yang jauh lebih besar, mulai dari 1024 hingga 4096 bit, guna memastikan tingkat keamanan yang memadai.

2. Mengapa AES lebih banyak digunakan dibanding DES di era modern?

AES lebih banyak digunakan dibanding DES pada era modern karena tingkat keamanan yang ditawarkannya jauh lebih tinggi. Panjang kunci DES yang terbatas hanya 56 bit memungkinkan algoritma tersebut dipecahkan dalam waktu yang relatif singkat menggunakan teknologi komputasi saat ini, sehingga tidak lagi memenuhi standar keamanan kontemporer. AES tidak hanya memiliki panjang kunci yang lebih besar, tetapi juga dirancang untuk memberikan performa yang optimal pada perangkat lunak dan perangkat keras. Selain itu, AES telah ditetapkan oleh National Institute of Standards and Technology (NIST) sebagai standar enkripsi internasional, dan digunakan secara luas pada berbagai sistem keamanan seperti jaringan nirkabel, VPN, serta protokol komunikasi Internet. Kombinasi antara keamanan yang kuat, efisiensi tinggi, dan standarisasi global menjadikan AES lebih unggul dan menggantikan DES sebagai pilihan utama.

3. Mengapa RSA dikategorikan sebagai algoritma asimetris, dan bagaimana proses pembangkitan kuncinya?

RSA dikategorikan sebagai algoritma asimetris karena menggunakan dua kunci yang berbeda dalam proses enkripsi dan dekripsi, yaitu kunci publik yang dapat didistribusikan secara terbuka dan kunci privat yang harus dijaga kerahasiaannya. Model penggunaan dua kunci ini didasarkan pada prinsip matematis bahwa mengetahui kunci publik tidak memungkinkan pihak lain untuk memperoleh kunci privat secara praktis. Keamanan RSA bergantung pada permasalahan faktorisasi bilangan komposit besar, yang hingga kini dianggap sulit diselesaikan secara efisien. Proses pembangkitan kunci RSA dimulai dengan memilih dua bilangan prima besar, p dan q, kemudian menghitung nilai modulus 𝑛=𝑝×𝑞. Selanjutnya dihitung fungsi totient Euler, 𝜑(𝑛)=(𝑝−1)(𝑞−1)φ(n)=(p−1)(q−1), yang digunakan untuk menentukan eksponen publik e yang relatif prima terhadap 𝜑(𝑛)φ(n). Setelah itu dihitung eksponen privat d, yaitu invers modulo dari 𝑒e terhadap 𝜑(𝑛)φ(n). Hasil akhir proses ini menghasilkan kunci publik (𝑒,𝑛)(e,n) dan kunci privat (𝑑,𝑛)
(d,n), yang masing-masing digunakan sesuai perannya dalam enkripsi, dekripsi, maupun penandatanganan digital.

## 8. Kesimpulan
DES, AES, dan RSA memiliki perbedaan mendasar dalam mekanisme kerja dan tingkat keamanannya. DES dan AES merupakan algoritma simetris, namun DES tidak lagi dianggap aman karena panjang kuncinya yang sangat terbatas, sementara AES menawarkan keamanan yang tinggi dan efisiensi sehingga menjadi standar enkripsi modern. Di sisi lain, RSA merupakan algoritma asimetris yang menggunakan sepasang kunci berbeda dan mengandalkan kesulitan faktorisasi bilangan besar, sehingga sangat efektif untuk proses autentikasi dan pertukaran kunci.

Secara umum, AES lebih banyak digunakan untuk enkripsi data karena kecepatan dan kekuatannya, sedangkan RSA digunakan untuk fungsi yang tidak dapat dilakukan algoritma simetris, seperti distribusi kunci dan tanda tangan digital. Kombinasi kedua jenis algoritma ini sering digunakan dalam sistem keamanan modern untuk mencapai keseimbangan antara keamanan yang kuat dan efisiensi operasional.

## 9. Daftar Pustaka

## 10. Commit Log
```
week6-cipher-modern
Author: Dimas Riyan Hidayat <dimasriyanhidayat01@gmail.com>
Date:   2025-09-20

    week6-Chiper-Modern:  )
```
