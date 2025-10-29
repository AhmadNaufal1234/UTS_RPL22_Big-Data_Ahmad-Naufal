# RSS Lifestyle Scraper

Proyek ini adalah skrip Python untuk mengambil berita kategori **Lifestyle** secara otomatis dari beberapa portal berita populer Indonesia melalui RSS feed. Skrip ini sederhana, efisien, dan mudah dikembangkan untuk kategori lainnya.

---

## Daftar Portal Berita yang Diambil

- **Antara News**: Mengambil artikel berita dari kategori Lifestyle  
  (https://www.antaranews.com/rss/lifestyle.xml)
- **Liputan6**: Mengambil artikel berita dari kategori Lifestyle  
  (https://feed.liputan6.com/rss/lifestyle)

---

## Struktur Proyek

```
UTS_RPL22_BIG_DATA_AHMAD_NAUFAL/
├── uts_rpl22_scraping.ipynb     # Skrip utama scraping
├── README.md                    # Dokumentasi proyek
├── news_dataset.csv             # Hasil scraping (opsional)
└── requirements.txt             # Daftar dependensi
```

---

## Cara Menjalankan Proyek

### 1. Persiapan Lingkungan Virtual

Disarankan menggunakan **virtual environment** agar dependensi proyek terkelola dengan baik.

```bash
# Buat lingkungan virtual baru
python -m venv .venv

# Aktifkan lingkungan virtual
# Di Windows:
.venv\Scripts\activate
# Di macOS/Linux:
source .venv/bin/activate
```

### 2. Instalasi Dependensi

Setelah lingkungan virtual aktif, instal semua pustaka Python yang diperlukan dari `requirements.txt`:

```bash
pip install -r requirements.txt
```

Jika belum ada `requirements.txt`, minimal install:

```bash
pip install requests
```

### 3. Menjalankan Skrip

Buka file notebook di VS Code dan jalankan semua cell, atau jika sudah dikonversi ke `.py`:

```bash
python uts_rpl22_scraping.py
```

**Contoh output jika berhasil:**

```
Scraping Antara RSS...
Berhasil ambil 20 artikel dari Antara

Scraping Liputan6 RSS...
Berhasil ambil 30 artikel dari Liputan6

Total artikel lifestyle diambil: 50
```

### 4. Menyimpan Hasil Scraping

Untuk menyimpan hasil scraping ke file CSV:

```python
import json

with open('news_dataset.csv', 'w', encoding='utf-8') as f:
    json.dump(all_articles, f, indent=2, ensure_ascii=False)

print('Hasil disimpan ke news_dataset.csv')
```

### 5. Tips Pengembangan

- Gunakan logging untuk memantau proses scraping.
- Jalankan otomatis menggunakan cron job atau task scheduler.
- Simpan hasil ke database (SQLite, MySQL, atau PostgreSQL) untuk analisis lanjut.
- Gunakan blok try-except untuk menangani error jaringan atau RSS kosong.

