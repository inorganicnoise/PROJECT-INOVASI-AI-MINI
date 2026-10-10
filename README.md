# Klasifikasi Status Jejak Karbon Individu 🌿

## 📌 Latar Belakang
Setiap aktivitas dan kebiasaan harian manusia—mulai dari pilihan transportasi, frekuensi perjalanan, hingga pola konsumsi barang dan penanganan sampah—menghasilkan emisi karbon yang berdampak langsung terhadap perubahan iklim. Sebagai langkah awal mendukung kesadaran lingkungan dan **SDG 12 (Konsumsi dan Produksi yang Bertanggung Jawab)**, diperlukan cara untuk mengenali sejauh mana pola hidup harian seseorang berpengaruh terhadap lingkungan.

## ❓ Rumusan Masalah
1. Bagaimana cara mengidentifikasi dampak emisi dari kebiasaan harian individu secara praktis dan otomatis?
2. Bagaimana merancang model *Artificial Intelligence* (AI) yang mampu memetakan pola perilaku konsumsi ke dalam status **"Tinggi Emisi"** atau **"Rendah Emisi"**?
3. Sejauh mana tingkat akurasi dan performa model AI dalam memprediksi status jejak karbon tersebut?

## 💡 Solusi
Mengembangkan sistem klasifikasi biner berbasis *Machine Learning* menggunakan algoritma **Random Forest** dan **Decision Tree** untuk memprediksi status emisi karbon.

* **Input:** Kebiasaan harian pengguna (opsi & jenis kendaraan, jarak tempuh bulanan, jumlah pakaian baru per bulan, frekuensi perjalanan udara, dan jumlah kantong sampah harian/mingguan).
* **Output:** Status emisi **`RENDAH`** (Ramah Lingkungan) atau **`TINGGI`** (Kurang Ramah Lingkungan), lengkap dengan saran aksi nyata yang disesuaikan untuk mengurangi jejak karbon individu.
