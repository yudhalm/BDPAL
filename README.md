Skip to content
mohliduo
bdpal
Repository navigation
Code
Issues
Pull requests
Actions
Projects
Security
Insights
bdpal
/README.md
mohliduo
mohliduo
Update dataset description for clarity and detail
348f971
 · 
1 hour ago
91 lines (70 loc) · 3.7 KB
bdpal
/README.md

Preview

Code

Blame
# UAS Big Data & Predictive Analytics Lanjut
# UAS Big Data & Predictive Analytics Lanjut

## 📌 Informasi Umum
- **Mata Kuliah** : Big Data & Predictive Analytics Lanjut  
- **Kode MK**     : ST153  
- **Program Studi** : S1 Informatika  
- **Universitas** : Universitas AMIKOM Yogyakarta  
- **Semester**    : Ganjil 2025/2026  

## 👨‍🏫 Dosen Pengampu
- Mulia Sulistiyono, S.Kom., M.Kom.

## 👥 Anggota Kelompok

| No | Nama | NIM |
|----|------|-----|
| 1  | Muhammad Ridho Ramadhan | 23.11.5772 |
| 2  | Fais Maulana Ma'ruf | 23.11.5789 |
| 3  | Laily Yudha Mukti | 23.11.5793 |
| 4  | Bani Hudli Daniar | 23.11.5795 |
| 5  | Muhammad Rafa Athalla Fawwaz | 23.11.5810 |

---

## 📂 Tentang Dataset
**Topik:** E-commerce Shopper Behavior and Lifestyle  
**Sumber:** [Kaggle Dataset](https://www.kaggle.com/api/v1/datasets/download/dhrubangtalukdar/e-commerce-shopper-behavior-amazonshopify-based)

Dataset ini dipilih karena memenuhi karakteristik Big Data (Volume, Velocity, Variety, Veracity, and Value), mencakup berbagai fitur demografis dan perilaku belanja pelanggan (seperti spending, frekuensi pembelian, dll) yang cocok untuk dianalisis secara batch processing.

---

## 🛠️ Tech Stack
* **Language:** Python (3.x)
* **Framework:** Apache Spark (PySpark)
* **Environment:** Google Colab / Local Jupyter Notebook
* **Libraries:** `pyspark.sql`, `pyspark.ml`, `pyspark.rdd`

---

## 📝 Penyelesaian Soal UAS

### 1. Data Ingestion & Storage (HDFS)
* Mengunduh dataset langsung dari Kaggle menggunakan `curl`.
* Menyimpan dan memuat dataset ke dalam Spark DataFrame (`spark.read.csv`).

### 2. Big Data Pipeline & Processing

* **MapReduce (RDD Operations):**
    * Menggunakan `map`, `reduceByKey`, `groupByKey`, dan `combineByKey` untuk menghitung aktivitas user dan rata-rata pengeluaran per negara secara manual.
* **Exploratory Data Analysis (EDA):**
    * Cek skema data (`printSchema`) dan statistik deskriptif.
    * Melihat distribusi user berdasarkan gender dan negara.
* **Preprocessing:**
    * *Data Cleaning:* Handling missing value dengan `.na.drop()`.
    * *Type Casting:* Mengubah tipe data kolom numerik (seperti `monthly_spend`, `weekly_purchases`) menjadi tipe yang sesuai (`Double/Int`) untuk pemrosesan.
* **Data Manipulation (Spark SQL):**
    * Menggunakan SQL Queries untuk agregasi nilai rata-rata pengeluaran per negara.
    * Filtering user dengan pengeluaran di atas threshold tertentu.

### 3. Machine Learning Modeling (MLlib)
Tugas ini melakukan klasifikasi (Supervised Learning) untuk memprediksi **`premium_subscription`** (Apakah user akan berlangganan premium atau tidak).

* **Feature Engineering:** Menggunakan `VectorAssembler` untuk menggabungkan fitur numerik (Age, Income, Spend, dll).
* **Komparasi Algoritma:**
    1.  ✅ **Logistic Regression**
    2.  ✅ **Random Forest Classifier**

### 4. Hyperparameter Tuning & Evaluation
* **Tuning:** Menggunakan `CrossValidator` dan `ParamGridBuilder` untuk mencari parameter terbaik pada model **Random Forest** (tuning `numTrees` dan `maxDepth`).
* **Model Evaluation:**
    Evaluasi dilakukan menggunakan metrik:
    * Area Under ROC (AUC)
    * Accuracy
    * Precision, Recall, & F1-Score

---

## 📊 Hasil Evaluasi (Summary)
Berdasarkan hasil :
* **Model Terbaik:** Random Forest (setelah tuning).
* **Akurasi:** ~64%
* **Kesimpulan:** Model dapat digunakan untuk memprediksi potensi user berlangganan premium, namun masih memerlukan *feature engineering* lebih lanjut untuk meningkatkan nilai AUC dan F1-Score.

---

## 🚀 Cara Menjalankan Project
1.  Clone repository ini atau download file `.ipynb`.
2.  Upload file ke Google Colab atau jalankan di local environment yang sudah terinstall Spark.
3.  Pastikan koneksi internet aktif untuk mendownload dataset via `curl` pada cell awal.
4.  Run All Cells.
 
