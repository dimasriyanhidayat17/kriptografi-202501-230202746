# Laporan Praktikum Kriptografi
Minggu ke-: X  
Topik: Public Key Infrastructure (PKI & Certificate Authority)  
Nama: Dimas Riyan Hidayat 
NIM: 230202746 
Kelas: 5IKRB  

## 1. Tujuan
1. Membuat sertifikat digital sederhana.
2. Menjelaskan peran Certificate Authority (CA) dalam sistem PKI.
3. Mengevaluasi fungsi PKI dalam komunikasi aman (contoh: HTTPS, TLS).

## 2. Dasar Teori
PKI pada dasarnya adalah mesin kepercayaan yang dibangun di atas kriptografi kunci publik. Sistem ini memanfaatkan pasangan kunci public key dan private key, lalu menambahkan struktur otoritas tepercaya (CA), sertifikat digital, dan proses validasi agar dua pihak bisa saling percaya walaupun tidak saling kenal. Inti kerjanya: memastikan identitas, menjaga kerahasiaan data, dan menjamin integritas komunikasi. PKI bekerja dengan konsep sertifikat digital yang mengikat public key dengan identitas pemiliknya, dan sertifikat itu diverifikasi menggunakan tanda tangan digital dari CA yang sudah dipercaya oleh browser atau OS. Karena itulah PKI jadi pondasi utama pada HTTPS/TLS, email terenkripsi, tanda tangan digital, dan banyak sistem otentikasi modern.

## 3. Alat dan Bahan
- Python 3.11  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (cryptography pyopenssl) 

## 4. Langkah Percobaan
1. Membuat file `pki.py` di folder `praktikum/week10-pki/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python pki.py`.)
4. mengerjakan quis

## 5. Source Code
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/be09d1ef-a3c0-4f3d-aa1e-0f69c2251766" />

## 6. Hasil dan Pembahasan
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/516aa8ba-706c-409d-a520-6c97cdcf915b" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c57f0990-c59c-49a1-8d52-d98e6504477b" />

2. A. Gunakan public key untuk memverifikasi tanda tangan sertifikat

Tanda tangan digital pada sertifikat X.509 dibuat menggunakan private key milik penerbit sertifikat, biasanya sebuah Certificate Authority (CA) atau self-signed certificate pada sistem sederhana. Untuk memastikan bahwa sertifikat tersebut asli dan tidak dimodifikasi, verifikasi dilakukan menggunakan public key dari penerbit. Prosesnya melibatkan pengecekan apakah tanda tangan digital cocok dengan data sertifikat yang belum ditandatangani (TBS certificate). Jika verifikasi menggunakan public key berhasil, berarti tanda tangan valid dan sertifikat tidak mengalami perubahan. Jika gagal, sertifikat dianggap tidak sah atau telah dimodifikasi. Dengan cara ini, public key penerbit berfungsi sebagai alat pembuktian integritas dan keaslian sertifikat.

B. Jelaskan bagaimana CA digunakan untuk menjamin keaslian sertifikat

Certificate Authority (CA) berperan sebagai pihak ketiga tepercaya yang memastikan bahwa sertifikat digital benar-benar mewakili identitas pemiliknya. CA terlebih dahulu memverifikasi identitas pemohon sertifikat, entah itu individu, organisasi, atau pemilik domain, melalui proses validasi yang resmi. Setelah identitas dipastikan benar, CA membuat sertifikat digital yang menggabungkan public key pemilik dengan identitas tersebut, lalu menandatanganinya menggunakan private key CA. Karena browser, sistem operasi, dan perangkat lunak modern memiliki daftar CA tepercaya, maka sertifikat apa pun yang ditandatangani oleh CA tersebut dapat diverifikasi dan diakui keasliannya. Dengan demikian, CA menjadi fondasi kepercayaan dalam komunikasi digital, memastikan publik dapat yakin bahwa public key yang digunakan benar-benar milik pihak yang sah.

