# BMLP
Repositori ini berisi implementasi lengkap pipeline Machine Learning untuk analisis data transaksi, mulai dari eksplorasi awal hingga pembangunan model clustering dan classification. Proyek ini dibuat secara sistematis dan empiris dengan pendekatan berbasis data yang logis dan terukur.

---

## Tahapan Proyek  

### **1. Exploratory Data Analysis (EDA)**  
Langkah ini bertujuan memahami struktur dan karakteristik dataset.  
Meliputi:  
- Menampilkan dataset awal dengan `head()`  
- Meninjau tipe data dan nilai kosong menggunakan `info()`  
- Mendapatkan ringkasan statistik deskriptif melalui `describe()`  

 *Tujuan:* Mengidentifikasi pola awal dan potensi anomali dalam data.  

---

### **2. Data Cleaning & Preprocessing**  
Dilakukan agar dataset siap digunakan dalam proses pelatihan model.  

Langkah-langkah:  
- Memeriksa *missing values* menggunakan `isnull().sum()`  
- Mendeteksi data duplikat dengan `duplicated().sum()`  
- Melakukan *feature scaling* menggunakan `MinMaxScaler()` atau `StandardScaler()`  
- Melakukan *feature encoding* pada fitur kategorikal dengan `LabelEncoder()`  
- Menghapus kolom identitas seperti:  
  `TransactionID`, `AccountID`, `DeviceID`, `IPAddress`, `MerchantID`  

 *Tujuan:* Meningkatkan kualitas data agar model dapat belajar secara optimal.  

---

### **3. Model Clustering (Unsupervised Learning)**  
Mengelompokkan pola transaksi dengan algoritma **K-Means Clustering**.  

Langkah-langkah utama:  
- Menentukan jumlah cluster optimal menggunakan **Elbow Method** dengan `KElbowVisualizer()`  
- Membangun model menggunakan `KMeans()` dari `sklearn.cluster`  
- Menyimpan model dengan `joblib.dump()` bernama **model_clustering**  

 *Tujuan:* Menemukan pola tersembunyi dan segmentasi alami pada data transaksi.  

---

### **4. Interpretasi Hasil Clustering**  
Menganalisis hasil pengelompokan untuk memahami karakteristik tiap cluster.  

Analisis mencakup:  
- Menghitung nilai **mean**, **min**, dan **max** dari fitur numerik  
- Mendeskripsikan ciri khas tiap cluster berdasarkan hasil agregasi  
- Menambahkan kolom hasil *clustering* bernama **Target** ke dataset  
- Mengekspor dataset hasil preprocessing untuk tahap selanjutnya  

 *Tujuan:* Memberikan wawasan deskriptif terhadap perilaku tiap kelompok data.  

---

### **5. Model Klasifikasi (Supervised Learning)**  
Menggunakan hasil *clustering* sebagai label (Target) untuk membangun model prediksi.  

Langkah-langkah:  
- Membagi dataset menjadi *train* dan *test* menggunakan `train_test_split()`  
- Melatih model menggunakan algoritma **Decision Tree Classifier**  
- Menyimpan model hasil pelatihan dengan `joblib.dump()` bernama **decision_tree_model.h5**  

 *Tujuan:* Mengembangkan model prediktif untuk klasifikasi data berdasarkan cluster.  

---

## Tools & Libraries  
Proyek ini dikembangkan menggunakan bahasa **Python** dan beberapa pustaka utama berikut:  

- `pandas` — manipulasi dan analisis data  
- `numpy` — operasi numerik  
- `matplotlib` & `seaborn` — visualisasi data  
- `scikit-learn` — implementasi algoritma *machine learning*  
- `yellowbrick` — visualisasi *Elbow Method*  
- `joblib` — penyimpanan model  

---

## Struktur Output  
| File / Folder | Deskripsi |
|----------------|------------|
| `model_clustering` | Model hasil *K-Means Clustering* |
| `decision_tree_model.h5` | Model *Decision Tree Classifier* |
| `preprocessed_dataset.csv` | Dataset hasil preprocessing dengan kolom **Target** |
| `notebook.ipynb` | Notebook utama berisi seluruh tahapan analisis |

---

## Cara Menjalankan Proyek  

1. Clone repositori ini  
   ```bash
   git clone https://github.com/username/BMLP.git
   cd BMLP
   ```

2. Install semua dependensi  
   ```bash
   pip install -r requirements.txt
   ```

3. Jalankan notebook utama  
   ```bash
   jupyter notebook notebook.ipynb
   ```

4. Pastikan model tersimpan otomatis setelah proses pelatihan:
   - `model_clustering`
   - `decision_tree_model.h5`

---

## Tujuan Akhir  
Menyediakan pipeline *end-to-end* yang dapat digunakan untuk:  
- Menganalisis dan memvisualisasikan pola transaksi  
- Mengelompokkan data secara otomatis  
- Mengklasifikasikan data baru berdasarkan hasil cluster  
- Menjadi dasar pengembangan sistem analitik berbasis data bisnis  

---

## Kata Kunci  
`Machine Learning` • `Clustering` • `K-Means` • `Classification` • `Decision Tree` • `EDA` • `Data Preprocessing` • `Python` • `Scikit-learn` • `Data Analytics`  

---

### Penulis  
**Rizki Muhammad Syamsi**  
Mahasiswa Teknik Informatika – Universitas Gunadarma  
