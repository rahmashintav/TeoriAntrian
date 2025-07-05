# Hospital Lead Time Classification

Proyek ini merupakan bagian dari tugas akhir pada mata kuliah Teori Antrian, yang bertujuan untuk mengklasifikasikan kategori waktu tunggu pasien UGD di lima rumah sakit Jakarta menggunakan pendekatan Machine Learning.

## Tujuan Proyek
Membangun model klasifikasi yang mampu memprediksi apakah waktu tunggu pasien berada dalam kategori *Cepat* (≤15 menit), *Sedang* (16–30 menit), atau *Lambat* (>30 menit) berdasarkan informasi waktu tanggap, waktu kedatangan, serta karakteristik fasilitas dan jam operasional rumah sakit.

## Dataset
Dataset diambil dari publikasi terbuka:
[Emergency Services Utilization in Jakarta (Brice et al., 2022) – Zenodo](https://zenodo.org/record/6607963)

## Metodologi
1. Eksplorasi Data dan Pembersihan
2. Feature Engineering 
3. Pembentukan Kelas Target (Cepat, Sedang, Lambat)
4. Penanganan Data Tidak Seimbang dengan SMOTENC
5. Pemilihan Model:
   - Balanced Random Forest
   - CatBoost
   - XGBoost
   - Voting Classifier
6. Evaluasi Model (Accuracy, Precision, Recall, F1-score)
7. Visualisasi Hasil Klasifikasi
8. Interpretasi Kinerja Model

## Hasil Model Terbaik
Model Voting Classifier memberikan kinerja keseluruhan terbaik dengan metrik:
- Akurasi: 90%
- F1-score Kelas Cepat: 0.95
- Macro Average F1-score: ±0.49
- Catatan: Performa pada kelas minoritas (Sedang & Lambat) masih perlu ditingkatkan lebih lanjut

## Visualisasi
- Distribusi waktu tunggu pasien
- Boxplot waktu tunggu berdasarkan shift
- Bar Plot Jumlah pasien berdasarkan shift
- Bar plot precision, recall, f1-score per kelas
- Confusion matrix

## Tools & Libraries
- Python 3.11
- Scikit-learn
- Pandas, NumPy, Matplotlib, Seaborn
- Imbalanced-learn
- XGBoost, CatBoost
- Google Colab

## Struktur File
- `eda_modeling.ipynb` – Notebook utama eksplorasi & klasifikasi
- `README.md` – Dokumentasi proyek
- `requirements.txt` – Dependensi pustaka
- `img/` – Visualisasi hasil (confusion matrix, metrik per kelas)
- `data/` – Dataset (opsional, bisa diunduh dari Zenodo)

## Catatan Tambahan
- Kelas "Cepat" sangat mendominasi dataset (>90%), menyebabkan tantangan signifikan dalam mendeteksi kategori minoritas.
- Implementasi SMOTENC membantu meningkatkan sensitivitas terhadap kelas "Sedang" dan "Lambat", meskipun hasilnya belum optimal.
- Temuan menarik lainnya adalah bahwa **mayoritas pasien dilayani secara cepat**, menandakan kualitas respons yang baik di kelima rumah sakit yang dianalisis.

## Author
Rahma Shinta V. – Master of Mathematics, Universitas Sebelas Maret
