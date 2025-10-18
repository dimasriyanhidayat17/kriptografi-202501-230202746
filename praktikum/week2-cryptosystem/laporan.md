# Laporan Praktikum Kriptografi
Minggu ke-: 2
Topik: crypto sistem 
Nama: Safira Dewi Rahmatika 
NIM: 230202784
Kelas: 5IKRB 

## 1. Tujuan
1. menjelaskan komponen dasar pada cryptosistem
2. menjelaskan proses enkripsi dan deskripsi sederhana
3. mengklasifikasikan jenis" yang ada pada cryptosistem
   
## 2. Dasar Teori
Kriptosistem adalah sistem yang digunakan untuk mengamankan data atau pesan dengan cara menyandikan (enkripsi) dan mengembalikannya ke bentuk semula (dekripsi) menggunakan algoritma dan kunci tertentu.
Komponen dasar dari sebuah kriptosistem meliputi:
1. Plaintext (teks asli)
Pesan atau data yang belum dienkripsi. Ini adalah informasi yang ingin dilindungi.
> Contoh: HELLO
2. Ciphertext (teks sandi)
Hasil dari proses enkripsi, yaitu bentuk pesan yang sudah disamarkan agar tidak bisa dibaca tanpa kunci.
> Contoh: KHOOR (hasil enkripsi dari “HELLO”)
3. Algoritma enkripsi
Prosedur atau aturan matematis yang digunakan untuk mengubah plaintext menjadi ciphertext.
> Contoh: algoritma Caesar Cipher, AES, RSA, dsb.
4. Algoritma dekripsi
Prosedur yang digunakan untuk mengembalikan ciphertext menjadi plaintext.
5. Kunci (key)
Nilai rahasia yang digunakan dalam proses enkripsi dan dekripsi. Kunci ini sangat penting karena menjamin keamanan sistem.
> Contoh: pada Caesar Cipher, kuncinya bisa berupa pergeseran huruf sebanyak 3.

Enkripsi adalah proses mengubah pesan asli (plaintext) menjadi bentuk sandi (ciphertext) agar tidak bisa dibaca oleh orang lain.Dekripsi adalah proses mengembalikan ciphertext menjadi plaintext agar pesan bisa dibaca kembali.
Proses ini menggunakan algoritma dan kunci (key) tertentu.Dalam sistem simetris, kunci enkripsi dan dekripsi sama.
Dalam sistem asimetris, kunci enkripsi dan dekripsi berbeda (public key & private key).
Tujuan utamanya: menjaga kerahasiaan, keaslian, dan keamanan data.
Contoh sederhana:
Pesan “HELLO” dienkripsi dengan pergeseran huruf 3 → jadi “KHOOR”.
Kemudian didekripsi kembali → “HELLO”.

Kriptosistem dapat dibedakan berdasarkan jenis kunci dan cara pengolahan datanya. Berdasarkan jenis kuncinya, terdapat dua macam yaitu kriptosistem simetris dan kriptosistem asimetris. Kriptosistem simetris menggunakan satu kunci yang sama untuk proses enkripsi dan dekripsi, sehingga lebih cepat namun memiliki risiko jika kunci bocor. Contohnya yaitu AES, DES, dan Blowfish. Sementara itu, kriptosistem asimetris menggunakan dua kunci berbeda, yaitu kunci publik untuk enkripsi dan kunci privat untuk dekripsi. Sistem ini lebih aman tetapi prosesnya lebih lambat, dengan contoh seperti RSA, ECC, dan ElGamal.

Berdasarkan cara pengolahan datanya, kriptosistem dibagi menjadi substitution cipher, transposition cipher, block cipher, dan stream cipher. Substitution cipher mengganti setiap huruf dengan huruf lain, transposition cipher menukar posisi huruf, block cipher mengenkripsi data dalam blok-blok tertentu, sedangkan stream cipher mengenkripsi data per bit atau karakter. Semua jenis kriptosistem memiliki tujuan utama untuk melindungi kerahasiaan dan keamanan data agar tidak dapat diakses oleh pihak yang tidak berwenang.

## 3. Alat dan Bahan
- Visual Studio Code 
- Git dan akun GitHub  
- Terminal CMD

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `caesar_cipher.py` di folder `praktikum/week2-cryptosystem/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)

---

## 5. Source Code
(Salin kode program utama yang dibuat atau dimodifikasi.  
Gunakan blok kode:

```python
# contoh potongan kode
def encrypt(text, key):
    return ...
```
)

---

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
(Jawab pertanyaan diskusi yang diberikan pada modul.  
- Pertanyaan 1: …  
- Pertanyaan 2: …  
)
---

## 8. Kesimpulan
(Tuliskan kesimpulan singkat (2–3 kalimat) berdasarkan percobaan.  )

---

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
