# Laporan Praktikum Kriptografi
Minggu ke-: IX  
Topik:  Digital Signature (RSA/DSA)
Nama: Dimas Riyan Hidayat  
NIM: 230202746 
Kelas: 5IKRB

## 1. Tujuan
1. Mengimplementasikan tanda tangan digital menggunakan algoritma RSA/DSA.
2. Memverifikasi keaslian tanda tangan digital.
3. Menjelaskan manfaat tanda tangan digital dalam otentikasi pesan dan integritas data.

## 2. Dasar Teori
Tanda tangan digital adalah mekanisme kriptografis yang digunakan untuk memastikan keaslian, integritas, dan non-repudiation (ketidakmampuan menyangkal) pada suatu pesan atau dokumen digital. Teknologi ini bekerja dengan memanfaatkan prinsip-prinsip kriptografi kunci publik, khususnya algoritma seperti RSA, DSA, atau ECDSA. Dalam sistem ini, setiap pengguna memiliki sepasang kunci: private key yang bersifat rahasia dan digunakan untuk membuat tanda tangan, serta public key yang disebarkan secara bebas dan digunakan untuk memverifikasi keaslian tanda tangan tersebut. Proses penandatanganan digital dilakukan dengan meng-hash pesan menggunakan fungsi hash kriptografis seperti SHA-256, kemudian mengenkripsi hash tersebut menggunakan private key. Hasil enkripsi inilah yang menjadi tanda tangan digital. Karena fungsi hash bersifat satu arah dan sensitif terhadap perubahan, tanda tangan digital dapat memastikan integritas pesan—sebab perubahan sekecil apa pun pada pesan akan membuat hash baru berbeda total.

RSA (Rivest–Shamir–Adleman) sendiri adalah salah satu algoritma kriptografi kunci publik paling populer yang digunakan untuk enkripsi maupun tanda tangan digital. Keamanan RSA didasarkan pada kesulitan matematis faktorisasi bilangan sangat besar menjadi faktor prima. Pada penggunaan tanda tangan digital RSA, algoritma ini tidak dipakai untuk merahasiakan pesan seperti pada proses enkripsi, melainkan untuk memberikan autentikasi dan validasi terhadap pesan. Private key digunakan untuk menandatangani hash pesan, sedangkan public key digunakan untuk memverifikasi tanda tangan tersebut. Dengan demikian, hanya pemilik private key yang dapat membuat tanda tangan valid, dan siapa pun yang mengetahui public key dapat memverifikasi keasliannya.

Dalam implementasi modern, sistem tanda tangan digital biasanya melibatkan Certificate Authority (CA) sebagai pihak ketiga yang dipercaya. CA bertugas mengeluarkan sertifikat digital yang mengikat identitas pemilik dengan public key-nya. Sertifikat ini memastikan bahwa public key yang dipakai untuk proses verifikasi benar-benar milik pihak yang sah, bukan hasil manipulasi atau penyamaran (spoofing). Dengan adanya CA, integritas hubungan identitas–public key terjaga, sehingga proses validasi tanda tangan digital dapat dilakukan dengan aman dalam skala luas, termasuk pada sistem keamanan web, email terenkripsi, hingga dokumen elektronik resmi. Secara keseluruhan, teori dasar tanda tangan digital bergantung pada kombinasi fungsi hash kriptografis, algoritma kunci publik, serta infrastruktur sertifikat digital untuk menciptakan sistem keamanan yang kuat dan tepercaya.

## 3. Alat dan Bahan
- Python 3.11
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan pycryptodome

