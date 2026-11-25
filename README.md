# master-image-drivers

Driver SSD/storage untuk tool WinPE **Master Image**.

Kalau SSD terbaca di BIOS tapi tidak di WinPE, tool otomatis mencari driver
yang cocok di repo ini (lewat internet kabel LAN), memuatnya, lalu ikut
memasangnya ke Windows hasil restore.

- `index.json` : daftar driver + kode perangkat + hash SHA-256 tiap file
- `index.sig`  : tanda tangan RSA admin untuk `index.json`.
  Tool menolak driver kalau tanda tangan tidak cocok.
- `drivers/`   : file driver (hasil extract: .inf/.sys/.cat)

Jangan ubah file di sini secara manual. Tambah/hapus driver lewat
`Admin\Tambah-Driver.ps1` di repo tool (butuh kunci privat admin).