# 🥣 Analisis Dataset Cereals — KNIME Workflow

Repository ini berisi hasil analisis nutrisi produk sereal menggunakan KNIME, mulai dari proses membaca data mentah (*Cereals.csv*), pembersihan data, eksplorasi, hingga visualisasi dan insight akhir. Analisis berfokus pada hubungan nutrisi dengan rating setiap sereal.

---

## 📥 1. Input Data  
### **Node: CSV Reader / File Reader**
- Membaca file **Cereals.csv**  
- Mengonversi secara otomatis tipe data (integer, double, string)  
- Mengecek apakah ada kolom kosong atau baris tidak valid  
- Menghasilkan tabel data mentah sebagai dasar analisis


## 1️⃣ Column Filter  
Node **Column Filter** digunakan sebagai langkah awal untuk memilih kolom-kolom
yang diperlukan saja dari dataset `Cereals.csv`.  
Kolom yang kurang relevan atau tidak digunakan untuk pemodelan dihapus
agar analisis menjadi lebih efisien.

---

## 🧹 2. Data Cleaning  
Workflow melakukan pembersihan awal agar data siap digunakan.
## 2️⃣ Missing Value  
Node **Missing Value** bertugas menangani data kosong.  
Pada tahap ini, KNIME melakukan:

- Pengisian nilai kosong secara otomatis (mean/median)  
- Menghilangkan baris jika diperlukan  
- Menstabilkan dataset sebelum diproses lebih lanjut  

Hal ini penting untuk menghindari error saat normalisasi atau pemodelan.

---

## 📊 3. Exploratory Data Analysis (EDA)
Workflow mengevaluasi pola dasar di dalam dataset.
## 3️⃣ Normalizer  
Node **Normalizer** menstandarkan seluruh nilai numerik.  
Normalisasi dilakukan agar:

- Semua variabel berada dalam skala yang seragam  
- Model regresi tidak bias terhadap kolom yang memiliki skala lebih besar  

Metode normalisasi biasanya menggunakan *min–max* atau *z-score*.

---

## 4️⃣ Linear Regression Learner  
Node **Linear Regression Learner** digunakan untuk melatih model regresi linear.  
Tujuannya untuk memprediksi **rating sereal** berdasarkan faktor nutrisi seperti:

- Kalori  
- Protein  
- Serat  
- Gula  
- Sodium  

Model mempelajari hubungan linier antara variabel nutrisi dan nilai rating.

---

## 5️⃣ Regression Predictor  
Node **Regression Predictor** memberikan prediksi rating baru berdasarkan model
yang sudah dilatih.  
Output-nya berupa kolom baru berisi nilai rating prediksi.

---

## 6️⃣ Numeric Scorer  
Node **Numeric Scorer** digunakan untuk mengevaluasi performa model.  
Metrik yang dihitung meliputi:

- RMSE (Root Mean Square Error)  
- MAE (Mean Absolute Error)  
- R² (Coefficient of Determination)  

Langkah ini membantu mengetahui seberapa baik model memprediksi rating produk.

---

## 7️⃣ Denormalizer  
Node **Denormalizer** mengembalikan data ke skala aslinya setelah proses prediksi.  
Hal ini diperlukan karena:

- Normalizer mengubah skala data  
- Prediksi model berada pada skala yang sudah dinormalisasi  
- Denormalizer mengembalikan nilai ke format yang dapat dibaca dan dianalisis

---

# 📊 Visualisasi Output

Workflow menghasilkan tiga jenis visualisasi utama:

---

## 📈 Scatter Plot  
Scatter plot digunakan untuk melihat hubungan antara variabel nutrisi 
(misalnya gula atau protein) dengan rating.  
Visualisasi ini membantu mengidentifikasi pola linear atau tren tertentu.

---

## 📉 Histogram  
Histogram digunakan untuk memahami distribusi nilai seperti:

- Distribusi kalori  
- Distribusi kandungan gula  
- Distribusi rating  

Visual ini menunjukkan bagaimana data tersebar dan apakah ada outlier.

---

## 📦 Box Plot  
Box plot menggambarkan:

- Outlier  
- Nilai median  
- Quartile distribusi nutrisi  

Sangat berguna untuk memahami variasi nutrisi antar jenis sereal.

---
# 📊 2. Visualisasi dan Penjelasan

Berikut visualisasi utama berdasarkan file PNG yang telah di-upload ke repository ini:

---

## 📈 **1. Distribusi Kalori (Histogram)**
![Histogram Kalori](Histogram.png)

Histogram menunjukkan bahwa sebagian besar produk sereal memiliki **90–120 kalori**.  
Ini menandakan produsen cenderung menjaga nilai kalori tetap moderat agar sereal dianggap lebih sehat sebagai menu sarapan.

---

## 📈 **2. Pengaruh Serat (Fiber) terhadap Rating**
![Scatter Fiber](Scatter%20Plot%20fiber.png)

Scatter plot menunjukkan hubungan kandungan **serat** dengan **rating**.  
Terlihat kecenderungan bahwa sereal dengan serat lebih tinggi sering mendapatkan rating lebih baik.  
Serat adalah komponen penting kesehatan sehingga memengaruhi persepsi kualitas.

---

## 📈 **3. Pengaruh Gula terhadap Rating**
![Scatter Gula](Scatter%20Plot%20sugars.png)

