# 💳 Pancaniti ET: Credit Card Fraud Scrutiny System V1.0

<div align="left">
  
  [![Open In Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)](https://colab.research.google.com/drive/19vLJUHVEptm-pDsfzts66aw82_pozZhU?usp=sharing)
  [![Hugging Face Model](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Models-yellow?style=for-the-badge)](https://huggingface.co/Ripanrz/credit-card-fraud-et-v1.0)
  [![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
  [![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)

</div>

---

## 📝 Deskripsi Proyek
***Pancaniti ET: Credit Card Fraud Scrutiny System V1.0*** adalah sistem deteksi penipuan kartu kredit berbasis *Machine Learning* yang dirancang khusus untuk menangani masalah ketidakseimbangan data *(imbalanced data)* secara ekstrem. 

Dengan mengombinasikan algoritma **Extra Trees Classifier** dan pendekatan ***Hybrid Resampling (SMOTE + Undersampling)***, sistem ini mampu mengenali pola transaksi mencurigakan dengan presisi di tengah jutaan transaksi normal. Proyek ini menggunakan dataset dari Kaggle (**"mlg-ulb/creditcardfraud"**) yang menerapkan standar ***Principal Component Analysis (PCA)*** untuk melindungi privasi pelanggan. Fitur-fitur asli ditransformasikan menjadi variabel numerik ($V1, V2, ..., V28$) untuk menjaga kerahasiaan tanpa menghilangkan karakteristik penting dalam pendeteksian pola transaksi.

---

## 🚀 Fitur Utama
* **Hybrid Resampling**: Solusi cerdas untuk menangani data yang sangat tidak seimbang (Fraud hanya 0.173%).
* **Extra Trees Power**: Memanfaatkan algoritma *Ensemble Learning* yang tangguh dan efisien.
* **Integrated Deployment**: Model dikemas menggunakan `joblib` dan diunggah langsung ke **Hugging Face Hub**.

---

## 🧠 Metodologi: Penjelasan Hybrid Resampling
Masalah utama dalam deteksi penipuan adalah **Data Jomplang**. Terdapat 284.315 transaksi normal berbanding hanya 492 transaksi penipuan. Proyek ini menggunakan teknik gabungan:

### 1. SMOTE (Oversampling Minoritas)
Menciptakan **data sintetis baru** berdasarkan pola transaksi penipuan yang ada. Ini memberi model lebih banyak contoh untuk dipelajari tanpa sekadar menduplikasi data lama.

### 2. Random Undersampling (Undersampling Mayoritas)
**Mengurangi sebagian data transaksi normal** agar jumlahnya tidak mendominasi memori model, sehingga model bisa lebih fokus pada perbedaan tipis antara transaksi asli dan palsu.

---

## 🛠️ Tech Stack
| Komponen | Teknologi |
| :--- | :--- |
| **Bahasa** | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) |
| **Modeling** | ![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white) ![Imbalanced-learn](https://img.shields.io/badge/Imbalanced--Learn-blue?style=flat-square) |
| **Manipulasi Data** | ![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/Numpy-013243?style=flat-square&logo=numpy&logoColor=white) |
| **Deployment** | ![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Repository-FFD21E?style=flat-square) |

---

## 📊 Hasil Evaluasi
Model Extra Trees menunjukkan performa *recall* yang tinggi dalam mendeteksi transaksi fraud. Namun, terdapat indikasi **overfitting** di mana model terlalu menyesuaikan diri dengan data hasil resampling.

**Saran Perbaikan:**
- Mengurangi rasio SMOTE.
- Membatasi `max_depth` pada pohon keputusan.
- Menerapkan teknik *pruning*.

<div align="center">
  <img src="hasil-evaluasi-credit-card-fraud-et-v1.0.png" alt="Hasil Evaluasi" width="800">
</div>

---

## 🌐 Akses Model
Anda dapat mengakses model yang telah di-deploy di sini:
👉 **[Hugging Face Repository](https://huggingface.co/Ripanrz/credit-card-fraud-et-v1.0)**

---
***Project dikembangkan sebagai bagian dari eksperimen sistem keamanan finansial berbasis AI.***
