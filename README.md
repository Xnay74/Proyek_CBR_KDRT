# Sistem Case-Based Reasoning (CBR) untuk Kasus KDRT
Proyek ini adalah implementasi sistem *Case-Based Reasoning* (CBR) untuk melakukan temu kembali (*retrieval*) kasus hukum Kekerasan Dalam Rumah Tangga (KDRT) berbasis kemiripan tekstual dari dokumen putusan Mahkamah Agung Republik Indonesia.

## 📁 Struktur Repositori
repositori ini disusun dengan struktur sebagai berikut:
```text
Proyek_CBR_KDRT/
│
├── data/
│   ├── raw/          # Berisi 60 dokumen putusan asli dalam format (.pdf)
│   ├── raw_txt/      # Hasil ekstraksi teks bersih dari PDF (.txt)
│   └── processed/    # Hasil ekstraksi fitur terstruktur dalam format tabel (.csv)
│
├── notebooks/
│   ├── 01_preprocessing.ipynb         # Tahap 1: Ekstraksi & Pembersihan Teks PDF
│   ├── 02_case_representation.ipynb    # Tahap 2: Ekstraksi Fitur & Representasi Kasus ke CSV
│   └── 03_similarity_retrieval.ipynb  # Tahap 3: Perhitungan Cosine Similarity & Retrieval
│
├── README.md         # Petunjuk instalasi dan eksekusi proyek (File ini)
└── requirements.txt  # Daftar dependensi library Python yang dibutuhkan

```

## 🛠️ Petunjuk Instalasi

Untuk menjalankan proyek ini di komputer lokal Anda, pastikan telah menginstal Python (disarankan versi 3.13+) dan ikuti langkah berikut:

1. Clone repositori ini ke komputer lokal Anda atau download sebagai ZIP.
2. Buka terminal atau Command Prompt di dalam folder proyek ini.
3. Instal seluruh library yang dibutuhkan dengan menjalankan perintah berikut:
```bash
pip install -r requirements.txt

```



## 🚀 Cara Menjalankan Pipeline (End-to-End)

Proyek ini dibagi menjadi 3 tahap berurutan di dalam folder `notebooks/`. Anda dapat mengeksekusinya langsung menggunakan editor VS Code atau Jupyter Notebook:

1. **Tahap 1: Preprocessing (`01_preprocessing.ipynb`)**
* Membaca 60 file PDF dari folder `data/raw/`.
* Melakukan *case folding* (huruf kecil) dan pembersihan spasi.
* Menyimpan hasilnya menjadi file teks di `data/raw_txt/`.


2. **Tahap 2: Case Representation (`02_case_representation.ipynb`)**
* Mengekstrak informasi penting (Nomor Perkara, Pasal, dan Fakta Hukum) menggunakan teknik pencarian kata kunci (Regex).
* Menghasilkan file basis data terstruktur utama: `data/processed/cases.csv`.


3. **Tahap 3: Similarity & Retrieval (`03_similarity_retrieval.ipynb`)**
* Memuat basis data kasus dari file CSV.
* Melakukan pembobotan kata menggunakan metode **TF-IDF**.
* Menerima keluhan/kasus KDRT baru dari pengguna, menghitung skor kemiripan menggunakan **Cosine Similarity**, dan mengembalikan 3 besar kasus lama yang paling mirip sebagai referensi hukum.



```

4. Simpan file (`Ctrl + S`).

---

### Langkah Akhir: Cek Hasil Kerja Kerasmu!

Sekarang coba lihat panel kiri VS Code kamu. Struktur folder utamanya pasti sudah sangat lengkap dan cantik seperti ini:
* `data/` (isi sub-foldernya lengkap)
* `notebooks/` (isinya 3 file `.ipynb` tahap proyek + file `tes.ipynb` kemarin kalau belum dihapus)
* `README.md`
* `requirements.txt`

Proyek *codingan* kamu secara lokal **sudah selesai 100% dan siap dikumpulkan!** Langkah terakhir tinggal mengunggah (*upload*) folder `Proyek_CBR_KDRT` ini ke akun GitHub kamu, lalu menyetel repositorinya ke **Public**, dan menyalin (*copy*) link GitHub tersebut ke LMS dosen.

Apakah kamu sudah familiar dengan cara membuat repositori di website GitHub dan meng-upload file ke sana, Mas? Atau perlu aku pandu sekalian cara termudah untuk meng-upload-nya?

```