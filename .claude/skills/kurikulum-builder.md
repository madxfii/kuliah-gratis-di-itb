# Kurikulum Builder - Otomasi Pembuatan Materi Mata Kuliah

## Overview

Skill ini mengotomasi **3-fase pipeline** untuk menyusun materi kurikulum berkualitas tinggi:
1. **Scholar Phase**: Riset sumber akademik berkualitas
2. **Critique Phase**: Validasi & organisir outline bertahap
3. **Lecturer Phase**: Tulis materi final ke repo kurikulum

Gunakan skill ini untuk setiap mata kuliah secara berkelanjutan tanpa perlu proses manual berulang.

## How to Use

```bash
/kurikulum-builder <semester> <kode-mk> "<nama-mk>" "<bahan-kajian-1>|<bahan-kajian-2>|..." "<cpmk-1>|<cpmk-2>|..."
```

### Parameters

| Parameter | Format | Contoh |
|-----------|--------|--------|
| `<semester>` | Nomor 1-8 | `1` atau `2` |
| `<kode-mk>` | Kode ITB | `WI1102`, `MA1101`, `IF2130` |
| `<nama-mk>` | Nama full (quoted) | `"Berpikir Komputasional"` |
| `<bahan-kajian>` | Pipe-separated list (quoted) | `"Konsep dasar CT\|Transformasi ke tools\|Dampak & tren"` |
| `<cpmk>` | Pipe-separated list (quoted) | `"Memahami & mempraktekkan CT\|Mendayagunakan CT untuk analisis"` |

### Examples

**WI1102 (already done, use for reference)**:
```bash
/kurikulum-builder 1 WI1102 "Berpikir Komputasional" \
  "Konsep dasar computational thinking (abstraksi, algoritme, dekomposisi, pengenalan pola)|Transformasi solusi computational thinking ke kakas komputasional|Dampak dan tren komputing pada domain tertentu" \
  "Mahasiswa memahami konsep dan mampu mempraktekkan proses berpikir komputasional yang tepat dan terarah untuk pemecahan masalah.|Mahasiswa mampu mendayagunakan teknik berpikir komputasional untuk menganalisis permasalahan baru, dan menghasilkan solusi atas permasalahan tersebut."
```

**MA1101 (next course in semester 1)**:
```bash
/kurikulum-builder 1 MA1101 "Matematika I" \
  "Fungsi dan relasi|Limit dan kontinuitas|Turunan dan aplikasi|Integral dan aplikasi" \
  "Mahasiswa memahami konsep fungsi, limit, dan kontinuitas serta aplikasinya.|Mahasiswa mampu menghitung turunan dan integral, serta menerapkannya dalam problem-solving."
```

## Workflow Otomasi

### Phase 1: Scholar Research (Otomatis)
```
INPUT: Mata kuliah + Bahan Kajian + CPMK
  ↓
PROCESS:
  - Load metadata dari WI[KODE].html di folder semester
  - Jalankan Scholar Agent: riset 5-8 sumber per bahan kajian
  - Output: riset-sumber-[KODE].md (scratchpad)
  ↓
STATUS: ✅ Riset selesai → Proceed to Critique
```

### Phase 2: Critique Validation (Otomatis)
```
INPUT: riset-sumber-[KODE].md + scaffold CPMK/bahan-kajian
  ↓
PROCESS:
  - Load outline dari riset Scholar
  - Validasi CPMK & perbaiki indikator jika perlu
  - Susun 3-4 modul bertahap (Konsep → Aplikasi → Dampak)
  - Output: outline-tervalidasi-[KODE].md (scratchpad)
  ↓
STATUS: ✅ Outline tervalidasi → Proceed to Lecturer
```

### Phase 3: Lecturer Writing (Otomatis)
```
INPUT: outline-tervalidasi-[KODE].md
  ↓
PROCESS:
  - Tentukan granularitas: file vs folder untuk setiap bahan kajian
  - Tulis materi bahan-kajian dengan struktur pedagogis:
    * Tujuan Pembelajaran
    * Prasyarat
    * Pembahasan bertahap (konkret → abstrak)
    * Ringkasan & Pertanyaan Reflektif
    * Referensi
  - Perbaiki file CPMK dengan indikator spesifik
  - Output: Semua file .md ditulis ke folder repo
  ↓
STATUS: ✅ Materi final selesai → Generate Report
```

### Phase 4: Report & Review
```
OUTPUT:
  - LAPORAN-[KODE].md (di scratchpad untuk review)
  - Tree struktur folder final
  - Statistik: jumlah file, durasi per modul, kompleksitas
  ↓
USER REVIEW:
  - User membaca laporan & contoh file
  - User approve atau minta revisi
  - Jika approved → siap untuk tahap berikutnya
```

## Example Output Structure

Setelah skill selesai, struktur repo akan terlihat seperti:

