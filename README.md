<div align="center">

# 🫁 BPJS Healthcare Tuberculosis Patient Segmentation & Strategic Intervention

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  &nbsp;
  <img src="https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white" alt="Flask" />
  &nbsp;
  <img src="https://img.shields.io/badge/scikit_learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn" />
  &nbsp;
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas" />
  &nbsp;
  <img src="https://img.shields.io/badge/Status-Completed-2ECC71?style=for-the-badge" alt="Status" />
</p>

<p align="center">
  <em>An end-to-end data mining and machine learning implementation to cluster Tuberculosis (TB) patients using K-Means Clustering and Principal Component Analysis (PCA), deployed via an interactive Flask web application.</em>
</p>

</div>

---

## 📌 Project Overview

Tuberkulosis (TB) adalah penyakit menular kronis yang membutuhkan penanganan jangka panjang serta alokasi sumber daya kesehatan yang terarah. Menggunakan dataset kontekstual **BPJS Kesehatan (2015–2021)**, proyek ini mengelompokkan pola perilaku akses fasilitas kesehatan (FKTP dan FKRTL) serta profil demografi usia pasien penderita TB untuk merancang strategi intervensi kesehatan yang lebih tepat sasaran.

Proyek ini disusun mengikuti metodologi standar industri **CRISP-DM (Cross-Industry Standard Process for Data Mining)**.

---

## 🔄 CRISP-DM Workflow

Markdown
<div align="center">

# 🫁 BPJS Healthcare Tuberculosis Patient Segmentation & Strategic Intervention

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  &nbsp;
  <img src="https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white" alt="Flask" />
  &nbsp;
  <img src="https://img.shields.io/badge/scikit_learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn" />
  &nbsp;
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas" />
  &nbsp;
  <img src="https://img.shields.io/badge/Status-Completed-2ECC71?style=for-the-badge" alt="Status" />
</p>

<p align="center">
  <em>An end-to-end data mining and machine learning implementation to cluster Tuberculosis (TB) patients using K-Means Clustering and Principal Component Analysis (PCA), deployed via an interactive Flask web application.</em>
</p>

</div>

---

## 📌 Project Overview

Tuberkulosis (TB) adalah penyakit menular kronis yang membutuhkan penanganan jangka panjang serta alokasi sumber daya kesehatan yang terarah. Menggunakan dataset kontekstual **BPJS Kesehatan (2015–2021)**, proyek ini mengelompokkan pola perilaku akses fasilitas kesehatan (FKTP dan FKRTL) serta profil demografi usia pasien penderita TB untuk merancang strategi intervensi kesehatan yang lebih tepat sasaran.

Proyek ini disusun mengikuti alur metodologi standar industri **CRISP-DM (Cross-Industry Standard Process for Data Mining)**.

---

## 🔄 CRISP-DM Workflow

[1. Business Understanding] ➔ [2. Data Understanding] ➔ [3. Data Preparation]
│
[6. Web Deployment]       ◄─── [5. Model Evaluation]   ◄── [4. K-Means Modeling]


### 1. Business Understanding
* **Tujuan Bisnis:** Membantu BPJS Kesehatan dalam mengidentifikasi tipologi pasien TB agar dapat mendistribusikan layanan, edukasi, dan intervensi rujukan secara efisien.
* **Sasaran Teknis:** Mengelompokkan peserta BPJS ke dalam klaster perilaku menggunakan **K-Means Clustering** dan membangun sistem pendukung keputusan interaktif berbasis web.

### 2. Data Understanding & Exploration
Analisis dilakukan terhadap tiga subset data utama BPJS Kesehatan:
* **Data Kepesertaan:** Karakteristik demografis (tanggal lahir, jenis kelamin, domisili, faskes terdaftar) periode 2019, 2020, dan 2021.
* **Pelayanan FKRTL:** Data rujukan tingkat lanjut lebih dari 1,58 juta baris mencakup diagnosis masuk/primer ICD-10 (A15–A19), tipe rumah sakit, dan status pulang.
* **Pelayanan FKTP Non-Kapitasi:** Data tindakan dan kunjungan fasilitas tingkat pertama.
* **Korelasi Heatmap:** Analisis keterkaitan antar variabel numerik dan biaya medis.

