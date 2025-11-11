# Laporan Praktikum Kriptografi
Minggu ke-: 6
Topik: chiper modern(DES,AES,RSA) 
Nama: Dhea Silvia
NIM: 230202742  
Kelas: 5IKRB 

---

## 1. Tujuan
1. Mengimplementasikan algoritma DES untuk blok data sederhana.
2. Menerapkan algoritma AES dengan panjang kunci 128 bit.
3. Menjelaskan proses pembangkitan kunci publik dan privat pada algoritma RS**.


## 2. Dasar Teori
Algoritma modern adalah sekumpulan prosedur logis dan sistematis yang dirancang untuk menyelesaikan permasalahan secara efektif dengan memanfaatkan kemajuan dalam bidang matematika, struktur data, dan teknologi komputasi. Tujuan utamanya terletak pada peningkatan efisiensi waktu dan penggunaan memori agar mampu mengolah data berukuran besar serta beroperasi optimal pada sistem paralel maupun terdistribusi. Jenis-jenis algoritma modern meliputi algoritma deterministik yang menghasilkan output tetap untuk input yang sama, algoritma non-deterministik yang mengandung elemen acak, serta algoritma heuristik dan metaheuristik seperti Genetic Algorithm, Simulated Annealing, dan Particle Swarm Optimization yang digunakan untuk menyelesaikan persoalan optimasi yang kompleks. Dalam ranah kecerdasan buatan, algoritma seperti Neural Network, Decision Tree, dan Q-Learning menjadi landasan utama sistem pembelajaran mesin yang mampu mengenali pola dan memprediksi hasil berdasarkan data.

Selain itu, teori algoritma modern juga menyoroti pentingnya analisis kompleksitas menggunakan notasi Big-O untuk menilai efisiensi suatu algoritma, serta mengadopsi berbagai paradigma pemrograman seperti divide and conquer, dynamic programming, greedy, dan backtracking. Penerapannya sangat luas, mulai dari bidang kriptografi (misalnya RSA dan AES) untuk keamanan data, hingga pengolahan big data dan komputasi kuantum melalui algoritma seperti MapReduce dan Shor’s Algorithm. Inovasi terkini juga mencakup algoritma deep learning serta optimisasi evolusioner yang meniru proses alam dalam menemukan solusi terbaik. Dengan demikian, algoritma modern menjadi pilar utama dalam kemajuan teknologi informasi, kecerdasan buatan, dan sistem komputasi masa kini yang semakin kompleks, adaptif, dan relevan dengan kebutuhan perkembangan zaman.

---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

