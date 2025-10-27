# Changelog - Modifikasi Project SVM

## Tanggal: 27 Oktober 2025

### 📝 Ringkasan Perubahan

Dokumen ini mencatat semua modifikasi yang dilakukan pada project Statistical Machine Learning.

---

## 1. Modifikasi `week10-2.ipynb` (Notebook Hands-on)

### ✅ Penambahan Cell Markdown untuk Penjelasan Pickle
- **Lokasi**: Sebelum cell yang menyimpan pickle file
- **Konten**: Penjelasan lengkap tentang:
  - Apa itu Pickle dan mengapa penting
  - Apa yang perlu disimpan (model, scaler, metadata)
  - Use cases untuk model yang disimpan
  - Warning tentang security pickle
  - Struktur file yang disimpan

### ✅ Opsi Penggunaan Persentase Dataset
- **Cell Markdown Baru**: Penjelasan tentang opsi menggunakan subset data
  - Keuntungan: Training lebih cepat, iterasi lebih banyak
  - Trade-offs: Akurasi mungkin berkurang
  - Rekomendasi penggunaan

- **Modifikasi Cell Loading Data**:
  - Tambahan variable `DATA_PERCENTAGE` di awal cell
  - Default: `1.0` (100% data)
  - Dapat diubah menjadi `0.5`, `0.7`, dll.
  
- **Fitur Stratified Sampling**:
  - Menggunakan `train_test_split` dengan stratification
  - Memastikan distribusi class tetap seimbang
  - Stratifikasi berdasarkan kolom `smoker` dan `region`
  - Fallback ke random sampling jika kolom tidak tersedia

- **⚠️ PENTING: DATA_PERCENTAGE Berlaku untuk SELURUH Notebook!**:
  - Persentase yang diset akan digunakan untuk SEMUA eksperimen
  - Termasuk: baseline training, GridSearchCV, final model, evaluasi, visualisasi
  - Tidak perlu mengubah cell-cell selanjutnya
  - Sekali set di awal, berlaku untuk semua

- **Output Informasi**:
  - Menampilkan persentase data yang digunakan
  - Menampilkan jumlah baris sebelum dan sesudah sampling
  - Warning untuk menggunakan 100% data untuk production

---

## 2. Modifikasi `svm_experiment_assignment.tex` (Assignment)

### ✅ Perubahan yang Dilakukan:

1. **Ukuran Kelompok**
   - **Maksimal 3 orang** (tidak ada minimum)
   - Individual mendapat bonus +10 poin

2. **Opsi Dataset**
   - Ditambahkan section: Boleh gunakan 50-100% data untuk eksperimen
   - **Wajib** menggunakan 100% untuk model final yang dilaporkan
   - Instruksi menggunakan stratified sampling
   - **Penting**: DATA_PERCENTAGE berlaku untuk seluruh notebook (baseline, GridSearchCV, final model)

3. **Penghapusan Spesifikasi Python Version**
   - Dihapus requirement "Python 3.8+"
   - Lebih fleksibel untuk berbagai environment
   - Lokasi: Section "Persyaratan Teknis"

4. **Eksperimen 1: Perbandingan Kernel**
   - Sebelum: Minimal 3 kernel
   - Sesudah: **Minimal 2 kernel berbeda**
   - Pilihan: 'linear', 'rbf', atau 'poly' (pilih 2)

5. **Eksperimen 2: Hyperparameter Tuning**
   - Tambahan Batasan:
     - **Minimal 3 kombinasi** hyperparameter
     - **Maksimal 6 kombinasi** hyperparameter
     - Kombinasi ini di luar Eksperimen 1
   - **Tools**: Harus menggunakan **GridSearchCV** (bukan RandomizedSearchCV)

6. **Struktur Laporan - Pendahuluan**
   - Tambahan untuk Kelompok:
     - Wajib mencantumkan nama dan NIM semua anggota
     - **Wajib** mendeskripsikan kontribusi masing-masing anggota
     - Contoh: "Anggota A: preprocessing & EDA, Anggota B: modeling & tuning, dst."

