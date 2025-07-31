🚕 Prediksi Durasi Perjalanan Taksi di New York City
Laporan Tugas Besar oleh Kelompok 168 untuk mata kuliah Machine Learning.

Nama	NIM
Mochammad Khoirullutfansyah	1301220126
Ridho Chan	1301223432
Sutan Rifky Tedjasukmana	1301223465

Ekspor ke Spreadsheet
Program Studi Sarjana Informatika, Fakultas Informatika, Universitas Telkom
Bandung, 2025

🎯 Pendahuluan
Proyek ini bertujuan untuk membangun model machine learning yang andal untuk memprediksi durasi perjalanan taksi di kota metropolitan New York. Analisis prediktif ini krusial untuk meningkatkan efisiensi layanan transportasi, membantu pengguna memperkirakan waktu tempuh, dan mendukung pengambilan keputusan berbasis data bagi operator taksi. Laporan ini mencakup proses dari eksplorasi data, feature engineering, hingga pemodelan dan evaluasi performa.

⚙️ Metodologi
Metodologi proyek dibagi menjadi beberapa tahapan utama sebagai berikut:

1. Dataset
Dataset yang digunakan adalah "New York City Taxi Trip Duration" dari platform Kaggle. Dataset ini mencakup lebih dari 1 juta data perjalanan dengan atribut-atribut penting seperti:

Waktu penjemputan dan pengantaran

Koordinat geografis (latitude, longitude)

Jumlah penumpang

Durasi perjalanan (target variabel dalam detik)

2. Eksplorasi Data Awal (EDA)
Tahap awal difokuskan untuk memahami karakteristik dasar dari dataset:

Missing Values: Tidak ditemukan nilai kosong pada dataset.

Distribusi Fitur: Analisis distribusi pada vendor_id, passenger_count, dan trip_duration dilakukan untuk mendapatkan wawasan awal. Ditemukan bahwa mayoritas perjalanan dilakukan dengan 1 penumpang.

Analisis Bivariat: Hubungan antar fitur dianalisis untuk menemukan pola, seperti hubungan antara jumlah penumpang dengan jarak tempuh dan vendor.

3. Feature Engineering
Untuk memperkaya informasi yang dapat dipelajari oleh model, beberapa fitur baru dibuat:

Fitur Waktu: pickup_hour, pickup_weekday, dan pickup_month diekstraksi dari pickup_datetime untuk menangkap pola temporal.

Fitur Jarak (distance): Jarak geodesik antara titik jemput dan antar dihitung menggunakan rumus Haversine.

Fitur Kecepatan (speed): Kecepatan rata-rata perjalanan (km/jam) dihitung dari fitur jarak dan durasi.

4. Eksplorasi Data Lanjutan
Setelah feature engineering, dilakukan analisis lebih dalam terhadap fitur-fitur baru:

Pola Perjalanan: Ditemukan puncak jumlah perjalanan terjadi pada jam 18:00-21:00 dan paling banyak terjadi pada hari Jumat.

Pola Durasi & Kecepatan: Durasi perjalanan rata-rata terlama terjadi pada hari Kamis. Kecepatan cenderung tinggi pada dini hari dan meningkat seiring bertambahnya jarak tempuh.

Analisis Lokasi: Lokasi penjemputan dan pengantaran paling terkonsentrasi di area tertentu seperti Manhattan dan Bandara JFK. Ini menginspirasi pembuatan fitur berbasis grid lokasi.

📈 Hasil dan Analisa Model
Beberapa model machine learning diuji untuk menemukan yang terbaik dalam memprediksi durasi perjalanan. Evaluasi dilakukan menggunakan metrik R-squared (R²).

Model	Skor R²	Keterangan
Linear Regression	0.6176	Kurang baik, terlalu sederhana.
Decision Tree	0.5541	Performa lebih rendah dari model linear.
MLP Regressor	0.6926	Peningkatan minor.
Gradient Boosting	0.7205	Performa cukup baik.
LightGBM	0.7547	Performa sangat baik, model tercepat.
🏆 Random Forest	0.7822	Model dengan performa terbaik.

Ekspor ke Spreadsheet
Hasil menunjukkan bahwa model ensemble berbasis tree, khususnya Random Forest, memberikan performa paling unggul.

🚀 Kesimpulan
Berdasarkan serangkaian pengujian, dapat disimpulkan bahwa model Random Forest adalah yang paling andal untuk memprediksi durasi perjalanan taksi di New York City, dengan skor R² sebesar 0.7822.

Keberhasilan ini tidak hanya didukung oleh kekuatan algoritma, tetapi juga oleh proses feature engineering yang komprehensif. Fitur-fitur turunan seperti jarak Haversine, pola waktu, dan kecepatan rata-rata terbukti sangat signifikan dalam meningkatkan akurasi prediksi model.
