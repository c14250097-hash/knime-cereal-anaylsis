# 🥣 Analisis Dataset Cereals — KNIME Workflow

Repository ini berisi hasil analisis data nutrisi sereal menggunakan KNIME, mulai dari proses membaca data mentah (*Cereals.csv*), pembersihan data, eksplorasi, hingga pembuatan visualisasi dan insight akhir.  

Seluruh analisis berfokus pada hubungan nutrisi dengan rating setiap produk sereal.

---

# 📥 1. Proses Analisis: Dari CSV → KNIME → Visualisasi

Berikut adalah alur lengkap bagaimana data diproses:

---

## 🔹 **1. Import Data (Cereals.csv)**  
Menggunakan node **CSV Reader**, KNIME membaca data mentah yang berisi:

- Kalori  
- Protein  
- Lemak  
- Natrium  
- Serat  
- Gula  
- Potassium  
- Rating  
- dan atribut lain

Langkah ini memastikan semua kolom dibaca dengan tipe data yang benar.

---

## 🔹 **2. Data Preprocessing (Pembersihan Data)**  
Node yang digunakan dalam workflow:

- **Missing Value** → menangani data kosong  
- **Column Filter** → memilih kolom relevan  
- **Row Filter** → membuang baris yang tidak lengkap  
- **Rule Engine / Math Formula** (jika perlu transformasi nilai)

Tahap ini bertujuan membuat data siap dianalisis tanpa error atau bias.

---

## 🔹 **3. Exploratory Data Analysis (EDA)**  
Node yang digunakan:

- **Statistics** → melihat mean, median, min, max  
- **Data Explorer** → mendeteksi outlier  
- **Sorter** / **GroupBy** → untuk agregasi & pola awal  

Hasil EDA memberi gambaran umum sebelum visual dibuat.

---

# 📊 2. Visualisasi & Penjelasan

Berikut visualisasi utama yang dihasilkan dari data:

---

## 📈 **1. Distribusi Kalori pada Sereal**  
![Distribusi Kalori](calories.png)

Sebagian besar sereal berada pada kisaran **90–120 kalori per porsi**, yang berarti produsen cenderung menargetkan produk sarapan sehat dengan kalori moderat.

---

## 📈 **2. Hubungan Kadar Gula dan Rating**  
![Sugar vs Rating](sugar_rating2.png)

Terlihat pola negatif: semakin tinggi kadar gula dalam sereal, rating **cenderung menurun**.  
Konsumen dan panel penilai tampaknya lebih menghargai sereal yang tidak terlalu manis.

---

## 📈 **3. Pengaruh Protein terhadap Rating**  
![Protein vs Rating](protein_rating.png)

Produk dengan kandungan protein lebih tinggi umumnya mendapat rating yang lebih baik.  
Ini menunjukkan bahwa nutrisi penting seperti protein berkontribusi positif terhadap persepsi kualitas sereal.

---

# 🧠 3. Insight & Kesimpulan Akhir

Dari seluruh proses analisis KNIME hingga visualisasi, diperoleh insight berikut:

### ✅ **1. Kalori stabil pada kisaran moderat**  
Mayoritas sereal tidak terlalu tinggi kalori, cocok untuk sarapan.

### ✅ **2. Gula memiliki pengaruh negatif terhadap rating**  
Sereal manis cenderung dinilai kurang baik, menunjukkan pergeseran preferensi ke arah makanan lebih sehat.

### ✅ **3. Protein meningkatkan rating**  
Kandungan protein memberi nilai tambah dalam persepsi kesehatan sereal.

### ✅ **4. Kombinasi nutrisi “ideal” bagi rating tinggi:**  
- Kalori moderat  
- Gula rendah  
- Protein cukup tinggi  

### 🎯 **Kesimpulan Utama:**  
Sereal dengan komposisi lebih sehat mendapatkan rating lebih tinggi. KNIME mempermudah keseluruhan proses mulai dari membaca data, membersihkan, menganalisis, hingga menghasilkan visualisasi yang mudah dipahami.

---

# 📂 4. Isi Repository

Repository ini sebaiknya berisi:

