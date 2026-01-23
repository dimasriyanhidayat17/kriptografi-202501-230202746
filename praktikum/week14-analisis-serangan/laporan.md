# Laporan Praktikum Kriptografi
Minggu ke-: 14  
Topik: Analisis Serangan
Nama: Dimas Riyan Hidayat 
NIM: 230202746 
Kelas: 5IKRB

## 1. Tujuan
1. Mengidentifikasi jenis serangan pada sistem informasi nyata.
2. Mengevaluasi kelemahan algoritma kriptografi yang digunakan.
3. Memberikan rekomendasi algoritma kriptografi yang sesuai untuk perbaikan keamanan.
   
## 2. Dasar Teori
Banyak sistem informasi lama masih rentan terhadap serangan brute force dan dictionary attack karena sistem tersebut dibangun menggunakan standar keamanan yang sudah tidak sesuai dengan perkembangan teknologi saat ini. Umumnya, sistem lama masih menggunakan algoritma hash yang sudah usang seperti MD5 yang memiliki kecepatan komputasi sangat tinggi, sehingga memungkinkan penyerang mencoba banyak kombinasi password dalam waktu singkat. Selain itu, sistem tersebut sering kali tidak menerapkan mekanisme keamanan tambahan seperti salt, pembatasan percobaan login (rate limiting), maupun kebijakan password yang kuat. Kurangnya pembaruan sistem dan minimnya kesadaran akan ancaman keamanan modern menyebabkan kerentanan ini terus berlanjut.

Perbedaan antara kelemahan algoritma dan kelemahan implementasi terletak pada sumber masalah keamanannya. Kelemahan algoritma berasal dari desain kriptografi itu sendiri, seperti pada MD5 yang telah terbukti memiliki kerentanan collision dan tidak lagi aman digunakan untuk perlindungan password. Sementara itu, kelemahan implementasi muncul akibat penerapan algoritma yang tidak tepat, misalnya tidak menggunakan salt, konfigurasi sistem yang lemah, atau tidak adanya mekanisme pengamanan tambahan. Dengan demikian, algoritma yang secara teoritis aman pun dapat menjadi tidak efektif apabila diimplementasikan dengan cara yang salah.

Untuk memastikan sistem kriptografi tetap aman di masa depan, organisasi perlu menerapkan algoritma yang mengikuti standar keamanan terbaru serta melakukan pembaruan sistem secara berkala. Penggunaan algoritma hash khusus untuk password seperti bcrypt atau Argon2, dikombinasikan dengan penerapan salt unik, autentikasi multi-faktor, dan audit keamanan rutin, dapat meningkatkan ketahanan sistem terhadap serangan modern. Selain itu, organisasi perlu terus memantau perkembangan ancaman keamanan dan mengikuti rekomendasi dari komunitas serta lembaga standar keamanan agar sistem tetap adaptif dan terlindungi.

## 3. Alat dan Bahan
- Python 3.11  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  

## 4. Langkah Percobaan
1. Identifikasi Serangan
Kasus yang dianalisis adalah serangan brute force dan dictionary attack terhadap sistem informasi lama, seperti sistem akademik atau situs web generasi awal, yang masih menyimpan kata sandi pengguna menggunakan algoritma hash MD5. Sistem semacam ini umumnya belum menerapkan standar keamanan modern sehingga rentan terhadap eksploitasi.
Vektor serangan terjadi ketika penyerang berhasil memperoleh basis data pengguna yang berisi hash password MD5 akibat kebocoran data atau celah keamanan pada sistem. Hash tersebut kemudian dianalisis menggunakan rainbow table atau dilakukan pencocokan secara brute force untuk menemukan kata sandi asli yang sesuai dengan nilai hash yang diperoleh.
Penyebab utama kelemahan keamanan terletak pada penggunaan MD5 yang memang tidak dirancang untuk penyimpanan password. Selain itu, sistem tidak menerapkan mekanisme salt pada proses hashing, sehingga hash yang sama dapat digunakan kembali untuk menyerang banyak akun. Ketiadaan pembatasan percobaan login (rate limiting) juga memperbesar peluang keberhasilan serangan secara signifikan.

2. Evaluasi Kelemahan
Dari sisi algoritma, MD5 memiliki kelemahan kriptografis yang serius. Algoritma ini bekerja sangat cepat dan telah diketahui rentan terhadap serangan collision, sehingga memungkinkan penyerang melakukan jutaan hingga miliaran percobaan hash dalam waktu singkat menggunakan perangkat keras modern seperti GPU.
Kelemahan dalam kasus ini tidak hanya berasal dari algoritma yang sudah usang, tetapi juga dari aspek implementasi dan konfigurasi sistem. Tidak digunakannya salt, tidak adanya pembatasan percobaan login, serta ketiadaan kebijakan password yang kuat menyebabkan perlindungan yang diberikan oleh sistem menjadi sangat minim. Akibatnya, meskipun password disimpan dalam bentuk hash, tingkat keamanannya tetap rendah dan mudah ditembus.

