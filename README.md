# 🏨 Akomodasi Data Visualization Dashboard

Proyek ini merupakan analisis dan visualisasi data akomodasi menggunakan Tableau.  
Dataset berasal dari Badan Pusat Statistik (BPS) Tahun 2024, dicek ulang secara manual dan disesuaikan dengan informasi terbaru dari Google Maps dan platform akomodasi. Setelah itu, data melalui proses pembersihan (cleaning) dan penyesuaian struktur sebelum divisualisasikan.

Dashboard ini dibuat untuk memberikan gambaran mengenai sebaran akomodasi, kategori layanan, dan informasi pendukung lain yang relevan.

---

## 📌 1. Tujuan Proyek
- Melakukan pembersihan dan penyeragaman data akomodasi.
- Menyiapkan data akhir yang siap digunakan untuk visualisasi.
- Membuat dashboard interaktif menggunakan Tableau untuk memudahkan analisis pola dan tren.
- Mendokumentasikan alur kerja (pipeline) dari data mentah hingga visualisasi akhir.

---

## 📂 2. Struktur Repository
```bash
akomodasi-data-visualization/
│
├── data/
│   ├── raw/
│   │   └── data_mentah.xlsx
│   │
│   ├── manual_ready/
│   │   └── data_visualisasi.csv
│   │
│   └── preprocessed_final/
│       └── data_clean.xlsx
│
├── notebook/
│   └── Data_Akomodasi_Prepro.ipynb
│
├── tableau/
│   ├── Dashboard_Data_Akomodasi.twbx
│   └── screenshot/
│       └── Dashboard_Data_Akomodasi.png
│
└── README.md
```

Penjelasan singkat:
- **raw/** — Data mentah sebelum diproses sama sekali.  
- **manual_ready/** — Data yang sudah disesuaikan secara manual (format tabel, longitude/latitude, kolom 0/1, dsb).  
- **preprocessed_final/** — Data yang sudah dibersihkan otomatis melalui notebook (lowercase, hapus karakter, normalisasi teks, dll).  
- **notebook/** — Notebook Jupyter berisi proses transformasi data.  
- **tableau/** — File Tableau dashboard dan screenshot tampilan akhirnya.

---

## 🔧 3. Alur Proses (Data Pipeline)

1. **Data Mentah**  
   Berasal dari pengumpulan lapangan atau sumber eksternal. Data masih belum rapi dan variasi penulisannya tinggi.

2. **Formatting Manual**  
   - Penyesuaian layout tabel  
   - Menambahkan kolom longitude & latitude  
   - Menambahkan kolom indikator (0/1) untuk platform akomodasi  
   - Perbaikan struktur agar mudah diproses lebih lanjut  

3. **Cleaning & Preprocessing (Notebook)**  
   Proses otomatis yang dilakukan di file `Data_Akomodasi_Prepro.ipynb`:
   - Mengubah huruf menjadi **lowercase**
   - Menghapus karakter khusus atau simbol tidak penting
   - Menstandarkan penulisan seperti mengganti `jl` → `jalan`
   - Membersihkan whitespace
   - Menyeragamkan nama kolom
   - Menyiapkan dataset final

4. **Visualisasi Tableau (Dashboard)**  
   - Menghubungkan dataset final ke Tableau  
   - Membuat dashboard interaktif: peta lokasi, bar chart, kategori akomodasi, dan insight lainnya  
   - Ekspor hasil ke `.twbx` dan screenshot

---

## 📊 4. Hasil Visualisasi

Dashboard dibuat menggunakan **Tableau** dan dapat dibuka melalui file tableau/Dashboard_Data_Akomodasi.twbx
Hasil visualisasi menunjukkan bahwa villa merupakan akomodasi terbanyak di Kota Batu dengan 309 unit, disusul homestay dan hotel. Dominasi villa ini sejalan dengan karakter wisatawan Batu yang umumnya datang berkelompok atau bersama keluarga. Sebaran akomodasi paling banyak ditemukan di wilayah Ngaglik, Sisir, Oro-oro Ombo, dan Temas, yakni area yang berdekatan dengan pusat wisata populer. Villa sendiri banyak terkonsentrasi di Songgoriti dan pusat kota, dua area yang menawarkan daya tarik berbeda: udara sejuk dan panorama alam, serta akses strategis ke fasilitas umum.

Dari sisi fasilitas, hotel cenderung lebih lengkap (kolam renang, restoran), sementara fasilitas villa dan homestay lebih bervariasi. Sebagian besar hotel di Batu belum memiliki klasifikasi bintang yang jelas, dan yang terdaftar didominasi hotel bintang 3. Harga akomodasi juga bervariasi: villa berada pada kisaran rendah–menengah, hotel umumnya lebih tinggi, sedangkan homestay relatif stabil terutama di area pusat kota.

Promosi akomodasi banyak dilakukan melalui Traveloka, Agoda, dan Tiket.com, menunjukkan bahwa pemilik akomodasi memaksimalkan platform populer untuk menjangkau pasar. Fasilitas tambahan seperti spa masih jarang tersedia, menandakan bahwa layanan premium belum menjadi fokus mayoritas akomodasi.

Secara keseluruhan, pola sebaran, fasilitas, dan harga akomodasi di Kota Batu menggambarkan penyesuaian terhadap kebutuhan wisatawan dan lokasi destinasi wisata utama.
