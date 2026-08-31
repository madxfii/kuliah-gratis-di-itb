# Kurikulum Teknik Informatika ITB - Materi Pembelajaran

Struktur folder untuk menyimpan bahan pembelajaran mata kuliah Program Studi Teknik Informatika ITB.

## 📁 Struktur Folder

```
kurikulum-itb/
├── [KODE]-[nama-mata-kuliah]/
│   ├── bahan-kajian/
│   │   ├── 01-topik-1.md
│   │   ├── 02-topik-2.md
│   │   └── ...
│   │
│   └── capaian-pembelajaran/
│       ├── cpmk-1.md
│       ├── cpmk-2.md
│       └── ...
│
├── IF1210-algoritma-dan-pemrograman-1/
├── IF1220-matematika-diskrit/
├── IF2130-sistem-operasi/
├── IF3170-inteligensi-artifisial/
└── ... (70 mata kuliah total)
```

## 📚 Daftar Mata Kuliah

### Semester 1-8 (Wajib - 44 mata kuliah)
- WI1102 - Berpikir Komputasional
- MA1101 - Matematika I
- FI1101 - Fisika Dasar I
- ... dan 41 mata kuliah lainnya

### Mata Kuliah Pilihan (Elektif - 26 mata kuliah)
Terbagi dalam 6 spesialisasi:
1. **Ilmu dan Rekayasa Data** (5 courses)
2. **Ilmu Komputer** (6 courses)
3. **Inteligensi Artifisial** (7 courses)
4. **Keamanan Siber** (5 courses)
5. **Rekayasa Perangkat Lunak** (7 courses)
6. **Rekayasa Sistem Perangkat Lunak** (7 courses)

## 📝 Konvensi Penamaan Folder

Format: `[KODE]-[nama-dengan-hyphen]`

**Contoh:**
- `IF1210-algoritma-dan-pemrograman-1`
- `IF2130-sistem-operasi`
- `IF3170-inteligensi-artifisial`
- `IF5152-visi-komputer`

## 📖 Cara Menggunakan

### 1. Menambah Bahan Kajian
Masuk ke folder mata kuliah, buka folder `bahan-kajian/`, kemudian buat file markdown:

```
IF1210-algoritma-dan-pemrograman-1/
└── bahan-kajian/
    ├── 01-konsep-dasar-algoritma.md
    ├── 02-pseudocode.md
    ├── 03-kompleksitas-algoritma.md
    └── 04-implementasi-algoritma.md
```

### 2. Menambah Capaian Pembelajaran (CPMK)
Masuk ke folder mata kuliah, buka folder `capaian-pembelajaran/`, buat file untuk setiap CPMK:

```
IF1210-algoritma-dan-pemrograman-1/
└── capaian-pembelajaran/
    ├── cpmk-1-memahami-konsep.md
    ├── cpmk-2-merancang-algoritma.md
    ├── cpmk-3-mengimplementasikan.md
    └── cpmk-4-menganalisis-kompleksitas.md
```

## 📄 Template File Markdown

### Template untuk Bahan Kajian (bahan-kajian/)
```markdown
# Bahan Kajian: [Nama Topik]

**Mata Kuliah:** [Kode] - [Nama Mata Kuliah]  
**Seminar ke:** X

## Deskripsi
[Penjelasan singkat topik]

## Materi Utama
1. [Poin utama 1]
2. [Poin utama 2]
3. [Poin utama 3]

## Sub-topik
### Sub-topik 1
[Penjelasan]

### Sub-topik 2
[Penjelasan]

## Referensi
- [Referensi 1]
- [Referensi 2]

## Latihan
- [Soal/tugas 1]
- [Soal/tugas 2]
```