---

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file AES.py, RSA.py, DES.py di folder `praktikum/week6-cipher modern/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah

---

## 5. Source Code
AES
from Crypto.Cipher import AES
from Crypto.Random import get_random_bytes

key = get_random_bytes(16)  # 128 bit key
cipher = AES.new(key, AES.MODE_EAX)

plaintext = b"Modern Cipher AES Example"
ciphertext, tag = cipher.encrypt_and_digest(plaintext)

print("Ciphertext:", ciphertext)

# Dekripsi
cipher_dec = AES.new(key, AES.MODE_EAX, nonce=cipher.nonce)
decrypted = cipher_dec.decrypt(ciphertext)
print("Decrypted:", decrypted.decode())

RSA
from Crypto.PublicKey import RSA
from Crypto.Cipher import PKCS1_OAEP

# Generate key pair
key = RSA.generate(2048)
private_key = key
public_key = key.publickey()

# Enkripsi dengan public key
cipher_rsa = PKCS1_OAEP.new(public_key)
plaintext = b"RSA Example"
ciphertext = cipher_rsa.encrypt(plaintext)
print("Ciphertext:", ciphertext)

# Dekripsi dengan private key
decipher_rsa = PKCS1_OAEP.new(private_key)
decrypted = decipher_rsa.decrypt(ciphertext)
print("Decrypted:", decrypted.decode())

DES
from Crypto.Cipher import DES
from Crypto.Random import get_random_bytes

key = get_random_bytes(8)  # kunci 64 bit (8 byte)
cipher = DES.new(key, DES.MODE_ECB)

plaintext = b"ABCDEFGH"
ciphertext = cipher.encrypt(plaintext)
print("Ciphertext:", ciphertext)

decipher = DES.new(key, DES.MODE_ECB)
decrypted = decipher.decrypt(ciphertext)
print("Decrypted:", decrypted)

## 6. Hasil dan Pembahasan
(- Lampirkan screenshot hasil eksekusi program (taruh di folder `screenshots/`).  
- Berikan tabel atau ringkasan hasil uji jika diperlukan.  
- Jelaskan apakah hasil sesuai ekspektasi.  
- Bahas error (jika ada) dan solusinya. 

Hasil eksekusi program Caesar Cipher:

![Hasil Eksekusi](screenshots/output.png)
![Hasil Input](screenshots/input.png)
![Hasil Output](screenshots/output.png)
)

---

## 7. Jawaban Pertanyaan
1. Perbedaan mendasar antara DES, AES, dan RSA dalam hal kunci dan keamanan DES dan AES termasuk dalam algoritma simetris, di mana proses enkripsi dan dekripsi menggunakan kunci yang sama, sedangkan RSA adalah asimetris karena menggunakan dua kunci berbeda, yaitu public key dan private key. Dari sisi keamanan, DES kini dianggap lemah karena hanya memiliki panjang kunci 56 bit yang mudah ditembus oleh serangan brute force. AES lebih kuat dengan panjang kunci hingga 256 bit dan struktur enkripsi yang kompleks, sementara RSA mengandalkan konsep matematika faktorisasi bilangan prima besar, sehingga menawarkan keamanan tinggi meski dengan kecepatan pemrosesan yang lebih lambat.
2. AES lebih banyak digunakan karena menawarkan keamanan yang jauh lebih tinggi dan efisiensi yang lebih baik dibanding DES. Kunci 56-bit pada DES kini mudah dipecahkan menggunakan komputer modern dalam hitungan jam atau bahkan menit, sedangkan AES dengan kunci 128-bit atau lebih praktis tidak dapat ditembus dengan brute-force menggunakan teknologi saat ini. Selain itu, AES lebih efisien dalam kecepatan enkripsi dan dekripsi, serta telah menjadi standar internasional (FIPS-197) yang diadopsi oleh pemerintah AS dan banyak organisasi di seluruh dunia. Struktur AES juga dirancang untuk optimal di perangkat keras maupun perangkat lunak, menjadikannya pilihan utama untuk keamanan data di era digital.
3.RSA dikategorikan asimetris karena Menggunakan dua kunci berbeda:
-Kunci publik (public key): digunakan untuk enkripsi data.
-Kunci privat (private key): digunakan untuk dekripsi data.
-Data yang dienkripsi dengan kunci publik hanya dapat dibuka oleh kunci privat yang sesuai, dan sebaliknya.
Hal ini berbeda dengan algoritma simetris yang memakai satu kunci yang sama untuk enkripsi dan dekripsi. 

## 8. Kesimpulan
Praktikum ini berhasil memverifikasi implementasi tiga algoritma kriptografi modern, yaitu DES, AES, dan RSA, yang menunjukkan kemampuan masing-masing algoritma dalam melakukan proses enkripsi dan dekripsi data secara efektif. Hasil percobaan memperlihatkan bahwa seluruh ciphertext yang dihasilkan, baik dari algoritma simetris (DES dan AES) maupun asimetris (RSA), dapat dikembalikan dengan tepat menjadi plaintext aslinya tanpa kehilangan integritas data. Hal ini membuktikan bahwa algoritma yang diimplementasikan berfungsi sesuai teori dan mampu menjaga kerahasiaan informasi melalui mekanisme pengacakan dan pemulihan data yang terstruktur.
Selain itu, hasil praktikum juga memperkuat pemahaman mengenai perbedaan mendasar antara algoritma simetris dan asimetris. Pada algoritma simetris, proses enkripsi dan dekripsi menggunakan kunci yang sama, sehingga lebih cepat namun membutuhkan mekanisme distribusi kunci yang aman. Sementara pada algoritma asimetris seperti RSA, proses tersebut menggunakan dua kunci berbeda, yakni kunci publik dan kunci privat, yang meningkatkan keamanan namun memerlukan waktu komputasi lebih tinggi. Dengan demikian, praktikum ini tidak hanya membuktikan fungsionalitas algoritma secara teknis, tetapi juga memberikan pemahaman yang lebih mendalam tentang konsep keamanan data, efisiensi algoritma, serta penerapan kriptografi dalam sistem keamanan informasi modern.

## 9. Daftar Pustaka


## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit cipher modern
Author: Dhea Silvia <dheasilvia51@gmail.com>
Date:   2025-11-11

    week6-cipher modern(aes,rsa,des)
```