7. **Data Loading dan Preparation**
   - Tambahan:
     - Instruksi untuk set `DATA_PERCENTAGE`
     - Gunakan 50%-100% sesuai kebutuhan eksperimen
     - Penjelasan bahwa persentase ini berlaku untuk seluruh notebook

8. **Kebijakan Kolaborasi**
   - Update:
     - Kelompok: **Maksimal 3 orang** (tidak ada minimum)
     - Wajib mencantumkan kontribusi setiap anggota di pendahuluan notebook

9. **Konvensi Penamaan File**
   - Update untuk kelompok:
     - 2 orang: `SVM_Assignment_[NIM1]_[NIM2].ipynb`
     - 3 orang: `SVM_Assignment_[NIM1]_[NIM2]_[NIM3].ipynb`
   - Contoh: `SVM_Assignment_121450001_121450002_121450003.ipynb`

10. **Tips untuk Sukses**
    - Tambahan: Gunakan subset data (50%-70%) untuk eksperimen awal
    - Hapus: Tips tentang RandomizedSearchCV

11. **Contoh Parameter Grid**
    - Revisi Lengkap:
      - Section baru: "Untuk Eksperimen Awal (Grid Kecil - 3 Kombinasi)"
      - Section baru: "Untuk Eksperimen Komprehensif (Grid Sedang - 6 Kombinasi)"
      - **Hapus**: Section tentang RandomizedSearchCV
      - Tambahan catatan tentang penggunaan `DATA_PERCENTAGE`

12. **FAQ (Frequently Asked Questions)**
    - Update pertanyaan: "Berapa lama GridSearchCV akan berjalan?"
      - Jawaban disesuaikan dengan opsi `DATA_PERCENTAGE`
      - Estimasi waktu dengan subset data
    
    - Pertanyaan Baru: "Bolehkah saya menggunakan kurang dari 100% data untuk model final?"
      - Jawaban: Tidak, model final harus 100% data
    
    - Pertanyaan Update: "Berapa jumlah anggota kelompok yang diperbolehkan?"
      - Jawaban: Maksimal 3 orang per kelompok

---

## 📊 Dampak Perubahan

### Untuk Mahasiswa:
1. **Lebih Fleksibel**: Bisa gunakan subset data untuk eksperimen cepat
2. **Lebih Sederhana**: Ukuran kelompok lebih fleksibel (1-3 orang)
3. **Lebih Realistis**: Batasan 3-6 kombinasi hyperparameter lebih achievable
4. **Lebih Jelas**: Requirement tentang GridSearchCV lebih spesifik
5. **Akuntabilitas**: Harus mencantumkan kontribusi masing-masing anggota
6. **Lebih Efisien**: DATA_PERCENTAGE berlaku untuk seluruh notebook, tidak perlu setting berulang

### Untuk Dosen:
1. **Evaluasi Lebih Fair**: Bisa lihat kontribusi setiap anggota kelompok
2. **Lebih Praktis**: Training time lebih cepat dengan opsi subset
3. **Lebih Fokus**: Mahasiswa fokus pada pemahaman, bukan waiting time
4. **Konsistensi**: Semua gunakan GridSearchCV (tidak ada RandomizedSearchCV)

---

## 🔧 Cara Menggunakan Fitur Baru

### Untuk Mahasiswa yang Mengerjakan Assignment:

1. **Buka file `week10-2.ipynb`**
2. **Cari cell dengan `DATA_PERCENTAGE = 1.0`**
3. **Ubah nilai sesuai kebutuhan**:
   ```python
   DATA_PERCENTAGE = 0.5  # Untuk eksperimen cepat
   # atau
   DATA_PERCENTAGE = 1.0  # Untuk model final
   ```
4. **Jalankan cell** - data akan otomatis di-sample dengan stratified sampling
5. **Jalankan seluruh notebook** - semua eksperimen akan menggunakan persentase yang sama

