# Perbandingan Efektivitas MLP dan Random Forest pada Klasifikasi Jenis Bunga

Kelompok 10:
- Adiyatma Eka Saputra (23081010134)
- Fauzan Ilyas Almeyda (23081010188)
- Miftahus Syifaul Haqqi (23081010197)
- Ahmad Baihaqi (23081010218)

## Dataset
Oxford Flower 17 Categories (Kaggle):
https://www.kaggle.com/datasets/cantonioupao/oxford-flower-17categories-labelled

Download dewe, terus ekstrak ke folder `data/`.

## Setup
```bash
git clone <url-repo>
cd flower-classification

python -m venv .venv
.venv\Scripts\activate

pip install -r requirements.txt
nbstripout --install
```

Di VS Code: `Ctrl+Shift+P` > **Python: Select Interpreter** > pilih `.venv`,
lalu pilih kernel `.venv` saat membuka notebook.

## Struktur
| File | Fungsi |
|---|---|
| `preprocessing.ipynb` | Load citra, ekstraksi fitur, simpan ke `data/features.npz` |
| `mlp.ipynb` | Training + evaluasi MLP |
| `random_forest.ipynb` | Training + evaluasi Random Forest |
| `comparison.ipynb` | Perbandingan hasil MLP vs Random Forest |
| `results/` | Metrik (JSON) dan grafik |
