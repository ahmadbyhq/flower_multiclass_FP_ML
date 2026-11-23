# Perbandingan Efektivitas MLP dan Random Forest pada Klasifikasi Jenis Bunga

Kelompok 10:
- Adiyatma Eka Saputra (23081010134)
- Fauzan Ilyas Almeyda (23081010188)
- Miftahus Syifaul Haqqi (23081010197)
- Ahmad Baihaqi (23081010218)

## Dataset
Oxford Flower 17 Categories (Kaggle):
https://www.kaggle.com/datasets/cantonioupao/oxford-flower-17categories-labelled

1. Unduh dataset dari link di atas, lalu ekstrak file zip-nya.
2. Salin **folder-folder kelas** (`bluebell`, `buttercup`, `cowslip`, dst.) langsung ke dalam folder `data/`.
3. Hasil akhirnya harus seperti ini:

```
data/
├── .gitkeep
├── bluebell/
│   ├── image_0241.jpg
│   └── ...
├── buttercup/
├── cowslip/
├── ...
└── windflower/

## Setup
```bash
git clone <url-repo>
cd flower-classification

Gunakan versi **Python 3.12**

python -m venv .venv atau py -3.12 -m venv .venv
.venv\Scripts\activate atau .\.venv\Scripts\Activate.ps1

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
