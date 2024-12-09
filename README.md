# Panduan Komprehensif untuk Membuat dan Menerbitkan Buku Jupyter

## Pendahuluan

Panduan ini akan memandu Anda dalam membuat, membuat, dan menerbitkan Jupyter Book, yang merupakan alat yang ampuh untuk membuat buku dan dokumen yang indah dan berkualitas publikasi dari berbagai jenis konten, termasuk Markdown dan Jupyter Notebook.

## Prasyarat

Sebelum memulai, pastikan Anda telah menginstal aplikasi berikut ini:
- Python (disarankan versi 10 atau yang lebih baru)
- pip (pengelola paket Python)
- Git (sistem kontrol versi)

## Penyiapan dan Instalasi

### Langkah 1: Instal Jupyter Book

Buka terminal atau command prompt dan jalankan perintah berikut:

```bash
pip install -U jupyter-book
```

Perintah ini akan menginstal versi terbaru dari Jupyter Book dan memperbarui instalasi yang sudah ada.

### Langkah 2: Membuat Proyek Buku Baru

Buat sebuah proyek buku baru bernama “materi” (Anda dapat mengganti “materi” dengan nama proyek yang Anda inginkan):

```bash
jupyter-book create materi
```

#### Struktur Proyek

Setelah dibuat, proyek Anda akan memiliki struktur sebagai berikut:

```
materi/
├── _config.yml # Pengaturan konfigurasi untuk buku Anda
├── _toc.yml # Konfigurasi daftar isi
├── intro.md # Halaman pengantar
├── logo.png # Logo proyek opsional
├── markdown-notebooks.md
├── markdown.md
├── notebooks.ipynb # Contoh buku catatan Jupyter
├── references.bib # File bibliografi opsional
└── requirements.txt # Ketergantungan proyek
```

### Langkah 3: Mengkonfigurasi Daftar Isi (_toc.yml)

Edit file `_toc.yml` untuk menentukan struktur buku Anda:

```yaml
format: jb-book
root: intro
bab:
  - file: markdown
  - file: notebooks
  - file: markdown-notebooks
```

#### Menambahkan Bab Baru

Ketika Anda menambahkan berkas markdown baru (misalnya, `himpunan.md`), sertakan berkas tersebut di dalam `_toc.yml`:

```yaml
format: jb-book
root: intro
bab:
  - file: markdown
  - file: notebooks
  - berkas: markdown-notebooks
  - berkas: himpunan
```

**Tips Penulisan yang Penting:**
- Selalu mulai berkas markdown baru dengan judul tingkat atas (#) yang menjelaskan bab tersebut dan sekaligus menampilkan nama materi di daftar isi
- Contoh:
  ``` penurunan harga
  # HIMPUNAN

  ## Identitas Himpunan
  Sisa dari konten Anda...
  ```

## Membangun Buku Anda

### Membangun Versi HTML

Untuk menghasilkan halaman HTML untuk notebooks Anda:

```bash
jupyter-book build materi
```

Keluarannya akan terlihat seperti:
```
Selesai membuat HTML untuk buku.
Halaman HTML buku Anda ada di sini:
    materi/_build/html/
Anda dapat melihat buku Anda dengan membuka:
    materi/_build/html/index.html
```

### Mempratinjau Buku Anda

Anda dapat melihat pratinjau HTML yang telah dibuat dengan:
1. Mengklik dua kali file `index.html` di folder lokal Anda
2. Membuka file tersebut di browser web dengan menggunakan jalur lengkap (misalnya, `file://path/to/materi/_build/html/index.html`)

### Memaksakan membuat file html Ulang Secara Menyeluruh

Jika Anda ingin membangun ulang semua halaman, bahkan halaman yang tidak berubah:

```bash
jupyter-book build --all materi/
```

## Kontrol Versi dan Integrasi GitHub

### Menyimpan dan Melakukan Perubahan

Gunakan Git untuk melacak dan menyimpan perubahan proyek Anda:

```bash
# menambahkan semua perubahan
git tambahkan .

# Melakukan komit perubahan dengan pesan lengkap
git commit -m “Menambahkan bab baru tentang himpunan”

# Meunggah ke repositori github
git push
```
Lakukan ini untuk menyimpan file ke github. Jaga jaga codespaces jika hilang/tidak sengaja terhapus

### Menerbitkan ke Halaman GitHub

#### Prasyarat
Instal `ghp-import`:
```bash
pip install ghp-import
```

#### Langkah-langkah Penerapan

1. Arahkan ke direktori buku Anda:
```bash
cd materi
```

2. Deployment ke Halaman GitHub Pages:
```bash
ghp-import -n -p -f _build/html
```

Catatan Deployment:** **Catatan Deployment
- Tunggu 1-5 menit untuk proses menjadi website online
- Periksa hasil website di bagian “Deployment” repositori GitHub Anda
- Tanda centang hijau menandakan deployment berhasil

## Pemecahan Masalah

### Daftar Isi Tidak Diperbarui
Jika perubahan pada `_toc.yml` tidak tercermin, coba:
```bash
jupyter-book build --all materi
```

### Tantangan Umum
- Setiap lingkungan mungkin memiliki kesalahan yang unik
- Jika Anda mengalami masalah, pertimbangkan:
  1. Memeriksa versi Python dan pip Anda
  2. Memastikan semua dependensi telah terinstal
  3. Memverifikasi file dan konfigurasi file

## Sumber Daya Tambahan

- Dokumentasi Buku Resmi Jupyter: https://jupyterbook.org/
- Repositori GitHub: -

## Kontribusi

- Dibuat oleh: @mfjrxn
- Kontribusi diterima! Silakan kirimkan permintaan penarikan
- Jangan lupa untuk membintangi repositori saya jika kamu merasa terbantu

## Kiat-kiat Akhir

1. Baca dokumentasi dengan seksama
2. Jangan menyalin-tempel secara membabi buta!
3. Pahami setiap langkah
4. Berlatih dan bereksperimen

Selamat membuat catatan materi! 📘✨
