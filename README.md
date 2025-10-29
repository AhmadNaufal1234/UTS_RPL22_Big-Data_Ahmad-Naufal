📰 RSS Lifestyle Scraper
Ambil berita kategori Lifestyle secara otomatis dari portal populer Indonesia — langsung dari RSS feed!

✨ Fitur Utama
•	✅ Ambil berita otomatis dari Antara, Liputan6, dan Okezone
•	✅ Parsing XML menjadi data terstruktur JSON
•	✅ Hanya ambil berita kategori Lifestyle
•	✅ Format tanggal ISO 8601 (standar internasional)
•	✅ Jeda acak antar scraping (ramah server, anti-banned)
•	✅ Mudah dikembangkan untuk kategori lain

🧩 Struktur Proyek
rss_lifestyle_scraper/
├── scrape_rss.py     # Script utama
├── README.md         # Dokumentasi proyek
└── lifestyle_articles.json  # (Opsional) hasil scrape

⚙️ Persiapan Lingkungan di VS Code
• Buka VS Code, lalu buat folder baru misalnya: rss_lifestyle_scraper
• Buat file baru bernama scrape_rss.py
• Salin kode scraper kamu ke file tersebut.

🐍 Install Python dan Library
Pastikan Python sudah terpasang di sistem kamu:
python --version
Jika belum, unduh di: https://www.python.org/downloads/

Lalu install library berikut:
pip install requests
🚀 Jalankan Skrip
Di terminal VS Code (Ctrl + ~):
python scrape_rss.py

Jika berhasil, kamu akan melihat output seperti berikut:

🔍 Scraping Antara RSS...
✅ Berhasil ambil 20 artikel dari Antara
🔍 Scraping Liputan6 RSS...
✅ Berhasil ambil 18 artikel dari Liputan6
🔍 Scraping Okezone RSS...
✅ Berhasil ambil 19 artikel dari Okezone
📰 Total artikel lifestyle diambil: 57

💾 Simpan Hasil ke JSON (Opsional)
Tambahkan kode berikut di akhir scrape_rss.py:
import json

with open('lifestyle_articles.json', 'w', encoding='utf-8') as f:
    json.dump(all_articles, f, indent=2, ensure_ascii=False)

print('💾 Disimpan ke lifestyle_articles.json')

🌐 Sumber RSS Feed
Sumber	URL RSS
Antara	https://www.antaranews.com/rss/lifestyle.xml
Liputan6	https://feed.liputan6.com/rss/lifestyle
Okezone	https://sindikasi.okezone.com/index.php/rss/0/Lifestyle
🧠 Tips Developer
•	💡 Tambahkan logging agar scraping lebih mudah dipantau.
•	💡 Gunakan cronjob / task scheduler untuk update otomatis.
•	💡 Simpan hasil ke database (SQLite / PostgreSQL) untuk analisis lanjut.
📄 Lisensi
Proyek ini dirilis dengan MIT License — bebas digunakan dan dimodifikasi untuk pembelajaran, penelitian, atau proyek pribadi.

🧡 Dibuat dengan Python dan kopi hangat ☕ oleh developer independen.
