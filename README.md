# LKPD Interaktif TJKT Kelas X

LKPD (Lembar Kerja Peserta Didik) interaktif untuk jurusan TJKT kelas X. Setiap LKPD berupa satu berkas HTML mandiri, tanpa build step.

| LKPD | Folder | Isi |
|---|---|---|
| Sistem Operasi DOS | `dos/` | Soal konsep, cocokkan perintah, terminal DOS simulasi (8 misi), uraian dan refleksi |
| Command for Network | `network/` | Soal konsep, cocokkan perintah, terminal jaringan simulasi (9 misi), studi kasus troubleshooting, uraian dan refleksi |

Kedua LKPD menghitung nilai otomatis (bagian uraian dinilai guru) dan bisa mengunduh hasil pengerjaan sebagai PDF.

## Menjalankan secara lokal

Buka `index.html` di browser. Tidak perlu instalasi apa pun. Untuk membuat PDF, perangkat perlu terhubung internet karena pustaka [jsPDF](https://github.com/parallax/jsPDF) 2.5.1 dimuat dari cdnjs.

## Mengunggah ke GitHub

Ganti `USERNAME` dengan nama akun GitHub Anda. Buat repositori kosong bernama `lkpd-tjkt` di github.com terlebih dahulu.

```bash
cd lkpd-tjkt
git init
git add .
git commit -m "LKPD interaktif TJKT kelas X"
git branch -M main
git remote add origin https://github.com/USERNAME/lkpd-tjkt.git
git push -u origin main
```

Tanpa Git, bisa juga lewat web: buka repositori, pilih **Add file > Upload files**, lalu seret seluruh isi folder ini.

## Membagikan ke siswa lewat GitHub Pages

1. Buka **Settings > Pages** pada repositori.
2. Pada **Build and deployment**, pilih **Deploy from a branch**, branch `main`, folder `/ (root)`, lalu **Save**.
3. Setelah beberapa menit, LKPD tersedia di `https://USERNAME.github.io/lkpd-tjkt/`.

## Menyesuaikan isi

- Soal pilihan ganda dan studi kasus: array `Q` (DOS) atau pemanggilan `mkQ([...])` (jaringan) di dalam tag `<script>`.
- Pasangan perintah: array `M`.
- Misi terminal: array `T`. Perintah dan keluaran simulasi ada di fungsi `run`.
- Host dan alamat IP simulasi (LKPD jaringan): objek `HS` dan `DN`.

## Catatan

- Jawaban siswa tidak dikirim ke server mana pun. Hasil dikumpulkan lewat berkas PDF yang diunduh siswa.
- Keluaran terminal adalah simulasi dengan data fiktif, bukan jaringan sebenarnya.
- PDF memakai huruf standar, sehingga karakter di luar huruf Latin (misalnya emoji) tampil sebagai tanda tanya.

## Lisensi

MIT. Silakan dipakai dan diubah untuk keperluan pembelajaran.
