# 🧠 Convolutional Neural Network (CNN) for CIFAR-10 Classification

*Project UTS Deep Learning*

## 📌 Deskripsi Projek

Proyek ini bertujuan untuk membangun dan mengevaluasi model **Convolutional Neural Network (CNN)** untuk mengklasifikasikan gambar pada dataset **CIFAR-10**. Selain itu, proyek ini membandingkan performa **Custom CNN** dengan arsitektur **ResNet** serta melakukan **hyperparameter tuning** untuk meningkatkan akurasi.

Fokus utama proyek:

* Mengklasifikasikan **10 kelas** objek CIFAR-10.
* Membandingkan performa **Custom CNN vs ResNet-18**.
* Melakukan **tuning hyperparameter** (learning rate, batch size, optimizer, scheduler).
* Menganalisis **feature maps** dan **confusion matrix** untuk memahami perilaku model.

---

## 📂 Dataset: CIFAR-10

Dataset CIFAR-10 berisi **60.000 gambar berwarna 32×32** dengan 10 kelas:

`plane, car, bird, cat, deer, dog, frog, horse, ship, truck`

Pembagian data:

* **45.000** gambar → *training*
* **5.000** gambar → *validation*
* **10.000** gambar → *testing*
* `set_seed(42)` digunakan untuk memastikan *reproducibility*.

---

## 🏗️ Arsitektur Model

### 🔹 Custom CNN

* Kedalaman jaringan: **dangkal** (8 convolutional layers)
* Optimizer: **Adam**
* Learning Rate: **0.001**
* Batch Size: **32**
* Scheduler: **ReduceLROnPlateau**

### 🔹 ResNet (ResNet-18)

* Kedalaman jaringan: **dalam** (18 layer + residual blocks)
* Optimizer: **SGD**
* Learning Rate: **0.1**
* Batch Size: **128**
* Scheduler: **CosineAnnealingLR**

### 🔎 Perbandingan Kinerja Model

| Aspek                  | CNN                    | ResNet                                  |
| ---------------------- | ---------------------- | --------------------------------------- |
| Akurasi Test           | **87%**                | **94.64%**                              |
| Kedalaman Jaringan     | Dangkal (8 conv layer) | Dalam (18 layer + residual block)       |
| Kemampuan Generalisasi | Cukup baik             | Sangat baik                             |
| Overfitting            | Tidak terlihat         | Tidak signifikan                        |
| Analisis Feature Map   | Menangkap fitur dasar  | Menangkap fitur kompleks & fokus tinggi |
| Arsitektur             | Custom ringan          | ResNet dengan skip-connection           |

---

## 📈 Hasil & Analisis

### ✔️ Performa Model

* **CNN**: Akurasi test mencapai **87%**
* **ResNet-18**: Akurasi validasi mencapai **94.64%**
* Kurva loss & accuracy stabil pada kedua model
* Jarak train vs validation kecil → **tidak terjadi overfitting**

### ✔️ Pengaruh Hyperparameter Tuning

* Performa meningkat signifikan setelah penyesuaian:

  * Learning rate
  * Batch size
  * Optimizer
  * Learning rate scheduler
* ResNet sangat diuntungkan oleh **SGD + CosineAnnealingLR**

### ✔️ Analisis Feature Maps

* Kedua model membangun representasi fitur hierarkis.
* ResNet menghasilkan **fitur lebih tajam, terfokus, dan mendalam** dibandingkan CNN.
* Confusion matrix membantu mengidentifikasi kelas-kelas yang sering tertukar.

---

## 🧪 Evaluasi

Evaluasi dilakukan menggunakan:

* **Accuracy** (train/val/test)
* **Loss curve**
* **Confusion matrix**
* **Visualisasi feature maps**
* **Perbandingan arsitektur dan generalisasi**

---

## 📜 Kesimpulan

* Baik CNN maupun ResNet mampu mengklasifikasikan CIFAR-10 dengan baik.
* **ResNet secara konsisten mengungguli CNN** dalam akurasi, generalisasi, dan depth-based learning.
* Hyperparameter tuning berperan besar dalam peningkatan performa.
* Feature maps menunjukkan bahwa **ResNet lebih efektif dalam mengekstraksi fitur kompleks** sehingga mencapai akurasi lebih tinggi.

---

## 📁 Struktur Repository (opsional, jika ingin ditambahkan)

```
.
├── models/
├── notebooks/
├── images/
├── README.md
└── requirements.txt
```

---
