
# 🩺 **Deteksi Gambar Untuk Klasifikasi Kanker Payudara**
## Domain Proyek

Proyek ini berada dalam domain kesehatan, khususnya dalam bidang deteksi kanker payudara melalui citra histopatologi digital. Dengan memanfaatkan teknik pembelajaran mesin dan deep learning, proyek ini bertujuan untuk membantu proses diagnosis dini kanker payudara secara otomatis, yang dapat menjadi pendukung keputusan bagi tenaga medis.

---

## 💼 Businees Understanding

Kanker payudara merupakan salah satu penyebab utama kematian akibat kanker pada wanita di seluruh dunia. Diagnosis dini sangat penting untuk meningkatkan peluang kesembuhan. Namun, proses identifikasi kanker dari citra histopatologi secara manual dapat memakan waktu, bersifat subjektif, dan rentan terhadap kesalahan.

Proyek ini bertujuan untuk membangun model deep learning yang dapat secara otomatis membedakan antara jaringan kanker dan non-kanker dalam gambar histopatologi, sehingga dapat:

- Meningkatkan efisiensi diagnosis.

- Mengurangi beban kerja tenaga medis.

- Memberikan hasil yang lebih konsisten dan objektif.

---



## 📊 Data Understanding

Dataset yang digunakan adalah Breast Histopathology Images (IDC Regular), yang terdiri dari ribuan patch citra mikroskopis ukuran 50x50 piksel dari jaringan payudara. Terdapat dua label klasifikasi:

- 0: Jaringan normal (non-kanker)

- 1: Invasive Ductal Carcinoma (IDC), yaitu kanker payudara

Distribusi data cukup seimbang, dan gambar disimpan dalam format JPEG. Contoh gambar dari masing-masing kelas dianalisis secara visual untuk memahami karakteristik visual dari sel kanker dan normal.

---
## 🧹 Data Preparation

Langkah-langkah dalam persiapan data:

- Ekstraksi dan pembacaan gambar dari folder dataset.

- Preprocessing termasuk resizing gambar menjadi ukuran yang seragam (50x50 piksel) dan normalisasi nilai piksel ke rentang [0, 1].

- Label encoding dan pembuatan array X (fitur/gambar) dan y (label).

- Split data menjadi set pelatihan dan pengujian (training dan testing) menggunakan `train_test_split`.

---

## 🤖 Model Development

Model yang digunakan adalah Convolutional Neural Network **(CNN)** dengan arsitektur sederhana yang terdiri dari:

- Lapisan konvolusi dan max pooling untuk mengekstrak fitur spasial dari gambar.

- Lapisan dropout untuk mencegah overfitting.

- Fully connected layer (dense) untuk klasifikasi akhir.

Model dikompilasi menggunakan:

- Loss function: Binary Crossentropy

- Optimizer: Adam

- Metrics: Akurasi (Accuracy)

Model dilatih selama beberapa epoch dan performa pada data validasi dievaluasi setiap epoch.

---

## 📈 Evaluasi Model
Model dievaluasi dengan menggunakan data uji (test set) dan beberapa metrik utama:

- **Akurasi**: Persentase prediksi yang benar.

- **Confusion Matrix**: Untuk melihat jumlah True Positive, True Negative, False Positive, dan False Negative.

- **Classification Report**: Menampilkan precision, recall, f1-score untuk masing-masing kelas.

Visualisasi seperti plot loss dan akurasi per epoch juga digunakan untuk mengevaluasi kinerja selama proses pelatihan.

Model menunjukkan performa yang baik dalam membedakan antara gambar jaringan kanker dan non-kanker, meskipun dapat ditingkatkan lebih lanjut dengan arsitektur CNN yang lebih kompleks atau augmentasi data.
