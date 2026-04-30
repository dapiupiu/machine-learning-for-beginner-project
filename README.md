# BMLP — Project: KakaDaviDharmawan

![Project](https://img.shields.io/badge/Project-BMLP-blue) ![Notebook-ready](https://img.shields.io/badge/Notebooks-Jupyter-orange)

**Deskripsi singkat:**
Proyek ini mengeksplorasi dan memodelkan data transaksi bank untuk tujuan clustering dan klasifikasi. Repositori berisi notebook eksperimen, dataset, dan model yang diekspor (.h5). README ini menjelaskan alur lengkap, cara menjalankan eksperimen secara interaktif, dan file penting yang ada.

**Daftar Isi**
- [Ringkasan Proyek](#ringkasan-proyek)
- [File Penting](#file-penting)
- [Alur Kerja (Rangkaian Eksperimen)](#alur-kerja-rangkaian-eksperimen)
- [Cara Menjalankan Secara Interaktif](#cara-menjalankan-secara-interaktif)
- [Model & Hasil](#model--hasil)
- [Tips Eksplorasi Cepat](#tips-eksplorasi-cepat)
- [Lanjutan & Kontribusi](#lanjutan--kontribusi)

## Ringkasan Proyek

Proyek ini terdiri dari dua fokus utama:
- Clustering: mengekstrak pola kelompok pada transaksi menggunakan PCA + model clustering.
- Klasifikasi: membangun model untuk memprediksi label/kelas berdasarkan fitur yang tersedia (Decision Tree, Random Forest, dan tuning).

Semua eksperimen direkam dalam notebook Jupyter sehingga mudah dieksekusi ulang dan dimodifikasi.

## File Penting
- **Notebooks:**
	- [Notebook Clustering](%5BClustering%5D_Submission_Akhir_BMLP_KakaDaviDharmawan.ipynb)
	- [Notebook Klasifikasi](%5BKlasifikasi%5D_Submission_Akhir_BMLP_KakaDaviDharmawan.ipynb)
- **Data:**
	- [bank_transactions_data_edited.csv](bank_transactions_data_edited.csv) — dataset utama untuk klasifikasi.
	- [data_clustering.csv](data_clustering.csv) — data input untuk proses clustering.
	- [data_clustering_inverse.csv](data_clustering_inverse.csv) — versi transformasi terbalik untuk interpretabilitas.
- **Model terlatih (.h5):**
	- [decision_tree_model.h5](decision_tree_model.h5)
	- [explore_RandomForest_classification.h5](explore_RandomForest_classification.h5)
	- [tuning_classification.h5](tuning_classification.h5)
	- [model_clustering.h5](model_clustering.h5)
	- [PCA_model_clustering.h5](PCA_model_clustering.h5)

## Alur Kerja (Rangkaian Eksperimen)
1. Data collection & pembersihan — `bank_transactions_data_edited.csv` menjadi sumber yang dibersihkan.
2. Eksplorasi fitur dan visualisasi dalam notebook.
3. Preprocessing & transformasi (skala, encoding, PCA untuk reduksi dimensi).
4. Clustering: pelatihan PCA + algoritma clustering, simpan `PCA_model_clustering.h5` dan `model_clustering.h5`.
5. Klasifikasi: eksperimen Decision Tree dan Random Forest, hyperparameter tuning, simpan model `.h5`.
6. Evaluasi hasil dan interpretabilitas (metrik, confusion matrix, analisis cluster).

## Cara Menjalankan Secara Interaktif
- Persyaratan minimal: Python 3.8+, Jupyter atau JupyterLab, dan dependensi yang diperlukan (pandas, scikit-learn, tensorflow/keras jika model .h5 di-load).

1) Jalankan Jupyter Notebook/Lab di folder proyek:

```bash
pip install -r requirements.txt  # jika tersedia
jupyter lab
```

2) Buka notebook yang ingin dijalankan: gunakan tautan pada bagian **File Penting**.

3) Eksekusi cell bertahap: mulai dari bagian data -> preprocessing -> training -> evaluasi. Notebook disusun agar setiap langkah dapat di-run mandiri.

4) Untuk melihat model tersimpan (.h5) secara cepat, jalankan snippet berikut di Python:

```python
from tensorflow import keras
model = keras.models.load_model('decision_tree_model.h5')
model.summary()
```

## Model & Hasil
- Semua model akhir disimpan sebagai file `.h5` di root repositori. Gunakan notebook untuk memuat model, mereproduksi metrik, dan memvisualisasikan hasil.
- Jika ingin membandingkan metrik antar-eksperimen, jalankan cell evaluasi di notebook yang relevan.

## Tips Eksplorasi Cepat
- Mulai dari notebook Klasifikasi untuk melihat pipeline end-to-end.
- Untuk eksperimen clustering, jalankan notebook Clustering lalu buka visualisasi PCA.
- Jika dataset besar terasa lambat, coba subset data (mis. `df.sample(10000)`) saat eksplorasi awal.

## Lanjutan & Kontribusi
- Jika Anda ingin menambahkan: dokumentasikan perubahan di notebook baru, simpan model baru dengan nama deskriptif, dan tambahkan ringkasan hasil ke file `CHANGELOG.md`.
- Ingin bantuan menjalankan eksperimen di Colab atau membuat UI interaktif? Saya bisa menyiapkan `requirements.txt`, skrip `run_experiment.py`, atau dashboard kecil menggunakan Streamlit.

---
Versi ini dibuat untuk memudahkan pembaca menavigasi eksperimen dan mereproduksi hasil. Jika ingin, saya bisa:
- Menambahkan `requirements.txt` dan skrip reproducible.
- Menyiapkan badge 'Open in Colab' untuk setiap notebook.

Perubahan ada di [README.md](README.md). Beri tahu saya opsi lanjutan mana yang Anda mau.