```
semester-1/01-WI1102-berpikir-komputasional/
├── WI1102.html                          [sumber asli ITB]
├── bahan-kajian/
│   ├── 01-konsep-dasar-computational-thinking/
│   │   ├── 00-pengantar.md
│   │   ├── 01-definisi-dan-konteks.md
│   │   ├── 02-empat-pilar-ct.md
│   │   ├── 03-ct-dalam-praktik.md
│   │   └── ringkasan.md
│   ├── 02-transformasi-solusi-computational-thinking/
│   │   ├── 00-pengantar.md
│   │   ├── 01-pseudocode.md
│   │   ├── 02-snap-implementation.md
│   │   ├── 03-python-implementation.md
│   │   ├── 04-debugging.md
│   │   └── ringkasan.md
│   └── 03-dampak-dan-tren-komputing.md
└── capaian-pembelajaran/
    ├── 01-cpmk-1-memahami-dan-mempraktekkan.md
    └── 02-cpmk-2-mendayagunakan-ct.md
```

## Execution Timeline

| Fase | Estimasi Waktu | Async |
|------|-----------------|-------|
| Scholar Research | 3-5 menit | ✅ Background |
| Critique Validation | 2-3 menit | ✅ Background |
| Lecturer Writing | 5-7 menit | ✅ Background |
| **Total** | **10-15 menit** | **Semua otomatis** |

**Per mata kuliah hanya butuh 10-15 menit!** User tidak perlu menunggu — skill berjalan di background.

## Batch Processing (Opsional)

Untuk mempercepat, Anda bisa batch multiple courses sekaligus:

```bash
# Process 2 mata kuliah semester 1 sekaligus (parallel background runs)
/kurikulum-builder 1 WI1102 "Berpikir Komputasional" "..." "..."
/kurikulum-builder 1 MA1101 "Matematika I" "..." "..."

# Terus lakukan yang lain tanpa tunggu
# User bisa lihat progress via `claude tasks list`
```

Skill akan queue semua requests dan proses secara bertahap.

## Expected Output per Course

Setiap skill execution menghasilkan:

✅ **Materi Pembelajaran** (di repo):
- 10-15 file markdown final siap mengajar
- Struktur pedagogis konsisten (Tujuan → Isi → Ringkasan)
- Referensi lengkap dengan link/ISBN

✅ **Laporan Ringkas** (di scratchpad):
- LAPORAN-[KODE].md: summary statistik, catatan kualitas, struktur final
- User bisa review sebelum approve → ready untuk publikasi

✅ **Database Sumber** (disimpan):
- riset-sumber-[KODE].md: untuk ref internal, bisa reuse untuk mata kuliah related
- outline-tervalidasi-[KODE].md: untuk tracking validasi akademis

## How to Get Started

1. **Tunggu WI1102 selesai** (seharusnya dalam beberapa menit)
2. **Review output WI1102** di repo + laporan di scratchpad
3. **Gunakan skill untuk mata kuliah berikutnya**:
   ```bash
   /kurikulum-builder 1 MA1101 "Matematika I" "..." "..."
   ```
4. **Repeat untuk 6 mata kuliah semester 1 sisanya**
5. **Lanjut ke semester 2** dengan workflow yang sama

## Tips Penggunaan

- **Batch processing**: Jalankan 2-3 mata kuliah sekaligus (parallelizable di background)
- **Monitor progress**: Gunakan `claude tasks` untuk lihat status real-time
- **Reuse sources**: Jika 2 MK share topik (mis. Matematika & Fisika), Scholar bisa cari source yang overlap
- **Iterative review**: Review laporan per 2-3 mata kuliah, bukan semua sekaligus

## Timeline Estimasi Penuh Kurikulum

| Semester | MK Count | Total Time | Calendar |
|----------|----------|-----------|----------|
| Sem 1 | 8 MK | ~2 jam (parallelizable) | 1 hari |
| Sem 2 | 7 MK | ~1.5 jam | 1 hari |
| Sem 3-4 | ~13 MK | ~3 jam | 2-3 hari |
| Sem 5-8 | ~15 MK | ~3.5 jam | 3-4 hari |
| **Spesialisasi** | ~26 MK | ~6 jam | 5-7 hari |
| **TOTAL** | 69 MK | **~15 jam** | **~2 minggu** |

**Dengan skill ini: Semua kurikulum (8 semester + 6 spesialisasi) bisa selesai dalam 2-3 minggu kerja!**

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Skill lambat (> 15 menit) | Batasi WebSearch depth di Scholar phase, atau split MK besar jadi 2 iterasi |
| Sumber tidak lengkap | Manual review LAPORAN-[KODE].md, request Scholar re-search specific topic |
| Materi terlalu panjang | Lecturer akan auto-split ke folder jika kompleks; review LAPORAN untuk struktur final |
| Prasyarat tidak terpenuhi | Critique akan tandai dengan `[PERLU KOORDINASI]`, delay MK tersebut sampai prasyarat done |

---

**Skill siap digunakan!** Jalankan untuk setiap mata kuliah semester 1-8 & spesialisasi untuk build full kurikulum.
