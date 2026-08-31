# 🤝 Panduan Kontribusi - Kurikulum ITB

Terima kasih telah tertarik untuk berkontribusi! Project ini adalah upaya kolektif untuk membangun kurikulum berkualitas tinggi untuk Program Studi Teknik Informatika ITB.

## 📋 Jenis-Jenis Kontribusi

Kami menerima kontribusi dalam bentuk:

### 1. **Materi Pembelajaran** (Bahan Kajian)
Tulis atau improve konten pembelajaran untuk mata kuliah.

**Requirements:**
- Bahasa Indonesia yang jelas & sederhana (target: pemula-menengah)
- Struktur pedagogis: Tujuan → Prasyarat → Pembahasan bertahap → Ringkasan → Latihan
- Minimal 2 referensi berkualitas (textbook, paper, OCW)
- Contoh konkret & relevan dengan kehidupan mahasiswa

**Tip:** Gunakan template di folder mata kuliah sebagai panduan.

### 2. **Validasi Akademik** (Code Review)
Review materi yang sudah ada dari segi:
- **Akurasi**: Apakah konten benar secara akademik?
- **Pedagogis**: Apakah mudah dipahami pemula?
- **Completeness**: Apakah mencakup semua topik CPMK?
- **Quality**: Apakah referensi berkualitas tinggi?

**Cara:** Fork, review, & buat PR dengan suggestions.

### 3. **Pengembangan Tools**
Improve atau develop tools untuk otomasi:
- Enhance kurikulum-builder skill
- Optimize agent pipeline
- Add features baru

**Requirement:** Python/bash scripting

### 4. **Dokumentasi**
Update atau tambah dokumentasi:
- README, CONTRIBUTING guidelines
- Template improvements
- Wiki atau FAQ

---

## 🚀 Quickstart

### Setup Repository

```bash
# 1. Fork & clone
git clone https://github.com/[username]/kurikulum-itb.git
cd kurikulum-itb

# 2. Buat branch untuk feature
git checkout -b feature/[deskripsi]
# Contoh: feature/improve-wi1102, feature/add-ma1101, feature/fix-templates
```

### Workflow untuk Materi Pembelajaran

```bash
# 1. Pilih mata kuliah yang ingin dikerjakan
# Cek semester-N/[NN-KODE-nama-mk]/

# 2. Buat/edit file di folder:
# - bahan-kajian/ untuk materi
# - capaian-pembelajaran/ untuk CPMK

# 3. Follow template yang ada

# 4. Test internal links
# Pastikan semua [link](../path) bekerja

# 5. Commit & Push
git add .
git commit -m "feat(MK-KODE): [deskripsi singkat]"
git push origin feature/[deskripsi]

# 6. Buat Pull Request di GitHub
```

### Commit Message Format

```
type(scope): subject

body (optional)
```

**Types:**
- `feat` — Fitur/materi baru
- `improve` — Perbaikan konten
- `fix` — Bug fix atau koreksi
- `refactor` — Reorganisasi struktur
- `docs` — Dokumentasi

**Scope:** Kode MK atau area (wi1102, ma1101, semester-1, automation)

**Examples:**
```
feat(WI1102): add computational thinking fundamentals
improve(MA1101): enhance calculus explanations with more examples
fix(IF2130): correct algorithm complexity analysis
refactor(semester-1): reorganize folder structure
docs(README): update contributing guidelines
```

---

## ✅ Checklist Sebelum Submit PR

### Konten Materi:
- [ ] Mengikuti template yang ada
- [ ] Bahasa Indonesia jelas & sederhana
- [ ] Struktur pedagogis lengkap (Tujuan → Isi → Ringkasan)
- [ ] Minimal 2 referensi berkualitas dengan link/ISBN
- [ ] Contoh konkret dan relevan
- [ ] Pertanyaan reflektif/latihan di akhir
- [ ] Internal links tested & working

### Metadata:
- [ ] Judul & deskripsi lengkap
- [ ] Author/contributor info
- [ ] Last updated date
- [ ] Related CPMK reference

### Code/Scripts:
- [ ] Follow Python/bash best practices
- [ ] Tested locally
- [ ] Documented dengan comments
- [ ] No hardcoded paths (use relative paths)

### Dokumentasi:
- [ ] Markdown formatted correctly
- [ ] Links bekerja
- [ ] No typos/grammar errors

---

## 📝 Template Struktur File

### Bahan Kajian (bahan-kajian/NN-topik.md)

```markdown
# Bahan Kajian: [Judul Topik]
**Mata Kuliah:** [Kode] - [Nama]  
**Modul ke:** N

## Tujuan Pembelajaran
[2-3 kalimat: apa yang bisa dilakukan pembaca setelah modul ini]

## Prasyarat
[Konsep dari modul sebelumnya yang harus dikuasai. Jika tidak ada, tulis "Tidak ada."]

## Pembahasan

### Sub-topik 1
[Konten - mulai konkret sebelum abstrak]

### Sub-topik 2
[Konten bertahap]

## Ringkasan
[Rekap 3-5 poin kunci, bullet list]

## Pertanyaan Reflektif
1. [Pertanyaan 1]
   - Jawaban: [...]
2. [Pertanyaan 2]
   - Jawaban: [...]

## Referensi
- [Judul](link) - Penulis, Tahun
- [Judul](link) - Penulis, Tahun
```

### CPMK (capaian-pembelajaran/NN-cpmk.md)