Terlihat pola negatif: semakin tinggi kadar gula, rating cenderung menurun.  
Konsumen cenderung memilih sereal yang tidak terlalu manis dan lebih sehat.

---

## 📈 **4. Scatter Plot Nutrisi Lainnya**
![Scatter Plot umum](Scatter%20Plot.png)

Scatter Plot ini memberikan gambaran hubungan nutrisi lain terhadap rating.  
Variasi pola membantu memahami faktor tambahan yang berpengaruh terhadap kualitas sereal.

---

# 🧠 3. Insight & Kesimpulan

Berikut kesimpulan dari analisis KNIME dan visualisasi:

### ✔ **1. Kalori moderat adalah rentang umum produk**
Mayoritas sereal tidak terlalu tinggi kalori, mendukung citra makanan sehat.

### ✔ **2. Gula memengaruhi rating secara negatif**
Semakin manis produk, semakin rendah ratingnya.  
Konsumen lebih memilih sereal rendah gula.

### ✔ **3. Serat dan nutrisi baik lainnya meningkatkan rating**
Sereal dengan kandungan nutrisi seimbang dan tinggi serat lebih disukai.

### ✔ **4. Komposisi ideal berdasarkan dataset:**
- Gula rendah  
- Serat dan protein cukup tinggi  
- Kalori moderat  

## ⭐ Kesimpulan Mendetail Mengenai Pengaruh KNIME dalam Analisis Data Cereal

Analisis yang dilakukan menggunakan KNIME memberikan gambaran yang
menyeluruh dan terstruktur mengenai bagaimana berbagai komponen nutrisi
pada produk sereal dapat memengaruhi persepsi kualitas, preferensi
konsumen, serta potensi harga pasar. Dengan kemampuan KNIME dalam
mengolah data mentah menjadi informasi yang rapi, workflow KNIME
memungkinkan analisis yang lebih mendalam dan akurat dibandingkan
sekadar pengamatan manual pada tabel nutrisi.

Melalui proses membaca data, pembersihan, eksplorasi, hingga
visualisasi, KNIME membantu mengungkap pola penting. Salah satu
temuan utamanya adalah bahwa rating produk sangat dipengaruhi oleh
kandungan nutrisi tertentu seperti gula, protein, serat, dan total
kalori. Produk dengan kadar gula tinggi cenderung mendapat rating
lebih rendah. Temuan ini sejalan dengan tren global di mana konsumen
semakin sadar akan risiko kesehatan seperti obesitas, diabetes, dan
konsumsi gula berlebih. Akibatnya, produsen sereal yang menawarkan
alternatif rendah gula cenderung memiliki posisi pasar yang lebih
kuat, karena produk tersebut lebih disukai dan dianggap lebih layak
dibayar dengan harga premium.

Di sisi lain, kandungan protein dan serat yang lebih tinggi tampak
memberikan kontribusi positif terhadap rating. Produk dengan protein
tinggi sering kali dipandang lebih mengenyangkan dan bergizi, sehingga
dapat menarik konsumen yang mencari sereal sebagai sumber energi
jangka panjang. Produk dengan serat tinggi juga dianggap lebih sehat
karena membantu pencernaan dan mengatur nafsu makan. Temuan ini
memberikan gambaran strategis bahwa produsen dapat meningkatkan nilai
jual produk dengan menambahkan bahan kaya protein atau memperkaya
kandungan serat. Dalam konteks harga, sereal dengan formulasi protein
atau serat lebih tinggi umumnya dijual dengan harga lebih mahal
karena dianggap premium dan berdasarkan analisis data, konsumen memang
memberikan rating lebih baik pada produk semacam itu.

KNIME berperan besar dalam memetakan hubungan nutrisi dengan rating
secara objektif. Workflow otomatis membantu menjaga konsistensi
analisis, mengurangi risiko kesalahan manusia, dan mempercepat proses
ketika dataset diperbarui. Dengan kemampuan untuk menjalankan ulang
analisis secara instan, KNIME menjadi alat yang sangat berguna dalam
pengembangan produk baru, penyesuaian resep, dan pemantauan perubahan
preferensi konsumen dari waktu ke waktu.

Selain itu, insight nutrisi juga dapat dikaitkan dengan strategi harga.
Sereal dengan gula rendah tetapi protein lebih tinggi dapat diposisikan
sebagai produk “premium healthy cereal”. Dengan rating tinggi, produk
seperti ini memiliki peluang besar untuk dijual dengan margin
keuntungan lebih tinggi. Sebaliknya, sereal yang terlalu manis atau
rendah nutrisi cenderung memiliki rating lebih rendah. Produk seperti
ini biasanya memiliki sensitivitas harga yang lebih tinggi karena
konsumen melihatnya sebagai produk komoditas, bukan produk bernilai
tambah.

Kesimpulannya, KNIME bukan hanya membantu memahami data nutrisi sereal
secara teknis, tetapi juga memberikan nilai strategis dalam memahami
perilaku konsumen, strategi penentuan harga, dan arah inovasi produk.
Workflow KNIME dapat digunakan untuk memprediksi performa produk baru
berdasarkan komposisi nutrisi, memvalidasi kelayakan resep, dan
memberikan rekomendasi praktis untuk meningkatkan daya saing di pasar.
Dengan demikian, analisis ini menunjukkan bagaimana data nutrisi yang
sederhana dapat diubah menjadi insight bisnis bernilai tinggi melalui
sistem analisis yang terstruktur seperti KNIME.


