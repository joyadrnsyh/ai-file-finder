# AI File Finder Pro

AI File Finder Pro adalah aplikasi desktop berbasis Python yang menggunakan Transformer AI untuk mencari file berdasarkan:

- Nama file
- Isi dokumen
- Semantic search (pencarian berdasarkan makna)

Aplikasi ini dapat membaca isi:

- PDF
- Word (.docx)
- Excel (.xlsx, .xls)
- TXT
- CSV
- File kode seperti Python, HTML, CSS, JS, PHP, JSON, XML, dll

Selain itu aplikasi juga memiliki fitur:

- Chat-style AI interface
- Auto indexing
- Semantic search menggunakan Sentence Transformers
- Organize file otomatis
- Preview isi file
- Preview organize sebelum file dipindahkan
- Open file & open folder langsung dari aplikasi

---

# Preview Fitur

## Semantic Search

Contoh:

```text
cari dokumen tentang lstm tokopedia
```

AI akan mencari file berdasarkan isi dokumen, bukan hanya nama file.

---

## Organize File

Contoh:

```text
organize file saya
```

File akan dipindahkan otomatis ke kategori:

```text
Dokumen
Gambar
Video
Audio
Archive
Kode
Lainnya
```

---

# Teknologi yang Digunakan

- Python
- CustomTkinter
- Sentence Transformers
- Scikit-learn
- PyPDF
- OpenPyXL
- Pandas
- Python-Docx

---

# Instalasi

## 1. Clone / Download Project

```bash
git clone https://github.com/username/ai-file-finder.git
cd ai-file-finder
```

Atau download ZIP project.

---

## 2. Buat Virtual Environment

Windows:

```bash
python -m venv venv
```

Aktifkan:

```bash
venv\Scripts\activate
```

---

## 3. Install Dependency

```bash
pip install customtkinter
pip install sentence-transformers
pip install scikit-learn
pip install pypdf
pip install python-docx
pip install openpyxl
pip install pandas
pip install xlrd
```

Atau:

```bash
pip install -r requirements.txt
```

---

# Menjalankan Aplikasi

```bash
python chat_gui.py
```

---

# Cara Penggunaan

## 1. Membuat Index

Saat pertama kali mencari file:

```text
cari tugas database
```

Aplikasi akan otomatis:

- membaca file
- membaca isi dokumen
- membuat embedding AI
- menyimpan index di memori

---

## 2. Mencari File

Contoh:

```text
laporan machine learning
```

atau:

```text
dokumen yang membahas tokopedia
```

AI akan menampilkan:

- nama file
- lokasi file
- preview isi file
- skor kecocokan

---

## 3. Membuka File

Klik:

```text
Buka File
```

Untuk membuka file langsung.

---

## 4. Membuka Folder

Klik:

```text
Buka Folder
```

Untuk membuka lokasi file.

---

## 5. Organize File

Ketik:

```text
organize file saya
```

Aplikasi akan:

1. membuat preview file yang akan dipindahkan
2. menampilkan kategori file
3. memindahkan file setelah tombol:

```text
Jalankan Organize
```

ditekan.

---

# Struktur Folder

```text
AI-Finder/
│
├── chat_gui.py
├── README.md
├── requirements.txt
├── venv/
└── AI_Organized_Files/
```

---

# Folder yang Dipindai

Secara default:

```python
FOLDER_TARGET = [
    Path.home() / "Documents",
    Path.home() / "Downloads",
    Path.home() / "Desktop"
]
```

---

# Supported File Types

## Dokumen

- PDF
- DOCX
- XLSX
- XLS
- CSV
- TXT

## File Kode

- PY
- HTML
- CSS
- JS
- PHP
- JSON
- XML
- JAVA
- CPP

---

# Cara Kerja AI

Aplikasi menggunakan:

```text
SentenceTransformer
```

Model:

```text
all-MiniLM-L6-v2
```

Setiap file akan diubah menjadi embedding vector.

Query user juga diubah menjadi embedding.

Kemudian dilakukan:

```text
Cosine Similarity
```

untuk mencari file paling relevan.

---

# Kelebihan

- Tidak membutuhkan internet setelah model terdownload
- Semua data tetap lokal di laptop
- Tidak upload file ke cloud
- Semantic search lebih akurat daripada search biasa
- Bisa membaca isi dokumen

---

# Kekurangan

- Indexing pertama cukup lama
- Membutuhkan RAM cukup besar jika file sangat banyak
- File .doc lama belum didukung
- Belum menggunakan vector database permanen

---

# Rencana Pengembangan

- SQLite vector database
- ChromaDB / FAISS
- Voice Assistant
- OCR gambar
- Drag & Drop file
- Multi-thread indexing
- GPU acceleration
- Chatbot AI lokal
- Summary dokumen otomatis
- Auto tagging file
- Export metadata

---

# Troubleshooting

## Error Torch

Install ulang:

```bash
pip uninstall torch torchvision torchaudio -y
pip install torch --index-url https://download.pytorch.org/whl/cpu
```

---

## Error Permission

Jalankan terminal sebagai Administrator.

---

## Indexing Lama

Kurangi folder scan:

```python
FOLDER_TARGET
```

---

# Lisensi

MIT License

---

# Author

Joy Adriansyah