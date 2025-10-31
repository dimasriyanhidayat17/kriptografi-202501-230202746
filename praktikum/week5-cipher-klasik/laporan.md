Minggu ke-: 5
Topik: cipher klasik(caesar,vigenere,tranposisi)
Nama: Dhea Silvia
NIM: 230202742
Kelas:5ikrb

---

## 1. Tujuan
1. Menerapkan algoritma Caesar Cipher untuk enkripsi dan dekripsi teks.
2. Menerapkan algoritma Vigenère Cipher dengan variasi kunci.
3. Mengimplementasikan algoritma transposisi sederhana.
4. Menjelaskan kelemahan algoritma kriptografi klasik dalam konteks keamanan modern.
---

## 2. Dasar Teori
Cipher klasik adalah metode kriptografi kuno yang menyembunyikan pesan melalui dua teknik utama: substitusi (mengganti huruf) atau transposisi (menyusun ulang huruf). Caesar Cipher adalah contoh substitusi yang paling sederhana, di mana setiap huruf digeser sejumlah n posisi pada alfabet, menggunakan prinsip aritmetika modular ($\text{mod } 26$) untuk memutar huruf.  Sebagai pengembangannya, Vigenère Cipher meningkatkan keamanan dengan menggunakan kata kunci yang berbeda-beda untuk setiap huruf dalam pesan, membuatnya lebih kompleks dan lebih sulit dipecahkan daripada Caesar. Sementara itu, Transposisi Cipher bekerja dengan mengubah urutan huruf alih-alih menggantinya; misalnya, pesan ditulis berbaris dan dibaca per kolom. Meskipun Transposisi Cipher kebal terhadap analisis frekuensi sederhana, semua cipher klasik ini rentan dan mudah dipecahkan oleh serangan komputasional modern karena ruang kuncinya yang kecil.

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
1. Membuat file `caesar_cipher.py` di folder `praktikum/week5-cryptosystem/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)

---

## 5. Source Code
langkah 1
def caesar_encrypt(plaintext, key):
    result = ""
    for char in plaintext:
        if char.isalpha():
            shift = 65 if char.isupper() else 97
            result += chr((ord(char) - shift + key) % 26 + shift)
        else:
            result += char
    return result

def caesar_decrypt(ciphertext, key):
    return caesar_encrypt(ciphertext, -key)
# Contoh uji
msg = "CLASSIC CIPHER"
key = 3
enc = caesar_encrypt(msg, key)
dec = caesar_decrypt(enc, key)
print("Plaintext :", msg)
print("Ciphertext:", enc)
print("Decrypted :", dec)

langkah 2:
def vigenere_encrypt(plaintext, key):
    result = []
    key = key.lower()
    key_index = 0
    for char in plaintext:
        if char.isalpha():
            shift = ord(key[key_index % len(key)]) - 97
            base = 65 if char.isupper() else 97
            result.append(chr((ord(char) - base + shift) % 26 + base))
            key_index += 1
        else:
            result.append(char)
    return "".join(result)

def vigenere_decrypt(ciphertext, key):
    result = []
    key = key.lower()
    key_index = 0
    for char in ciphertext:
        if char.isalpha():
            shift = ord(key[key_index % len(key)]) - 97
            base = 65 if char.isupper() else 97
            result.append(chr((ord(char) - base - shift) % 26 + base))
            key_index += 1
        else:
            result.append(char)
    return "".join(result)

# Contoh uji
msg = "KRIPTOGRAFI"
key = "KEY"
enc = vigenere_encrypt(msg, key)
dec = vigenere_decrypt(enc, key)
print("Plaintext :", msg)
print("Ciphertext:", enc)
print("Decrypted :", dec)

langkah 3:
def transpose_encrypt(plaintext, key=5):
    ciphertext = [''] * key
    for col in range(key):
        pointer = col
        while pointer < len(plaintext):
            ciphertext[col] += plaintext[pointer]
            pointer += key
    return ''.join(ciphertext)

def transpose_decrypt(ciphertext, key=5):
    num_of_cols = int(len(ciphertext) / key + 0.9999)
    num_of_rows = key
    num_of_shaded_boxes = (num_of_cols * num_of_rows) - len(ciphertext)
    plaintext = [''] * num_of_cols
    col = 0
    row = 0
    for symbol in ciphertext:
        plaintext[col] += symbol
        col += 1
        if (col == num_of_cols) or (col == num_of_cols - 1 and row >= num_of_rows - num_of_shaded_boxes):
            col = 0
            row += 1
    return ''.join(plaintext)

# Contoh uji
msg = "TRANSPOSITIONCIPHER"
enc = transpose_encrypt(msg, key=5)
dec = transpose_decrypt(enc, key=5)
print("Plaintext :", msg)
print("Ciphertext:", enc)
print("Decrypted :", dec)

## 6. Hasil dan Pembahasan


<img width="1366" height="768" alt="Capture 3" src="https://github.com/user-attachments/assets/72c32bd5-1bce-4b6f-b400-c2b49c340348" />
<img width="1366" height="768" alt="Capture 4" src="https://github.com/user-attachments/assets/571dadc2-74ba-43c9-b15d-cc8662db6a75" />
<img width="1366" height="768" alt="Capture 2" src="https://github.com/user-attachments/assets/9bc24bc5-3086-41d8-91f9-67a6a131f9a8" />

---

## 7. Jawaban Pertanyaan
**1. Apa kelemahan utama algoritma Caesar Cipher dan Vigenère Cipher?** Caesar Cipher memiliki ruang kunci yang sangat kecil (hanya 25 kemungkinan), sehingga mudah dipecahkan dengan brute-force. Vigenère Cipher lebih kuat, tetapi tetap rentan terhadap frequency analysis dan Kasiski examination jika kuncinya pendek atau berulang.

**2. Mengapa cipher klasik mudah diserang dengan analisis frekuensi?** Karena cipher klasik tidak mengubah frekuensi kemunculan huruf secara signifikan. Pola distribusi huruf dalam bahasa alami tetap bisa dikenali, sehingga analis dapat menebak substitusi yang digunakan.

**3. Bandingkan kelebihan dan kelemahan cipher substitusi vs transposisi.** Substitusi Cipher: Mengganti huruf, tetapi mempertahankan urutan. Lebih mudah diimplementasikan, namun pola frekuensi tetap terlihat. Transposisi Cipher: Menyusun ulang urutan huruf tanpa mengganti karakter. Lebih sulit dipecahkan dengan analisis frekuensi, tetapi masih bisa direkonstruksi dengan serangan posisi karakter.

## 8. Kesimpulan
Praktikum ini memperkenalkan prinsip dasar kriptografi klasik melalui implementasi Caesar, Vigenère, dan Transposisi Cipher. Dari hasil uji, seluruh algoritma berhasil melakukan enkripsi dan dekripsi dengan benar. Namun, cipher klasik terbukti tidak aman untuk komunikasi modern karena mudah diserang dengan teknik analisis frekuensi dan brute-force.

---

## 9. Daftar Pustaka
Schneier, Bruce. (2015). Applied Cryptography: Protocols, Algorithms, and Source Code in C. John Wiley & Sons.

---

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit week5-chiper klasik
Author: dhea silvia <dheasilvia51@gmail.coml>
Date:   2025-10-31

    week5-chiper klasik: implementasi Caesar Cipher dan laporan )
```
