# Laporan Praktikum Kriptografi
Minggu ke-: X  
Topik: Public Key Infrastructure  
Nama: Safira Dewi Rahmatika  
NIM: 230202784  
Kelas: 5IKRB  

## 1. Tujuan
1. Membuat sertifikat digital sederhana.
2. Menjelaskan peran Certificate Authority (CA) dalam sistem PKI.
3. Mengevaluasi fungsi PKI dalam komunikasi aman (contoh: HTTPS, TLS).
   
## 2. Dasar Teori
Certificate Authority (CA) merupakan komponen utama dalam sistem keamanan berbasis kriptografi kunci publik. CA berperan sebagai pihak tepercaya yang bertugas memverifikasi identitas individu atau organisasi sebelum menerbitkan sertifikat digital. Sertifikat ini berfungsi untuk mengikat identitas pemilik dengan kunci publik tertentu dan ditandatangani secara digital oleh CA, sehingga pihak lain dapat mempercayai keaslian kunci publik tersebut.

Self-signed certificate adalah sertifikat yang ditandatangani oleh pemiliknya sendiri tanpa keterlibatan CA. Meskipun dapat digunakan untuk keperluan pengujian atau lingkungan internal, sertifikat ini tidak memberikan jaminan kepercayaan dalam sistem produksi karena tidak ada pihak ketiga yang memverifikasi identitas pemiliknya. Akibatnya, browser dan klien akan menampilkan peringatan keamanan karena tidak dapat memastikan keaslian server.

Public Key Infrastructure (PKI) menyediakan kerangka kerja untuk mengelola sertifikat digital, termasuk penerbitan, distribusi, dan verifikasi sertifikat. Dalam komunikasi TLS/HTTPS, PKI mencegah serangan Man-in-the-Middle (MITM) dengan memastikan bahwa sertifikat server diverifikasi menggunakan rantai kepercayaan hingga CA yang tepercaya. Dengan mekanisme ini, klien dapat memastikan bahwa koneksi aman dan data yang ditransmisikan tidak dapat disadap atau dimanipulasi oleh pihak yang tidak berwenang.

## 3. Alat dan Bahan
- Python 3.11  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (cryptography pyopenssl)
  
