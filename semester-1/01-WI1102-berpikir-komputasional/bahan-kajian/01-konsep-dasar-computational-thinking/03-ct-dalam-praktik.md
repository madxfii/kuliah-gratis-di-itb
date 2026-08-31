# Sub-Modul 1.3: Computational Thinking dalam Praktik

**Durasi:** 1-1.5 minggu | **Target Bloom Level:** Apply (C3) → Analyze (C4)

---

## Tujuan Pembelajaran Sub-Modul

Setelah mempelajari sub-modul ini, Anda mampu:
- **Menganalisis studi kasus real-world** dan mengidentifikasi pilar-pilar CT yang digunakan
- **Menerapkan CT process** untuk memecahkan masalah sederhana yang belum pernah Anda lihat
- **Menulis pseudocode** sederhana (instruksi terstruktur) untuk masalah-masalah praktis
- **Mengevaluasi berbagai pendekatan** terhadap satu masalah dan memilih yang paling efektif

---

## Prasyarat

Anda sudah memahami Sub-Modul 1.1 dan 1.2 (definisi CT dan empat pilarnya).

---

## Studi Kasus 1: Google Maps — Mencari Rute Tercepat

### Masalah Nyata

Anda di Jakarta, ingin pergi ke Bandung menggunakan mobil. Ada 5 rute berbeda:
- Rute A: Via Puncak (80 km, biasanya lancar)
- Rute B: Via Padalarang (100 km, sering macet jam 7-9 pagi)
- Rute C: Via Subang (120 km, jarang macet)
- Rute D: Via Karawang (200 km, perjalanan sangat panjang)
- Rute E: Via Cianjur (110 km, biasanya lancar tapi ada risiko macet mendadak)

**Pertanyaan**: Mana rute tercepat untuk waktu tempuh minimal?

### Solusi dengan CT

#### **Dekomposisi**
```
PROBLEM: Cari rute tercepat Jakarta → Bandung

Sub-problems:
1. Kumpulkan data rute: jarak, kondisi real-time, traffic prediction
2. Estimasi waktu tempuh untuk setiap rute berdasarkan kondisi saat ini
3. Bandingkan waktu tempuh
4. Pilih rute dengan waktu tempuh minimal
5. Berikan rekomendasi & update real-time jika traffic berubah
```

#### **Pengenalan Pola**
```
Pattern yang diamati (dari data historis):
- Jam 6-9 pagi: traffic padat di Puncak, Padalarang
- Jam 9-12 siang: traffic mulai normal
- Jam 1-5 sore: normal
- Jam 5-8 malam: padat lagi (pulang kerja)

Pattern kondisi jalan:
- Jalan tol: lebih stabil, lebih predictable
- Jalan biasa: bisa unpredictable, lebih banyak faktor

Recognition: Untuk waktu pagi, hindari Puncak & Padalarang. 
Sebaiknya pakai Subang atau Cianjur meski lebih jauh tapi lebih lancar.
```

#### **Abstraksi**
```
Fokus pada:
- Jarak rute (dalam km)
- Kecepatan rata-rata di kondisi current (dalam km/jam)
- Waktu tempuh = Jarak / Kecepatan

Abaikan detail:
- Tipe kendaraan (mobil, motor, truk) — diasumsikan mobil
- Bensin yang dipakai, biaya parkir
- Pemandangan indah di jalan
- Driver personality (suka berlahan atau tergesa)
```

#### **Algoritma (Pseudocode)**
```
ALGORITMA: Cari Rute Tercepat
INPUT: Jam berangkat, kondisi traffic real-time
OUTPUT: Rute dengan waktu tempuh minimal

LANGKAH-LANGKAH:
1. GET kondisi traffic terkini dari data real-time (API Google Maps)
2. FOR EACH rute dalam daftar 5 rute:
     CALCULATE waktu_tempuh = jarak / kecepatan_rata_rata
     STORE (rute, waktu_tempuh) dalam daftar
3. FIND rute dengan waktu_tempuh paling kecil
4. RECOMMEND rute itu ke user
5. MONITOR traffic setiap 5 menit
6. IF traffic berubah drastis:
     RECALCULATE rute terbaik
     NOTIFY user dengan rute baru (jika signifikan berbeda)

PSEUDOCODE (lebih detail):
```
```python
# Pseudocode (mirip syntax tapi bukan kode asli)
best_route = None
minimum_time = INFINITY

FOR each_route IN routes_list:
    current_speed = GET_CURRENT_SPEED(each_route)  # dari traffic data
    time_estimate = each_route.distance / current_speed
    
    IF time_estimate < minimum_time:
        minimum_time = time_estimate
        best_route = each_route

RECOMMEND(best_route)
MONITOR_TRAFFIC(best_route) every 5 minutes
```

