# Laporan Praktikum Kriptografi
Minggu ke-: 2
Topik: crypto sistem 
Nama: Safira Dewi Rahmatika 
NIM: 230202784
Kelas: 5IKRB 

## 1. Tujuan
1. Mengidentifikasi komponen dasar kriptosistem (plaintext, ciphertext, kunci, algoritma).
2. Menggambarkan proses enkripsi dan dekripsi sederhana.
3. Mengklasifikasikan jenis kriptosistem (simetris dan asimetris).
   
## 2. Dasar Teori
Kriptosistem adalah sistem yang digunakan untuk mengamankan data atau pesan dengan cara menyandikan (enkripsi) dan mengembalikannya ke bentuk semula (dekripsi) menggunakan algoritma dan kunci tertentu.
Komponen dasar dari sebuah kriptosistem meliputi:
1. Plaintext (teks asli)
Pesan atau data yang belum dienkripsi. Ini adalah informasi yang ingin dilindungi.
2. Ciphertext (teks sandi)
Hasil dari proses enkripsi, yaitu bentuk pesan yang sudah disamarkan agar tidak bisa dibaca tanpa kunci.
3. Algoritma enkripsi
Prosedur atau aturan matematis yang digunakan untuk mengubah plaintext menjadi ciphertext.
Contoh: algoritma Caesar Cipher, AES, RSA, dsb.
4. Algoritma dekripsi
Prosedur yang digunakan untuk mengembalikan ciphertext menjadi plaintext.
5. Kunci (key)
Nilai rahasia yang digunakan dalam proses enkripsi dan dekripsi. Kunci ini sangat penting karena menjamin keamanan sistem. Contoh: pada Caesar Cipher, kuncinya bisa berupa pergeseran huruf sebanyak 3.

Enkripsi adalah proses mengubah pesan asli (plaintext) menjadi bentuk sandi (ciphertext) agar tidak bisa dibaca oleh orang lain.Dekripsi adalah proses mengembalikan ciphertext menjadi plaintext agar pesan bisa dibaca kembali.
Proses ini menggunakan algoritma dan kunci (key) tertentu.Dalam sistem simetris, kunci enkripsi dan dekripsi sama.
Dalam sistem asimetris, kunci enkripsi dan dekripsi berbeda (public key & private key).
Tujuan utamanya: menjaga kerahasiaan, keaslian, dan keamanan data.
Contoh sederhana: Pesan “HELLO” dienkripsi dengan pergeseran huruf 3 jadi “KHOOR”. Kemudian didekripsi kembali “HELLO”.

Kriptosistem dapat dibedakan berdasarkan jenis kunci dan cara pengolahan datanya. Berdasarkan jenis kuncinya, terdapat dua macam yaitu kriptosistem simetris dan kriptosistem asimetris. Kriptosistem simetris menggunakan satu kunci yang sama untuk proses enkripsi dan dekripsi, sehingga lebih cepat namun memiliki risiko jika kunci bocor. Contohnya yaitu AES, DES, dan Blowfish. Sementara itu, kriptosistem asimetris menggunakan dua kunci berbeda, yaitu kunci publik untuk enkripsi dan kunci privat untuk dekripsi. Sistem ini lebih aman tetapi prosesnya lebih lambat, dengan contoh seperti RSA, ECC, dan ElGamal.

Ringkasan Komponen Kriptosistem:
Kriptosistem terdiri dari empat komponen utama, yaitu plaintext, ciphertext, kunci, dan algoritma. Plaintext adalah pesan asli yang belum disandikan, sedangkan ciphertext merupakan hasil enkripsi yang tidak dapat dibaca. Kunci digunakan untuk mengontrol proses enkripsi dan dekripsi agar hanya pihak berwenang yang dapat membaca pesan. Algoritma adalah metode atau aturan yang digunakan untuk mengubah plaintext menjadi ciphertext dan sebaliknya.

Perbedaan Kriptosistem Simetris dan Asimetris:
Kriptosistem simetris menggunakan satu kunci yang sama untuk proses enkripsi dan dekripsi. Sistem ini cepat dan efisien, tetapi memiliki kelemahan dalam hal keamanan distribusi kunci. Sementara itu, kriptosistem asimetris menggunakan dua kunci berbeda, yaitu kunci publik untuk enkripsi dan kunci privat untuk dekripsi. Sistem ini lebih aman untuk pertukaran data, meskipun prosesnya lebih lambat dibandingkan sistem simetris.


## 3. Alat dan Bahan
- Visual Studio Code 
- Git dan akun GitHub
- Draw IO 

## 4. Langkah Percobaan
1. Membuat file caesar_cipher.py di folder praktikum/week2-cryptosystem/src/.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah python caesar_cipher.py
4. Membuat diagram kriptosistem di draw IO 
5. Membuat folder praktikum/week2-cryptosystem/ berisi laporan.md dan folder screenshots.
6. Menulis ringkasan materi singkat.
7. Menjawab quiz

## 5. Source Code



## 6. Hasil dan Pembahasan


## 7. Jawaban Pertanyaan
Soal
1. Sebutkan komponen utama dalam sebuah kriptosistem.
2. Apa kelebihan dan kelemahan sistem simetris dibandingkan asimetris?
3. Mengapa distribusi kunci menjadi masalah utama dalam kriptografi simetris?
   
Jawaban.
1. Komponen utama dalam sebuah kriptosistem:
Komponen dasar kriptosistem terdiri dari plaintext, ciphertext, kunci (key), dan algoritma (cipher). Plaintext adalah pesan asli yang masih bisa dibaca manusia, ciphertext merupakan hasil enkripsi yang tidak dapat dibaca, kunci berfungsi sebagai nilai rahasia yang digunakan dalam proses enkripsi dan dekripsi, sedangkan algoritma adalah langkah atau aturan matematis yang digunakan untuk mengubah plaintext menjadi ciphertext dan sebaliknya.
2. Kelebihan dan kelemahan sistem simetris dibandingkan asimetris:
Kriptosistem simetris memiliki kelebihan berupa proses enkripsi dan dekripsi yang lebih cepat dan efisien, karena hanya menggunakan satu kunci yang sama. Namun, kelemahannya terletak pada keamanan distribusi kunci, sebaika kunci tersebut bocor, semua pesan yang terenkripsi dapat terbaca. Sementara itu, sistem asimetris lebih aman dalam pertukaran kunci karena menggunakan pasangan kunci publik dan privat, tetapi prosesnya lebih lambat karena membutuhkan perhitungan yang lebih kompleks.
3. Mengapa distribusi kunci menjadi masalah utama dalam kriptografi simetris:
Distribusi kunci menjadi masalah utama karena pengirim dan penerima harus memiliki kunci yang sama, sehingga kunci tersebut harus dikirim melalui saluran komunikasi yang aman. Jika kunci tersebut dicegat atau diketahui pihak ketiga, maka seluruh sistem keamanan bisa terancam karena semua pesan yang terenkripsi dapat dengan mudah didekripsi oleh pihak yang tidak berwenang.

## 8. Kesimpulan


## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
commit week2
Author: Safira Dewi Rahmatika safiradewirahmatika26@gmail.com
    week2-cryptosystem: implementasi Caesar Cipher dan laporan 
