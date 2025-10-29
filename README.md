RSS Lifestyle Scraper

RSS Lifestyle Scraper adalah skrip Python untuk mengambil berita kategori Lifestyle secara otomatis dari beberapa portal berita populer Indonesia melalui RSS feed.
Skrip ini sederhana, efisien, dan mudah dikembangkan untuk kategori lainnya.

Fitur Utama

Ambil berita otomatis dari Antara, Liputan6, dan Okezone

Parsing XML menjadi data terstruktur (JSON)

Hanya mengambil berita kategori Lifestyle

Format tanggal menggunakan standar ISO 8601

Jeda acak antar scraping (ramah server dan mengurangi risiko pemblokiran)

Dapat dikembangkan untuk kategori atau sumber berita lain

Struktur Proyek
rss_lifestyle_scraper/
├── scrape_rss.py              # Skrip utama
├── README.md                  # Dokumentasi proyek
└── lifestyle_articles.json    # (Opsional) hasil scraping

Persiapan Lingkungan

Buka VS Code
Buat folder baru, misalnya rss_lifestyle_scraper.

Buat file baru
Buat file bernama scrape_rss.py dan salin kode scraper ke dalamnya.

Pastikan Python terpasang

python --version


Jika belum, unduh di python.org/downloads
.

Instal library yang dibutuhkan

pip install requests

Menjalankan Skrip

Jalankan perintah berikut di terminal VS Code:

python scrape_rss.py


Contoh output jika berhasil:

Scraping Antara RSS...
Berhasil ambil 20 artikel dari Antara

Scraping Liputan6 RSS...
Berhasil ambil 18 artikel dari Liputan6

Scraping Okezone RSS...
Berhasil ambil 19 artikel dari Okezone

Total artikel lifestyle diambil: 57

Simpan Hasil ke JSON (Opsional)

Tambahkan kode berikut di akhir scrape_rss.py untuk menyimpan hasil scraping ke file:

import json

with open('lifestyle_articles.json', 'w', encoding='utf-8') as f:
    json.dump(all_articles, f, indent=2, ensure_ascii=False)

print('Hasil disimpan ke lifestyle_articles.json')

Sumber RSS Feed
Sumber	URL RSS
Antara	https://www.antaranews.com/rss/lifestyle.xml

Liputan6	https://feed.liputan6.com/rss/lifestyle

Okezone	https://sindikasi.okezone.com/index.php/rss/0/Lifestyle
Tips Pengembangan

Tambahkan logging untuk memantau proses scraping.

Gunakan cron job atau task scheduler agar scraping berjalan otomatis.

Simpan hasil ke database (SQLite, MySQL, atau PostgreSQL) untuk analisis lebih lanjut.

Gunakan try-except untuk menangani error jaringan atau feed kosong.