# Laporan Praktikum Kriptografi
Minggu ke-: XIII
Topik: Tiny-chain
Nama: Dimas Riyan Hidayat
NIM: 230202746
Kelas: 5IKRB

## 1. Tujuan
1. Menjelaskan peran hash function dalam blockchain.
2. Melakukan simulasi sederhana Proof of Work (PoW).
3. Menganalisis keamanan cryptocurrency berbasis kriptografi.
   
## 2. Dasar Teori
Peran Hash Function dalam Blockchain
Hash function berperan penting dalam blockchain untuk menjaga integritas dan keamanan data. Setiap blok pada blockchain memiliki nilai hash unik yang dihasilkan dari data blok tersebut. Hash ini digunakan untuk menghubungkan satu blok dengan blok sebelumnya, sehingga apabila data pada satu blok diubah, nilai hash akan berubah dan merusak seluruh rantai. Selain itu, hash function juga digunakan dalam proses validasi transaksi dan mekanisme konsensus.

Simulasi Sederhana Proof of Work (PoW) Proof of Work merupakan mekanisme konsensus yang mengharuskan penambang (miner) memecahkan permasalahan kriptografi dengan mencari nilai hash yang memenuhi syarat tertentu, seperti memiliki jumlah nol di awal. Proses ini dilakukan melalui perhitungan berulang (hashing) hingga ditemukan solusi yang valid. PoW bertujuan untuk mencegah manipulasi data dan serangan, karena membutuhkan sumber daya komputasi yang besar untuk memalsukan blok.

Keamanan Cryptocurrency Berbasis Kriptografi bergantung pada penerapan kriptografi, seperti hash function, kriptografi kunci publik, dan mekanisme konsensus. Kriptografi memastikan transaksi bersifat aman, transparan, dan tidak dapat diubah setelah dicatat di blockchain. Meskipun demikian, tantangan keamanan tetap ada, seperti risiko serangan 51%, kesalahan implementasi, dan pencurian kunci privat, sehingga pengguna harus menjaga keamanan akses terhadap aset digital mereka.

## 3. Alat dan Bahan
- Python 3.11 
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

## 4. Langkah Percobaan
1. Membuat struktur blok
2. Membuat blokchain
3. Analisis Proof of Work (PoW)

## 5. Source Code
<img width="1200" height="916" alt="Screenshot 2026-01-12 231805" src="https://github.com/user-attachments/assets/0c0f6bf9-dd02-4d42-a559-ec0b5a328786" />
<img width="723" height="441" alt="Screenshot 2026-01-12 231817" src="https://github.com/user-attachments/assets/7c5264b6-9c52-4303-b1e3-51190d74c542" />

## 6. Hasil dan Pembahasan
<img width="890" height="284" alt="Screenshot 2026-01-12 231840" src="https://github.com/user-attachments/assets/466498ac-d7ad-40a5-aa92-2e246a6e9721" />

Berdasarkan hasil eksekusi program tinychain.py, terlihat bahwa setiap proses penambangan (mining) menghasilkan nilai hash blok yang berbeda, meskipun program dijalankan dengan jumlah blok yang sama. Hal ini terjadi karena proses Proof of Work melibatkan pencarian nilai nonce secara acak hingga ditemukan hash yang memenuhi kriteria tertentu, yaitu diawali dengan sejumlah nol (0000). Perbedaan hasil hash menunjukkan sifat fungsi hash yang sensitif terhadap perubahan kecil pada input, sekaligus membuktikan bahwa PoW membutuhkan perhitungan berulang sebelum blok dinyatakan valid. Proses ini menggambarkan bagaimana blockchain menjaga keamanan dan keutuhan data dengan membuat pemalsuan blok menjadi sulit dan memerlukan sumber daya komputasi yang besar.

## 7. Jawaban Pertanyaan
1. Mengapa fungsi hash sangat penting dalam blockchain?
Fungsi hash sangat penting karena digunakan untuk menjaga integritas dan keamanan data pada blockchain. Hash memastikan bahwa setiap perubahan kecil pada data akan menghasilkan nilai hash yang berbeda, sehingga manipulasi data dapat dengan mudah terdeteksi. Hash juga menghubungkan setiap blok dengan blok sebelumnya, membentuk rantai yang sulit diubah.

2. Bagaimana Proof of Work mencegah double spending?
Proof of Work mencegah double spending dengan memastikan bahwa setiap transaksi harus diverifikasi dan dimasukkan ke dalam blok yang telah disetujui oleh jaringan. Proses penambangan yang membutuhkan perhitungan komputasi tinggi membuat pemalsuan transaksi atau penggandaan penggunaan koin menjadi sangat sulit dan mahal.

3. Apa kelemahan dari PoW dalam hal efisiensi energi?
Kelemahan utama Proof of Work adalah konsumsi energi yang sangat besar karena proses penambangan membutuhkan daya komputasi tinggi dan perhitungan hash secara terus-menerus. Hal ini menyebabkan pemborosan energi dan berdampak negatif terhadap lingkungan.

## 8. Kesimpulan
Berdasarkan hasil simulasi Proof of Work menggunakan program tinychain.py, dapat disimpulkan bahwa mekanisme PoW berhasil menunjukkan prinsip dasar blockchain dalam menjaga keamanan data. Proses penambangan memerlukan perhitungan hash berulang hingga memenuhi tingkat kesulitan tertentu, sehingga setiap blok yang dihasilkan bersifat unik dan sulit untuk dimanipulasi. Perbedaan nilai hash pada setiap eksekusi membuktikan sifat fungsi hash yang sensitif terhadap perubahan input. Dengan demikian, Proof of Work berperan penting dalam mencegah pemalsuan data dan double spending, meskipun memiliki kelemahan dalam hal efisiensi energi.

## 9. Daftar Pustaka
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )


## 10. Commit Log
Author: Dimas Riyan Hidayat dimasriyanhidayat01@gmail.com
Date:   2026-01-12

  week14-Tiny-chain 
