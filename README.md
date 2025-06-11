# DATA ARBUTUS
A. KAS DAN SETARA KAS

Masuk terlebih dahulu ke akun utama untuk melaksanakan Test of Control berupa Integrity Test, yang mencakup tiga aspek: Verify, Duplicate, dan Gap:
1) Verify bertujuan untuk memastikan bahwa setiap isian data sudah sesuai dengan desain sistem. Sebagai contoh, kolom yang ditujukan untuk karakter, angka, atau tanggal harus diisi dengan data yang sesuai dengan tipe yang telah ditentukan. Berdasarkan hasil verify tidak ada kesalahan dalam akun kas.

![image](https://github.com/user-attachments/assets/e42b8172-16dd-43d0-ade0-45c259004755)

2) Duplicate digunakan untuk memeriksa apakah terdapat data yang seharusnya bersifat unik namun muncul lebih dari satu kali. Kemunculan data ganda merupakan tanda bahwa sistem tidak berjalan sebagaimana mestinya. Oleh karena itu, jika setelah dilakukan pengecekan pada elemen unik seperti nomor voucher tidak ditemukan duplikasi, maka dapat disimpulkan bahwa tidak terjadi kesalahan dalam penomoran transaksi.


![image](https://github.com/user-attachments/assets/702b56fb-6130-41b7-a2b6-7ce11c7af04b)

3) Gap digunakan untuk mengevaluasi apakah terdapat nomor urut yang tercetak namun tidak tercatat dalam sistem. Ketidaksesuaian ini umumnya menjadi indikasi adanya kesalahan pencatatan. Dalam konteks test of control, hilangnya nomor urut yang tercetak bisa disebabkan oleh pengabaian prosedur yang seharusnya dijalankan secara sistematis. Setelah dilakukan analisis terhadap gap, ditemukan adanya selisih pada nomor transaksi antara 1 hingga 21.000. Namun, hal ini terjadi karena perusahaan baru mulai beroperasi pada tahun 2021, sehingga penomoran transaksi dimulai dari 21001, bukan dari angka 1. Dengan demikian, temuan tersebut dianggap tidak signifikan.