### ⚠️ PENTING: Satu Setting untuk Seluruh Notebook!

**DATA_PERCENTAGE yang Anda set akan otomatis berlaku untuk:**
- ✅ Training dan validation data awal
- ✅ Baseline model training (Langkah 6)
- ✅ GridSearchCV hyperparameter tuning (Langkah 9)
- ✅ Final model training
- ✅ Semua evaluasi dan visualisasi

**Tidak perlu mengubah apapun di cell-cell selanjutnya!**

### Strategi Pengerjaan yang Direkomendasikan:

```
Fase 1: Eksperimen Awal (1-2 hari)
├── Set DATA_PERCENTAGE = 0.5 (50% data)
├── Jalankan seluruh notebook
├── Test berbagai kernel (Eksperimen 1)
├── Test parameter grid kecil (2-3 kombinasi)
└── Tentukan konfigurasi terbaik

Fase 2: Fine-tuning (1-2 hari)
├── Set DATA_PERCENTAGE = 0.7 (70% data)
├── Jalankan ulang notebook
├── Test parameter grid lebih detail (4-6 kombinasi)
├── Analisis hasil lebih mendalam
└── Buat visualisasi

Fase 3: Model Final (1 hari)
├── Set DATA_PERCENTAGE = 1.0 (100% data)
├── Jalankan ulang notebook dengan best parameters
├── Evaluasi lengkap
├── Tulis analisis dan kesimpulan
└── Export ke PDF dan submit
```

---

## 📋 Checklist Compliance

### Untuk Assignment yang Dikumpulkan:

- [ ] Jika kelompok: Maksimal 3 anggota
- [ ] Jika kelompok: Kontribusi setiap anggota dicantumkan di pendahuluan
- [ ] Model final menggunakan `DATA_PERCENTAGE = 1.0` (100% data)
- [ ] Eksperimen 1: Minimal 2 kernel dibandingkan
- [ ] Eksperimen 2: Minimal 3 kombinasi, maksimal 6 kombinasi
- [ ] Eksperimen 2: Menggunakan **GridSearchCV** (bukan RandomizedSearchCV)
- [ ] Semua cell sudah dieksekusi tanpa error
- [ ] File penamaan sesuai konvensi (termasuk NIM semua anggota jika kelompok)

---

## 🔍 Testing yang Dilakukan

### Test Notebook (`week10-2.ipynb`):
- ✅ Cell loading data dengan `DATA_PERCENTAGE = 1.0` (full data)
- ✅ Cell loading data dengan `DATA_PERCENTAGE = 0.5` (50% data)
- ✅ Cell loading data dengan `DATA_PERCENTAGE = 0.7` (70% data)
- ✅ Stratified sampling menggunakan kolom smoker dan region
- ✅ Output menampilkan informasi jumlah data yang digunakan
- ✅ Markdown cell penjelasan pickle sudah ditambahkan
- ✅ Markdown cell menjelaskan DATA_PERCENTAGE berlaku untuk seluruh notebook

### Test LaTeX (`svm_experiment_assignment.tex`):
- ✅ File compile tanpa error
- ✅ Semua perubahan text sudah sesuai
- ✅ Semua references ke RandomizedSearchCV sudah dihapus
- ✅ Format tabel dan enumerate masih konsisten
- ✅ Ukuran kelompok maksimal 3 orang

---

## 📝 Notes untuk Maintenance

### File yang Dimodifikasi:
1. `/week10-2.ipynb` - Hands-on notebook
2. `/assignments/svm_experiment_assignment.tex` - Assignment description
3. `/CHANGELOG_MODIFICATIONS.md` - Dokumentasi perubahan (file ini)

### File yang Dihapus:
- `PANDUAN_PENGGUNAAN_FITUR_BARU.md` - Tidak diperlukan lagi

### File yang TIDAK Diubah:
- `medical_insurance.csv` - Dataset original
- `train_data.csv` & `validation_data.csv` - Pre-split data (jika ada)
- `week10-1.ipynb` - EDA notebook
- File-file lain di repository