```markdown
# CPMK N: [Deskripsi Capaian]
**Mata Kuliah:** [Kode] - [Nama]

## Pernyataan Capaian
[Apa yang diharapkan mahasiswa capai - menggunakan Bloom's verbs]

## Indikator Pencapaian
- [ ] Spesifik indicator 1
- [ ] Spesifik indicator 2
- [ ] Spesifik indicator 3

## Sub-Topik Terkait
- [Bahan Kajian 1](../bahan-kajian/01-...)
- [Bahan Kajian 2](../bahan-kajian/02-...)

## Metode Penilaian
- Ujian: 40%
- Tugas: 40%
- Partisipasi: 20%

## Contoh Luaran
[Bagaimana mahasiswa menunjukkan pencapaian CPMK ini - project, assignment, dll]
```

---

## 🎓 Panduan Menulis Materi Pedagogis

### 1. **Scaffolding** (Konstruksi Bertahap)
Mulai dari yang **konkret** menuju **abstrak**:

```
Contoh konkret → Analogi → Definisi formal → Aplikasi → Latihan
```

**Contoh untuk "Algoritma Rekursif":**
- Konkret: Boneka matrioshka, pencarian di kamus
- Analogi: "Fungsi yang memanggil dirinya dengan input lebih sederhana"
- Definisi: "Algoritma yang memecah masalah ke sub-masalah serupa"
- Aplikasi: Faktorial, Fibonacci, tree traversal
- Latihan: Implementasi & trace

### 2. **Chunking** (Pembagian Konten)
Bagi konten ke bagian kecil yang bisa dicerna dalam 15-20 menit:

- ✅ BAIK: 3-4 sub-topik per modul, 500-800 kata per sub-topik
- ❌ BURUK: 10+ sub-topik per modul, 2000+ kata tanpa jeda

### 3. **Examples & Case Studies**
Berikan 2-3 contoh per konsep:
1. **Contoh Mudah** — Relatable, simple, familiar context
2. **Contoh Medium** — Slightly more complex, real-world
3. **Contoh Kompleks** (Opsional) — Advanced application

### 4. **Referensi Berkualitas**
Prioritas sumber:
1. Textbook standar (O'Reilly, MIT Press, Springer)
2. Paper peer-reviewed (ACM, IEEE)
3. Kursus online terbuka (MIT OCW, Coursera, edX)
4. Dokumentasi resmi (Python.org, etc)

**❌ HINDARI:** Blog pribadi, tutorial random YouTube, Wikipedia

### 5. **Bahasa Sederhana**
Target pembaca: mahasiswa pemula semester 1

- ✅ "Algoritma adalah langkah-langkah sistematis untuk menyelesaikan masalah"
- ❌ "Algoritma merupakan prosedur komputasional yang mengoptimalkan kompleksitas asimtotik"

---

## 🔄 Review & Feedback Loop

### Review Process:

1. **Author Submit**: Buat PR dengan materi baru/improvement
2. **Maintainer Review**: 
   - Check pedagogical quality
   - Verify referensi berkualitas
   - Validate accuracy
3. **Feedback**: Comment dengan suggestions
4. **Revision**: Author update based on feedback
5. **Approval & Merge**: PR diterima & di-merge

### Expected Timeline:
- Simple PR (bug fix, typo): 1-3 hari
- Medium PR (new section): 3-7 hari
- Large PR (full module): 1-2 minggu

---

## 🎯 Kontribusi untuk Skill Otomasi

Untuk improve kurikulum-builder skill & agent pipeline:

### Requirement:
- Python 3.8+
- Familiarity dengan agent frameworks (Claude SDK)
- Understanding of educational pedagogy

### Struktur:
```
.claude/
├── agents/
│   ├── scholar.md      (Research agent)
│   ├── critique.md     (Validation agent)
│   └── lecturer.md     (Content writing agent)
└── skills/
    └── kurikulum-builder.md  (Orchestration skill)
```

### Cara berkontribusi:
1. Fork & improve agent prompt
2. Test dengan pilot mata kuliah
3. Measure: faster completion, better quality?
4. Submit PR dengan testing results

---

## ⚖️ Lisensi & Attribution

Semua kontribusi akan di-publish di bawah **CC BY 4.0 License**.

Dengan kontribusi, Anda setuju:
- ✅ Konten dapat digunakan & di-share secara gratis
- ✅ Credit akan diberikan ke kontributor
- ✅ Konten dapat di-modify & di-improve

---

## 🙋 FAQ

### P: Apakah saya perlu expert untuk berkontribusi?
**J:** Tidak! Kami welcome kontribusi dari semua level. Maintainer akan review & provide feedback.

### P: Berapa lama review process?
**J:** Tergantung kompleksitas. Simple fix: 1-3 hari. Full modul: 1-2 minggu.

### P: Apakah saya bisa kontribusi untuk mata kuliah spesifik?
**J:** Tentu! Check PROGRESS.md untuk lihat mata kuliah mana yang masih butuh materi.

### P: Bagaimana jika saya tidak sempat sampai selesai?
**J:** Tidak masalah! Submit PR apa adanya dengan deskripsi jelas tentang status. Contributor lain bisa lanjutkan.

### P: Apakah ada kompensasi?
**J:** Project ini open-source volunteer-based. Kompensasi utama adalah:
- ✅ Credit & attribution
- ✅ Portfolio building
- ✅ Community impact
- ✅ Networking dengan kontributor lain

---

## 🚀 Mulai Sekarang!

1. **Lihat daftar mata kuliah yang butuh materi**: [PROGRESS.md](./PROGRESS.md)
2. **Fork repository** & buat branch baru
3. **Tulis/improve materi** mengikuti template & guidelines
4. **Test & validasi** sebelum submit
5. **Buat Pull Request** & wait untuk review

**Questions?** 
- Buka GitHub Discussion
- Email maintainer
- Join komunitas!

---

**Happy Contributing! 🎓✨**

Terima kasih telah membantu membangun kurikulum berkualitas untuk generasi informatikawan Indonesia!
