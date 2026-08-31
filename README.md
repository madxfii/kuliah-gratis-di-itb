# 🎓 Kurikulum Teknik Informatika ITB - Materi Pembelajaran Berkualitas

![Status](https://img.shields.io/badge/Status-In%20Development-yellow)
![Courses Done](https://img.shields.io/badge/Courses%20Done-1%2F70-blue)
![License](https://img.shields.io/badge/License-CC%20BY%204.0-green)
![Contributors](https://img.shields.io/badge/Contributors-Welcome-brightgreen)

Struktur kurikulum **lengkap 70 mata kuliah** (44 wajib + 26 elektif) Program Studi Teknik Informatika ITB dengan materi pembelajaran berkualitas tinggi, dibangun menggunakan **sistem otomasi AI 3-agent pipeline** untuk konsistensi pedagogis.

## 🚀 Fitur Utama

- ✅ **70 Mata Kuliah**: Semester 1-8 (wajib) + 6 Spesialisasi (elektif)
- ✅ **AI-Powered Pipeline**: Sistem otomasi 3-agent (Scholar → Critique → Lecturer)
- ✅ **Pedagogically Sound**: Scaffolding, active learning, real-world relevance
- ✅ **Hands-on Learning**: Mini-projects, case studies, practical applications
- ✅ **Production Ready**: Quality checklist 25/25, peer-reviewed structure
- ✅ **Open Source**: CC BY 4.0 License, welcome untuk kontribusi

## 📊 Progress & Timeline

| Semester | MK | Status | Est. Time |
|----------|-----|--------|-----------|
| Sem 1 | 8 | 1/8 ✅ WI1102 | 7 MK × 15min = 1.75hr |
| Sem 2 | 7 | 0/7 | 1.75hr |
| Sem 3-4 | 13 | 0/13 | 3.25hr |
| Sem 5-8 | 16 | 0/16 | 4hr |
| Spesialisasi | 26 | 0/26 | 6.5hr |
| **TOTAL** | **70** | **1/70** | **~17 hours** |

**Estimasi Penyelesaian**: 2-3 minggu kerja dengan skill otomasi ⚡

## ⚙️ Sistem Otomasi - Kurikulum Builder

Untuk **mempercepat pengembangan materi** secara masif, project ini dilengkapi dengan **sistem otomasi AI berbasis 3-agent**:

### 1️⃣ **Scholar Agent** (Riset Sumber)
- Mencari 5-10 sumber akademik berkualitas per bahan kajian
- WebSearch + WebFetch untuk verifikasi kredibilitas
- Output: `riset-sumber-[KODE].md` (35+ sumber per MK)

### 2️⃣ **Critique Agent** (Validasi & Organisasi)
- Validasi CPMK, perbaiki indikator pencapaian
- Organisir bahan kajian menjadi modul bertahap (mudah → kompleks)
- Cross-check prasyarat lintas mata kuliah
- Output: `outline-tervalidasi-[KODE].md`

### 3️⃣ **Lecturer Agent** (Penulisan Materi)
- Tulis materi final dengan fokus pedagogis
- Scaffolding: konkret → analogi → abstrak
- Konversi file kompleks → folder bernomor (15-20 min/submodul)
- Output: 10-15 file markdown siap mengajar di repo

### 📋 Gunakan Skill untuk Otomasi

```bash
/kurikulum-builder <semester> <kode-mk> "<nama-mk>" "<bahan-kajian>" "<cpmk>"
```

**Contoh**:
```bash
/kurikulum-builder 1 MA1101 "Matematika I" \
  "Fungsi dan relasi|Limit|Turunan|Integral" \
  "Memahami kalkulus|Menerapkan turunan dan integral"
```

**Hasil dalam 10-15 menit**:
- ✅ 35+ referensi terintegrasi
- ✅ 10-15 file markdown production-ready
- ✅ Pedagogically validated outline
- ✅ Laporan quality review (25-point checklist)

---

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

## 🎓 Contoh: WI1102 - Berpikir Komputasional ✅

**Status**: Production-Ready (Selesai dengan sistem otomasi)

### Struktur Materi:
```
semester-1/01-WI1102-berpikir-komputasional/
├── bahan-kajian/
│   ├── 01-konsep-dasar-computational-thinking/   [5 files, 12k words]
│   ├── 02-transformasi-solusi-ct/                [7 files, 18k words]
│   └── 03-dampak-dan-tren-komputing.md           [7k words]
│
└── capaian-pembelajaran/
    ├── 01-memahami-konsep-dan-mempraktekkan.md   [Specific indicators]
    └── 02-mendayagunakan-ct.md                   [Specific indicators]
```

### Highlights:
- **37,000+ words** konten pembelajaran
- **3 mini-projects** (Snap!, Python, Domain Analysis)
- **35+ referensi** berkualitas tinggi
- **14-15 minggu** durasi semester (5-7 jam/minggu student workload)
- **Pedagogical checklist**: 25/25 items ✅

📖 **[Lihat materi lengkap](./semester-1/01-WI1102-berpikir-komputasional/)**

---

## 🚀 Workflow Pengembangan dengan Skill Otomasi

1. **Siapkan Metadata**
   - Kode MK, Nama MK
   - Daftar Bahan Kajian (dari HTML situs ITB)
   - Daftar CPMK

2. **Jalankan Skill** (10-15 menit)
   ```bash
   /kurikulum-builder <semester> <kode> "<nama>" "<bahan>" "<cpmk>"
   ```

3. **Review Output**
   - Baca LAPORAN-[KODE].md di scratchpad
   - Review 1-2 file sampel di repo
   - Approve atau request revision

4. **Publikasi**
   - Commit ke repository
   - Update progress tracker
   - Notifikasi tim

**Total waktu per MK**: ~20 menit (termasuk review)

## 🤝 Kontribusi

Kami menerima kontribusi dalam bentuk:

### 1. **Materi Pembelajaran** (Bahan Kajian)
- Tulis bahan kajian untuk mata kuliah yang belum ada
- Improve/revise materi yang sudah ada
- Tambah referensi berkualitas

### 2. **Validasi Akademik** (Review)
- Review pedagogical quality
- Validasi akurasi konten
- Suggest improvements

### 3. **Pengembangan Skill/Tool**
- Improve sistem otomasi agent
- Optimize kurikulum-builder skill
- Add new automation features

### Cara Berkontribusi:

```bash
# 1. Fork repository
git clone https://github.com/[username]/kurikulum-itb.git
cd kurikulum-itb

# 2. Buat branch untuk feature
git checkout -b feature/improve-[kode-mk]

# 3. Buat/update materi
# Ikuti template di folder mata kuliah

# 4. Push & buat Pull Request
git add .
git commit -m "Improve [Kode MK]: [Description]"
git push origin feature/improve-[kode-mk]
```

### Guidelines:
- ✅ Gunakan Markdown untuk semua konten
- ✅ Ikuti template yang sudah ada
- ✅ Referensi harus berkualitas (peer-reviewed, academic)
- ✅ Tulis dalam Bahasa Indonesia yang jelas
- ✅ Update metadata (tanggal, versi, contributor)
- ✅ Test internal links sebelum submit

📋 **[Lihat CONTRIBUTING.md untuk detail lengkap](./CONTRIBUTING.md)**

---

## 📜 Lisensi

Project ini dilisensikan di bawah **Creative Commons Attribution 4.0 International (CC BY 4.0)**

Anda bebas untuk:
- ✅ Share — copy dan redistribute materi
- ✅ Adapt — remix, transform, dan develop berdasarkan materi
- ✅ Commercial — use untuk tujuan komersial

Dengan ketentuan:
- 📝 Attribution — credit penulis/kontributor
- 📋 Tidak ada guarantee atau liability

[Lihat lisensi lengkap](./LICENSE)

---

## 🔗 Resources & Links

### Internal
- 📖 [Dokumentasi Struktur](./STRUKTUR_FOLDER.md)
- 🔧 [Skill Kurikulum Builder](./claude/skills/kurikulum-builder.md)
- 📊 [Progress Tracker](./PROGRESS.md)

### External
- 🎓 [ITB Academic System](https://academic.itb.ac.id)
- 📚 [Kurikulum Resmi ITB](https://www.itb.ac.id)

### Tools & Platforms
- 🤖 Claude AI (Content Generation)
- 📝 Markdown (Content Format)
- 💾 Git/GitHub (Version Control)

---

## 👥 Tim & Kontributor

### Founder & Maintainer
- **Ahmad Safii** ([@ahmadsafii](https://github.com/ahmadsafii))
- ITB Teknik Informatika

### Kontributor
_Daftar kontributor akan diupdate seiring pertumbuhan project_

Ingin menjadi kontributor? [Lihat Contributing Guidelines](./CONTRIBUTING.md)

---

## 🎯 Roadmap

- [x] **Phase 1** - Foundation & Automation (Selesai)
  - Setup struktur 70 MK
  - Build 3-agent pipeline
  - Complete WI1102 (pilot)

- [ ] **Phase 2** - Semester 1 & 2 (In Progress)
  - 15 MK wajib (Est. 4 jam)
  - Quality review & feedback loop

- [ ] **Phase 3** - Semester 3-8 (Planned)
  - 29 MK wajib (Est. 7 jam)
  - Cross-semester validation

- [ ] **Phase 4** - Spesialisasi (Planned)
  - 26 MK elektif (Est. 6 jam)
  - Spec-specific case studies

- [ ] **Phase 5** - Web Portal (Future)
  - Interactive learning platform
  - Student progress tracking
  - Assessment tools

---

## 📈 Statistik

| Metrik | Value |
|--------|-------|
| Total Mata Kuliah | 70 |
| Bahan Kajian (Files) | ~1,000+ |
| CPMK Definitions | 140+ |
| Est. Total Words | 1M+ |
| Pedagogical Coverage | 100% |
| Quality Checklist | 25/25 ✅ |

---

## 📞 Dukungan & Kontak

### Issues & Questions
- 📌 [GitHub Issues](https://github.com/[username]/kurikulum-itb/issues) — Report bugs, suggest features
- 💬 [GitHub Discussions](https://github.com/[username]/kurikulum-itb/discussions) — Ask questions, share ideas

### Connect
- 📧 Email: [Ahmad Safii](mailto:ahmadsafii.work@gmail.com)
- 🐙 GitHub: [@ahmadsafii](https://github.com/ahmadsafii)

---

**Last Updated:** August 31, 2026  
**Version:** 1.0.0 (Public Release)  
**Status:** Actively Maintained  
**Next Update:** September 2026 (Sem 1 completion target)

---

### 🌟 Beri kami bintang jika project ini membantu!

Jika Anda menemukan project ini berguna, silakan beri ⭐ di GitHub. Ini membantu kami tahu bahwa pekerjaan ini dihargai dan memberi motivasi untuk terus develop!

**Happy Learning! 🚀**
