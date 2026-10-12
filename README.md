# Mini Project Machine Learning - SDGs 12 Konsumsi dan Produksi yang Bertanggung Jawab

## Klasifikasi Status Jejak Karbon Individu 🌿
Proyek ini dibuat untuk memenuhi tugas kelompok dengan berfokus pada penerapan Artificial Intelligence untuk mendukung capaian Sustainable Development Goals (SDGs) 12: Konsumsi dan Produksi yang Bertanggung Jawab.

## 👥 Anggota Kelompok 5:
- Rahmah Hidayah Lahompu (NIM: F1G125047)
- Kenzo William (NIM: F1G125036)
- Muh. Dani Nugrah Ramadhan (NIM: F1G125067)

**Program Studi Ilmu Komputer**  
**Fakultas Matematika dan Ilmu Pengetahuan Alam**  
**Universitas Halu Oleo**

## 📌 Latar Belakang
Setiap aktivitas dan kebiasaan harian manusia—mulai dari pilihan transportasi, frekuensi perjalanan, hingga pola konsumsi barang dan penanganan sampah—menghasilkan emisi karbon yang berdampak langsung terhadap perubahan iklim. Sebagai langkah awal mendukung kesadaran lingkungan dan **SDG 12 (Konsumsi dan Produksi yang Bertanggung Jawab)**, diperlukan cara untuk mengenali sejauh mana pola hidup harian seseorang berpengaruh terhadap lingkungan.

## ❓ Rumusan Masalah
1. Bagaimana cara mengidentifikasi dampak emisi dari kebiasaan harian individu secara praktis dan otomatis?
2. Bagaimana merancang model *Artificial Intelligence* (AI) yang mampu memetakan pola perilaku konsumsi ke dalam status **"Tinggi Emisi"** atau **"Rendah Emisi"**?
3. Sejauh mana tingkat akurasi dan performa model AI dalam memprediksi status jejak karbon tersebut?

## 💡 Solusi
Mengembangkan sistem klasifikasi biner berbasis *Machine Learning* dengan membandingkan 2 algoritma machine learning yaitu **Random Forest** dan **Decision Tree** untuk memprediksi status emisi karbon. Lalu menentukan algoritma terbaik berdasarkan metrik evaluasi (Accuracy, Precision, Recall, dan F1-Score) yang akan digunakan untuk sistem prediksi.

- **Input:** Kebiasaan harian pengguna (opsi & jenis kendaraan, jarak tempuh bulanan, jumlah pakaian baru per bulan, frekuensi perjalanan udara, dan jumlah kantong sampah harian/mingguan).
- **Output:** Status emisi **`RENDAH`** (Ramah Lingkungan) atau **`TINGGI`** (Kurang Ramah Lingkungan), lengkap dengan saran aksi nyata yang disesuaikan untuk mengurangi jejak karbon individu.

## 📊 Dataset
Proyek ini menggunakan dataset publik yang bersumber dari Kaggle:  
👉 **[Individual Carbon Footprint Calculation (Mesut Duman)](https://www.kaggle.com/datasets/dumanmesut/individual-carbon-footprint-calculation)**

* **Ukuran Data:** Terdiri dari 10.000 baris data dan 20 kolom fitur yang mencakup berbagai aspek gaya hidup serta aktivitas harian individu.
* **Fitur Utama yang Digunakan:** Dari total kolom yang tersedia, dipilih 6 fitur utama yang paling relevan untuk proses pemodelan (transportasi utama, jenis kendaraan, jarak tempuh bulanan, jumlah pakaian baru per bulan, frekuensi perjalanan udara, dan jumlah kantong sampah).
* **Target Variabel (`CarbonEmission`):** Nilai emisi karbon numerik yang kemudian dikonversi menjadi label biner (`0` = Rendah, `1` = Tinggi) menggunakan batas nilai median ($\pm 2.080$).

## 🔄 Alur
1. **Muat Dataset:** Mengimpor data dari file CSV (`Carbon Emission.csv`).
2. **Cleaning & Preprocessing:** Pengecekan data null & duplikat, pengisian nilai kosong pada kolom `Vehicle Type` dengan `'Unknown'`, serta pelabelan target biner (`Status_Emisi`) berdasarkan nilai median emisi.
3. **Exploratory Data Analysis (EDA):** Visualisasi distribusi status emisi, sebaran emisi berdasarkan frekuensi penerbangan, dan *heatmap* korelasi antar fitur numerik.
4. **Feature Selection:** Memilih 6 fitur prediktor utama dan melakukan *One-Hot Encoding* pada data kategorikal.
5. **Train-Test Split:** Membagi data menjadi 80% data latih (8.000 data) dan 20% data uji (2.000 data) menggunakan *stratified split*.
6. **Pemodelan:** Melatih dua algoritma klasifikasi, yaitu **Decision Tree** (`max_depth=3`) dan **Random Forest** (`n_estimators=100`, `max_depth=8`).
7. **Evaluasi Model:** Mengukur performa model menggunakan akurasi, presisi, *recall*, *F1-score*, dan *cross-validation*.
8. **Prediksi & Interpretasi:** Sistem menerima input kebiasaan harian pengguna, memproses prediksi, dan memberikan saran aksi nyata untuk mengurangi jejak karbon.

## 📈 Hasil Evaluasi Model

| No | Model | Accuracy | Precision | Recall | F1-Score |
| :---: | :--- | :---: | :---: | :---: | :---: |
| 1 | **Random Forest** | **0.8570** | **0.8800** | **0.8200** | **0.8500** |
| 2 | **Decision Tree** | **0.8270** | **0.9100** | **0.7300** | **0.8100** |

* **Kesimpulan:** **Random Forest** terbukti lebih unggul dalam akurasi keseluruhan dan keseimbangan deteksi (F1-Score 0.85) dibandingkan *Decision Tree*.
