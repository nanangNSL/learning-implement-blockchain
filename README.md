# Implementasi Blockchain dengan Node.js

Implementasi sederhana dari blockchain menggunakan Node.js.

## Instalasi

1. Pastikan Anda telah menginstal Node.js di komputer Anda.
2. Clone repositori ini dengan perintah berikut:

   ```bash
   git clone https://github.com/nanangNSL/learning-implement-blockchain.git
   ```

3. Masuk ke direktori proyek:

   ```bash
   cd learning-implement-blockchain
   ```

4. Instal dependensi dengan menjalankan perintah:

   ```bash
   npm install
   ```

## Penggunaan

1. Jalankan aplikasi dengan perintah:

   ```bash
   npm start
   ```

2. Buka browser dan akses `http://localhost:7000` untuk mengakses aplikasi blockchain.
3. Ini adalah list node defaultnya kamu bebas ganti dengan port berapapun tapi jangan sama
  ```bash
  [
    "http://0.0.0.0:7000",
    "http://0.0.0.0:7001",
    "http://0.0.0.0:7002"
   ]
   ```
4. Melihat list nodes
   ```bash
   GET http://0.0.0.0:7000/nodes
   ```
   Hasilnya
   ```bash
   [
    "http://0.0.0.0:7001",
    "http://0.0.0.0:7002"
   ]
   ```
5. Posting transaksi blockchain
   ```bash
   POST http://0.0.0.0:4000/transaction
   ```
   Dengan data yang dikirimkan
   ```bash
   '{"from":"bd748a5a5479649cfd83132d3be99d0c1a2ebadc1e4c405e","to":"3be24b8dccf3c0a171c76b092e2a95f6e9d387eac6b647f1","amount": 1}'
   ```
   Content-Type: application/json dan jika berjalan baik maka
   ```bash
   {
      "success": 1
   }
     ```
6. Cara mengambil semua transaksi blockchain
   ```bash
   GET http://0.0.0.0:7000/transactions
   ```
   Hasilnya 
   ```bash
   [
    {
        "from": "bd748a5a5479649cfd83132d3be99d0c1a2ebadc1e4c405e",
        "to": "3be24b8dccf3c0a171c76b092e2a95f6e9d387eac6b647f1",
        "amount": 1,
        "timestamp": 1685433416
    }
   ]
   ```
7. Cara mengambil block yang di tambang
   ```bash
   GET http://0.0.0.0:7000/mine
   ```
   Hasilnya : 
   ```bash
   {
      "index": 1,
      "previousHash": "00002818703517bab21046d807a3fc0284b8a05979ce48baa40ed2eeeadd3b92",
      "hash": "000eb8c42f469eeb319c279e75cb8e3b6e59f63c5d712ea50aa66d242cc9b29f",
      "timestamp": 1685433712,
      "nonce": 1759,
      "transactions": [
         {
               "from": "bd748a5a5479649cfd83132d3be99d0c1a2ebadc1e4c405e",
               "to": "3be24b8dccf3c0a171c76b092e2a95f6e9d387eac6b647f1",
               "amount": 1,
               "timestamp": 1685433416
         }
      ]
   }
   ```
8. Cara mendapatkan Rantai data blockchain
   ```bash
   GET http://0.0.0.0:7000/blockchain
   ```
   Hasilnya :
   ```bash
   [
      {
         "index": 0,
         "previousHash": "0000000000000000",
         "hash": "00002818703517bab21046d807a3fc0284b8a05979ce48baa40ed2eeeadd3b92",
         "timestamp": 1685432641,
         "nonce": 4190,
         "transactions": []
      },
      {
         "index": 1,
         "previousHash": "00002818703517bab21046d807a3fc0284b8a05979ce48baa40ed2eeeadd3b92",
         "hash": "000eb8c42f469eeb319c279e75cb8e3b6e59f63c5d712ea50aa66d242cc9b29f",
         "timestamp": 1685433712,
         "nonce": 1759,
         "transactions": [
               {
                  "from": "bd748a5a5479649cfd83132d3be99d0c1a2ebadc1e4c405e",
                  "to": "3be24b8dccf3c0a171c76b092e2a95f6e9d387eac6b647f1",
                  "amount": 1,
                  "timestamp": 1685433416
               }
         ]
      }
      ]
      ```
9. Mengambil block berdasarkan index
   ```bash
   GET http://0.0.0.0:7000/blockchain/1
   ```
   Hasilnya :
   ```bash
   {
    "index": 1,
    "previousHash": "00002818703517bab21046d807a3fc0284b8a05979ce48baa40ed2eeeadd3b92",
    "hash": "000eb8c42f469eeb319c279e75cb8e3b6e59f63c5d712ea50aa66d242cc9b29f",
    "timestamp": 1685433712,
    "nonce": 1759,
    "transactions": [
        {
            "from": "bd748a5a5479649cfd83132d3be99d0c1a2ebadc1e4c405e",
            "to": "3be24b8dccf3c0a171c76b092e2a95f6e9d387eac6b647f1",
            "amount": 1,
            "timestamp": 1685433416
        }
    ]
   }
   ```
10. Mengambil index terakhir berdasarkan block terakhir
   ```bash
   GET http://0.0.0.0:7000/blockchain/last-index
   ```
   Hasilnya :
   ```bash
   1
   ```
  



## Kontribusi

Kontribusi selalu diterima. Jika Anda ingin berkontribusi pada proyek ini, ikuti langkah-langkah berikut:

1. Fork repositori ini.
2. Buat branch baru untuk fitur atau perbaikan yang ingin Anda tambahkan (`git checkout -b fitur-baru`).
3. Lakukan perubahan yang diinginkan dan commit perubahan Anda (`git commit -am 'Menambahkan fitur baru'`).
4. Push ke branch Anda di repositori Anda (`git push origin fitur-baru`).
5. Ajukan permintaan tarik (pull request) ke repositori ini.

## Lisensi

Diprogram dengan menggunakan lisensi [MIT](LICENSE).

Terima kasih kepada [nanangNSL](https://github.com/nanangNSL) atas kontribusi dan pembelajaran yang disediakan dalam proyek ini.
