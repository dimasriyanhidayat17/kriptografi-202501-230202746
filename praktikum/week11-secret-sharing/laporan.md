# Laporan Praktikum Kriptografi
Minggu ke-: XI
Topik: Shamir Secret Sharing (SSS). 
Nama: Safira Dewi Rahmatika 
NIM: 230202784  
Kelas: 5IKRB

## 1. Tujuan
1. Menjelaskan konsep Shamir Secret Sharing (SSS).
2. Melakukan simulasi pembagian rahasia ke beberapa pihak menggunakan skema SSS.
3. Menganalisis keamanan skema distribusi rahasia

## 2. Dasar Teori
Shamir Secret Sharing (SSS) merupakan salah satu skema kriptografi yang digunakan untuk membagi sebuah rahasia menjadi beberapa bagian (share) dan mendistribusikannya kepada sejumlah pihak. Prinsip utama dari SSS adalah penggunaan polinomial matematika, di mana nilai rahasia disimpan sebagai konstanta dari sebuah polinomial berderajat tertentu. Setiap pihak menerima satu nilai hasil perhitungan polinomial tersebut, sehingga tidak ada satu pihak pun yang dapat mengetahui rahasia secara utuh tanpa bekerja sama dengan pihak lain. Rahasia hanya dapat direkonstruksi kembali apabila jumlah share yang digabungkan telah memenuhi ambang batas minimum yang telah ditentukan sebelumnya.

Dalam prosesnya, SSS melakukan pembangkitan polinomial secara acak untuk menjaga kerahasiaan, kemudian membagikan hasilnya sebagai share kepada masing-masing pihak. Pada tahap rekonstruksi, beberapa pihak yang memenuhi ambang batas dapat menggunakan metode interpolasi, seperti interpolasi Lagrange, untuk memperoleh kembali polinomial awal dan menemukan rahasia yang tersimpan di dalamnya. Dari sisi keamanan, skema ini memiliki keunggulan karena bersifat sangat aman secara teoritis, di mana pihak yang memiliki jumlah share di bawah ambang batas tidak memperoleh informasi apa pun tentang rahasia. Oleh karena itu, Shamir Secret Sharing banyak digunakan dalam sistem terdistribusi, manajemen kunci kriptografi, serta aplikasi keamanan data yang membutuhkan perlindungan tinggi terhadap kebocoran informasi.

## 3. Alat dan Bahan
- Python 3.x  
- Visual Studio Code
- Git dan akun GitHub  

## 4. Langkah Percobaan
1. Menginstal library secretsharing menggunakan pip install secretsharing.
2. Mengimplementasikan Shamir Secret Sharing dengan Python.
3. Melakukan simulasi manual menggunakan polinomial modulo bilangan prima.
4. Menganalisis keamanan skema Shamir Secret Sharing.
5. Menjawab pertanyaan diskusi.
6. Menyelesaikan penulisan laporan laporan.md.

## 5. Source Code
<img width="793" height="772" alt="image" src="https://github.com/user-attachments/assets/74f6202c-1538-4fee-81b1-bc7e5fdb8c77" />


## 6. Hasil dan Pembahasan
<img width="454" height="177" alt="image" src="https://github.com/user-attachments/assets/73a8450f-2c23-4fac-a6d3-e48d459b3fe7" />

Hasil pengujian menunjukkan bahwa rahasia berhasil dibagi menjadi beberapa share dengan nilai yang berbeda pada setiap eksekusi program karena penggunaan koefisien polinomial acak, namun proses rekonstruksi selalu menghasilkan nilai rahasia yang sama ketika jumlah share yang digunakan memenuhi nilai threshold, sehingga membuktikan bahwa implementasi Shamir Secret Sharing berjalan sesuai dengan konsep dan teori yang berlaku.

## 7. Jawaban Pertanyaan
JAWABAN 
1. Keuntungan utama Shamir Secret Sharing dibanding membagikan salinan kunci secara langsung
Keuntungan utama Shamir Secret Sharing (SSS) adalah keamanannya yang lebih tinggi. Dalam pembagian kunci secara langsung, setiap pihak memegang salinan kunci yang sama, sehingga jika satu kunci bocor atau hilang, seluruh sistem menjadi tidak aman. Pada SSS, tidak ada pihak yang memegang rahasia secara utuh. Setiap pihak hanya memiliki sebagian rahasia (share) yang tidak bermakna jika berdiri sendiri, sehingga kebocoran satu atau beberapa share tidak langsung mengungkapkan rahasia utama.

2. Peran threshold (k) dalam keamanan secret sharing
Threshold (k) berfungsi sebagai batas minimum jumlah share yang harus dikumpulkan untuk merekonstruksi rahasia. Nilai k menentukan tingkat keamanan sistem, karena pihak yang memiliki share kurang dari k tidak akan memperoleh informasi apa pun tentang rahasia. Semakin besar nilai k, semakin tinggi tingkat keamanan, namun semakin banyak pula pihak yang harus bekerja sama untuk membuka rahasia tersebut.

3. Contoh skenario nyata penggunaan Shamir Secret Sharing
Salah satu contoh penggunaan SSS adalah dalam pengelolaan kunci enkripsi pada sistem perbankan atau pusat data. Kunci utama server tidak disimpan oleh satu orang saja, melainkan dibagi ke beberapa administrator. Kunci hanya dapat digunakan jika sejumlah administrator tertentu hadir dan menggabungkan share mereka, sehingga mencegah penyalahgunaan kunci oleh satu pihak dan meningkatkan keamanan sistem secara keseluruhan.

## 8. Kesimpulan
Berdasarkan praktikum yang telah dilakukan, dapat disimpulkan bahwa Shamir Secret Sharing berhasil diimplementasikan dengan baik menggunakan Python. Rahasia dapat dibagi ke dalam beberapa share dan hanya dapat direkonstruksi kembali apabila jumlah share yang digunakan memenuhi nilai threshold yang telah ditentukan. Hasil percobaan menunjukkan bahwa skema ini mampu menjaga keamanan rahasia meskipun sebagian share diketahui, sehingga Shamir Secret Sharing efektif digunakan untuk distribusi dan pengelolaan rahasia secara aman.

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
Author:safira dewi rahmatika safiraa1026@gmail.com
Date:   2025-12-31

    week11-Shamir Secret Sharing (SSS): 
