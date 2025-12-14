# Laporan Praktikum Kriptografi
Minggu ke-: IX  
Topik: Digital Signature  
Nama: Safira Dewi Rahmatika 
NIM: 230202784 
Kelas: 5IKRB  

## 1. Tujuan
1. Mengimplementasikan tanda tangan digital menggunakan algoritma RSA/DSA.
2. Memverifikasi keaslian tanda tangan digital.
3. Menjelaskan manfaat tanda tangan digital dalam otentikasi pesan dan integritas data.

## 2. Dasar Teori
Kriptografi kunci publik adalah teknik pengamanan data yang menggunakan sepasang kunci, yaitu kunci publik dan kunci privat, yang saling berkaitan secara matematis. Salah satu algoritma kriptografi kunci publik yang paling banyak digunakan adalah RSA, yang keamanannya bergantung pada kesulitan memfaktorkan bilangan prima besar. Dalam penerapannya, RSA digunakan baik untuk enkripsi maupun tanda tangan digital, namun keduanya memiliki tujuan yang berbeda.

Enkripsi RSA bertujuan untuk menjaga kerahasiaan pesan, di mana pesan dienkripsi menggunakan kunci publik penerima dan hanya dapat didekripsi dengan kunci privat penerima. Sementara itu, tanda tangan digital RSA digunakan untuk menjamin keaslian dan keutuhan pesan dengan cara mengenkripsi nilai hash pesan menggunakan kunci privat pengirim. Jika pesan diubah, nilai hash akan berubah sehingga tanda tangan menjadi tidak valid, yang menunjukkan bahwa integritas pesan telah terganggu.

Untuk menjamin kepercayaan terhadap kunci publik yang digunakan dalam verifikasi tanda tangan digital, sistem modern memanfaatkan Public Key Infrastructure (PKI) dengan Certificate Authority (CA) sebagai pihak tepercaya. CA bertugas memverifikasi identitas pemilik kunci sebelum menerbitkan sertifikat digital yang mengikat identitas dengan kunci publik tertentu. Dengan adanya CA, pengguna dapat memastikan bahwa kunci publik benar-benar milik pihak yang sah, sehingga keamanan komunikasi terjaga dari pemalsuan identitas dan serangan Man-in-the-Middle (MITM).

## 3. Alat dan Bahan
- Python 3.11
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (pycryptodome)
  
## 4. Langkah Percobaan
1. Membuat file `digital signature.py` di folder `praktikum/week9-Digital Signature/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python digital signature.py`.
4. mengerjakan quis

## 5. Source Code
<img width="1613" height="934" alt="Screenshot 2025-12-12 222603" src="https://github.com/user-attachments/assets/2f60abe1-4992-4102-af26-a78339e51b78" />


## 6. Hasil dan Pembahasan
<img width="1620" height="711" alt="Screenshot 2025-12-12 222621" src="https://github.com/user-attachments/assets/0d54e413-6066-4ac3-a32d-eab029504bcb" />


## 7. Jawaban Pertanyaan
1. Perbedaan utama antara enkripsi RSA dan tanda tangan digital RSA
Enkripsi RSA digunakan untuk menjaga kerahasiaan pesan. Prosesnya: pesan dienkripsi menggunakan kunci publik penerima dan hanya bisa didekripsi dengan kunci privat penerima. Tujuannya agar isi pesan tidak bisa dibaca pihak lain.
Sebaliknya, tanda tangan digital RSA digunakan untuk menjamin keaslian dan keutuhan pesan, bukan kerahasiaan. Prosesnya: pengirim membuat tanda tangan dengan kunci privat miliknya, lalu siapa pun dapat memverifikasinya menggunakan kunci publik pengirim.

2. Mengapa tanda tangan digital menjamin integritas dan otentikasi pesan?
Tanda tangan digital menjamin integritas karena dibuat dari nilai hash pesan. Jika isi pesan diubah sedikit saja, hash akan berubah dan verifikasi tanda tangan gagal.
Selain itu, tanda tangan digital menjamin otentikasi karena hanya pemilik kunci privat yang sah yang dapat membuat tanda tangan tersebut. Jika tanda tangan valid saat diverifikasi dengan kunci publik, maka pengirim dapat dipastikan autentik.

3. Peran Certificate Authority (CA) dalam sistem tanda tangan digital modern
Certificate Authority (CA) berperan sebagai pihak tepercaya yang mengaitkan identitas seseorang atau organisasi dengan kunci publiknya melalui sertifikat digital. CA memverifikasi identitas pemilik sertifikat sebelum menerbitkannya.
Dengan adanya CA, penerima pesan dapat percaya bahwa kunci publik yang digunakan untuk memverifikasi tanda tangan digital benar-benar milik pengirim yang sah, sehingga mencegah pemalsuan identitas dan serangan Man-in-the-Middle (MITM).

## 8. Kesimpulan
RSA memiliki dua peran utama dalam kriptografi kunci publik, yaitu enkripsi untuk menjaga kerahasiaan pesan dan tanda tangan digital untuk menjamin keaslian serta keutuhan pesan. Tanda tangan digital memanfaatkan fungsi hash dan kunci privat pengirim sehingga setiap perubahan pesan dapat terdeteksi dan identitas pengirim dapat diverifikasi. Agar kunci publik yang digunakan benar-benar tepercaya, diperlukan peran Certificate Authority (CA) melalui sistem PKI yang memverifikasi identitas dan menerbitkan sertifikat digital, sehingga komunikasi digital menjadi lebih aman dan terlindungi dari pemalsuan identitas serta serangan Man-in-the-Middle (MITM).

## 9. Daftar Pustaka

## 10. Commit Log
commit week9-digital-signature
Author: Safira Dewi Rahmatika <Safiraa1026@gmail.com>
Date:   2025-12-14
