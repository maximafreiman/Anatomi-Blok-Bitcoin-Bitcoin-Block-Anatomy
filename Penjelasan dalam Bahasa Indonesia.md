Anatomi Block Bitcoin
---
Halo semuanya. Apa kabar? Baik, puji syukur. Kurang baik? Besok bisa jadi akan membaik.

Kali ini, tiba-tiba kepikiran aja gitu. Di masa senggang begini, adakalanya aku mau tulis sesuatu yang sebenarnya fundamental. Ya, seperti yang udah ditulis di judul, tentu saja. Aku mau menjelaskan mengenai seperti apa block Bitcoin itu sebenernya. Dan ya, aku akan membahas ini dengan bahasa yang sederhana sekali.

Sebelum aku mulai masuk ke inti pembahasan, aku akan buka pembahasan ini dengan 1 kalimat:


**"Kalau mau membayangkan blok bitcoin itu seperti apa, anggap aja itu seperti sebuah brankas yang berisi "dokumen" data transaksi. Brankas ini punya label identitasnya sendiri dalam bentuk kode yang dimana semua datanya (label dan isi brankas) tidak bisa dimanipulasi, karena semuanya dibuat secara otomatis dengan kekuatan konsensus mesin/komputer)."**

Karena "brankas ini" (block bitcoin) ini isinya adalah data transaksi, maka kita akan mulai semuanya dari data transaksi dulu.

Anggap saja data transaksi ini seperti dalam bentuk dokumen. Dokumen yang berisi rincian transaksi menggunakan bitcoin. Ada 2 jenis transaksi disini, yaitu Coinbase Transaction dan Normal Transaction.

**A. Coinbase Transaction**

Singkatnya gini, ini adalah transaksi untuk miner, dimana miner berhasil membuat blok bitcoin + dapet fee juga tiap transaksi. Semua dicatat dalam "dokumen transaksi" dengan format seperti ini: 
![1](https://github.com/user-attachments/assets/44a8beca-8e3c-4925-964b-d77bcc14e167)
Sederhana sebenernya. Isinya adalah catatan berapa blok yang berhasil dibuat miner + total fee transaksi dalam kurun waktu sebelum menit. Adapun breakdown yang dibagian bawah, itu cuma sebagai dasar aja biar tau total fee itu dari hasil fee berbagai transaksi bitcoin yang ditotalkan, dan breakdown fee sebenernya nggak ditulis, cuma aku tambahkan biar tau aja total fee dari mana.

Sederhana kan? Blok yang berhasil dibuat + Total fee semua transaksi yang tercatat selama kurun waktu kurang lebih 10 menit. 

Pertanyaannya, bagaimana miner ini bisa dapat fee dari setiap transaksi? Disinilah kita akan bahas bagaimana transaksi dalam Bitcoin ini terjadi.

**B. Normal Transaction**

Anggaplah ada seseorang, Bu Yayuk namanya. Dia mau beli cabe seharga 4 BTC (Ini cabe carolina reaper 1 ton kayaknya). Dia mau beli cabe tersebut ke Bu Erni. Bu Yayuk punya 10 BTC. Secara aturan konsensus bitcoin, dia tidak bisa mengirim 4 BTC saja secara langsung, melainkan dia harus kirim semua 10 BTC nya ke bu Erni dulu. Secara otomatis, setelah Bu Erni dapat 10 BTC, kembalian akan dikirim ke Bu Yayuk sejumlah 6,01 BTC. Adapun Bu Erni, dia akhirnya dapat 3,99 BTC. Kenapa tidak 4 BTC secara utuh? 

Disinilah "biaya admin" atau fee untuk miner berlaku. Pada saat Bu Yayuk mengirim BTC ke Bu Erni, Bu Yayuk juga kena ongkos kirim sejumlah 0,01 BTC ke miner.

Nah, skema visualnya kurang lebih kayak gini:

![2](https://github.com/user-attachments/assets/f49662a9-bf7e-4dab-a159-597512b49e74)

Nah ini adalah rangkaian transaksi yang terjadi dalam Bitcoin. Jadi lebih mirip seperti koin cash, hanya saja dalam bentuk digital.


--


Nah, itu tadi adalah satu rangkaian bentuk transaksi pakai Bitcoin. Dan semuanya tercatat dalam 1 dokumen yang detail seperti ini:

![3](https://github.com/user-attachments/assets/072913ce-63e4-4522-afe4-a9d51dfb6211)

Satu data dokumen transaksi berisi alamat pengirim, detail aktivitas transaksi, dan alamat penerima.

--

Transaksi dalam Bitcoin itu nggak cuma sekali doang. Dan setiap transaksi, terdokumentasi seperti contoh transaksi antara Bu Yayuk dan Bu Erni. Makanya, ada 2 jenis data transaksi yang dicatat disini:

1 coinbase transaction, dan banyak normal transaction.

![4](https://github.com/user-attachments/assets/ad769b69-2ee8-4fde-afcf-0c015810f88f)

--

Sekarang, ada 1 masalah. Kalau data transaksi yang ditulis sedetail itu, pastinya akan butuh verifikasi waktu yang lama dan rawan manipulasi. Karena kan transaksi yang terjadi banyak banget. Untuk efisiensi dalam pencatatan data transaksi, akhirnya masing-masing transaksi beserta datanya "dirangkum" menjadi 1 kode acak untuk setiap transaksi.

Inilah yang disebut dengan TXID.

![5](https://github.com/user-attachments/assets/ba6ed1af-a0a0-44ae-8e9b-684280da8e22)

Sekali data transaksi ini berubah, maka seluruh huruf dan angka yang ada dalam kode TXID akan berubah. Makanya, transaksi menggunakan bitcoin itu pencatatannya immutable, alias sangat susah buat dimanipulasi.

--

Jadi sekarang, semua transaksi baik coinbase atau normal transaction, sudah dikumpulkan dan masing-masing dirangkum dalam bentuk kode TXID. Sekarang waktunya untuk memasukkan semua TXID ini ke kotak brankas. Kotak brankas inilah yang disebut dengan **Block.** Dan brankas ini punya semacam "label". Label "brankas" ini disebut sebagai **Block Header**.


<img width="1920" height="1080" alt="bc1q9f3k7xw2m0s8p4v5r6t2j3h5n7a8e9d4c6b" src="https://github.com/user-attachments/assets/047669da-1bfe-43dc-b61b-b55c38fc46cf" />


Kalau dilihat-lihat, Block Header masih terlalu panjang dan detail. Sehingga berkat kekuatan SHA256 (kriptografi yang mengubah suatu data menjadi 1 tulisan huruf dan angka acak sejumlah 64 digit), Block header diringkas menjadi 1 label utuh dalam bentuk tulisan acak. Inilah yang disebut dengan **Block Hash.**


![7](https://github.com/user-attachments/assets/1175744a-82cc-4c50-ad33-69f1daae4af7)

--

Jadi, secara kesimpulan besarnya, block bitcoin itu anatominya seperti ini:

- Block Header: label tag berisi keterangan detail suatu blok. Dan Block Header juga dipersingkat isi kontennya menjadi 1 Block Hash
- Block Body: Brankas berisi kumpulan TXID (1 TXID berisi detail transaksi menggunakan Bitcoin). Dan TXID ada 2 macam, yaitu coinbase transation (tiap blok cuma 1), dan normal transaction

--------

Selesai. Boleh bertanya atau berdiskusi jika ada yg ingin bertanya.
Nodus meus lex mea.



