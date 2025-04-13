- 🇮🇩 [Bahasa Indonesia](#versi-bahasa-indonesia)
- 🇬🇧 [English Version](#english-version)

# 📸 Instagram Grid Cropper with Framing & Mirrored Edges

**Instagram Grid Cropper** adalah script Python untuk memotong gambar besar menjadi beberapa bagian (1x3, 2x3, 3x3, dst) yang sesuai untuk diunggah sebagai feed Instagram, lengkap dengan tambahan frame dan efek mirrored edge agar tampil lebih estetik dan profesional pada preview instagram.

---

## 📦 Fitur

- ✂️ Otomatis crop gambar berdasarkan grid (1, 2, atau 3 kolom dan banyak baris).
- 🖼️ Tambahkan **frame hitam** agar rasio sesuai target (contoh: dari 3:4 ke 4:5).
- 🔁 Tambahkan **mirror edges** di sisi kiri/kanan untuk efek seamless.
- 💾 Simpan hasil sebagai file ZIP berisi potongan gambar siap pakai.

---

## 🧩 Contoh Kasus Penggunaan

> Kamu memiliki satu gambar besar (perhatikan **Tips Tambahan**) yang ingin dipotong menjadi 6 bagian dalam format 2 baris dan 3 kolom (2x3), agar bisa diunggah sebagai **feed Instagram** terpisah (feed puzzle). Sehingga tiap bagian gambar memiliki rasio **3:4**, namun Instagram tidak mendukung rasio ini secara langsung. Untuk itu, tool ini akan secara otomatis:
>
> - Memotong gambar menjadi bagian-bagian kecil sesuai layout,
> - Menyesuaikan rasio ke **4:5** (rasio preview Instagram),
> - Menambahkan padding (cermin/pinggiran) agar konten tetap utuh,
> - Menghasilkan gambar-gambar siap unggah yang tampil **presisi di preview feed Instagram**.

---

## 🛠️ Cara Pakai

### 1. Instalasi
Pastikan kamu sudah menginstal `Pillow`:
```bash
pip install pillow
```

### 2. Jalankan Script
```python
if __name__ == '__main__':
    input_image_path = '/path/to/your/image.png'
    output_zip_name = 'hasil_crop.zip'
    coloms = 3
    rows = 2
    process_image(
        input_path=input_image_path,
        coloms=coloms,
        rows=rows,
        output_zip_path=output_zip_name,
        to_format="4/5",     # Target rasio carousel Instagram
        from_format="3/4"    # Rasio asli gambar
    )
```

---

## 📚 Dokumentasi Fungsi

### `process_image(...)`
Memproses gambar utama menjadi potongan grid siap pakai untuk carousel Instagram.

**Parameter:**
- `input_path` *(str)*: Lokasi file gambar input.
- `coloms` *(int)*: Jumlah kolom untuk membagi gambar (biasanya 1, 2, atau 3).
- `rows` *(int)*: Jumlah baris pemotongan.
- `output_zip_path` *(str)*: Nama file .zip untuk menyimpan hasil.
- `format_upload_feed` *(str)*: Rasio target Instagram carousel (default: `"4/5"`).
- `format_preview` *(str)*: Rasio asli gambar tiap bagian dan rasio preview (default: `"3/4"`).

---

## 📌 Struktur Output

File hasil akan berupa `.zip` berisi file gambar dengan nama:
```
cropped_1_1.jpg
cropped_2_1.jpg
cropped_1_2.jpg
...
```
Artinya: `cropped_<row>_<column>.jpg`

---

## 🖼️ Tips Tambahan

- Rasio feed instagram yang diupload (format_upload_feed): **4:5** atau **1:1**
- Gunakan grid **3 kolom** untuk hasil panorama (feed puzzle)
- Gunakan input gambar besar yang sesuai dengan ukuran (jika targetnya adalah M baris N kolom dengan format preview instagram adalah **3:4**, maka rasio gambar yang digunakan **Nx3:Mx4**). Contoh:
    - Untuk 1 baris 3 kolom dengan format preview instagram adalah **3:4**, maka rasio gambar yang digunakan **3x3:1x4** = **9:4**, sehingga gunakan gambar dengan rasio 9:4 (e.g 3375x1500, 6750x3000, etc)
    - Untuk 2 baris 3 kolom dengan format preview instagram adalah **3:4**, maka rasio gambar yang digunakan **3x3:2x4** = **9:8**, sehingga gunakan gambar dengan rasio 9:8 (e.g 3375x3000, 6750x6000, etc)
    - Untuk 3 baris 3 kolom dengan format preview instagram adalah **3:4**, maka rasio gambar yang digunakan **3x3:3x4** = **3:4**, sehingga gunakan gambar dengan rasio 3:4 (e.g 1125x1500, 3375x4500, etc)

---

## 📁 Contoh Hasil

| Input Image | Output Grid (3x1) |
|-------------|------------------|
| ![Input](example_input.jpg) | ![Output](example_output_grid.jpg) |

---

## ⚖️ Lisensi

Script ini open-source dan dapat digunakan secara bebas untuk keperluan pribadi atau komersial.

Lisensi: **MIT License**

---

---
**English Version**

# 📸 Instagram Grid Cropper with Framing & Mirrored Edges

**Instagram Grid Cropper** is a Python script that splits a large image into smaller segments (e.g. 1x3, 2x3, 3x3, etc.) suitable for Instagram feed uploads. It automatically adds framing and mirrored edges for a cleaner, more aesthetic look in Instagram’s preview grid.

---

## 📦 Features

- ✂️ Automatically crops images into grids (1, 2, or 3 columns with any number of rows).
- 🖼️ Adds **black framing** to adjust to the target ratio (e.g. from 3:4 to 4:5).
- 🔁 Adds **mirrored edges** on the sides for a seamless layout.
- 💾 Saves all results in a ZIP file containing upload-ready image pieces.

---

## 🧩 Use Case Example

> You have a large image (see **Extra Tips**) and want to split it into 6 parts in a 2-row and 3-column (2x3) layout, to upload as a **separate Instagram feed posts** (feed puzzle). Each image part will have a **3:4 ratio**, but Instagram doesn't support this format directly. This tool will:
>
> - Split your image into smaller parts based on the grid layout,
> - Adjust each part to **4:5** (Instagram's carousel preview ratio),
> - Add side padding (mirror effect) to maintain original content,
> - Generate **upload-ready images** that fit precisely on Instagram's feed preview.

---

## 🛠️ How to Use

### 1. Installation
Make sure `Pillow` is installed:
```bash
pip install pillow
```

### 2. Run the Script
```python
if __name__ == '__main__':
    input_image_path = '/path/to/your/image.png'
    output_zip_name = 'hasil_crop.zip'
    coloms = 3
    rows = 2
    process_image(
        input_path=input_image_path,
        coloms=coloms,
        rows=rows,
        output_zip_path=output_zip_name,
        to_format="4/5",     # Instagram carousel upload format
        from_format="3/4"    # Original image ratio
    )
```

---

## 📚 Function Documentation

### `process_image(...)`
Processes the main image into ready-to-upload grid parts for Instagram carousel.

**Parameters:**
- `input_path` *(str)*: Path to the input image.
- `coloms` *(int)*: Number of columns to split (usually 1, 2, or 3).
- `rows` *(int)*: Number of rows.
- `output_zip_path` *(str)*: Output `.zip` filename.
- `format_upload_feed` *(str)*: Target Instagram ratio (default: `"4/5"`).
- `format_preview` *(str)*: Original image part ratio and preview layout (default: `"3/4"`).

---

## 📌 Output Structure

The result will be a `.zip` file containing cropped images with names like:
```
cropped_1_1.jpg
cropped_2_1.jpg
cropped_1_2.jpg
...
```
Meaning: `cropped_<row>_<column>.jpg`

---

## 🖼️ Extra Tips

- Recommended Instagram upload ratios (format_upload_feed): **4:5** or **1:1**
- Use **3-column grids** for panorama-style feed puzzles.
- Use a large image with correct proportions. If your layout is M rows × N columns and Instagram preview format is **3:4**, then use an image with ratio **Nx3 : Mx4**. Examples:
    - For 1 row × 3 columns → ratio = **9:4** (e.g. 3375x1500, 6750x3000)
    - For 2 rows × 3 columns → ratio = **9:8** (e.g. 3375x3000, 6750x6000)
    - For 3 rows × 3 columns → ratio = **3:4** (e.g. 1125x1500, 3375x4500)

---

## 📁 Output Example

| Input Image | Output Grid (3x1) |
|-------------|------------------|
| ![Input](example_input.jpg) | ![Output](example_output_grid.jpg) |

---

## ⚖️ License

This script is open-source and free to use for personal or commercial purposes.

License: **MIT License**

---