### Backward Compatibility:
- ✅ Default `DATA_PERCENTAGE = 1.0` memastikan behavior sama dengan sebelumnya
- ✅ Student yang tidak ingin menggunakan subset bisa langsung run tanpa modifikasi
- ✅ Code tetap kompatibel dengan data files yang sudah ada

---

## 🎯 Kesimpulan

Semua modifikasi telah berhasil dilakukan sesuai requirement:

1. ✅ Notebook: Ditambahkan markdown explanation untuk pickle saving
2. ✅ Notebook: Ditambahkan opsi persentase dataset dengan stratified sampling
3. ✅ Notebook: DATA_PERCENTAGE berlaku untuk SELURUH notebook (baseline, GridSearchCV, final model)
4. ✅ Assignment: Opsi 50-100% dataset untuk faster training di seluruh eksperimen
5. ✅ Assignment: Penghapusan spesifikasi Python version
6. ✅ Assignment: Eksperimen 1 - minimal 2 kernel (bukan 3)
7. ✅ Assignment: Eksperimen 2 - minimal 3, maksimal 6 kombinasi
8. ✅ Assignment: Wajib GridSearchCV (bukan RandomizedSearchCV)
9. ✅ Assignment: Kelompok maksimal 3 orang (tidak ada minimum)
10. ✅ Assignment: Wajib deskripsi kontribusi anggota kelompok

Semua perubahan ditulis dalam Bahasa Indonesia dengan istilah teknis dalam Bahasa Inggris.

---

**Dipersiapkan oleh**: GitHub Copilot
**Tanggal**: 27 Oktober 2025
**Status**: ✅ Selesai dan Tested
**Revisi Terakhir**: 27 Oktober 2025 (Update: Kelompok maks 3 orang, DATA_PERCENTAGE berlaku untuk seluruh notebook)

### ✅ Perubahan Ukuran Kelompok
- **Sebelum**: Maksimal 2 orang
- **Sesudah**: Minimal 3 orang, maksimal 4 orang
- **Lokasi**: Section "Informasi Penting" dan "Kebijakan Kolaborasi"

### ✅ Opsi Penggunaan Subset Dataset
- **Tambahan di Section "Dataset"**:
  - Boleh menggunakan 50%-100% data
  - Gunakan subset (50%-70%) untuk eksperimen awal
  - **Wajib** menggunakan 100% untuk model final
  - Harus menggunakan stratified sampling
  - Instruksi setting `DATA_PERCENTAGE`

### ✅ Penghapusan Spesifikasi Python Version
- **Dihapus**: Requirement "Python 3.8+"
- **Alasan**: Lebih fleksibel untuk berbagai environment
- **Lokasi**: Section "Persyaratan Teknis"

### ✅ Eksperimen 1: Perbandingan Kernel
- **Sebelum**: Minimal 3 kernel berbeda
- **Sesudah**: Minimal 2 kernel berbeda
- **Pilihan**: 'linear', 'rbf', atau 'poly' (pilih 2)

### ✅ Eksperimen 2: Hyperparameter Tuning
- **Tambahan Batasan**:
  - Minimal 3 kombinasi hyperparameter
  - Maksimal 6 kombinasi hyperparameter
  - Kombinasi ini di luar Eksperimen 1
- **Tools**: Harus menggunakan GridSearchCV (bukan RandomizedSearchCV)

### ✅ Struktur Laporan - Pendahuluan
- **Tambahan untuk Kelompok**:
  - Wajib mencantumkan nama dan NIM semua anggota
  - **Wajib** mendeskripsikan kontribusi masing-masing anggota
  - Contoh: "Anggota A: preprocessing & EDA, Anggota B: modeling & tuning, dst."

### ✅ Data Loading dan Preparation
- **Tambahan**:
  - Instruksi untuk set `DATA_PERCENTAGE`
  - Gunakan 50%-100% sesuai kebutuhan eksperimen

