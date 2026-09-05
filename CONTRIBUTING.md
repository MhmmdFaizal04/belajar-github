# Panduan Kontribusi

Gunakan perubahan dokumentasi yang kecil dan bermanfaat untuk berlatih.
Contohnya memperbaiki salah ketik, memperjelas istilah, atau menambah contoh.

## Mulai dari Issue

1. Periksa issue yang sudah ada agar tidak membuat duplikat.
2. Jelaskan masalah, perubahan yang diusulkan, dan tanda pekerjaan selesai.
3. Catat nomor issue untuk dihubungkan dengan pull request.

## Latihan Melalui Terminal

Contoh berikut untuk pemilik repository yang memiliki izin push.
Kontributor lain dapat membuat fork dan menyesuaikan alamat clone.
Pastikan Git sudah terpasang dan autentikasi GitHub sudah tersedia.

Clone repository sekali saja:

```sh
git clone https://github.com/MhmmdFaizal04/belajar-github.git
cd belajar-github
```

Mulai perubahan dari branch utama yang terbaru:

```sh
git switch main
git pull --ff-only
git switch -c docs/perjelas-istilah
```

Edit `README.md`, lalu periksa dan simpan perubahan:

```sh
git diff --check
git diff
git add README.md
git diff --cached
git commit -m "Clarify GitHub terminology"
git push -u origin docs/perjelas-istilah
```

Buka tautan yang ditampilkan setelah push untuk membuat PR ke `main`.
Jika menggunakan GitHub CLI, jalankan `gh pr create --base main`.

## Checklist Sebelum Merge

- Perubahan sesuai tujuan issue dan tidak memuat data sensitif.
- Isi, ejaan, dan tautan Markdown sudah diperiksa.
- `git diff --check` tidak melaporkan masalah whitespace.
- Tab **Files changed** hanya memuat file yang dimaksud.
- Aturan review dan pemeriksaan otomatis repository sudah dipenuhi.

Untuk menutup issue otomatis, tulis `Closes #N` pada deskripsi PR,
dengan `N` diganti nomor issue yang benar-benar diselesaikan.
Setelah PR di-merge, hapus branch latihan melalui GitHub dan perbarui lokal:

```sh
git switch main
git pull --ff-only
git fetch --prune
```

Jangan melewati persyaratan review proyek lain demi achievement.
Repository ini berisi dokumentasi saja, sehingga tidak memiliki tes aplikasi.
