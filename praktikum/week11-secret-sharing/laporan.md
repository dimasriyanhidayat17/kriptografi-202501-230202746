# Laporan Praktikum Kriptografi
Minggu ke-: XI 
Topik: Secret Sharing (Shamir’s Secret Sharing)  
Nama: Dimas Riyan Hidayat  
NIM: 230202746  
Kelas: 5IKRB  

---

## 1. Tujuan
1. Menjelaskan konsep Shamir Secret Sharing (SSS).
2. Melakukan simulasi pembagian rahasia ke beberapa pihak menggunakan skema SSS.
3. Menganalisis keamanan skema distribusi rahasia.

## 2. Dasar Teori
Shamir’s Secret Sharing (SSS) merupakan skema kriptografi yang digunakan untuk membagi suatu informasi rahasia menjadi beberapa bagian yang disebut share. Skema ini diperkenalkan oleh Adi Shamir pada tahun 1979 dengan tujuan menghindari risiko penyimpanan rahasia pada satu pihak atau satu lokasi. Dalam SSS, tidak ada satu pun share yang dapat mengungkapkan rahasia secara mandiri, sehingga kebocoran sebagian data tidak langsung membahayakan informasi rahasia.

Prinsip kerja Shamir’s Secret Sharing didasarkan pada penggunaan polinomial berderajat k−1 dalam aritmetika modulo bilangan prima. Nilai rahasia direpresentasikan sebagai konstanta polinomial, sedangkan nilai-nilai lainnya dipilih secara acak. Setiap share dibentuk dari pasangan nilai (x,f(x)) dan didistribusikan kepada pihak yang berbeda. Rekonstruksi rahasia dilakukan menggunakan interpolasi Lagrange apabila jumlah share yang tersedia memenuhi ambang batas (threshold) yang ditentukan.

Skema Shamir’s Secret Sharing memiliki tingkat keamanan yang tinggi karena bersifat information-theoretic security, yaitu keamanannya tidak bergantung pada kemampuan komputasi penyerang. Apabila jumlah share yang dimiliki kurang dari threshold, rahasia tidak dapat ditentukan secara matematis. Oleh karena itu, SSS banyak diterapkan dalam manajemen kunci kriptografi, sistem pemulihan akses, dan pengamanan data penting yang memerlukan kolaborasi beberapa pihak.

## 3. Alat dan Bahan
- Python 3.11 
- Visual Studio Code  
- Git dan akun GitHub  
- Library tambahan (pip install secretsharing)  


## 4. Langkah Percobaan
1. Membuat file `secretsharing.py` di folder `praktikum/week11-seceretsharing/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `seceretsharing.py`.
4. mengerjakan quis


## 5. Source Code
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f18bbc84-6904-475c-84a9-49fde0dfb4f2" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2d5ade71-b4e8-488e-88ab-2019dc828cff" />


## 6. Hasil dan Pembahasan
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/dc8cefd2-14e8-4615-a075-7d5b12f14e52" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5a57dc45-4615-46c9-b850-d318c2e81508" />

Mengapa skema (k, n) aman meskipun sebagian share bocor?
Skema Shamir’s Secret Sharing (k, n) tetap aman meskipun sebagian share bocor karena keamanannya bersifat information-theoretic security. Rahasia disimpan sebagai konstanta dari suatu polinomial berderajat k−1, sehingga dibutuhkan minimal k buah titik (share) yang berbeda untuk dapat merekonstruksi polinomial tersebut secara unik. Apabila penyerang hanya memiliki kurang dari k share, maka terdapat banyak kemungkinan polinomial yang dapat dibentuk, masing-masing menghasilkan nilai rahasia yang berbeda. Dengan demikian, kepemilikan sebagian share tidak memberikan informasi apa pun mengenai nilai rahasia yang sebenarnya.

Apa risiko jika threshold k terlalu kecil atau terlalu besar?
Pemilihan nilai threshold k yang tidak tepat dapat menimbulkan risiko keamanan maupun ketersediaan sistem. Jika nilai k terlalu kecil, maka sejumlah kecil pihak sudah cukup untuk merekonstruksi rahasia, sehingga meningkatkan risiko kebocoran akibat kolusi atau kompromi. Sebaliknya, jika nilai k terlalu besar, sistem menjadi tidak toleran terhadap kehilangan share, karena hilangnya satu atau dua share saja dapat menyebabkan rahasia tidak dapat dipulihkan sama sekali. Oleh karena itu, penentuan nilai k harus mempertimbangkan keseimbangan antara tingkat keamanan dan ketersediaan sistem.

Bagaimana penerapan Shamir’s Secret Sharing di dunia nyata?
Shamir’s Secret Sharing banyak diterapkan dalam sistem keamanan modern, terutama pada manajemen kunci kriptografi dan mekanisme pemulihan akses. Dalam dunia cryptocurrency, skema ini digunakan untuk membagi private key ke beberapa perangkat atau pihak, sehingga tidak ada satu pihak pun yang memegang kunci secara utuh. Selain itu, SSS juga digunakan pada sistem recovery password dan pengelolaan master key di lingkungan enterprise, di mana beberapa administrator harus bekerja sama untuk mendapatkan kembali akses. Penerapan ini menghilangkan single point of failure dan meningkatkan keamanan terhadap pencurian maupun kehilangan data penting.

## 7. Jawaban Pertanyaan
1. Apa keuntungan utama Shamir Secret Sharing dibanding membagikan salinan kunci secara langsung?
Keuntungan utama Shamir Secret Sharing adalah tidak adanya pihak yang menyimpan kunci secara utuh. Setiap share tidak bermakna secara mandiri dan rahasia hanya dapat direkonstruksi jika jumlah share yang digunakan memenuhi threshold, sehingga risiko kebocoran akibat kompromi satu pihak dapat diminimalkan.
2. Apa peran threshold (k) dalam keamanan secret sharing?
Threshold (k) menentukan jumlah minimum share yang diperlukan untuk merekonstruksi rahasia dan berfungsi menyeimbangkan keamanan dan ketersediaan. Nilai k yang lebih besar meningkatkan keamanan, sedangkan nilai k yang lebih kecil meningkatkan kemudahan pemulihan rahasia.
3. Berikan satu contoh skenario nyata di mana SSS sangat bermanfaat.
Shamir Secret Sharing bermanfaat dalam manajemen private key cryptocurrency, di mana kunci dibagi ke beberapa pihak dan hanya dapat digunakan jika sejumlah minimum pihak bekerja sama, sehingga mencegah penyalahgunaan dan kehilangan akses.

## 8. Kesimpulan
Shamir’s Secret Sharing merupakan metode kriptografi yang efektif untuk mengamankan informasi rahasia dengan cara membaginya ke dalam beberapa share sehingga tidak ada satu pihak pun yang menyimpan rahasia secara utuh. Keamanan skema ini ditentukan oleh parameter threshold yang mengatur jumlah minimum share yang diperlukan untuk merekonstruksi rahasia, sehingga mampu menyeimbangkan antara keamanan dan ketersediaan sistem. Dengan sifat keamanannya yang kuat dan kemampuannya menghilangkan single point of failure, Shamir’s Secret Sharing banyak diterapkan pada pengamanan kunci kriptografi dan sistem pemulihan akses di dunia nyata.

## 9. Daftar Pustaka

## 10. Commit Log
Author: Dimas Riyan Hidayat <dimasriyanhidayat01@gmail.com>
Date:   2026-1-6

    week11-seceretsharing: (Shamir’s Secret Sharing)
```
