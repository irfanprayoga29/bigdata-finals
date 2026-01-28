<br />
<p align="center">

  <h3 align="center">Klasifikasi Status Infeksi Pasien AIDS Menggunakan Random Forest</h3>

  <p align="center">
    Implementasi Data Mining untuk Prediksi Progresivitas Penyakit HIV/AIDS
    <br />
  </p>
</p>

## Tentang Proyek

Proyek ini bertujuan untuk membangun model *Machine Learning* yang mampu memprediksi apakah seorang pasien AIDS berisiko mengalami infeksi lanjut/kegagalan terapi (*critical infection*) atau tidak. 

Menggunakan algoritma **Random Forest Classifier**, proyek ini menganalisis pola dari data klinis pasien untuk memberikan prediksi yang akurat. Pendekatan ini diharapkan dapat membantu tenaga medis dalam menentukan strategi intervensi yang lebih dini dan tepat sasaran.

**Fitur Utama:**
* **Handling Imbalance Data:** Menggunakan teknik *Random Over-Sampling* untuk menangani ketimpangan data pasien.
* **Feature Selection:** Mengidentifikasi faktor risiko dominan (seperti jumlah CD4, usia, riwayat pengobatan).
* **High Accuracy:** Model mencapai akurasi **~94%** pada data uji.

## Dataset

Dataset yang digunakan adalah **AIDS Clinical Trials Group Study 175 (ACTG 175)** yang merupakan data publik dari uji klinis resmi di Amerika Serikat.

* **Sumber:** [Kaggle - AIDS Clinical Trials Group Study 175](https://www.kaggle.com/datasets/tanshihjen/aids-clinical-trials)
* **Jumlah Data:** 2.139 Baris (Pasien)
* **Jumlah Fitur:** 23 Variabel Klinis + 1 Target Label
* **Target Variable:** `cid` (0 = Stabil/Censoring, 1 = Gagal/Terinfeksi)

## Teknologi & Tools

Proyek ini dibangun menggunakan bahasa pemrograman Python dan library Data Science standar industri:

* ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) **Python 3.x**
* ![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white) **Pandas** (Manipulasi Data)
* ![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white) **Scikit-Learn** (Modeling)
* ![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black) **Matplotlib & Seaborn** (Visualisasi)
* **Imbalanced-learn** (Untuk teknik Resampling)

## Alur Kerja (Methodology)

Proses pengembangan model mengikuti standar **CRISP-DM**:

1.  **Data Understanding:** Eksplorasi distribusi kelas target dan korelasi antar fitur (EDA).
2.  **Preprocessing:**
    * Pemisahan fitur (X) dan target (y).
    * **Oversampling** dengan `RandomOverSampler` (menangani rasio kelas 1:4).
    * **Scaling** dengan `StandardScaler` (menormalisasi rentang nilai numerik).
3.  **Modeling:** Pelatihan algoritma `RandomForestClassifier` (n_estimators=200).
4.  **Evaluation:** Pengujian model menggunakan metrik Akurasi, Confusion Matrix, dan ROC-AUC.

## Hasil Evaluasi

Model berhasil menunjukkan performa yang sangat baik dalam mengklasifikasikan status pasien:

| Metrik | Skor |
| :--- | :--- |
| **Akurasi** | **94.14%** |
| **Precision** | High |
| **Recall** | High |
| **F1-Score** | High |

> *Catatan: Grafik ROC Curve dan Feature Importance dapat dilihat selengkapnya di dalam notebook.*

## Cara Menjalankan (Installation)

1.  **Clone Repository**
    ```sh
    git clone https://github.com/irfanprayoga29/bigdata-finals.git
    ```
2.  **Install Library**
    Pastikan Anda memiliki Python, lalu install library yang dibutuhkan:
    ```sh
    pip install pandas numpy scikit-learn matplotlib seaborn imbalanced-learn joblib
    ```
3.  **Jalankan Notebook**
    Buka file `.ipynb` menggunakan Jupyter Notebook atau Google Colab untuk melihat proses analisis lengkap.
4.  **Gunakan Model (Deploy)**
    Model yang sudah dilatih tersimpan dalam file `.joblib`. Anda bisa memuatnya kembali dengan script berikut:
    ```python
    import joblib
    model = joblib.load('model_uas_satria_rf.joblib')
    # model.predict(data_baru)
    ```

## 👤Detail Author

**Satria Irfan Prayoga**
* 23.61.0266
* IF-BigData6