## 4. Langkah Percobaan
1. Membuat file `Digital Signature.py` di folder `praktikum/week9-Digital Signature/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `Digital Signature.py`.)
4. mengerjakan quis

## 5. Source Code
<img width="1920" height="1080" alt="Screenshot 2025-12-12 213200" src="https://github.com/user-attachments/assets/8b312617-0f13-4269-aad4-8bd4b9a9d0fe" />


## 6. Hasil dan Pembahasan
<img width="1920" height="1080" alt="Screenshot 2025-12-12 213459" src="https://github.com/user-attachments/assets/b421877e-f10c-4b9d-9f2b-bf90e802db3e" />


## 7. Jawaban Pertanyaan
1. Apa perbedaan utama antara enkripsi RSA dan tanda tangan digital RSA?

Enkripsi RSA digunakan untuk menjaga kerahasiaan pesan, di mana pengirim mengenkripsi data menggunakan public key penerima sehingga hanya penerima yang dapat membaca pesan tersebut dengan private key-nya. Sebaliknya, tanda tangan digital RSA berfungsi untuk memastikan keaslian dan integritas pesan. Dalam tanda tangan digital, pengirim menggunakan private key miliknya untuk menandatangani hash pesan, dan siapa pun dapat memverifikasinya menggunakan public key pengirim. Jadi, perbedaan utamanya adalah tujuan: enkripsi RSA fokus pada kerahasiaan, sementara tanda tangan digital fokus pada otentikasi pengirim, integritas pesan, dan pencegahan pemalsuan.

2. Mengapa tanda tangan digital menjamin integritas dan otentikasi pesan?

Tanda tangan digital menjamin integritas karena yang ditandatangani adalah hash dari pesan. Jika pesan mengalami perubahan sekecil apa pun, hash yang dihasilkan akan berbeda total, sehingga tanda tangan langsung dianggap tidak valid. Ini memastikan bahwa isi pesan tetap asli sejak ditandatangani. Selain itu, tanda tangan digital memberikan otentikasi karena hanya pemilik private key yang bisa menghasilkan tanda tangan tersebut. Saat pihak lain memverifikasi menggunakan public key pengirim, mereka dapat memastikan bahwa pesan benar-benar berasal dari pemilik private key dan tidak dapat disangkal. Kombinasi integritas dan otentikasi inilah yang membuat tanda tangan digital sangat kuat dan tepercaya.

3. Bagaimana peran Certificate Authority (CA) dalam sistem tanda tangan digital modern?

Certificate Authority (CA) berperan sebagai pihak ketiga tepercaya yang memastikan bahwa public key yang digunakan dalam verifikasi benar-benar milik orang atau organisasi yang mengklaimnya. CA melakukan proses verifikasi identitas sebelum menerbitkan sertifikat digital yang berisi public key beserta data identitas pemiliknya, lalu ditandatangani oleh CA sendiri. Dengan sertifikat ini, pengguna atau sistem lain dapat memvalidasi bahwa public key tersebut resmi dan tidak dipalsukan. Peran CA sangat penting dalam skala internet modern karena tanpa CA, tidak ada cara standar untuk memastikan apakah public key benar-benar milik pihak yang mengaku sebagai pemilik.

## 8. Kesimpulan
Tanda tangan digital merupakan mekanisme penting dalam keamanan informasi modern karena mampu menjamin otentikasi pengirim, integritas data, dan mencegah penyangkalan atas pesan yang telah dikirim. Dengan memanfaatkan kriptografi kunci publik, terutama algoritma RSA, tanda tangan digital memungkinkan hash pesan ditandatangani menggunakan private key sehingga hanya pemilik kunci tersebut yang dapat membuat tanda tangan yang valid. Proses verifikasi menggunakan public key memastikan bahwa pesan tidak mengalami perubahan dan benar berasal dari pihak yang sah. Untuk memperkuat kepercayaan dalam skala besar, sistem ini didukung oleh Certificate Authority (CA) yang menerbitkan sertifikat digital guna memvalidasi kepemilikan public key. Dengan gabungan konsep fungsi hash, algoritma RSA, dan peran CA, tanda tangan digital menjadi solusi komprehensif yang sangat andal dalam melindungi komunikasi dan transaksi digital.

## 9. Daftar Pustaka

## 10. Commit Log
commit week9-digital-signature
Author: Dimas Riyan Hidayat <email>
Date:   2025-12-12

