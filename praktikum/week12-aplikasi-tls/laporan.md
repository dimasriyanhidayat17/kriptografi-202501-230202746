# Laporan Praktikum Kriptografi
Minggu ke-: XII
Topik: Aplikasi TLS & E-commerce 
Nama: Dimas Riyan Hidayat  
NIM: 230202746  
Kelas: 5IKRB 


## 1. Tujuan
1. Menganalisis penggunaan kriptografi pada email dan SSL/TLS.
2. Menjelaskan enkripsi dalam transaksi e-commerce.
3. Mengevaluasi isu etika & privasi dalam penggunaan kriptografi di kehidupan sehari-hari.

## 2. Dasar Teori
Komunikasi digital pada jaringan internet umumnya menggunakan protokol HTTP (Hypertext Transfer Protocol) untuk pertukaran data antara klien dan server. Namun, HTTP tidak menyediakan mekanisme keamanan sehingga data yang dikirimkan dapat dibaca atau dimodifikasi oleh pihak lain. Untuk mengatasi kelemahan tersebut, dikembangkan HTTPS (Hypertext Transfer Protocol Secure), yaitu HTTP yang dilengkapi dengan protokol keamanan TLS (Transport Layer Security) guna melindungi data selama proses transmisi.

TLS bekerja dengan menerapkan kriptografi untuk menjamin tiga aspek utama keamanan komunikasi, yaitu kerahasiaan, integritas, dan autentikasi. Kerahasiaan dicapai melalui enkripsi data menggunakan algoritma kriptografi simetris, sedangkan autentikasi server dilakukan menggunakan sertifikat digital yang diterbitkan oleh Certificate Authority (CA) tepercaya. Sertifikat digital berfungsi untuk memverifikasi identitas server dan memastikan bahwa kunci publik yang digunakan benar-benar milik pihak yang sah, sehingga mencegah serangan penyamaran.

Kriptografi berperan penting dalam menjaga privasi komunikasi digital dengan memastikan bahwa hanya pihak yang berwenang yang dapat mengakses isi pesan. Meskipun demikian, penggunaan enkripsi juga menimbulkan tantangan hukum dan etika, terutama terkait pengawasan, penegakan hukum, dan kepentingan keamanan nasional. Oleh karena itu, penerapan kriptografi harus disertai dengan kebijakan dan regulasi yang jelas agar perlindungan privasi individu tetap seimbang dengan kebutuhan keamanan dan kepatuhan hukum.

## 3. Alat dan Bahan
- Python 3.11 
- Visual Studio Code 
- Git dan akun GitHub  

## 4. Langkah Percobaan
Langkah 1 — Analisis SSL/TLS pada Email & Web
Langkah 2 — Studi Kasus E-commerce
Langkah 3 — Analisis Etika & Privasi

## 5. Source Code

## 6. Hasil dan Pembahasan
langkah 1
Analisis SSL/TLS pada website e-commerce dapat dilakukan menggunakan browser seperti Chrome atau Firefox dengan memeriksa sertifikat digital melalui ikon gembok pada address bar. Pada website e-commerce seperti Tokopedia, Shopee, dan Bukalapak, sertifikat SSL/TLS umumnya diterbitkan oleh Certificate Authority (CA) tepercaya dengan masa berlaku tertentu dan diperbarui secara berkala. Algoritma enkripsi yang digunakan biasanya berupa kombinasi RSA atau ECDSA untuk pertukaran kunci dan AES untuk enkripsi data selama proses komunikasi.

Perbedaan utama antara website yang menggunakan HTTPS dan yang tidak menggunakan HTTPS terletak pada tingkat keamanannya. Website HTTPS mengenkripsi data yang dikirim antara pengguna dan server sehingga melindungi informasi dari penyadapan dan serangan man-in-the-middle. Sebaliknya, website tanpa HTTPS mengirimkan data dalam bentuk teks biasa sehingga rentan disadap dan umumnya ditandai tidak aman oleh browser, yang dapat menurunkan tingkat kepercayaan pengguna.

langkah 2
Pada sistem e-commerce, enkripsi digunakan untuk melindungi transaksi online seperti proses login dan pembayaran dengan memanfaatkan protokol TLS. Saat pengguna memasukkan data sensitif seperti username, password, atau informasi pembayaran, data tersebut dienkripsi sebelum dikirim ke server sehingga tidak dapat dibaca oleh pihak lain selama proses transmisi. TLS juga memastikan keaslian server melalui sertifikat digital serta menjaga integritas data agar tidak dapat diubah selama perjalanan dari pengguna ke server.

