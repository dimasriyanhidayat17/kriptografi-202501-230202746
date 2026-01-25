# Laporan Praktikum Kriptografi
Minggu ke-:XV
Topik: TinyCoin ERC20  
Nama: Dimas Riyan hidayat  
NIM: 230202746
Kelas: 5IKRB  

---

## 1. Tujuan
1. Mengembangkan proyek sederhana berbasis algoritma kriptografi.
2. Mendokumentasikan proses implementasi proyek ke dalam repository Git.
3. Menyusun laporan teknis hasil proyek akhir.


## 2. Dasar Teori
1. Blockchain

Blockchain merupakan teknologi penyimpanan data berbasis jaringan terdistribusi yang memungkinkan transaksi dicatat secara permanen dalam bentuk blok-blok yang saling terhubung. Setiap blok berisi informasi transaksi yang telah diverifikasi oleh jaringan, sehingga data yang tersimpan sulit untuk diubah atau dimanipulasi. Teknologi blockchain banyak digunakan dalam sistem keuangan digital karena sifatnya yang transparan, aman, dan tidak bergantung pada pihak pusat (decentralized).

2. Ethereum

Ethereum adalah salah satu platform blockchain yang mendukung pengembangan aplikasi terdesentralisasi (Decentralized Applications atau DApps). Berbeda dengan blockchain Bitcoin yang hanya fokus pada transaksi mata uang digital, Ethereum menyediakan fitur tambahan berupa smart contract, yaitu program otomatis yang dapat dijalankan langsung di blockchain. Ethereum menjadi ekosistem utama dalam pengembangan token digital dan aplikasi berbasis blockchain.

3. Smart Contract

Smart contract merupakan program komputer yang berjalan di atas blockchain dan dapat mengeksekusi perintah secara otomatis ketika kondisi tertentu terpenuhi. Smart contract digunakan untuk mengurangi kebutuhan pihak ketiga dalam transaksi digital karena semua aturan telah tertanam di dalam kode program. Namun, smart contract bersifat immutable, artinya kode yang telah dideploy tidak dapat diubah, sehingga pengujian dan keamanan menjadi aspek yang sangat penting.

4. Token dalam Blockchain

Token adalah aset digital yang dibuat dan dijalankan di atas jaringan blockchain. Token dapat digunakan sebagai alat pembayaran, representasi kepemilikan, maupun akses layanan tertentu dalam suatu sistem. Dalam ekosistem Ethereum, token biasanya dibuat menggunakan standar tertentu agar dapat digunakan secara luas oleh berbagai aplikasi dan wallet.

5. Standar ERC20

ERC20 merupakan standar token yang paling umum digunakan pada jaringan Ethereum. Standar ini mendefinisikan sekumpulan fungsi dasar yang harus dimiliki oleh token agar kompatibel dengan berbagai platform seperti MetaMask, exchange, dan aplikasi DeFi. Beberapa fungsi utama dalam ERC20 meliputi transfer, balanceOf, approve, dan totalSupply. Dengan adanya ERC20, token dapat berinteraksi secara konsisten dalam ekosistem Ethereum.

6. Mekanisme Transfer Token ERC20

Transfer token pada kontrak ERC20 dilakukan melalui fungsi transfer(address to, uint256 amount). Proses ini dimulai dengan pengecekan saldo pengirim, kemudian kontrak akan mengurangi saldo pengirim dan menambahkan saldo penerima sesuai jumlah token yang dikirim. Setiap transaksi transfer akan dicatat melalui event Transfer, sehingga aktivitas token dapat dipantau secara transparan melalui blockchain explorer.

7. Keamanan Smart Contract

Keamanan smart contract merupakan hal penting karena kontrak yang telah dideploy tidak dapat diubah. Risiko umum dalam smart contract meliputi serangan reentrancy, kesalahan logika program, serta akses fungsi yang tidak dibatasi. Mitigasi dapat dilakukan dengan menggunakan library terpercaya seperti OpenZeppelin, menerapkan kontrol akses seperti onlyOwner, serta melakukan audit dan pengujian di jaringan testnet sebelum digunakan di mainnet.

8. Sepolia Testnet

Sepolia merupakan jaringan testnet Ethereum yang digunakan untuk pengujian smart contract tanpa menggunakan ETH asli. Sepolia menyediakan ETH gratis melalui faucet sehingga developer dapat melakukan deployment dan simulasi transaksi secara aman. Penggunaan testnet sangat penting dalam tahap pengembangan untuk menghindari kerugian finansial sebelum aplikasi dijalankan di jaringan utama.