### Template untuk CPMK (capaian-pembelajaran/)
```markdown
# CPMK X: [Deskripsi Capaian]

**Mata Kuliah:** [Kode] - [Nama Mata Kuliah]

## Pernyataan Capaian
[Deskripsi lengkap apa yang mahasiswa harus capai]

## Indikator Pencapaian
- [ ] Indikator 1
- [ ] Indikator 2
- [ ] Indikator 3

## Topik yang Diajarkan
1. [Topik 1] (bahan-kajian/01-...)
2. [Topik 2] (bahan-kajian/02-...)
3. [Topik 3] (bahan-kajian/03-...)

## Metode Penilaian
- [Metode 1]: [Bobot]%
- [Metode 2]: [Bobot]%

## Contoh Luaran
[Deskripsi bagaimana mahasiswa menunjukkan pencapaian CPMK ini]
```

## 🎯 Panduan Pengisian

### Bahan Kajian (Learning Material)
Gunakan untuk menyimpan:
- ✅ Ringkasan topik pembelajaran
- ✅ Slide presentasi (dalam format markdown)
- ✅ Catatan penting
- ✅ Definisi dan konsep
- ✅ Contoh dan kasus studi
- ✅ Link ke referensi eksternal

### Capaian Pembelajaran (Learning Outcomes)
Gunakan untuk:
- ✅ Mendeskripsikan hasil belajar yang diharapkan
- ✅ Menentukan indikator pencapaian
- ✅ Menghubungkan dengan bahan kajian
- ✅ Menentukan metode penilaian
- ✅ Memberikan contoh tugas/proyek

## 💡 Tips Organisasi

1. **Urutan File**
   - Gunakan nomor prefix (01-, 02-, etc) untuk urutan logis
   - Dimulai dari konsep dasar menuju topik kompleks

2. **Link Internal**
   - Gunakan path relatif: `[Bahan](../bahan-kajian/01-konsep.md)`
   - Mudah menavigasi antar file

3. **Format Konsisten**
   - Gunakan markdown untuk semua file teks
   - Ikuti template yang sudah ada
   - Jaga konsistensi heading dan formatting

4. **Dokumentasi Lengkap**
   - Tambahkan metadata di atas file (frontmatter)
   - Jelaskan referensi dan sumber
   - Sertakan tanggal update terakhir

## 📊 Statistik Struktur

| Kategori | Jumlah |
|----------|--------|
| Total Mata Kuliah | 70 |
| Mata Kuliah Wajib | 44 |
| Mata Kuliah Elektif | 26 |
| Folder Bahan Kajian | 70 |
| Folder Capaian Pembelajaran | 70 |

## 🔗 Integrasi dengan Struktur Lain

Struktur ini dapat diintegrasikan dengan:
- **docs/** - Interactive GitHub Pages (sudah dibuat)
- **mk/** - Original HTML files dari ITB academic system
- **content-and-links/** - Repository konten tambahan

## 📋 Checklist Pengisian Materi

Untuk setiap mata kuliah:
- [ ] Folder bahan-kajian dibuat
- [ ] Folder capaian-pembelajaran dibuat
- [ ] Minimal 3-5 file di bahan-kajian
- [ ] Semua CPMK terdokumentasi
- [ ] Link internal sudah berfungsi
- [ ] README lokal di folder (opsional)

## 🚀 Workflow Pengembangan

1. **Perencanaan**
   - Tentukan jumlah bahan kajian (topik)
   - Identifikasi semua CPMK
   - Buat outline struktur

2. **Penulisan**
   - Tulis bahan kajian terlebih dahulu
   - Dokumentasikan CPMK berdasarkan bahan
   - Hubungkan keduanya

3. **Review**
   - Periksa konsistensi format
   - Validasi link internal
   - Update metadata

4. **Publikasi**
   - Commit ke repository
   - Sync dengan web (docs/)
   - Inform stakeholders

## 📞 Dukungan

Untuk pertanyaan tentang struktur atau konvensi, lihat:
- README di root project
- RESTRUCTURE_SUMMARY.md
- Template files di folder manapun

---

**Last Updated:** August 31, 2024  
**Total Folders Created:** 70  
**Ready for:** Content population
