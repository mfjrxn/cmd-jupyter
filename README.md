# Command Jupyter Notebook

# Bagian pertama kali
Bagi yang pertama kali install

```
$ pip install -U jupyter-book -> untuk Install jupyter-book
$ jupyter-book create materi
```

- Note:
  - (->) untuk komentar. Baca baik baik, jangan asal copas, budayakan literasi! 

**Struktur setelah jadi:**

```
$ tree materi
materi/
├── _config.yml
├── _toc.yml
├── intro.md
├── logo.png
├── markdown-notebooks.md
├── markdown.md
├── notebooks.ipynb
├── references.bib
└── requirements.txt
```

### Table of Contents (_toc.yml)

```
# Di _toc.yml
format: jb-book
root: intro
chapters:
- file: markdown
- file: notebooks
- file: markdown-notebooks
- file: boolean.md
```
- Note:
  - Disini tempat daftar isinya yang akan muncul di web. tambahkan setiap ada penambahan file md baru. contoh ada materi himpunan maka tambahkan
  - ```
    - file: himpunan.md
    ```
  - Setiap file baru wajib paling atas (#)  agar di table of content keluar judul materinya. contohnya:
  - ```
    # HIMPUNAN

    lalu disusul heading lain, contohnya:

    ## Identitas Himpunan
    ```

By default, Jupyter Book will only build the HTML for pages that have been updated since the last time you built the book.
If you’d like to force Jupyter Book to re-build a particular page, you can either edit the corresponding file in your book’s folder, or delete that page’s HTML in the _build/html folder.
You can also signal a full re-build using the --all option:

```
$ jupyter-book build --all mybookname/
```

#### Preview your built HTML
To preview your book, you can open the generated HTML files in your browser. Either double-click the html file in your local folder, or enter the absolute path to the file in your browser navigation bar adding file:// at the beginning (e.g. file://materi/_build/index.html).


# Bagian yang sudah selesai
Jika sudah pernah membuat dan ingin menjadikan web publish ke github pages.

## Tahap 1 (Setiap pengubahan materi)
* rules:
Jangan lupa setiap file markdown wajib paling atas (#) sebagai judul dari materi.
- tambahkan file .md baru sesuai judul materi
- tambahkan nama file md baru dibuat ditambahkan ke toc => materi/_toc.yml
  - Jalankan perintah: ($)
```
$ jupyter-book build materi  -> cmd untuk build menjadi html
```

## Tahap 2 (Push file perubahan ke github)
* bagian ini **ga wajib** hanya saran kalau data di codespace hilang, jaga jaga jadi bisa di lihat di repo.
Jalankan perintah: ($)
```
$ git add .  -> cmd Memasukan file ke list untuk di simpan 
$ git commit -m "materi"  -> cmd memberi komen perubahan file, "materi" bebas di ganti namanya atau default gpp.
$ git push  -> cmd push file ke github
```

## Tahap 3 (Hasil build menjadi website online di github pages)
Jalankan perintah: ($) 
```
$ pip install ghp-import -> skip perintah ini jika merasa sudah install
$ cd materi -> cmd masuk ke materi
$ ghp-import -n -p -f _build/html  -> cmd push ke branch gh-pages dan menjadi website online
```
**Tunggu progress deploy kurang lebih 1 menitan, 5 menit maks. bisa dilihat progress di repos bagian deployments, jika sudah centang hijau berarti sudah selesai dan silahkan cek webnya.**

### NOTES:
- Note:
  - (->) untuk komentar. Baca baik baik, jangan asal copas, budayakan literasi! 
- Setiap ada perubahan di file maupun _toc.yml wajib build ulang

If your book’s Table of Contents doesn’t update after changing the _toc.yml file, try:
```
$ jupyter-book build --all materi
```

- &Jika ada error sabar, kadang setiap orang beda beda errornya. laporkan tambahkan issue ke repository ini

- refrensi web official: https://jupyterbook.org/en/stable/start/your-first-book.html
### Creator dokumentasi: 
> - @mfjrxn
> - **Jangan lupa klik star!**
> - Jika ingin menambahkan dokumentasi ajukan pull, jika sesuai akan saya setujui. 
