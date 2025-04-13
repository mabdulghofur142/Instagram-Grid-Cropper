# 📸 Instagram Grid Cropper with Framing & Mirrored Edges

**Instagram Grid Cropper** adalah script Python untuk memotong gambar besar menjadi beberapa bagian (1x3, 2x3, 3x3, dst) yang sesuai untuk diunggah sebagai carousel Instagram, lengkap dengan tambahan frame dan efek mirrored edge agar tampil lebih estetik dan profesional.

---

## 📦 Fitur

- ✂️ Otomatis crop gambar berdasarkan grid (1, 2, atau 3 kolom dan banyak baris).
- 🖼️ Tambahkan **frame hitam** agar rasio sesuai target (contoh: dari 3:4 ke 4:5).
- 🔁 Tambahkan **mirror edges** di sisi kiri/kanan untuk efek seamless.
- 💾 Simpan hasil sebagai file ZIP berisi potongan gambar siap pakai.

---

## 🧩 Contoh Kasus Penggunaan

> Kamu punya 1 gambar besar berukuran 3:4, lalu ingin membaginya menjadi 3 post carousel 4:5 untuk Instagram. Tool ini akan secara otomatis memotong, memberi padding, dan menghasilkan gambar yang sesuai.

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
- `to_format` *(str)*: Rasio target Instagram carousel (default: `"4/5"`).
- `from_format` *(str)*: Rasio asli gambar (default: `"3/4"`).

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

- Rasio Instagram carousel ideal: **4:5**
- Rasio foto portrait biasa: **3:4**
- Gunakan grid **3 kolom** untuk hasil panorama (feed puzzle)
- Bisa dikombinasikan dengan Canva, Photoshop, atau CapCut untuk efek lebih lanjut

---

## 📁 Contoh Hasil

| Input Image | Output Grid (3x1) |
|-------------|------------------|
| ![Input](example_input.jpg) | ![Output](example_output_grid.jpg) |

---

## ⚖️ Lisensi

Script ini open-source dan dapat digunakan secara bebas untuk keperluan pribadi atau komersial.

Lisensi: **MIT License**