![image](https://github.com/user-attachments/assets/8698a65a-6a3a-4b4f-8cf0-73b4cec85ea8)

B. TEST OF CONTROL (ATTRIBUTE SAMPLING)

Selanjutnya, dilakukan pengujian pengendalian menggunakan metode attribute sampling yang berfokus pada proses otorisasi, yang terdiri dari tiga tingkat otorisasi, yaitu:
1) Pengeluaran dengan nilai antara Rp20.000.000 hingga Rp50.000.000 harus mendapatkan persetujuan dari kepala bagian.
![image](https://github.com/user-attachments/assets/cf31be40-e6a4-4ab7-aee5-89f237dc875c)

Jadi, pada bagian kas di general ledger, saya melakukan proses ekstraksi data dan menggabungkannya dengan rumus seperti yang ditampilkan pada gambar. Setelah rumus diterapkan, hasil akhirnya dapat dilihat seperti di bawah ini:
![image](https://github.com/user-attachments/assets/c8fa735c-af5f-49c9-bd54-d3e4e406c04a)

Pada bagian ini, transaksi telah disaring berdasarkan nominal antara 20.000.000 hingga 50.000.000, sesuai dengan ketentuan otorisasi level 1.

2) Pengeluaran dengan nominal antara Rp50.000.000 hingga Rp100.000.000 harus mendapatkan persetujuan dari manajer keuangan.
![image](https://github.com/user-attachments/assets/122b4b5a-3cf4-4157-830b-45bdbd3576c4)

Jadi, pada bagian general ledger kas, saya melakukan proses ekstraksi data dan menggabungkannya dengan rumus sesuai yang ditunjukkan pada gambar. Setelah penerapan rumus tersebut, diperoleh hasil seperti yang ditampilkan di bawah ini:
![image](https://github.com/user-attachments/assets/8085952d-0184-4b06-8f0d-7bbacc0581d5)

Pada bagian ini, transaksi sudah difilter dengan nominal antara 50.000.000 hingga 100.000.000 untuk otorisasi level 2.

3) Pengeluaran lebih dari 100.000.000 memerlukan otorisasi dari direktur utama.
![image](https://github.com/user-attachments/assets/dc14a54e-1695-482f-a06d-d63e3d3086e2)

Jadi, pada bagian kas di general ledger, saya melakukan proses ekstraksi data dan menerapkan rumus sesuai dengan yang ditampilkan pada gambar. Setelah rumus diterapkan, hasil akhirnya tampak seperti di bawah ini:
![image](https://github.com/user-attachments/assets/167dff1d-bb02-467f-8738-fc70e3b8ae56)

Pada bagian ini, transaksi sudah difilter dengan nominal lebih dari 100.000.000 untuk otorisasi level 3.

C. PIUTANG

Selanjutnya, Lakukan test integritas verify ,duplicate, dan gaps.

![image](https://github.com/user-attachments/assets/f1802608-cfa5-4c75-8f00-f4812925cf2e)

![image](https://github.com/user-attachments/assets/6980f4ac-4169-427c-947f-58b2f02a5869)

![image](https://github.com/user-attachments/assets/a3faaf4a-6ff0-448c-9ca6-3375a0ce7ddc)

![image](https://github.com/user-attachments/assets/66f4e74c-bda2-4510-8799-a661852bb4ac)

![image](https://github.com/user-attachments/assets/1c19e435-1176-4b98-8306-d2e11ee02b8d) 

![image](https://github.com/user-attachments/assets/3cdcd050-9241-41d2-b1e9-ed5d448790a8)

- Hasil dari proses verify menunjukkan bahwa tidak ditemukan kesalahan pada akun piutang.
- Dari hasil duplicate, teridentifikasi 263 duplikasi pada nomor pelanggan. Namun, hal ini masih dianggap normal karena pelanggan kemungkinan melakukan pembelian lebih dari satu kali sehingga membutuhkan nomor pelanggan.
- Dari hasil gaps, ditemukan 35 celah pada urutan nomor pelanggan. Meski demikian, hal ini masih dapat diterima karena kemungkinan ada beberapa pelanggan yang sudah tidak lagi melakukan transaksi dengan Realsa.

D. TEST OF DETAILS (PARAMETER)

Untuk melakukan pemeriksaan:
1) Cek customer yang nilai transaksinya melebihi credit limitnya
![image](https://github.com/user-attachments/assets/da85fd8f-3ce1-43a4-9e05-bd4a6db3c10f)
Masukan rumusnya di extract kemudian lakukan. Maka, telah ditemukan ada 2 transaksi melebihi kredit:
![image](https://github.com/user-attachments/assets/94308410-36d1-475f-90e4-a17f65aa3867)
2) Cek transaksi piutang yang bersaldo negatif
![image](https://github.com/user-attachments/assets/a206eb07-e4a1-4181-9966-97777f55ea04)
![image](https://github.com/user-attachments/assets/4d37dce6-6a26-483b-b03b-b469608af178)
![image](https://github.com/user-attachments/assets/16d6e62d-edd8-495c-8f50-b8f137c0c93f)

Kita mengikuti perhitungan sesuai rumus pada gambar, namun ternyata terdapat piutang negatif sebesar Rp3.238.500, dengan rincian transaksi seperti yang ditampilkan pada gambar diatas.

E. ANALISIS PIUTANG

![image](https://github.com/user-attachments/assets/f2414685-87d4-44cb-8ea1-ec5188112023)
- Berdasarkan hasil analisis umur piutang, diketahui terdapat 167 transaksi yang akan jatuh tempo dalam waktu 0 hingga 30 hari ke depan. Selain itu, terdapat sekitar 123 transaksi piutang yang sudah melewati jatuh tempo namun belum dibayarkan oleh pelanggan.
- Kemudian, terdapat 6 transaksi piutang yang diperkirakan akan jatuh tempo dalam lebih dari 30 hari.
- Terdapat juga 1 transaksi dengan umur piutang antara 151 hingga 180 hari, serta 2 transaksi lainnya yang sudah jatuh tempo lebih dari 180 hari.

Detail transaksi tersebut dapat dilihat pada foto di bawah ini:
![image](https://github.com/user-attachments/assets/c5712e92-7a2e-4a9d-ab0f-3ca2b0dc81dc)
![image](https://github.com/user-attachments/assets/1a9d4a08-25d5-42e0-a5ac-79fbe130a4ae)
![image](https://github.com/user-attachments/assets/edb76eb5-5c87-470d-84cb-5b119bb8dd64)

F. INVENTORY

Seperti biasa, lakukan pengujian Integritas, Verify, Duplicate, dan Gaps.
1) Berdasarkan hasil verifiy, adanya kesalahan pada transaksi nomor urut 13, di mana tidak ada tanggal yang tertera dalam transaksi tersebut, masuk ke dalam temuan:

![image](https://github.com/user-attachments/assets/04c16201-c5a4-4e8e-91c1-48c465f36ade)
![image](https://github.com/user-attachments/assets/e60f5d9d-1df1-4476-a949-03ec26caff3e)

2) Berdasarkan Duplicates, tidak ada kesalahan dalam data inventory.

![image](https://github.com/user-attachments/assets/e7164d90-fa65-4edb-be0b-6222b6144292)

3) Berdasarkan hasil gaps, ternyata ada 34 gaps, tapi itu merupakan hal wajar karena tidak selalu tiap hari ada transaksi, jadi ada tanggal di mana tidak ada transaksi.
   
![image](https://github.com/user-attachments/assets/37413132-ecf6-439f-a5d2-8c986d4c4a29)
![image](https://github.com/user-attachments/assets/33c3d52a-8849-4dac-9821-96f893643a02)

4) Melakukan Total Verify -> Ada total sekian dan ternyata sesuai dengan total inventory di laporan keuangan.

![image](https://github.com/user-attachments/assets/97e8d91b-a1c6-4404-97a7-b34c6aadef9e)

G. ANALISIS STATISTIK

1) Persediaan Minus

![image](https://github.com/user-attachments/assets/a0fe8e2c-e059-40fb-b584-d5b369757511)

![gambar](https://github.com/user-attachments/assets/f1be555b-b973-4ffe-b33d-e21521927b95)

![gambar](https://github.com/user-attachments/assets/fcb0c9f7-a182-4c83-9bdd-9ef284fbd47b)

Hasil analisis statistik menunjukkan adanya nilai persediaan negatif sebesar 200 ribu, disertai rincian transaksi terkait. Padahal, secara logika piutang seharusnya tidak bisa bernilai negatif. Hal ini tergolong sebagai sebuah temuan.

2) Aset Tetap -> Membandingkan saldo aset tetap di neraca dengan daftar aset
![gambar](https://github.com/user-attachments/assets/699c3ae5-9d19-4c95-81da-2bc8db29b4d0)
- Pada foto dibawah ini, dilakukan analisis crosstab terhadap data untuk membandingkan saldo aset tetap yang tercantum di neraca dalam pembukuan dengan hasil perhitungan harga perolehan aset menggunakan Arbutus.
![gambar](https://github.com/user-attachments/assets/4bea1b83-54f2-467c-b773-3cebebe37b88)
- Pada foto dibawah ini, dilakukan analisis crosstab terhadap data dan perbandingan antara akumulasi penyusutan tahun 2020 yang tercatat di neraca dalam buku dengan hasil perhitungan akumulasi penyusutan aset tahun 2020 menggunakan Arbutus.
![gambar](https://github.com/user-attachments/assets/41d06676-9e82-4d99-974e-6c3a9cc4f487)
- Pada foto dibawah ini, dilakukan analisis crosstab terhadap data dan perbandingan antara akumulasi penyusutan tahun 2021 yang tercantum di neraca buku dengan hasil perhitungan akumulasi penyusutan tahun 2021 aset menggunakan Arbutus.
![gambar](https://github.com/user-attachments/assets/4acfdb76-d324-4990-895c-81a0c16d2396)

Jadi, setelah melakukan pencocokan harga perolehan, akumulasi penyusutan 2021, dan 2022. Kita melakukan analisis dengan rumus expression untuk menilai perhitungan aset tetap yang dilakukan manajemen itu benar dan salah.
![gambar](https://github.com/user-attachments/assets/b60eba58-d4df-464d-b02f-12c8039eecbb)

Setelah itu, diketahui terdapat 5 kesalahan dalam penilaian penyajian aset tetap, khususnya terkait pengakuan biaya penyusutan dan akumulasi penyusutan. Selisih yang bersifat positif menunjukkan bahwa penyusutan disajikan melebihi jumlah yang seharusnya. Sebaliknya, selisih yang bersifat negatif menunjukkan bahwa penyusutan disajikan lebih rendah dari yang seharusnya.
![gambar](https://github.com/user-attachments/assets/93269d3d-fe16-48b4-bd50-5d67d94f7e9c)


H. UTANG

Tes integritas, seperti Uji Total, Verify, Duplicates
![gambar](https://github.com/user-attachments/assets/aeab3337-e88e-4343-8ec1-c482d5a95610)
![gambar](https://github.com/user-attachments/assets/5ddb1de9-c73b-44dd-8e31-46f8727724bd)

- Total utang tercatat sebesar 155.267.110 berdasarkan laporan keuangan.
- Hasil uji verifikasi menunjukkan tidak terdapat temuan, yang berarti tidak ada kesalahan atau kolom yang kosong.
- Sementara itu, hasil uji duplikasi mengindikasikan adanya kemiripan pada nomor transaksi, meskipun nomor vendor yang digunakan sama. Temuan ini perlu diklarifikasi lebih lanjut dengan pihak manajemen.

Tes Detail Parameter
1) Analyse – Clasify (Sepuluh kreditur dengan jumlah saldo terbesar)
![gambar](https://github.com/user-attachments/assets/a2bbbcb6-6714-44c8-ad97-e5592caf8a46)
2) Lima kreditur dengan masa utang paling lama
![gambar](https://github.com/user-attachments/assets/ae2f4d8e-0b62-4773-a6bb-4ffd35408ba7)

Setelah dilakukan analisis umur utang, diketahui bahwa tidak ada utang yang akan jatuh tempo dalam 30 hari ke depan, maupun utang yang telah melewati tanggal jatuh temponya. Selanjutnya, dapat diketahui bahwa utang dengan masa jatuh tempo terpanjang terdapat pada gambar kedua, yaitu utang yang dimulai pada 5 November 2021 dan jatuh tempo pada 5 Januari 2022.