### Takeaway

Google Maps menggunakan **CT process** ini untuk memberikan rekomendasi rute terbaik kepada jutaan pengguna setiap hari. Kombinasi dari:
- **Dekomposisi** (break problem into data collection, estimation, comparison)
- **Pattern Recognition** (know traffic patterns at different times)
- **Abstraction** (focus on time & distance, ignore irrelevant details)
- **Algorithm Design** (structured steps to find best route)

---

## Studi Kasus 2: Data Scientist Menganalisis Penjualan Produk

### Masalah Nyata

Perusahaan e-commerce punya 1 juta data penjualan per bulan. Manager ingin tahu: "Produk mana yang paling profitable? Bagaimana trend penjualan? Apa actionable insights?"

### Solusi dengan CT

#### **Dekomposisi**
```
PROBLEM: Analisis 1 juta data penjualan untuk actionable insights

Sub-problems:
1. DATA COLLECTION: Kumpulkan data dari sistem penjualan
2. DATA CLEANING: Hapus outliers, handle missing values
3. EXPLORATORY ANALYSIS: Lihat pattern di data (produk populer, trend, etc)
4. DEEP DIVE: Analisis subset tertentu (produk mahal vs murah, by region, dll)
5. VISUALIZATION: Buat chart/graph yang mudah dipahami manager
6. RECOMMENDATION: Berikan action (produk mana yang perlu marketing push, dll)
```

#### **Pengenalan Pola**
```
Pola dari data:
- Produk elektronik: penjualan tinggi di akhir tahun (Black Friday, Natal)
- Fashion: penjualan tinggi musim pergantian (spring/summer, fall/winter)
- Food: penjualan stabil sepanjang tahun tapi spike saat promo
- Geographic pattern: penjualan higher di kota-kota besar

Recognition dari pattern ini:
→ Jadwalkan inventory & marketing di waktu yang tepat
→ Alokasikan budget ke kategori yang high-demand di musim tertentu
```

#### **Abstraksi**
```
Fokus pada:
- Kategori produk
- Volume penjualan
- Revenue (price × quantity)
- Regional distribution
- Month-over-month trend

Abaikan detail:
- Nama pelanggan individual
- Detail shipping address (kecuali region)
- Exact timestamp (cukup hari atau minggu)
- Personal preference dari reviewer
```

#### **Algoritma**
```
ALGORITMA: Analisis Penjualan & Generate Insight

INPUT: 1 juta transaksi penjualan (produk, kategori, harga, qty, region, date)
OUTPUT: Rekomendasi strategis untuk sales/marketing team

LANGKAH-LANGKAH:
1. IMPORT data penjualan
2. CLEAN data: hapus null/duplicate/invalid entries
3. CALCULATE metrics:
   - Total revenue by product
   - Total revenue by category
   - Total revenue by region
   - Month-over-month growth rate
4. SORT produk by revenue (descending)
5. IDENTIFY top 20 produk (80/20 rule: 20% produk contribute 80% revenue)
6. ANALYZE trend: is revenue growing/declining/stable?
7. IDENTIFY seasonal patterns: ada spike di bulan tertentu?
8. SEGMENT: bandingkan revenue dari berbagai region
9. GENERATE INSIGHTS:
   - Produk mana paling profitable? (reward dengan marketing budget)
   - Produk mana declining? (clear inventory atau discontinue)
   - Region mana yang underperform? (increase marketing effort)
   - Musim apa yang paling profitable? (hire temporary staff, stock up)
10. CREATE visuals: dashboard dengan chart untuk communicate ke stakeholders
```

### Takeaway

Data scientist menggunakan **CT** setiap hari untuk:
- **Dekomposisi** data besar menjadi pieces yang manageable
- **Pattern Recognition** untuk identifikasi trend & seasonal patterns
- **Abstraction** untuk fokus pada metrics yang penting (revenue, growth)
- **Algorithms** untuk efficiently process jutaan data points

---

## Studi Kasus 3: Dokter Diagnosa Pasien (Healthcare Domain)

### Masalah Nyata

Pasien datang dengan gejala: demam, batuk, sakit kepala, mual. Dokter perlu diagnosa cepat dan akurat. Apa yang mungkin menyebabkan gejala ini? Tes apa yang perlu dilakukan?

### Solusi dengan CT

