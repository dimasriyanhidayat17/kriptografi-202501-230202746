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
Dalam kriptografi, **entropy** merupakan ukuran tingkat keacakan atau ketidakpastian dari suatu kunci yang digunakan dalam proses enkripsi. Semakin tinggi nilai entropi, semakin besar ruang kemungkinan kunci yang tersedia, sehingga semakin sulit bagi penyerang untuk menebaknya melalui brute force. Nilai entropi yang tinggi menunjukkan bahwa kunci sulit diprediksi dan memiliki keamanan yang lebih baik karena peluang untuk menebak kunci secara benar menjadi sangat kecil. Oleh karena itu, entropi menjadi indikator penting dalam menentukan kekuatan dan keandalan suatu sistem kriptografi.

**Unicity distance** merupakan jumlah minimal ciphertext yang dibutuhkan agar kunci enkripsi dapat ditentukan secara unik melalui analisis kriptografi. Konsep ini diperkenalkan oleh Claude Shannon dan berfungsi untuk mengukur seberapa banyak data terenkripsi yang diperlukan agar cipher dapat diretas secara pasti. Nilai unicity distance bergantung pada entropi kunci dan tingkat redundansi dari plaintext. Jika ciphertext yang diperoleh lebih sedikit dari nilai unicity distance, maka kriptanalis tidak dapat memastikan kunci yang benar, sehingga cipher masih tergolong aman. Dengan demikian, semakin besar nilai unicity distance, semakin tinggi tingkat keamanan sistem enkripsi tersebut.

Meskipun algoritma modern seperti AES, RSA, dan ECC memiliki struktur matematis yang sangat kuat, **brute force** tetap menjadi ancaman nyata dalam dunia keamanan data. Ancaman ini tidak semata-mata berasal dari lemahnya algoritma, tetapi dari faktor eksternal seperti penggunaan kunci yang lemah, kesalahan implementasi, serta kemajuan teknologi komputasi yang memungkinkan proses pencarian kunci dilakukan lebih cepat. Perkembangan perangkat keras seperti GPU dan potensi komputer kuantum juga dapat mempercepat serangan brute force. Oleh karena itu, keamanan sistem kriptografi tidak hanya ditentukan oleh kekuatan algoritma, tetapi juga oleh pengelolaan kunci yang tepat dan penerapan sistem keamanan yang menyeluruh.


## 3. Alat dan Bahan 
- Python 3.11
- Git dan akun GitHub

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `entropy.py` di folder `praktikum/week4-cryptosystem/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `entropy.py`.)
4. menjawab pertanyaan yang ada di panduan
5. melengkapi laporan

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
Berdasarkan pembahasan tersebut, dapat disimpulkan bahwa keamanan suatu sistem kriptografi tidak hanya bergantung pada kekuatan algoritma yang digunakan, tetapi juga pada tingkat keacakan kunci, panjang kunci, serta cara pengelolaannya. Nilai **entropy** yang tinggi memastikan kunci sulit ditebak, sedangkan **unicity distance** menunjukkan batas jumlah ciphertext yang masih aman sebelum kunci dapat diprediksi secara pasti. Meskipun algoritma modern telah dirancang dengan keamanan yang kuat, **serangan brute force** tetap menjadi ancaman apabila kunci yang digunakan lemah atau sistem tidak diterapkan dengan benar. Oleh karena itu, dalam menjaga keamanan data, diperlukan penerapan prinsip kriptografi yang baik, penggunaan kunci yang memiliki entropi tinggi, serta pengelolaan dan perlindungan kunci yang cermat untuk mencegah potensi kebocoran informasi.


## 9. Daftar Pustaka

## 10. Commit Log
commit abc12345
Author: Dimas Riyan Hidayat <dimasriyanhidayat01@gmail.com>
Date:   2025-11-1

    week4-entropy-unicity: implementasi Caesar Cipher dan laporan )
```