## 3. Alat dan Bahan
- metamask
- Git dan akun GitHub  
- remix IDE

## 4. Langkah Percobaan
- masuk metamask
- copy address wallet
- masuk ke remix IDE
- buat file nya
- ikuti ketentuannya
- lalu deploy

---

## 5. Source Code
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract TinyCoin is ERC20 {
    constructor(uint256 initialSupply) ERC20("TinyCoin", "TNC") {
        _mint(msg.sender, initialSupply);
    }
}

## 6. Hasil dan Pembahasan
<img width="1910" height="1078" alt="image" src="https://github.com/user-attachments/assets/13b7e6d9-9c55-49fb-b131-d471f0732397" />


## 7. Jawaban Pertanyaan
1. Apa fungsi utama ERC20 dalam ekosistem blockchain?

ERC20 berfungsi sebagai standar utama dalam pembuatan token di jaringan Ethereum. Dengan adanya standar ini, token yang dibuat menjadi lebih mudah dikenali dan kompatibel dengan berbagai aplikasi blockchain seperti wallet, exchange, dan platform DeFi. ERC20 membantu memastikan bahwa setiap token memiliki fungsi dasar yang seragam, sehingga pengguna dapat melakukan transaksi token dengan cara yang konsisten dan aman di seluruh ekosistem Ethereum.

2. Bagaimana mekanisme transfer token bekerja dalam kontrak ERC20?

Mekanisme transfer token dalam kontrak ERC20 berjalan melalui fungsi transfer, di mana pengirim menentukan alamat penerima serta jumlah token yang ingin dikirim. Smart contract kemudian memverifikasi apakah saldo pengirim mencukupi, setelah itu saldo pengirim akan dikurangi dan saldo penerima ditambahkan sesuai jumlah token yang ditransfer. Semua proses ini dicatat secara permanen di blockchain melalui event Transfer, sehingga transaksi dapat dilacak dengan transparan.

3. Apa risiko utama dalam implementasi smart contract dan bagaimana cara mitigasinya?

Risiko utama dalam implementasi smart contract meliputi serangan reentrancy, kesalahan perhitungan seperti overflow, serta akses fungsi yang tidak dibatasi dengan baik. Jika kontrak tidak dirancang dengan aman, penyerang dapat mengeksploitasi celah tersebut untuk merugikan sistem. Cara mitigasinya adalah dengan menggunakan library terpercaya seperti OpenZeppelin, menerapkan kontrol akses seperti onlyOwner, melakukan pengujian menyeluruh di testnet, serta menjalankan audit kode sebelum kontrak digunakan di jaringan utama.

## 8. Kesimpulan
Berdasarkan hasil implementasi dan pengujian smart contract ERC20 TinyCoin, dapat disimpulkan bahwa standar ERC20 merupakan salah satu komponen penting dalam ekosistem blockchain Ethereum karena menyediakan aturan baku dalam pembuatan dan pengelolaan token digital. Melalui kontrak TinyCoin, token berhasil dibuat dan dideploy pada jaringan Sepolia testnet, serta dapat menjalankan fungsi utama seperti pencetakan supply awal, pengecekan saldo, dan transfer token antar alamat wallet.

Mekanisme transfer token pada ERC20 bekerja dengan cara mengurangi saldo pengirim dan menambahkan saldo penerima secara otomatis melalui smart contract, serta seluruh transaksi tercatat secara transparan di blockchain. Selain itu, penggunaan library OpenZeppelin membantu meningkatkan keamanan kontrak dengan menyediakan implementasi standar yang telah banyak diuji.

Namun, smart contract tetap memiliki potensi risiko seperti reentrancy attack, kesalahan logika, dan akses fungsi yang tidak dibatasi. Oleh karena itu, pengujian pada testnet seperti Sepolia serta penerapan kontrol keamanan sangat diperlukan sebelum kontrak digunakan pada jaringan utama. Dengan demikian, pengembangan token berbasis ERC20 menjadi langkah awal yang efektif dalam memahami teknologi blockchain dan penerapan smart contract secara praktis.

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log

```
week15-tinycoin-erc20
Author: Dimas Riyan Hidayat <dimasriyanhidayat01@gmail.com>
Date:   2025-09-20


```