#### **Dekomposisi**
```
PROBLEM: Diagnosa penyakit dari gejala

Sub-problems:
1. GATHER INFO: Tanyakan detail gejala (berapa lama? berapa derajat demam? etc)
2. MEDICAL HISTORY: Tanyakan riwayat penyakit, alergi, obat yang diminum
3. DIFFERENTIAL DIAGNOSIS: Berdasarkan gejala, apa penyakit yang mungkin?
4. INITIAL TESTING: Tes mana yang bisa help rule in/out?
5. ANALYZE RESULT: Hasil tes apa yang didapat? Apakah cocok dengan diagnosa?
6. FINAL DIAGNOSIS & TREATMENT: Apa diagnosa final? Obat apa yang tepat?
```

#### **Pengenalan Pola**
```
Dokter recognize patterns dari pengalaman bertahun-tahun:
- Demam + batuk + sakit kepala (tanpa mual) → likely Flu
- Demam + batuk + sakit kepala + mual (bahkan muntah) → could be Dengue atau COVID
- Demam rendah (37-37.5°C) + batuk mild → likely mild cold
- Demam tinggi (39-40°C) + batuk parah + sesak napas → red flag, could be pneumonia

Pattern dari test results:
- Rapid test flu positif → confirm influenza
- Dengue serology positive → confirm dengue
- Chest X-ray shows infiltrates → pneumonia
```

#### **Abstraksi**
```
Fokus pada:
- Gejala utama (demam, batuk, sakit kepala, mual)
- Durasi gejala (berapa hari)
- Severity (mild/moderate/severe)
- Riwayat penyakit sebelumnya
- Test results

Abaikan detail:
- Preferensi warna obat pasien
- Pekerjaan pasien yang detil
- Hobby pasien
- Nama lengkap (cukup inisial untuk privacy)
```

#### **Algoritma (Decision Tree)**
```
START: Pasien dengan demam + batuk + sakit kepala + mual

STEP 1: Tanya durasi gejala?
  - Jika < 3 hari → Go to STEP 2
  - Jika 3-7 hari → Go to STEP 2 (tapi elevated concern)
  - Jika > 7 hari → Concern untuk bacterial infection atau chronic condition

STEP 2: Cek severity demam?
  - Jika demam < 38°C → likely viral, monitor
  - Jika demam 38-39°C → moderate concern, do rapid test (flu/COVID)
  - Jika demam > 39°C → high concern, do blood test & imaging

STEP 3: Riwayat penyakit?
  - Jika patient punya diabetes/asthma → elevated risk, prescribe more caution
  - Jika patient immunocompromised → high risk, escalate ke specialist

STEP 4: Order tests:
  - Rapid flu/COVID test
  - If positive → confirm diagnosis, treat dengan antivirals
  - If negative → blood test untuk dengue serology, CBC (complete blood count)

STEP 5: Analyze hasil + Diagnosa final:
  - Dengue serology positive → Dengue, supportive care, monitor untuk complication
  - Flu test positive → Influenza, antiviral (Tamiflu), rest & fluid
  - CBC shows high white cells + pneumonia symptoms → suspect bacterial, antibiotics

STEP 6: Prescribe treatment & follow-up:
  - Medication (antiviral/antibiotic sesuai diagnosa)
  - Rest & hydration instructions
  - Follow-up appointment dalam 3 hari jika gejala tidak membaik
```

### Takeaway

Dokter menggunakan **CT** untuk:
- **Dekomposisi** masalah kompleks (satu set gejala bisa dari banyak penyakit)
- **Pattern Recognition** dari training/experience (mengenali signature symptoms)
- **Abstraction** (fokus pada gejala kunci, bukan detail tidak relevan)
- **Algorithm Design** (systematic approach untuk diagnosa yang akurat dan aman)

---

## Praktik Terbimbing: Solve Your Own Problem

### Exercise 1: Organize Study Session

**Problem**: "Saya punya 5 mata kuliah semester ini, dan saya merasa tertinggal. Saya perlu organize time yang efisien untuk belajar semua mata kuliah tanpa overwhelmed."

**Solusi dengan CT**:

**Dekomposisi**:
```
1. Kumpulkan info: berapa banyak materi tiap mata kuliah? Kapan ujian?
2. Prioritas: mata kuliah mana yang paling sulit? Mana deadline-nya paling dekat?
3. Alokasi waktu: berapa jam per minggu untuk setiap mata kuliah?
4. Buat jadwal: hari/jam mana saya belajar apa?
5. Tracking: monitor progress, adjust jika diperlukan
```

**Pengenalan Pola**:
- Pagi hari (6-9am) saya paling alert → gunakan untuk mata kuliah sulit
- Sore hari (3-5pm) saya agak brain-fogged → gunakan untuk review ringan
- Malam hari (8-10pm) saya bisa fokus tapi mudah lelah → gunakan untuk tugas/latihan

