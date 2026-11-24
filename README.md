# Tugas Preprocessing Teks Ulasan E-Commerce Bahasa Indonesia

Tugas Natural Language Processing - analisis sentimen pada dataset ulasan *e-commerce* berbahasa Indonesia, mulai dari pemeriksaan dataset sampai lima tahap *text Preprocessing*.

| | |
|---|---|
| **Nama** | Lusi Fitriani |
| **NIM** | 25146065 |
| **Mata Kuliah** | Natural Processing Language |
| **Dataset** | [dipawidia/ecommerce-product-review-sentiment](https://huggingface.co/dipawidia/ecommerce-product-review-sentiment) |

# Isi Repository

|---|---|
| **tugas_nlp_lusi_fitriani_25146065.ipynb** | Notebook utama: informasi dataset, 5 tahap prepocessing, 10 contoh sebelum/sesudah, dan analisis pengaruh preprocessing. Sudah dieksekusi, output tersimpan di dalamnya. |
| **README.md** | Profil saya yang menjelaskan isi dari project saya |

## Cara Menjalankan

```bash
# 1. Clone
git clone https://github.com/lusifitriani-02/tugas_nlp_lusi_fitriani_25146065.git
cd tugas_nlp_lusi_fitriani_25146065

# 2. Virtual environtment (Windows)
python -m venv .venv
.venv\Script\active
pip install -r reqruitments.txt

# 3. Jalankan notebook
jupyter notebook tugas_nlp_lusi_fitriani_25146065.ipynb
```
## Tahap Preprocessing yang Dikerjakan

1. **Case Folding** - seluruh huruf menjadi kecil.
2. **Cleaning** - URL, penyebutan akun/*hashtag*, angka & harga, tanda baca, emoji, karakter khusus dihapus.
3. **Tokenisasi** - teks dipecah menjadi token kata dengan `nltk.tokenizse.RegexpTokenizer` (pola `[a-z]+`, sehingga hanya deret huruf yang tersisa sebagai sebagai tokenb).
4. **Stopword Removal** - kata umnum bahasa Indonesia dibuang (daftar *stopword* NLTK).
5. **Stemming** - kata berimbuhan dikembalikan ke bentuk dasar dengan **Sastrawi**.

|  |  |
|---|---|
| Jumlah data | 11.606 x 3 kolom |
| Kolom | `review` (teks ulasan), `sentimen` (1 = positif, 0 = negatif), `translate` (terjemah Inggris, tidak dipakai) |
| Distribusi label | negatif 5.803 dan positif 5.803 - seimbang (50 % : 50 %) |

hasil pengukuran dampak preprocessing (jumlah token, kosakata unik, *type-token ratio*, dan sebaran panjang ulasan) dihitung pada seluruh korpus dan dicetak langsung di bagian 6 notebook.