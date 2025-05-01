# ✈️ Prediksi Jumlah Penerbangan Bersamaan (Concurrent Flights)

Proyek ini membangun model prediktif untuk memperkirakan jumlah penerbangan yang terjadi secara bersamaan menggunakan data historis penerbangan. Dataset yang digunakan terdiri dari lebih dari **6 juta entri**, yang telah dibersihkan dan diproses untuk mendukung performa model secara optimal.

## 🧹 Pra-pemrosesan Data

Langkah-langkah utama dalam proses pembersihan data:
- Menghapus kolom yang tidak relevan dengan prediksi.
- Menangani nilai yang hilang (missing values).
- Membuat kategori waktu keberangkatan (pagi, siang, malam) dari fitur waktu.

## 🧠 Model dan Algoritma

Dua algoritma yang digunakan untuk membangun model prediktif:

- `RandomForestRegressor` dari scikit-learn
- `XGBRegressor` dari XGBoost

Keduanya melalui proses **hyperparameter tuning** menggunakan `RandomizedSearchCV`.