### 3. Data Preparation & Feature Engineering
* **Pembersihan Data:** Menangani *missing values* menggunakan `SimpleImputer` (strategi mean dan mode) serta menghapus duplikasi data.
* **Feature Construction:**
  * Ekstraksi fitur `Usia` dari tanggal lahir peserta (`PSTV03`).
  * Perhitungan frekuensi kunjungan: `Frekuensi_Kunjungan_FKRTL` dan `Frekuensi_Kunjungan_FKTP`.
  * Pembentukan label kategori usia (`Muda`, `Dewasa`, `Lansia`).
* **Integrasi & Encoding:** Menggabungkan ketiga tabel menggunakan relasi *inner join* berdasarkan `PSTV01` (Nomor Peserta) dan melakukan konversi fitur menggunakan `LabelEncoder`.
* **Standardisasi Skala:** Normalisasi fitur numerik menggunakan `StandardScaler` untuk menyamakan bobot jarak Euclidean.

### 4. Modeling & Clustering
* **Metode Elbow:** Menguji variasi nilai K (1 hingga 10) terhadap *inertia*, menemukan titik lengkungan optimal pada **K = 3**.
* **Model K-Means:** Melatih model klastering pada K=3.
* **Reduksi Dimensi (PCA):** Memproyeksikan fitur multi-dimensi ke dalam 2 komponen utama (`PCA1` dan `PCA2`) untuk visualisasi scatter plot interaktif.

### 5. Model Evaluation
* **Silhouette Coefficient:** Menghasilkan skor evaluasi kualitas pemisahan klaster internal (SC = 0.2745).
* **Relevansi Kebijakan:** Validasi domain medis untuk memastikan setiap klaster menghasilkan tindakan penanganan yang masuk akal bagi pengambil kebijakan.

---

## 🎯 Karakteristik Klaster & Rekomendasi Intervensi

| Klaster | Karakteristik Pasien | Rekomendasi Strategi Kebijakan |
| :---: | :--- | :--- |
| **Klaster 0** *(Kuning)* | Pasien dengan frekuensi akses fasilitas kesehatan rendah dan risiko keparahan tahap awal. 
| **Edukasi Preventif:** Sosialisasi penyuluhan pola hidup sehat, edukasi gejala dini TB, dan penyediaan fasilitas skrining berkala di faskes tingkat primer. |
| **Klaster 1** *(Turquoise)* | Pasien usia dewasa dengan frekuensi akses ke rumah sakit rujukan (FKRTL) tinggi. 
| **Manajemen Perawatan Lanjutan:** Pemantauan intensif kepatuhan minum obat jangka panjang, pencegahan resistensi obat (MDR-TB), serta optimalisasi alokasi poli rujukan. |
| **Klaster 2** *(Ungu)* | Pasien yang jarang berkunjung ke faskes, namun memerlukan perhatian medis intensif saat datang. 
| **Penjangkauan Proaktif:** Skrining aktif (*case-finding*) berbasis komunitas lokal guna mendeteksi penyakit lebih awal sebelum mencapai fase darurat. |

---

## 🌐 Web Application & Deployment

Model K-Means dan *scaler* disimpan dalam format serial (`.pkl`) dan diintegrasikan ke dalam antarmuka web berbasis **Flask** untuk inferensi data pasien secara *real-time*.

### Fitur Input Aplikasi:
1. `Usia` (Usia Pasien)
2. `PSTV05` (Jenis Kelamin Terkode)
3. `PSTV09` (Provinsi Domisili Terkode)
4. `Frekuensi_Kunjungan_FKRTL` (Total kunjungan rumah sakit)
5. `Frekuensi_Kunjungan_FKTP` (Total kunjungan faskes primer)

---

## 📂 Repository Structure

```text
├── templates/
│   └── index.html             # Antarmuka input formulir dan visualisasi output
├── app.py                     # Script backend Flask untuk prediksi klaster
├── model.pkl                  # Model K-Means Clustering yang telah dilatih
├── scaler_model.pkl           # StandardScaler terkalibrasi
├── requirements.txt           # Daftar pustaka Python yang dibutuhkan
└── README.md                  # Dokumentasi proyek

⚙️ Installation & Usage Guide
1.Clone repository ini:
git clone [https://github.com/Krisniasiahaan/bpjs-tuberculosis-patient-clustering.git](https://github.com/Krisniasiahaan/bpjs-tuberculosis-patient-clustering.git)
cd bpjs-tuberculosis-patient-clustering

2.Buat & aktifkan virtual environment (opsional):
python -m venv venv
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

3.Install dependensi:
pip install -r requirements.txt

4.Jalankan aplikasi web:
python app.py
