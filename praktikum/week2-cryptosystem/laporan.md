# Laporan Praktikum Kriptografi
Minggu ke-: 2  
Topik: Komponen, Enkripsi & Dekripsi, Simetris & Asimetris  
Nama: Dimas Riyan Hidayat  
NIM: 230202746  
Kelas: 5IKRB 

---

## 1. Tujuan
-Menganalisis struktur dasar sistem kriptografi, termasuk peran esensial dari Plaintext, Ciphertext, Kunci, dan Algoritma.
-Mendemonstrasikan alur kerja (workflow) lengkap untuk mengubah data menjadi bentuk terenkripsi dan memulihkannya kembali.
-Membandingkan dan membedakan dua kategori utama kriptosistem (Simetris vs. Asimetris) berdasarkan mekanisme penggunaan kuncinya.



## 2. Dasar Teori
Kriptografi adalah metode untuk mengamankan pesan menggunakan sandi. Inti dari setiap sistem sandi (kriptosistem) adalah mengubah pesan biasa (Plaintext) menjadi pesan acak yang tidak dapat dibaca (Ciphertext) melalui proses Enkripsi. Proses ini dikontrol oleh Algoritma (aturan matematis, misalnya AES atau Caesar Cipher) dan Kunci (kode rahasia). Agar penerima dapat membaca pesan, proses Dekripsi membalikkan operasi tersebut, menggunakan Algoritma dan Kunci yang benar untuk mengembalikan Ciphertext menjadi Plaintext.

Kriptosistem terbagi dua: Simetris dan Asimetris. Kriptografi Simetris menggunakan satu Kunci yang Sama untuk enkripsi dan dekripsi; keuntungannya adalah kecepatan, tetapi kuncinya harus dibagikan secara rahasia. Sebaliknya, Kriptografi Asimetris menggunakan pasangan kunci: Kunci Publik untuk enkripsi dan Kunci Privat untuk dekripsi. Sistem asimetris lebih lambat tetapi unggul dalam pertukaran kunci yang aman dan digunakan untuk sistem seperti RSA. Algoritma yang mendasari sandi-sandi ini, terutama yang klasik, sering kali memanfaatkan Aritmetika Modular untuk memetakan dan menggeser huruf atau angka secara berulang.

---

## 3. Alat dan Bahan
(- Python 3.12  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Draw Io )
- 

