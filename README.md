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

```

## Catatan Dataset

Pada dataset ini ternyata hanya ada 15 folder. Lalu saat di cek manual, ternyata ada beberapa citra yang salah masuk folder (satu folder isinya dua kelas).

Setelah mencari sumber lain dari  :
https://www.robots.ox.ac.uk/~vgg/data/flowers/17/
Ternyata dataset tersebut memiliki informasi seperti ini :
- Oxford 17 Flowers Dataset terdiri dari 17 kelas x 80 citra = 1.360 citra.
- Lalu untuk nama file citra dimulai dari `image_0001.jpg` sampai `image_1360.jpg` dengan jumlah 80 citra tiap kelas.
- Untuk kelas yang foldernya hilang dari dataset kaggle adalah colts foot dan lily valley.

 Untuk citra yang salah masuk folder ada seperti berikut :

| Folder Kaggle | Jumlah | Isi sebenarnya | Masalah |
|---|---|---|---|
| `snowdrop` | 160 | 0081-0160 snowdrop + 0161-0240 lily valley | dua kelas digabung |
| `dandelion` | 160 | 0881-0960 colts foot + 0961-1040 dandelion | dua kelas digabung |
| `daisy` | 85 | 0796-0800 sunflower + 0801-0880 daisy | 5 citra sunflower nyasar |
| `sunflower` | 75 | 0721-0795 | kurang 5 citra (ada di `daisy`) |

Silahkan membuat dua folder baru, yaitu **colts foot** dan **lily valley**.

**Lalu pindah manual gambar yang masih nyasar ke folder yang tepat**

Untuk urutan nomor file gambar per kelas seperti berikut ini :

| No | Kelas | Nomor file |
|---|---|---|
| 1 | daffodil | 0001 - 0080 |
| 2 | snowdrop | 0081 - 0160 |
| 3 | lily valley | 0161 - 0240 |
| 4 | bluebell | 0241 - 0320 |
| 5 | crocus | 0321 - 0400 |
| 6 | iris | 0401 - 0480 |
| 7 | tiger lily | 0481 - 0560 |
| 8 | tulip | 0561 - 0640 |
| 9 | fritillary | 0641 - 0720 |
| 10 | sunflower | 0721 - 0800 |
| 11 | daisy | 0801 - 0880 |
| 12 | colts foot | 0881 - 0960 |
| 13 | dandelion | 0961 - 1040 |
| 14 | cowslip | 1041 - 1120 |
| 15 | buttercup | 1121 - 1200 |
| 16 | windflower | 1201 - 1280 |
| 17 | pansy | 1281 - 1360 |



## Setup
```
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