3. Rekomendasi Solusi
Untuk meningkatkan keamanan sistem, penggunaan MD5 sebaiknya digantikan dengan algoritma hash yang secara khusus dirancang untuk penyimpanan password, seperti bcrypt, scrypt, atau Argon2. Algoritma-algoritma tersebut memiliki mekanisme pengaturan kompleksitas dan konsumsi sumber daya yang tinggi.
Selain itu, setiap password perlu dilengkapi dengan salt unik agar hash yang dihasilkan tidak dapat dengan mudah dicocokkan menggunakan tabel pra-hitung. Penerapan mekanisme tambahan seperti rate limiting, account lockout, serta multi-factor authentication (MFA) juga sangat disarankan untuk memperkuat sistem autentikasi.
Pemilihan algoritma seperti bcrypt, scrypt, dan Argon2 didasarkan pada kemampuannya untuk memperlambat proses hashing sehingga serangan brute force menjadi tidak efisien dan mahal secara komputasi. Dengan kombinasi salt dan mekanisme pengamanan tambahan, kebocoran basis data tidak serta-merta membahayakan akun pengguna. Dampaknya, sistem menjadi lebih tahan terhadap serangan kriptografi modern dan perlindungan data pengguna dapat ditingkatkan secara signifikan.

## 5. Source Code
<img width="795" height="672" alt="image" src="https://github.com/user-attachments/assets/cbdb3a7c-7d84-4cf3-86ec-44be95c08783" />


## 6. Hasil dan Pembahasan
<img width="189" height="64" alt="image" src="https://github.com/user-attachments/assets/bde3a108-dd22-4d41-b04b-51d602c4f8aa" />

Program mampu menemukan kata sandi “123” hanya dengan mencoba sejumlah kecil kombinasi sederhana. Temuan ini menunjukkan bahwa algoritma MD5 memiliki kecepatan komputasi yang sangat tinggi, sehingga proses pencocokan hash dapat dilakukan dengan cepat. Selain itu, penggunaan password yang sederhana membuatnya mudah ditebak, dan ketiadaan mekanisme salt memungkinkan nilai hash dicocokkan secara langsung tanpa hambatan tambahan.

## 7. Jawaban Pertanyaan
1. Mengapa banyak sistem lama masih rentan terhadap brute force atau dictionary attack?
Banyak sistem lama masih rentan karena dirancang menggunakan standar keamanan yang sudah tidak relevan dengan perkembangan teknologi saat ini. Sistem tersebut umumnya masih menggunakan algoritma hash lama seperti MD5 atau SHA-1 yang memiliki kecepatan komputasi tinggi sehingga mudah diserang dengan brute force maupun dictionary attack. Selain itu, sistem lama sering kali tidak menerapkan salt, rate limiting, atau kebijakan password yang kuat. Keterbatasan sumber daya, kurangnya pembaruan sistem, serta anggapan bahwa sistem lama “masih berjalan dengan baik” juga menyebabkan kerentanan ini terus dibiarkan.

2. Apa bedanya kelemahan algoritma dengan kelemahan implementasi?
Kelemahan algoritma adalah kelemahan yang melekat pada desain kriptografi itu sendiri. Contohnya, MD5 memiliki kelemahan collision dan kecepatan hash yang terlalu tinggi, sehingga secara teori dan praktik sudah tidak aman untuk perlindungan password.
Sementara itu, kelemahan implementasi terjadi akibat cara penerapan algoritma yang tidak tepat. Misalnya, penggunaan algoritma yang sebenarnya aman tetapi tanpa salt, tanpa pembatasan percobaan login, atau dengan konfigurasi yang salah. Dengan kata lain, algoritma yang kuat pun dapat menjadi tidak aman jika diimplementasikan secara keliru.

3. Bagaimana organisasi dapat memastikan sistem kriptografi mereka tetap aman di masa depan?
Organisasi dapat menjaga keamanan sistem kriptografi dengan menerapkan algoritma yang mengikuti standar keamanan terbaru, seperti menggunakan algoritma hash khusus password (misalnya bcrypt atau Argon2). Selain itu, organisasi perlu melakukan audit keamanan secara berkala, memperbarui sistem dan pustaka kriptografi, serta mengikuti rekomendasi dari lembaga standar keamanan. Penerapan praktik keamanan tambahan seperti multi-factor authentication (MFA), rate limiting, dan edukasi keamanan bagi pengembang juga sangat penting agar sistem tetap adaptif terhadap ancaman kriptografi di masa depan.

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log

commit abc12345
Author: Dimas Riyan Hidayat DimasRiyanHidayat@gmail.com
Date:   2026-01-23

  week-14 : Analisis Serangan
