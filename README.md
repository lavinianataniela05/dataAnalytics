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

## 🔧 Hyperparameter Tuning (Contoh Sintaks)

```python
from sklearn.ensemble import RandomForestRegressor
from sklearn.model_selection import RandomizedSearchCV

rf = RandomForestRegressor()
param_dist = {
    'n_estimators': [100, 200, 300],
    'max_depth': [10, 20, 30, None],
    'min_samples_split': [2, 5, 10]
}

rf_random = RandomizedSearchCV(
    estimator=rf,
    param_distributions=param_dist,
    n_iter=10,
    cv=3,
    verbose=2,
    n_jobs=-1
)

rf_random.fit(X_train, y_train)
