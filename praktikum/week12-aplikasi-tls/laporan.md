# Laporan Praktikum Kriptografi
Minggu ke-: XII
Topik: Aplikasi TLS & E-commerce 
Nama: Safira Dewi Rahmatika
NIM: 230202784 
Kelas: 5 IKRB

## 1. Tujuan
1. Menganalisis penerapan kriptografi pada sistem email serta protokol SSL/TLS.
2. Menjelaskan peran enkripsi dalam menjaga keamanan transaksi e-commerce.
3. Mengevaluasi aspek etika dan privasi dalam penggunaan kriptografi pada kehidupan sehari-hari.

## 2. Dasar Teori
Kriptografi berperan penting dalam menjaga keamanan komunikasi digital, termasuk pada sistem email dan protokol SSL/TLS. Pada sistem email, kriptografi digunakan untuk melindungi isi pesan agar hanya dapat dibaca oleh pihak yang berwenang melalui mekanisme enkripsi dan tanda tangan digital. Sementara itu, protokol SSL/TLS berfungsi untuk mengamankan pertukaran data antara klien dan server dengan mengenkripsi informasi yang dikirimkan, sehingga mencegah penyadapan dan manipulasi data selama proses komunikasi berlangsung.

Dalam transaksi e-commerce, enkripsi digunakan untuk melindungi data sensitif seperti informasi kartu pembayaran, identitas pengguna, dan detail transaksi. Dengan adanya enkripsi, data yang dikirimkan antara pembeli dan penjual menjadi aman dari akses pihak tidak berwenang, sehingga meningkatkan kepercayaan pengguna terhadap sistem e-commerce. Penerapan kriptografi ini memastikan integritas dan kerahasiaan data selama proses transaksi online.

Selain manfaatnya, penggunaan kriptografi juga menimbulkan isu etika dan privasi dalam kehidupan sehari-hari. Kriptografi dapat melindungi privasi individu, namun di sisi lain juga dapat disalahgunakan untuk menyembunyikan aktivitas ilegal. Oleh karena itu, diperlukan keseimbangan antara perlindungan privasi pengguna dan kepentingan keamanan publik agar penerapan kriptografi tetap memberikan manfaat tanpa melanggar nilai etika dan hukum yang berlaku.

## 3. Alat dan Bahan
- Python 3.14
- Visual Studio Code  
- Git dan akun GitHub  

## 4. Langkah Percobaan
1. Laporan studi kasus tentang penerapan SSL/TLS pada email dan e-commerce.
2. Analisis isu privasi dan etika penggunaan kriptografi.

## 5. Source Code
## 6. Hasil dan Pembahasan
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/02e40f78-e3cb-4da3-8497-13383147d3ac" />

1. Analisis SSL/TLS Website E-commerce (Shopee)
Website Shopee telah menggunakan protokol HTTPS yang menandakan penerapan SSL/TLS untuk mengamankan komunikasi data antara pengguna dan server. Hal ini dibuktikan dengan adanya ikon gembok pada browser serta sertifikat digital yang diterbitkan oleh Certificate Authority (CA) tepercaya. SSL/TLS memastikan data seperti login akun, alamat, dan transaksi tidak dapat disadap atau dimodifikasi oleh pihak tidak berwenang.

2. Studi Kasus Penggunaan Enkripsi pada E-commerce
Dalam sistem e-commerce, enkripsi berperan penting saat proses login, pemesanan, dan pembayaran. Data sensitif pengguna dienkripsi sebelum dikirimkan melalui jaringan sehingga tetap aman meskipun terjadi penyadapan. Tanpa enkripsi TLS, transaksi berisiko terkena serangan seperti Man-in-the-Middle yang dapat mencuri informasi penting pengguna.

3. Analisis Etika & Privasi
Penggunaan kriptografi meningkatkan keamanan data pengguna, namun juga menimbulkan isu etika dan privasi. Perusahaan harus menjaga transparansi dalam pengelolaan data dan tidak menyalahgunakan akses terhadap informasi pribadi pengguna. Selain itu, pengawasan komunikasi terenkripsi oleh pihak tertentu perlu diatur secara etis agar tidak melanggar hak privasi pengguna.

## 7. Jawaban Pertanyaan
1. Apa perbedaan utama antara HTTP dan HTTPS?
HTTP tidak menggunakan enkripsi sehingga data yang dikirim dapat disadap atau dimodifikasi oleh pihak lain. HTTPS menggunakan SSL/TLS untuk mengenkripsi data, sehingga komunikasi antara pengguna dan server menjadi aman dan terlindungi.

2. Mengapa sertifikat digital menjadi penting dalam komunikasi TLS?
Sertifikat digital berfungsi untuk memverifikasi identitas server dan memastikan bahwa pengguna benar-benar terhubung ke server yang sah. Sertifikat ini juga digunakan untuk membangun koneksi terenkripsi yang aman antara klien dan server.

3. Bagaimana kriptografi mendukung privasi tetapi menimbulkan tantangan hukum dan etika?
Kriptografi melindungi privasi dengan mengenkripsi data agar tidak dapat diakses oleh pihak tidak berwenang. Namun, enkripsi juga menimbulkan tantangan hukum dan etika karena dapat menghambat proses pengawasan atau penegakan hukum, sehingga diperlukan keseimbangan antara keamanan, privasi, dan kepentingan publik.

## 8. Kesimpulan
Berdasarkan hasil analisis pada website Shopee, dapat disimpulkan bahwa Shopee telah menerapkan protokol HTTPS dengan SSL/TLS secara baik untuk mengamankan komunikasi antara pengguna dan server. Hal ini ditunjukkan dengan adanya ikon gembok pada address bar serta informasi sertifikat digital yang valid dan dikeluarkan oleh Certificate Authority (CA) terpercaya. Penerapan enkripsi ini melindungi data sensitif pengguna, seperti informasi login dan transaksi pembayaran, dari ancaman penyadapan dan serangan pihak tidak berwenang, sehingga meningkatkan keamanan dan kepercayaan pengguna dalam melakukan transaksi e-commerce.

Berdasarkan hasil pengamatan dan pembahasan, dapat disimpulkan bahwa penggunaan SSL/TLS dan kriptografi sangat penting dalam menjaga keamanan dan kerahasiaan data pada komunikasi digital, khususnya pada email dan transaksi e-commerce. HTTPS dengan dukungan sertifikat digital mampu melindungi data pengguna dari ancaman penyadapan dan manipulasi, sehingga meningkatkan kepercayaan pengguna. Namun, di balik manfaat tersebut, penerapan kriptografi juga menimbulkan tantangan etika dan hukum terkait privasi, pengawasan, serta akses data oleh pihak berwenang. Oleh karena itu, diperlukan penerapan kebijakan yang seimbang agar keamanan data tetap terjaga tanpa mengabaikan aspek hukum dan etika.

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
Author: safira dewi rahmatika safiraa1026@gmail.com
Date: 2026-01-12
week12-apliaksi-tls: implementasi Aplikasi TLS & E-commerce shopee.
   
