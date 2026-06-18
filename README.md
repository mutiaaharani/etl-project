# etl-project
# Persiapan Awal

Sebelum menjalankan program, pastikan semua dependensi telah terpasang.

Install pytest dan pytest-cov dengan perintah berikut:
python -m pip install pytest pytest-cov

Jika menggunakan integrasi Google Sheets, install juga library berikut:
pip install google-auth google-api-python-client

# Menjalankan Proses ETL

Untuk menjalankan pipeline ETL, gunakan perintah berikut pada terminal:

python main.py

Program ini akan melakukan beberapa tahapan secara otomatis:
- Mengambil data produk dari website https://fashion-studio.dicoding.dev
- Membersihkan dan memproses data (termasuk konversi harga ke rupiah)
- Menyimpan data ke dalam file CSV (products.csv)
- Mengunggah data ke Google Sheets

# Menjalankan Pengujian (Unit Test)

Untuk memastikan setiap fungsi berjalan dengan baik, jalankan unit test dengan perintah:

python -m pytest tests

Pengujian mencakup beberapa modul utama:
- test_extract.py → menguji proses pengambilan data
- test_transform.py → menguji proses pembersihan data
- test_load.py → menguji proses penyimpanan data

# Menjalankan Coverage Test

Untuk melihat seberapa besar cakupan pengujian, gunakan perintah berikut:

python -m coverage run -m pytest tests

Kemudian tampilkan hasilnya dengan:

python -m coverage report

Coverage pada proyek ini telah memenuhi standar minimum yaitu di atas 20%.

# Link Google Sheets

Data hasil ETL dapat diakses melalui Google Sheets berikut:
https://docs.google.com/spreadsheets/d/1OXch19qbj6fsLY29Yhh0YDebCwmBgNUWWQL04HI0D4k/edit?gid=0#gid=0

# Konfigurasi PostgreSQL

Jika menggunakan database PostgreSQL, pastikan konfigurasi berikut sesuai:
- Host: localhost
- Database: etl_pipeline
- Username: pipeline
- Password: pipeline

# Informasi Tambahan

- File google-sheets-api.json digunakan sebagai kredensial untuk autentikasi ke Google Sheets API.
- Pastikan file tersebut berada di folder utama proyek.
- Berikan akses Editor pada Google Sheets kepada service account yang digunakan.
- Jalankan instalasi dependency terlebih dahulu sebelum mengeksekusi program.