**Abstraksi**:
- Fokus: mata kuliah, durasi, difficulty level, deadline
- Abaikan: lokasi belajar detil, snack yang dimakan, siapa yang di sekitar

**Algoritma**:
```
FOR EACH mata kuliah:
    IF deadline_ujian adalah ini minggu:
        ALLOCATE 3 jam/hari
    ELSE IF deadline adalah 2-3 minggu:
        ALLOCATE 2 jam/hari
    ELSE:
        ALLOCATE 1 jam/hari

SCHEDULE:
    Morning slot (6am-9am): Hardest subject
    Evening slot (8pm-10pm): Tugas & practice
    Weekend: Review & catch-up
    
TRACK progress mingguan
IF progress behind schedule:
    INCREASE allocate time atau EXTEND study jam
```

---

### Exercise 2: Plan a Team Project (Software Development)

**Problem**: "Tim saya diberi tugas membuat aplikasi kalkulator dengan GUI. Kami 4 orang, deadline 3 minggu. Bagaimana caranya agar efisien dan tepat waktu?"

**Solusi dengan CT**:

**Dekomposisi**:
```
1. Design: UI design, choose technology/framework
2. Architecture: sistem design, file structure
3. Implementation: split work per module
   - Module 1: Input handling & display (person A)
   - Module 2: Basic operations (+, -, *, /) (person B)
   - Module 3: Advanced operations (sqrt, power, etc) (person C)
   - Module 4: Integration & testing (person D)
4. Testing: unit test + integration test
5. Deployment: package & deliver
```

**Pengenalan Pola**:
- Software project yang gagal biasanya karena:  poor planning, unclear requirements, bad communication
- Successful project pattern: clear spec, modular design, frequent integration, testing early

**Abstraksi**:
- Fokus: functionality (apa yang kalkulator bisa lakukan), timeline, team roles
- Abaikan: nama variable yang cantik, exact color scheme, easter eggs

**Algoritma** (Project plan):
```
WEEK 1:
  - Meeting 1 (Day 1): Discuss requirements, agree on tech stack
  - Design UI mockup (Day 2-3)
  - Setup dev environment untuk semua (Day 4)
  - Start basic implementation (Day 5)

WEEK 2:
  - Each person works on assigned module (Day 1-3)
  - Daily standup: 15 min, report progress & blockers
  - Module integration: combine modules (Day 4)
  - Testing: find & fix bugs (Day 5)

WEEK 3:
  - Bug fixing & edge case testing (Day 1-2)
  - Code review dari team (Day 3)
  - Final polish & documentation (Day 4)
  - Submission & demo (Day 5)
```

---

## Ringkasan Sub-Modul 1.3

### Poin-Poin Kunci:

✓ **CT adalah universal** — bisa diapply ke berbagai domain (tech, healthcare, business, education)
✓ **Dekomposisi membantu manage complexity** — break big problem menjadi pieces yang manageable
✓ **Pengenalan pola = leverage experience & data** — untuk predict & optimize
✓ **Abstraksi fokus pada essential** — untuk clarity dan efficiency
✓ **Algoritma = structured plan** — untuk execute solution secara konsisten

✓ **CT + Domain Knowledge = Powerful** — kombinasi cara berpikir + pengetahuan spesifik domain

---

## Pertanyaan Reflektif

1. **Dari 3 studi kasus (Google Maps, Data Science, Healthcare), mana yang paling resonan dengan Anda? Mengapa?**
   - Jawaban: _________________

2. **Ambil satu problem dari bidang studi Anda (matematika, sains, dll). Bagaimana Anda bisa apply 4 pilar CT untuk solve-nya?**
   - Problem: _________________
   - Dekomposisi: _________________
   - Pattern: _________________
   - Abstraksi: _________________
   - Algoritma: _________________

3. **Dalam kerja tim atau grup, bagaimana Anda menggunakan CT untuk kolaborasi yang lebih efektif?**
   - Jawaban: _________________

---

## Referensi

1. **Beecher, K. (2017).** Ch. 7-9 — Case Studies & Applications
   - Catatan: Real-world examples dari berbagai domain

2. **Computational Thinking in Data Science (CACM, 2020)**
   - Link: https://cacm.acm.org/
   - Catatan: Academic perspective tapi accessible

3. **MIT 18.S191 — Case Studies from Real-World Problems**
   - Link: https://ocw.mit.edu/
   - Catatan: Energy, climate, biology examples

4. **UC Berkeley CS10 (BJC Curriculum) — Applications of Computing**
   - Link: https://bjc.berkeley.edu/
   - Catatan: Interactive projects & case studies

---

**Selesai Modul 1!** Lanjut ke **Ringkasan Modul** untuk recap semua yang sudah dipelajari.