### ✅ Kebijakan Kolaborasi
- **Update**:
  - Kelompok: Minimal 3 orang, maksimal 4 orang
  - Wajib mencantumkan kontribusi setiap anggota di pendahuluan notebook

### ✅ Konvensi Penamaan File
- **Update untuk kelompok**:
  - Format: `SVM_Assignment_[NIM1]_[NIM2]_[NIM3].ipynb`
  - Contoh: `SVM_Assignment_121450001_121450002_121450003.ipynb`

### ✅ Tips untuk Sukses
- **Tambahan**: Gunakan subset data (50%-70%) untuk eksperimen awal
- **Hapus**: Tips tentang RandomizedSearchCV

### ✅ Contoh Parameter Grid
- **Revisi Lengkap**:
  - Section baru: "Untuk Eksperimen Awal (Grid Kecil - 3 Kombinasi)"
  - Section baru: "Untuk Eksperimen Komprehensif (Grid Sedang - 6 Kombinasi)"
  - **Hapus**: Section tentang RandomizedSearchCV
  - Tambahan catatan tentang penggunaan `DATA_PERCENTAGE`

### ✅ FAQ (Frequently Asked Questions)
- **Update pertanyaan**: "Berapa lama GridSearchCV akan berjalan?"
  - Jawaban disesuaikan dengan opsi `DATA_PERCENTAGE`
  - Estimasi waktu dengan subset data
  
- **Pertanyaan Baru**: "Bolehkah saya menggunakan kurang dari 100% data untuk model final?"
  - Jawaban: Tidak, model final harus 100% data
  
- **Pertanyaan Baru**: "Berapa jumlah anggota kelompok yang diperbolehkan?"
  - Jawaban: Minimal 3, maksimal 4 orang

---

## 📊 Dampak Perubahan

### Untuk Mahasiswa:
1. **Lebih Fleksibel**: Bisa gunakan subset data untuk eksperimen cepat
2. **Lebih Kolaboratif**: Kelompok 3-4 orang memungkinkan pembagian kerja lebih baik
3. **Lebih Realistis**: Batasan 3-6 kombinasi hyperparameter lebih achievable
4. **Lebih Jelas**: Requirement tentang GridSearchCV lebih spesifik
5. **Akuntabilitas**: Harus mencantumkan kontribusi masing-masing anggota

### Untuk Dosen:
1. **Evaluasi Lebih Fair**: Bisa lihat kontribusi setiap anggota kelompok
2. **Lebih Praktis**: Training time lebih cepat dengan opsi subset
3. **Lebih Fokus**: Mahasiswa fokus pada pemahaman, bukan waiting time
4. **Konsistensi**: Semua gunakan GridSearchCV (tidak ada RandomizedSearchCV)

---

## 🔧 Cara Menggunakan Fitur Baru

### Untuk Mahasiswa yang Mengerjakan Assignment:

1. **Buka file `week10-2.ipynb`**
2. **Cari cell dengan `DATA_PERCENTAGE = 1.0`**
3. **Ubah nilai sesuai kebutuhan**:
   ```python
   DATA_PERCENTAGE = 0.5  # Untuk eksperimen cepat
   # atau
   DATA_PERCENTAGE = 1.0  # Untuk model final
   ```
4. **Jalankan cell** - data akan otomatis di-sample dengan stratified sampling

### Strategi Pengerjaan yang Direkomendasikan:

```
Fase 1: Eksperimen Awal (1-2 hari)
├── Set DATA_PERCENTAGE = 0.5 (50% data)
├── Test berbagai kernel (Eksperimen 1)
├── Test parameter grid kecil (2-3 kombinasi)
└── Tentukan konfigurasi terbaik

Fase 2: Fine-tuning (1-2 hari)
├── Set DATA_PERCENTAGE = 0.7 (70% data)
├── Test parameter grid lebih detail (4-6 kombinasi)
├── Analisis hasil lebih mendalam
└── Buat visualisasi

Fase 3: Model Final (1 hari)
├── Set DATA_PERCENTAGE = 1.0 (100% data)
├── Train dengan best parameters
├── Evaluasi lengkap
├── Tulis analisis dan kesimpulan
└── Export ke PDF dan submit
```