## 4. Langkah Percobaan
1. Membuat file `pki.py` di folder `praktikum/week10-pki/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.
4. mengarjakan quis

## 5. Source Code
<img width="1621" height="934" alt="Screenshot 2025-12-12 222639" src="https://github.com/user-attachments/assets/ce1bba1c-d7ee-4182-8ca6-0604fb189f7a" />

## 6. Hasil dan Pembahasan
<img width="1607" height="704" alt="Screenshot 2025-12-12 222700" src="https://github.com/user-attachments/assets/55025446-4d8b-470e-91e3-2dd2a1f64bf3" />
<img width="1919" height="1021" alt="image" src="https://github.com/user-attachments/assets/12f840a6-2095-49a9-aaa5-cbed2f5420cb" />
2. Pada langkah ini dilakukan verifikasi tanda tangan digital sertifikat menggunakan public key. Tujuan verifikasi adalah untuk memastikan bahwa sertifikat benar-benar ditandatangani oleh pihak yang menerbitkannya dan tidak mengalami perubahan sejak dibuat. Karena sertifikat yang digunakan bersifat self-signed, maka public key yang dipakai untuk verifikasi berasal dari sertifikat itu sendiri.

Proses verifikasi dilakukan dengan mencocokkan tanda tangan digital sertifikat menggunakan algoritma kriptografi dan fungsi hash yang sesuai (misalnya SHA-256). Jika verifikasi berhasil, maka integritas sertifikat terjamin dan sertifikat dianggap valid. Sebaliknya, jika isi sertifikat telah dimodifikasi atau tanda tangan tidak sesuai, proses verifikasi akan gagal sehingga sertifikat dinyatakan tidak sah.
3. 1. Bagaimana browser memverifikasi sertifikat HTTPS?
Browser memverifikasi sertifikat HTTPS dengan memeriksa tanda tangan digital pada sertifikat menggunakan public key milik Certificate Authority (CA) yang sudah tersimpan di dalam trust store browser. Browser juga mengecek masa berlaku sertifikat, kecocokan nama domain, serta memastikan sertifikat tidak dicabut. Jika seluruh pemeriksaan valid, koneksi HTTPS dianggap aman dan dapat dipercaya.

2. Apa yang terjadi jika CA palsu menerbitkan sertifikat?
Jika CA palsu berhasil menerbitkan sertifikat dan sertifikat tersebut dipercaya oleh sistem atau browser, maka penyerang dapat menyamar sebagai server yang sah. Hal ini memungkinkan terjadinya serangan Man-in-the-Middle (MITM), di mana penyerang dapat menyadap atau memodifikasi data tanpa diketahui pengguna. Namun, jika CA tersebut tidak dipercaya oleh browser, sertifikat akan ditolak dan pengguna akan mendapat peringatan keamanan.

3. Mengapa PKI penting dalam komunikasi aman (misalnya transaksi online)?
Public Key Infrastructure (PKI) penting karena menyediakan mekanisme untuk memverifikasi identitas pihak yang berkomunikasi melalui sertifikat digital. Dengan PKI, pengguna dapat memastikan bahwa mereka benar-benar terhubung ke pihak yang sah, sehingga data yang dikirim seperti informasi login atau transaksi keuangan terlindungi dari penyadapan, pemalsuan identitas, dan serangan Man-in-the-Middle (MITM).

## 7. Jawaban Pertanyaan
1. Apa fungsi utama Certificate Authority (CA)?
Certificate Authority (CA) berfungsi sebagai pihak tepercaya yang memverifikasi identitas pemilik sertifikat digital dan menerbitkan sertifikat yang mengikat identitas tersebut dengan kunci publik. Dengan tanda tangan digital dari CA, pihak lain dapat mempercayai bahwa kunci publik benar-benar milik entitas yang sah.

2. Mengapa self-signed certificate tidak cukup untuk sistem produksi?
Self-signed certificate tidak cukup untuk sistem produksi karena tidak melibatkan pihak tepercaya yang memverifikasi identitas pemilik sertifikat. Akibatnya, sertifikat jenis ini tidak dipercaya oleh browser atau sistem klien secara default dan rentan terhadap serangan pemalsuan identitas, sehingga kurang aman untuk komunikasi publik.

3. Bagaimana PKI mencegah serangan MITM dalam komunikasi TLS/HTTPS?
PKI mencegah serangan Man-in-the-Middle (MITM) dengan memastikan keaslian identitas server melalui sertifikat digital yang ditandatangani oleh CA tepercaya. Browser memverifikasi sertifikat tersebut sebelum membangun koneksi TLS, sehingga penyerang tidak dapat menyamar sebagai server yang sah tanpa memiliki sertifikat valid dari CA.
## 8. Kesimpulan
Certificate Authority (CA) memiliki peran penting sebagai pihak tepercaya yang menjamin keaslian identitas pemilik sertifikat digital melalui sistem PKI. Self-signed certificate tidak cukup digunakan pada sistem produksi karena tidak memberikan jaminan kepercayaan dan rentan terhadap pemalsuan identitas. Dengan adanya PKI, komunikasi TLS/HTTPS dapat berlangsung secara aman karena sertifikat diverifikasi melalui rantai kepercayaan, sehingga serangan Man-in-the-Middle (MITM) dapat dicegah dan keamanan data, terutama pada transaksi online, dapat terjaga.

## 9. Daftar Pustaka

## 10. Commit Log

commit week10-pki
Author: Safira Dewi Rahmatika <Safiraa1026@gmail.com>
Date:   2025-12-14

