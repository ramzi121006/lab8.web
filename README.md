# lab8.web

**NAMA                : Valentino Ramzi**

**NIM                 : 312410454**

**KELAS               : TI.24.A.5**

**MATKUL              : PEMOGRAMAN WEB 1**

**Dosen Pengampu      : Agung Nugroho, S.Kom., M.Kom.**

## 📌 Tujuan Praktikum
Praktikum ini bertujuan untuk mempelajari:
- Menghubungkan PHP dengan database MySQL menggunakan `mysqli`
- Melakukan operasi **CRUD** (Create, Read, Update, Delete)
- Menggunakan form HTML untuk input data
- Upload file (gambar) menggunakan `enctype="multipart/form-data"`
- Menampilkan data dalam bentuk tabel
- Mengatur struktur folder pada XAMPP (`htdocs`)

---

## 🗄️ 1. Membuat Database & Tabel

Database dibuat melalui phpMyAdmin:

```sql
CREATE DATABASE latihan1;
USE latihan1;

CREATE TABLE data_barang (
  id_barang INT(10) AUTO_INCREMENT PRIMARY KEY,
  kategori VARCHAR(30),
  nama VARCHAR(30),
  gambar VARCHAR(100),
  harga_beli DECIMAL(10,0),
  harga_jual DECIMAL(10,0),
  stok INT(4)
);

```

**Hasil :**

![foto](https://github.com/ramzi121006/lab8.web/blob/5741d028ba86cd3b444f6b3aa538c0cb1dfa3ce3/ss_prak8/Xamp.png)

## 2. Membuat Koneksi Database (koneksi.php)

Koneksi menggunakan mysqli_connect:

```sql

<?php
$host = "localhost";
$user = "root";
$pass = "";
$db   = "latihan1";

$conn = mysqli_connect($host, $user, $pass, $db);
if (!$conn) {
  echo "Koneksi gagal: " . mysqli_connect_error();
    die();
}
?>

```

## 📄 3. Menampilkan Data (index.php)

Halaman utama menampilkan semua data dari `tabel data_barang` dalam bentuk tabel.

Fitur pada halaman ini:

`Menampilkan` data lengkap

`Menampilkan` gambar

`Tombol` Ubah

`Tombol` Hapus

`Tombol` Tambah Barang

**Hasil :**

![foto](https://github.com/NadhiaShafira/Lab8Web./blob/7be584f4b85a18dec4385243c71600edfd9d3289/SS_Prak8/Index.png)

## ➕ 4. Menambah Data Barang (tambah.php)

Pada bagian ini, user bisa menambahkan:

`Nama` barang

`Kategori`

`Harga jual`

`Harga beli`

`Stok`

`Upload` Gambar

Data yang diinput akan disimpan dalam database.

**Hasil :**

![foto](https://github.com/NadhiaShafira/Lab8Web./blob/719dcc702e53e00cd51bee8e04eb5481925f865d/SS_Prak8/tambah.png)

## ✏️ 5. Mengubah Data (ubah.php)

User bisa meng-update data barang yang sudah ada.
Termasuk mengganti:

`Nama` barang

`Kategori`

`Harga`

`Stok`

`Gambar` (opsional)

Jika user tidak memilih gambar baru, gambar lama tetap digunakan.

**Hasil :**

![foto](https://github.com/NadhiaShafira/Lab8Web./blob/3824c684ec5eb88e2621e10a3d3001c7039175b3/SS_Prak8/ubah.png)

## ❌ 6. Menghapus Data (hapus.php)

Menghapus data barang berdasarkan ID.
Setelah dihapus, halaman akan langsung kembali ke index.php.

**Hasil :**

![foto](https://github.com/NadhiaShafira/Lab8Web./blob/45d9ccde0e7283cf225861a8f8284b957b950ea6/SS_Prak8/hapus.png) 