---

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `caesar_cipher.py` di folder `praktikum/week2-cryptosystem/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)
4. membuat diagram menggunakan draw io
5. 

---

## 5. Source Code
from __future__ import annotations
import argparse
import sys
import logging
from typing import Optional

# Setup basic logging (user can override by setting env/log level if needed)
logging.basicConfig(level=logging.INFO, format="%(message)s")
logger = logging.getLogger("simple_crypto")


def _normalize_key(key: int) -> int:
    """Normalize key into range 0..25."""
    return key % 26


def _shift_char(char: str, key: int, encrypting: bool = True) -> str:
    """Shift a single alphabetical character by key. Preserve case."""
    if not char.isalpha():
        return char
    base = ord('A') if char.isupper() else ord('a')
    k = _normalize_key(key)
    if not encrypting:
        k = (-k) % 26
    # compute shifted character
    return chr((ord(char) - base + k) % 26 + base)


def caesar_transform(text: str, key: int, encrypting: bool = True) -> str:
    """
    Transform text using Caesar cipher.
    If encrypting True -> shift forward by key (encrypt).
    If encrypting False -> shift backward by key (decrypt).
    Non-alphabet characters are preserved.
    """
    return ''.join(_shift_char(c, key, encrypting) for c in text)


def encrypt(plaintext: str, key: int) -> str:
    """Encrypt plaintext with Caesar cipher key."""
    return caesar_transform(plaintext, key, encrypting=True)


def decrypt(ciphertext: str, key: int) -> str:
    """Decrypt ciphertext with Caesar cipher key."""
    return caesar_transform(ciphertext, key, encrypting=False)


def brute_force(ciphertext: str) -> dict[int, str]:
    """Return a dict mapping key -> attempt for keys 1..25."""
    results = {}
    for k in range(1, 26):
        results[k] = decrypt(ciphertext, k)
    return results


def _read_input_text(args: argparse.Namespace) -> str:
    """Read text from --text, --input-file, or stdin (interactive)."""
    if args.text is not None:
        return args.text
    if args.input:
        try:
            with open(args.input, 'r', encoding='utf-8') as f:
                return f.read()
        except Exception as e:
            logger.error(f"Error reading input file '{args.input}': {e}")
            sys.exit(2)
    # fallback: read from stdin (useful for piping)
    if not sys.stdin.isatty():
        return sys.stdin.read()
    # interactive prompt
    prompt = "Masukkan teks: "
    return input(prompt)


def _write_output_text(args: argparse.Namespace, out_text: str) -> None:
    """Write output to file if provided, otherwise to stdout."""
    if args.output:
        try:
            with open(args.output, 'w', encoding='utf-8') as f:
                f.write(out_text)
            logger.info(f"Hasil ditulis ke file: {args.output}")
        except Exception as e:
            logger.error(f"Error menulis output file '{args.output}': {e}")
            sys.exit(2)
    else:
        # print to stdout
        print(out_text)


def parse_args(argv: Optional[list[str]] = None) -> argparse.Namespace:
    p = argparse.ArgumentParser(prog="simple_crypto.py", description="Caesar cipher utility (encrypt/decrypt/brute-force)")
    p.add_argument("-m", "--mode", choices=["e", "d", "b"], default=None,
                   help="Mode: e=encrypt, d=decrypt, b=brute-force")
    p.add_argument("-k", "--key", type=int, default=0, help="Key (integer). Can be negative or >26; normalized automatically.")
    p.add_argument("-t", "--text", type=str, default=None, help="Text to process (useful for quick commands).")
    p.add_argument("-i", "--input", type=str, default=None, help="Input filename (reads full file).")
    p.add_argument("-o", "--output", type=str, default=None, help="Output filename (writes result).")
    p.add_argument("--preview", action="store_true", help="Show preview result but do not write to output file.")
    p.add_argument("--run-tests", action="store_true", help="Run internal unit tests and exit.")
    p.add_argument("--quiet", action="store_true", help="Minimize logging (only errors).")
    return p.parse_args(argv)


def main(argv: Optional[list[str]] = None) -> None:
    args = parse_args(argv)

    if args.quiet:
        logger.setLevel(logging.ERROR)

    if args.run_tests:
        # run unit tests by invoking the test module
        import unittest

        class SimpleCryptoTests(unittest.TestCase):
            def test_normalize_key(self):
                self.assertEqual(_normalize_key(0), 0)
                self.assertEqual(_normalize_key(26), 0)
                self.assertEqual(_normalize_key(-1), 25)
                self.assertEqual(_normalize_key(27), 1)

            def test_shift_char_preserve(self):
                self.assertEqual(_shift_char('A', 1), 'B')
                self.assertEqual(_shift_char('z', 2), 'b')
                self.assertEqual(_shift_char('!', 5), '!')
                self.assertEqual(_shift_char('a', 26), 'a')

            def test_encrypt_decrypt_roundtrip(self):
                t = "Halo Bro! 123"
                k = 5
                c = encrypt(t, k)
                self.assertNotEqual(c, t)
                self.assertEqual(decrypt(c, k), t)

            def test_bruteforce_contains_plain(self):
                plain = "Secret"
                k = 7
                c = encrypt(plain, k)
                bf = brute_force(c)
                self.assertIn(k, bf)
                self.assertEqual(bf[k], plain)

        suite = unittest.defaultTestLoader.loadTestsFromTestCase(SimpleCryptoTests)
        runner = unittest.TextTestRunner(verbosity=2)
        runner.run(suite)
        return

    # Determine mode: priority CLI mode, else ask interactively
    mode = args.mode
    if mode is None:
        mode = input("Pilih mode (e=encrypt, d=decrypt, b=brute force): ").strip().lower()
        if mode not in ("e", "d", "b"):
            logger.error("Mode tidak valid. Gunakan e/d/b.")
            sys.exit(1)

    text = _read_input_text(args)

    if mode == "e":
        if args.key == 0:
            # if key was default 0 and not provided via CLI, prompt user
            try:
                k = int(input("Masukkan key (1-25; bisa negatif atau >26): ").strip())
            except ValueError:
                logger.error("Key tidak valid (harus integer).")
                sys.exit(1)
        else:
            k = args.key
        out = encrypt(text, k)
        logger.info(f"Plaintext  : {text}")
        logger.info(f"Ciphertext : {out}")

    elif mode == "d":
        if args.key == 0:
            try:
                k = int(input("Masukkan key (1-25; bisa negatif atau >26): ").strip())
            except ValueError:
                logger.error("Key tidak valid (harus integer).")
                sys.exit(1)
        else:
            k = args.key
        out = decrypt(text, k)
        logger.info(f"Ciphertext : {text}")
        logger.info(f"Plaintext  : {out}")

    else:  # brute-force
        results = brute_force(text)
        # format nicely
        lines = [f"Key {k:2}: {v}" for k, v in results.items()]
        out = "\n".join(lines)
        logger.info("Brute-force results (keys 1..25):")

    # Preview prints result to stdout regardless of --output; user explicitly asked preview
    if args.preview:
        print("\n=== Preview ===")
        print(out)
        print("=== End Preview ===")
    else:
        # write to file or stdout depending on args
        _write_output_text(args, out)


if __name__ == "__main__":
    main()

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
1. Komponen Utama Kriptosistem
Sebuah kriptosistem didefinisikan oleh enam komponen inti yang bekerja sama untuk menjamin kerahasiaan data. Komponen-komponen ini meliputi Plaintext, yaitu pesan yang belum disandikan; Ciphertext, yaitu pesan yang telah diacak dan tidak dapat dibaca; Algoritma, yaitu serangkaian aturan matematis formal yang menentukan proses enkripsi dan dekripsi; dan Kunci, yaitu nilai rahasia yang mengontrol operasi Algoritma. Kedua proses krusial yang menghubungkan komponen-komponen ini adalah Enkripsi (mengubah Plaintext menjadi Ciphertext) dan Dekripsi (memulihkan Ciphertext menjadi Plaintext).

2. Kelebihan dan Kelemahan Sistem Simetris dibandingkan Asimetris
Kriptosistem terbagi menjadi dua kelas utama yang memiliki kelebihan dan kelemahan kontras. Sistem Simetris memiliki keunggulan signifikan dalam kecepatan dan efisiensi pemrosesan data, menjadikannya pilihan ideal untuk enkripsi data dalam volume besar karena ia hanya menggunakan satu kunci rahasia. Sebaliknya, Sistem Asimetris jauh lebih lambat karena membutuhkan daya komputasi yang lebih besar; namun, keunggulan utamanya terletak pada kemampuannya memecahkan masalah distribusi kunci dengan menggunakan pasangan kunci Publik dan Privat, dan juga secara inheren mendukung Tanda Tangan Digital.

3. Mengapa Distribusi Kunci Menjadi Masalah Utama dalam Kriptografi Simetris
Distribusi kunci merupakan masalah utama dalam kriptografi simetris karena seluruh keamanan sistem bergantung pada kerahasiaan satu kunci bersama yang digunakan oleh kedua belah pihak. Kunci ini harus dikirimkan dari pengirim ke penerima melalui saluran yang sudah dijamin keamanannya sebelum komunikasi terenkripsi dapat dimulai. Jika kunci dicegat oleh pihak ketiga selama proses distribusi, seluruh komunikasi yang dienkripsi menggunakan kunci tersebut akan terkompromi. Selain itu, masalah ini menjadi tidak praktis dan sulit dikelola (non-scalable) ketika jumlah pengguna dalam jaringan meningkat, karena setiap pasangan pengguna memerlukan kunci rahasia unik tersendiri.

## 8. Kesimpulan
Berdasarkan percobaan dan analisis yang dilakukan, dapat disimpulkan bahwa kriptosistem berfungsi melalui dua proses berlawanan, yaitu Enkripsi dan Dekripsi, yang keduanya bergantung pada kombinasi spesifik Algoritma dan Kunci untuk mengubah Plaintext menjadi Ciphertext dan sebaliknya. Perbandingan antara sistem simetris yang cepat namun bermasalah dalam distribusi kunci, dengan sistem asimetris yang lambat namun aman dalam pertukaran kunci, menegaskan bahwa pemilihan kriptosistem harus disesuaikan dengan kebutuhan kecepatan dan mekanisme pertukaran kunci yang diinginkan.

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
commit cryptosystem
Author: Dimas Riyan Hidayat <dimasriyanhidayat01@gmail.com>
Date:   2025-10-12

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