---

## 📋 Checklist Compliance

### Untuk Assignment yang Dikumpulkan:

- [ ] Jika kelompok: Minimal 3 anggota, maksimal 4 anggota
- [ ] Jika kelompok: Kontribusi setiap anggota dicantumkan di pendahuluan
- [ ] Model final menggunakan `DATA_PERCENTAGE = 1.0` (100% data)
- [ ] Eksperimen 1: Minimal 2 kernel dibandingkan
- [ ] Eksperimen 2: Minimal 3 kombinasi, maksimal 6 kombinasi
- [ ] Eksperimen 2: Menggunakan **GridSearchCV** (bukan RandomizedSearchCV)
- [ ] Semua cell sudah dieksekusi tanpa error
- [ ] File penamaan sesuai konvensi (termasuk NIM semua anggota jika kelompok)

---

## 🔍 Testing yang Dilakukan

### Test Notebook (`week10-2.ipynb`):
- ✅ Cell loading data dengan `DATA_PERCENTAGE = 1.0` (full data)
- ✅ Cell loading data dengan `DATA_PERCENTAGE = 0.5` (50% data)
- ✅ Cell loading data dengan `DATA_PERCENTAGE = 0.7` (70% data)
- ✅ Stratified sampling menggunakan kolom smoker dan region
- ✅ Output menampilkan informasi jumlah data yang digunakan
- ✅ Markdown cell penjelasan pickle sudah ditambahkan

### Test LaTeX (`svm_experiment_assignment.tex`):
- ✅ File compile tanpa error
- ✅ Semua perubahan text sudah sesuai
- ✅ Semua references ke RandomizedSearchCV sudah dihapus
- ✅ Format tabel dan enumerate masih konsisten

---

## 📝 Notes untuk Maintenance

### File yang Dimodifikasi:
1. `/week10-2.ipynb` - Hands-on notebook
2. `/assignments/svm_experiment_assignment.tex` - Assignment description

### File yang TIDAK Diubah:
- `medical_insurance.csv` - Dataset original
- `train_data.csv` & `validation_data.csv` - Pre-split data (jika ada)
- `week10-1.ipynb` - EDA notebook
- File-file lain di repository

### Backward Compatibility:
- ✅ Default `DATA_PERCENTAGE = 1.0` memastikan behavior sama dengan sebelumnya
- ✅ Student yang tidak ingin menggunakan subset bisa langsung run tanpa modifikasi
- ✅ Code tetap kompatibel dengan data files yang sudah ada

---

## 🎯 Kesimpulan

Semua modifikasi telah berhasil dilakukan sesuai requirement:

1. ✅ Notebook: Ditambahkan markdown explanation untuk pickle saving
2. ✅ Notebook: Ditambahkan opsi persentase dataset dengan stratified sampling
3. ✅ Assignment: Opsi 50-100% dataset untuk faster training
4. ✅ Assignment: Penghapusan spesifikasi Python version
5. ✅ Assignment: Eksperimen 1 - minimal 2 kernel (bukan 3)
6. ✅ Assignment: Eksperimen 2 - minimal 3, maksimal 6 kombinasi
7. ✅ Assignment: Wajib GridSearchCV (bukan RandomizedSearchCV)
8. ✅ Assignment: Kelompok minimal 3 orang (bukan 2)
9. ✅ Assignment: Wajib deskripsi kontribusi anggota kelompok

Semua perubahan ditulis dalam Bahasa Indonesia dengan istilah teknis dalam Bahasa Inggris.

---

**Dipersiapkan oleh**: GitHub Copilot
**Tanggal**: 27 Oktober 2025
**Status**: ✅ Selesai dan Tested