3. A. Bagaimana browser memverifikasi sertifikat HTTPS?

Browser memeriksa sertifikat yang dikirim server, lalu memverifikasi tanda tangan digitalnya menggunakan public key CA yang ada dalam daftar trusted root. Browser juga mengecek apakah sertifikat cocok dengan domain, masih berlaku, dan tidak dicabut. Jika semua valid, koneksi dianggap aman dan terenkripsi.

B. Apa yang terjadi jika CA palsu menerbitkan sertifikat?

Sertifikat dari CA palsu langsung ditolak browser karena tidak ada dalam daftar CA tepercaya. Namun jika CA resmi diretas dan menerbitkan sertifikat ilegal, penyerang bisa menyamar sebagai situs asli dan melakukan serangan MITM—karena itu browser akan segera mencabut kepercayaan terhadap CA yang bermasalah.

C. Mengapa PKI penting dalam komunikasi aman?

PKI penting karena memastikan identitas server, menjaga integritas data, dan memungkinkan enkripsi yang aman. Dalam transaksi online, PKI menjamin bahwa pengguna terhubung ke situs resmi dan bahwa data sensitif (misalnya password dan informasi finansial) tidak bisa disadap atau diubah.


## 7. Jawaban Pertanyaan
1. Apa fungsi utama Certificate Authority (CA)?

Certificate Authority (CA) berfungsi sebagai pihak ketiga tepercaya yang memverifikasi identitas pemilik sertifikat dan kemudian menandatangani sertifikat digital mereka. Dengan adanya tanda tangan CA, browser dan sistem lain dapat yakin bahwa public key dalam sertifikat benar-benar milik pihak yang sah, sehingga identitas server atau organisasi dapat dibuktikan. CA menjadi fondasi kepercayaan dalam ekosistem keamanan internet.

2. Mengapa self-signed certificate tidak cukup untuk sistem produksi?

Self-signed certificate tidak diakui oleh browser atau perangkat pengguna karena tidak ada pihak ketiga tepercaya yang menjamin keasliannya. Akibatnya, koneksi akan dianggap tidak aman dan pengguna akan melihat peringatan “certificate not trusted.” Dalam lingkungan produksi, terutama untuk layanan publik seperti website, API, atau aplikasi online, sertifikat harus diterbitkan oleh CA resmi agar dipercaya otomatis dan tidak memicu peringatan keamanan.

3. Bagaimana PKI mencegah serangan MITM dalam komunikasi TLS/HTTPS?

PKI mencegah serangan Man-in-the-Middle dengan memastikan bahwa pengguna hanya bisa membangun koneksi terenkripsi dengan server yang memiliki sertifikat valid dari CA tepercaya. Browser memverifikasi tanda tangan digital sertifikat, memeriksa domain, dan memastikan sertifikat belum dicabut. Jika seorang penyerang mencoba menyisipkan server palsu atau memalsukan sertifikat, verifikasi akan gagal sehingga koneksi diblokir. Dengan begitu, PKI membuat MITM hampir tidak mungkin dilakukan jika sertifikat dan CA tidak diretas.
## 8. Kesimpulan
Singkatnya, PKI adalah fondasi kepercayaan di dunia digital. Dengan menggabungkan kriptografi kunci publik, sertifikat digital, dan otoritas tepercaya (CA), PKI memastikan bahwa identitas server valid, data tidak bisa diubah, dan komunikasi tetap aman dari penyadapan maupun manipulasi. Tanpa PKI, protokol seperti HTTPS atau transaksi online tidak akan punya jaminan keaslian maupun keamanan, sehingga risiko serangan—terutama MITM—jadi jauh lebih besar. PKI hadir untuk memastikan semua pihak bisa berkomunikasi dengan aman meskipun berada di jaringan yang tidak aman.

## 9. Daftar Pustaka

## 10. Commit Log
commit week10-pki
Author: Dimas Riyan Hidayat <dimasriyanhidayat01@gmail.com>
Date:   2025-12-12

