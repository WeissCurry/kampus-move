# Smart Contract Data Mahasiswa SUI

Smart contract ini dibangun di atas blockchain SUI dan berfungsi untuk mengelola data mahasiswa. Ini adalah contoh sederhana yang menunjukkan cara membuat, memodifikasi, dan membaca data dari sebuah objek di SUI.

---

## Fitur Utama

Kontrak ini menyediakan beberapa fungsi dasar untuk manajemen data mahasiswa:

* **Pendaftaran Mahasiswa**: Membuat objek mahasiswa baru dengan informasi dasar.
* **Pengambilan Mata Kuliah**: Menambahkan jumlah SKS yang telah diambil oleh mahasiswa.
* **Status Kelulusan**: Memperbarui status kelulusan mahasiswa jika syarat SKS minimum telah terpenuhi.
* **Informasi Mahasiswa**: Mengambil detail penting dari data mahasiswa.

---

## Struktur Data

Smart contract ini mendefinisikan satu struct utama:

### `Mahasiswa`

Struct ini merepresentasikan data lengkap seorang mahasiswa.

* `id`: **UID** unik untuk mengidentifikasi objek `Mahasiswa`.
* `nama`: Nama lengkap mahasiswa (**String**).
* `nim`: Nomor Induk Mahasiswa (**u32**).
* `jurusan`: Jurusan yang diambil (**String**).
* `umur`: Usia mahasiswa (**u8**).
* `total_sks`: Jumlah total Satuan Kredit Semester yang telah diambil (**u64**).
* `aktif`: Status keaktifan mahasiswa (**bool**).
* `lulus`: Status kelulusan mahasiswa (**bool**).

---

## Fungsi-Fungsi (Public)

Berikut adalah fungsi-fungsi yang dapat dipanggil oleh pengguna:

### `daftar_mahasiswa`

Menciptakan objek `Mahasiswa` baru dan mengembalikannya.

* **Parameter:** `nama`, `nim`, `jurusan`, `umur`
* **Mengembalikan:** `Mahasiswa`

### `ambil_mata_kuliah`

Menambahkan jumlah SKS ke dalam data mahasiswa.

* **Parameter:** `mhs` (objek **Mahasiswa**), `sks` (**u64**)

### `set_lulus`

Memeriksa syarat kelulusan (minimal **144 SKS**) dan memperbarui status `lulus` mahasiswa.

* **Parameter:** `mhs` (objek **Mahasiswa**)

### `get_info`

Mengambil beberapa informasi kunci dari objek mahasiswa.

* **Parameter:** `mhs` (objek **Mahasiswa**)
* **Mengembalikan:** Sebuah tuple `(String, u32, u64, bool)` yang berisi `(nama, nim, total_sks, lulus)`.

---

## Contoh Transaksi

Anda dapat melihat contoh transaksi yang melibatkan objek `Mahasiswa` di SUI Testnet melalui tautan berikut:
[Lihat Objek Mahasiswa di SUI Testnet](https://suiscan.xyz/testnet/object/0x1355a4f1264c195e5d84c0bc77d0bf4038bb39a8b475b77137b5d4fa2818bf27/tx-blocks)
