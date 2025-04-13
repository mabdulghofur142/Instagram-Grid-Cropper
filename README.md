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
    - Jika targetnya adalah 1 baris 3 kolom dengan format preview instagram adalah **3:4**, maka rasio gambar yang digunakan **3x3:1x4** = **9:4**, sehingga gunakan gambar dengan rasio 9:4 (e.g 3375x1500, 6750x3000, etc)
    - Jika targetnya adalah 2 baris 3 kolom dengan format preview instagram adalah **3:4**, maka rasio gambar yang digunakan **3x3:2x4** = **9:8**, sehingga gunakan gambar dengan rasio 9:8 (e.g 3375x3000, 6750x6000, etc)
    - Jika targetnya adalah 3 baris 3 kolom dengan format preview instagram adalah **3:4**, maka rasio gambar yang digunakan **3x3:3x4** = **3:4**, sehingga gunakan gambar dengan rasio 3:4 (e.g 1125x1500, 3375x4500, etc)

---

## 📁 Contoh Hasil

| Input Image | Output Grid (3x1) |
|-------------|------------------|
| ![Input](example_input.jpg) | ![Output](example_output_grid.jpg) |

---

## ⚖️ Lisensi

Script ini open-source dan dapat digunakan secara bebas untuk keperluan pribadi atau komersial.

Lisensi: **MIT License**
