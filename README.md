# UTS Machine Learning
## Klasifikasi Potensi Nasabah Berlangganan Deposito Menggunakan Support Vector Machine (SVM)

### Identitas Mahasiswa
- **Nama:** [Galang Ombak Wahyu Syahputra]
- **NIM:** [2301010265]
- **Program Studi:** Informatika
- **Mata Kuliah:** Machine Learning
- **Dosen:** Dr. I Gede Totok Suryawan, S.Kom., M.T.
- **Semester:** Ganjil
- **Kelas:** [XX]

---

## 1. Deskripsi Proyek

Proyek ini bertujuan membangun model Machine Learning untuk mengklasifikasikan apakah seorang nasabah bank berlangganan deposito berjangka atau tidak berdasarkan karakteristik nasabah dan informasi kampanye pemasaran.

Algoritma yang digunakan adalah Support Vector Machine (SVM) dengan kernel Radial Basis Function (RBF), kemudian dibandingkan dengan DummyClassifier sebagai model baseline.

Pengerjaan proyek mengikuti tahapan CRISP-DM.

## 2. Dataset

- **Nama dataset:** Bank Marketing
- **Sumber:** UCI Machine Learning Repository
- **Link:** https://archive.ics.uci.edu/dataset/222/bank+marketing
- **File:** bank.csv
- **Jumlah data:** 4.521 baris
- **Jumlah atribut:** 17 kolom
- **Tanggal akses:** 26 November 2026
- **Lisensi:** CC BY 4.0

Dataset berisi informasi nasabah dan hasil kampanye pemasaran sebuah institusi perbankan. Kolom `y` menjadi target klasifikasi dengan kategori `yes` dan `no`.

Referensi:
Moro, S., Rita, P., & Cortez, P. (2014). Bank Marketing. UCI Machine Learning Repository. https://doi.org/10.24432/C5K306.

## 3. Metode

Penelitian menggunakan Jalur A (Klasifikasi), dengan tahapan:
1. Exploratory Data Analysis (EDA).
2. Preprocessing data.
3. Pembagian data training dan testing sebesar 80:20.
4. Pemodelan SVM dengan kernel RBF.
5. Perbandingan dengan DummyClassifier.
6. Stratified 5-Fold Cross Validation.
7. Hyperparameter Tuning menggunakan GridSearchCV.
8. Evaluasi menggunakan Confusion Matrix, Accuracy, Precision, Recall, dan F1-score.

## 4. Hasil Evaluasi

Hasil pengujian pada data testing:

| Metrik | SVM | DummyClassifier |
|---|---:|---:|
| Accuracy | 81,10% | 88,51% |
| Precision (yes) | 30,64% | 0% |
| Recall (yes) | 50,96% | 0% |
| F1-score (yes) | 38,27% | 0% |
| F1-macro | 64% | 47% |

Parameter terbaik GridSearchCV:
- C = 1
- class_weight = balanced
- gamma = scale

F1-score Cross Validation terbaik sebesar 36,22%.

SVM lebih mampu mengenali kelas `yes` dibandingkan DummyClassifier, walaupun accuracy-nya lebih rendah.

## 5. Struktur Repository

```text
UTS-ML-NIM-Nama/
├── README.md
├── notebook/
│   └── UTS_ML_NIM_Nama.ipynb
├── data/
│   └── bank.csv
└── reports/
    ├── grafik/
    └── slide-presentasi/
```

## 6. Pernyataan Penggunaan AI

ChatGPT digunakan sebagai alat bantu untuk memahami tahapan CRISP-DM, mempelajari konsep Machine Learning, membantu menyusun dan memeriksa kode Python, serta membantu interpretasi hasil evaluasi.

Seluruh kode dijalankan melalui Google Colab dan hasilnya diperiksa kembali oleh penulis. Penulis mempelajari keputusan preprocessing, pemodelan, evaluasi, dan kesimpulan serta bertanggung jawab atas hasil akhir proyek.

## 7. Cara Menjalankan

1. Buka notebook pada folder `notebook`.
2. Jalankan menggunakan Google Colab atau Jupyter Notebook.
3. Pastikan file `bank.csv` tersedia pada folder `data`.
4. Jalankan seluruh sel notebook dari awal sampai akhir.
