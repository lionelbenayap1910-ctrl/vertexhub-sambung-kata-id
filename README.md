# VertexHub - Sambung Kata GUI

![Version](https://img.shields.io/badge/version-2.0-blue)
![Roblox](https://img.shields.io/badge/Roblox-Executor-red)
![KBBI](https://img.shields.io/badge/KBBI-v2-green)

**VertexHub** adalah GUI Roblox untuk membantu permainan *sambung kata* (word chain). Script ini menyediakan pencarian kata dari database **KBBI** (Kamus Besar Bahasa Indonesia) dengan dua mode pencarian: **Prefix** (awalan) dan **Suffix** (akhiran).  

Fitur unggulan: **Auto-type** dengan kecepatan dapat diatur, **cut system** cerdas, dan **rapid backspace**.

---

## ✨ Fitur Utama

- 📚 **Database KBBI** (100.000+ kata) – otomatis mengambil dari repository (v2 → fallback v1)
- 🔍 **Pencarian Prefix / Suffix** – temukan kata berdasarkan awalan atau akhiran
- ⚡ **Auto-Type** – klik kata, script akan mengetik otomatis (bisa diaktifkan Enter otomatis)
- ✂️ **Cut System Cerdas**  
  - *Mode Prefix*: klik langsung memotong kata sesuai jumlah huruf di kotak pencarian  
  - *Mode Suffix*: tombol **-1 s/d -5** untuk memotong dari depan  
- ⌫ **Rapid Backspace** – tahan tombol untuk hapus cepat
- 🎨 **GUI Modern** – dark mode, draggable, minimize, settings panel
- ⚙️ **Settings Penuh** – atur kecepatan typing, delay Enter, kecepatan backspace (5–1000 ms)

---

## 📸 Screenshot

> *Tambahkan screenshot GUI di sini*

---

## 🚀 Cara Penggunaan

### 1. Persyaratan
- Executor Roblox (Synapse X, Krnl, ScriptWare, dll.)
- Koneksi internet (untuk mengambil database KBBI)

### 2. Instalasi
Salin seluruh script dan jalankan di executor saat berada di dalam game.

### 3. Cara Operasi

#### Mode PREFIX (Awalan)
1. Ketik huruf awal di kotak pencarian (contoh: `s`)
2. Daftar kata dengan awalan `s` akan muncul
3. **Klik pada kata** → script akan:
   - Memotong kata sesuai jumlah huruf yang ada di kotak pencarian
   - Contoh: kotak pencarian berisi `sa`, kata `sate` → akan mengetik `te`
4. Jika Auto Enter ON → langsung submit

#### Mode SUFFIX (Akhiran)
1. Pilih tab **Suffix**
2. Ketik akhiran (contoh: `si`)
3. Daftar kata berakhiran `si` muncul
4. **Klik pada kata** → mengetik kata **utuh**
5. Gunakan tombol **-1, -2, -3, -4, -5** untuk memotong dari depan

### 4. Tombol dan Kontrol

| Tombol | Fungsi |
|--------|--------|
| `Auto ON/OFF` | Mengaktifkan/mematikan Enter otomatis setelah mengetik |
| `Rapid Bksp` | Tahan untuk backspace cepat |
| `Reset` | Menghapus riwayat kata yang sudah digunakan |
| `⚙️` | Buka pengaturan kecepatan |
| `-` / `+` | Minimize/Maximize GUI |

---

## ⚙️ Pengaturan

Klik ikon **⚙️** untuk membuka panel settings:

| Parameter | Rentang | Default | Deskripsi |
|-----------|---------|---------|------------|
| Typing speed | 5–1000 ms | 25 ms | Delay antar huruf saat mengetik |
| Enter delay | 20–1000 ms | 150 ms | Delay sebelum menekan Enter (jika Auto ON) |
| Backspace speed | 10–1000 ms | 40 ms | Delay antar backspace saat rapid |

---

## 🧠 Database KBBI

- Script mengambil kata dari repository GitHub:  
  `vertex_kbbi_v2.txt` (prioritas)  
  `vertex_kbbi_v1.txt` (fallback)
- Filter: hanya kata **3–15 huruf**, hanya huruf **a-z**, tanpa spasi/tanda hubung
- Total kata unik yang tersedia: **lebih dari 100.000 kata**
- Kata yang sudah digunakan dalam satu sesi akan ditandai `[USED]` dan tidak akan muncul lagi (kecuali di-reset)

---

## 🔧 Kustomisasi Lanjutan

Jika ingin mengganti URL database atau mengubah batasan kata, edit bagian `CONFIG` di awal script.

```lua
local CONFIG = {
    MaxResults = 150,          -- maksimal hasil pencarian
    TypeDelay = 0.025,         -- typing speed dalam detik
    EnterDelay = 0.15,         -- delay enter
    BackspaceDelay = 0.04,     -- delay backspace
}