Apabila TLS tidak digunakan, transaksi online menjadi sangat rentan terhadap berbagai ancaman keamanan. Salah satu ancaman utama adalah serangan Man-in-the-Middle, di mana penyerang dapat menyadap, memodifikasi, atau mencuri data yang dikirimkan antara pengguna dan server. Tanpa enkripsi, informasi sensitif seperti kredensial login dan data pembayaran dapat bocor, yang berpotensi menyebabkan pencurian akun, penipuan finansial, dan hilangnya kepercayaan pengguna terhadap platform e-commerce.

langkah 3
Penggunaan email terenkripsi seperti PGP dan S/MIME menimbulkan isu privasi karena hanya pengirim dan penerima yang dapat membaca isi pesan. Di satu sisi, enkripsi melindungi kerahasiaan komunikasi dari penyadapan dan kebocoran data, namun di sisi lain dapat menyulitkan organisasi dalam melakukan pemantauan keamanan, audit internal, atau investigasi insiden. Hal ini menimbulkan tantangan dalam menyeimbangkan hak privasi individu dengan kebutuhan pengawasan keamanan.

Dilema etika muncul ketika perusahaan ingin melakukan dekripsi email karyawan untuk kepentingan audit atau kepatuhan. Dari sudut pandang keamanan organisasi, dekripsi dapat dibenarkan untuk mencegah kebocoran data, penipuan, atau pelanggaran kebijakan internal. Namun, dari sisi etika dan privasi, tindakan tersebut berpotensi melanggar hak pribadi karyawan jika dilakukan tanpa persetujuan yang jelas, transparansi, dan batasan yang tegas.

Dalam konteks kebijakan pemerintah, pengawasan terhadap komunikasi terenkripsi juga menjadi perdebatan etis. Pemerintah memiliki kepentingan dalam menjaga keamanan nasional dan mencegah kejahatan siber, tetapi pengawasan berlebihan dapat mengancam kebebasan berekspresi dan hak privasi warga negara. Oleh karena itu, kebijakan pengawasan komunikasi terenkripsi seharusnya diatur secara ketat melalui hukum yang jelas, mekanisme pengawasan independen, dan prinsip proporsionalitas agar tidak disalahgunakan.

## 7. Jawaban Pertanyaan
Apa perbedaan utama antara HTTP dan HTTPS?
Perbedaan utama antara HTTP dan HTTPS terletak pada aspek keamanannya. HTTP mengirimkan data dalam bentuk teks biasa sehingga mudah disadap atau dimodifikasi oleh pihak tidak berwenang. Sementara itu, HTTPS menggunakan protokol TLS untuk mengenkripsi data yang dikirim antara pengguna dan server, sehingga menjaga kerahasiaan, integritas, dan keaslian komunikasi.

Mengapa sertifikat digital menjadi penting dalam komunikasi TLS?
Sertifikat digital berperan penting dalam komunikasi TLS karena digunakan untuk memverifikasi identitas server dan mencegah pengguna terhubung ke server palsu. Sertifikat yang diterbitkan oleh Certificate Authority (CA) tepercaya memastikan bahwa kunci publik yang digunakan dalam proses enkripsi benar-benar milik pihak yang sah, sehingga komunikasi dapat berlangsung secara aman dan terpercaya.

Bagaimana kriptografi mendukung privasi dalam komunikasi digital, tetapi sekaligus menimbulkan tantangan hukum dan etika?
Kriptografi mendukung privasi dengan mengenkripsi data sehingga hanya pihak yang berwenang yang dapat mengakses isi komunikasi. Namun, di sisi lain, enkripsi juga menimbulkan tantangan hukum dan etika karena dapat menghambat proses pengawasan, penegakan hukum, dan investigasi kejahatan. Kondisi ini menuntut adanya keseimbangan antara perlindungan privasi individu dan kepentingan keamanan serta hukum yang diatur secara jelas dan proporsional.

## 8. Kesimpulan


## 9. Daftar Pustaka


## 10. Commit Log
week12-aplikasi-tls
Author: Dimas Riyan Hidayat <dimasriyanhidayat01@gmail.com>
Date:   2026-1-6

 
