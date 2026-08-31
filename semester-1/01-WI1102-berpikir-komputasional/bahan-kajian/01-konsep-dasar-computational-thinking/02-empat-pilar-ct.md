# Sub-Modul 1.2: Empat Pilar Computational Thinking

**Durasi:** 2-2.5 minggu | **Target Bloom Level:** Understand (C2) → Apply (C3)

---

## Tujuan Pembelajaran Sub-Modul

Setelah mempelajari sub-modul ini, Anda mampu:
- Mendefinisikan dan menjelaskan **empat pilar CT**: Dekomposisi, Pengenalan Pola, Abstraksi, dan Desain Algoritma
- Memberikan **minimal 3 contoh konkret untuk setiap pilar** dari kehidupan sehari-hari
- **Mengenali pilar mana yang digunakan** dalam berbagai skenario masalah
- **Menerapkan pilar-pilar ini** untuk memecahkan masalah sederhana

---

## Prasyarat

Anda sudah memahami Sub-Modul 1.1 (apa itu CT dan mengapa penting).

---

## Pengenalan: Membedah Masalah Kompleks

Bayangkan Anda sedang bingung: "Bagaimana saya menemukan rute tercepat untuk sampai ke kampus pagi ini?"

Ini adalah masalah kompleks yang melibatkan banyak faktor: jarak, lalu lintas, kendaraan yang tersedia, waktu, dll.

Jika Anda menggunakan **keempat pilar CT**, Anda akan:

1. **Dekomposisi**: Pecah masalah → "Apa pilihan transportasi saya? Mana yang paling cepat? Apa hambatannya?"
2. **Pengenalan Pola**: "Saya pernah mencoba rute ini sebelumnya. Pada jam 7 pagi selalu macet di jalan utama, jadi saya lewat jalan samping."
3. **Abstraksi**: Fokus pada rute dan waktu saja, abaikan detail (warna kendaraan, siapa supir, dll)
4. **Algoritma**: "Langkah 1: Cek lalu lintas real-time. Langkah 2: Pilih rute alternatif jika macet. Langkah 3: Berangkat 15 menit lebih awal untuk buffer."

Sekarang, mari kita pelajari setiap pilar secara detail!

---

## Pilar 1: Dekomposisi (Decomposition)

### Definisi

**Dekomposisi** adalah proses memecah masalah besar dan kompleks menjadi bagian-bagian yang lebih kecil, lebih mudah dipahami, dan lebih mudah diselesaikan.

### Intuisi Sederhana

Pikirkan Anda adalah **manajer proyek yang memimpin pembangunan rumah besar**. Anda tidak bisa mulai dengan "bangun rumah" dalam satu langkah besar. Sebaliknya, Anda pecah:

```
RUMAH (masalah besar)
├─ Fondasi
├─ Struktur (kolom, balok)
├─ Dinding & Atap
├─ Instalasi (listrik, air, gas)
├─ Finishing (cat, lantai, pintu)
└─ Interior (furniture, dekorasi)
```

Setiap bagian ini bisa dipecah lagi:
- **Fondasi**: Gali, pasang bekisting, cor beton, curing
- **Listrik**: Pasang kabel utama, sub-panel, outlet, lampu

Dengan cara ini, masalah besar yang terasa tidak mungkin menjadi serangkaian tugas kecil yang bisa dikelola.

### Contoh 1: Memasak Nasi Goreng

**Masalah Besar**: "Saya ingin membuat nasi goreng untuk 10 orang."

**Dekomposisi**:
```
Nasi Goreng (untuk 10 orang)
├─ Persiapan Bahan
│  ├─ Cuci beras & masak (2 jam sebelumnya)
│  ├─ Siapkan telur (aduk dalam mangkuk)
│  ├─ Siapkan sayur (potong bawang, carrot, kacang polong)
│  └─ Siapkan bumbu (kecap, garam, merica, bawang putih)
│
├─ Memasak
│  ├─ Panaskan wajan/kuali besar
│  ├─ Tumis bawang putih hingga wangi
│  ├─ Masukkan nasi, aduk rata
│  ├─ Masukkan sayur, aduk rata
│  ├─ Buat lubang, masukkan telur, aduk
│  ├─ Tambahkan bumbu (kecap, garam)
│  └─ Aduk hingga rata, 3-5 menit
│
└─ Penyajian
   ├─ Ambil porsi ke piring individual
   ├─ Tambah pelengkap (acar, perkedel, dll)
   └─ Sajikan selama masih panas
```

Dengan dekomposisi ini, masalah "memasak nasi goreng untuk 10 orang" tidak lagi overwhelming. Anda tahu persis apa yang harus dilakukan di setiap tahap.

### Contoh 2: Membuat Aplikasi Game Sederhana

**Masalah Besar**: "Saya ingin membuat game yang fun dan bisa dimainin orang lain."

**Dekomposisi** (dari perspektif game developer):
```
Game Kecil
├─ Desain Game
│  ├─ Tentukan tujuan pemain (menghindari obstacle? mengumpulkan point?)
│  ├─ Tentukan mekanik (cara bermain, kontrol)
│  ├─ Tentukan grafis/tema (minimalis, colorful, dll)
│  └─ Desain level (easy → hard)
│
├─ Implementasi (Koding)
│  ├─ Setup sprite & animasi
│  ├─ Program kontrol pemain (keyboard input)
│  ├─ Program obstacle/enemy behavior
│  ├─ Program collision detection (tumbukan)
│  ├─ Program scoring system
│  └─ Program win/lose condition
│
├─ Testing & Debugging
│  ├─ Coba bermain sendiri
│  ├─ Coba dengan teman, amati reaksi
│  ├─ Cari bug (kesalahan)
│  └─ Perbaiki bug
│
└─ Launch
   ├─ Buat packaging yang menarik
   ├─ Buat manual/instruksi
   └─ Bagikan ke orang lain
```

Lihat? Masalah besar menjadi serangkaian sub-masalah yang manageable!

### Contoh 3: Analisis Data Penjualan (Domain Bisnis)

**Masalah**: "Saya ingin tahu mengapa penjualan turun bulan ini."

**Dekomposisi**:
```
Analisis Penjualan
├─ Kumpulkan Data
│  ├─ Data penjualan per produk
│  ├─ Data penjualan per region
│  ├─ Data per tipe pelanggan (baru vs existing)
│  └─ Data harga & diskon yang diberikan
│
├─ Analisis Awal
│  ├─ Bandingkan bulan ini vs bulan lalu
│  ├─ Bandingkan dengan tahun lalu (trend)
│  ├─ Identifikasi produk/region mana yang turun drastis
│  └─ Identifikasi produk/region yang naik
│
├─ Investigasi Mendalam
│  ├─ Tanyakan ke sales team: "Apa hambatan?"
│  ├─ Cek faktor eksternal (musim, kompetitor, keadaan ekonomi)
│  ├─ Analisis kepuasan pelanggan (feedback, return rate)
│  └─ Cek operasional (stok, pengiriman, customer service)
│
└─ Rekomendasi & Action
   ├─ Identifikasi root cause
   ├─ Buat rencana perbaikan
   └─ Monitornya
```

---

### Kapan Menggunakan Dekomposisi?

Gunakan dekomposisi ketika:
- ✓ Masalah terasa besar dan overwhelming
- ✓ Ada banyak aspek berbeda yang perlu dipertimbangkan
- ✓ Anda tidak tahu dari mana harus mulai
- ✓ Anda bekerja dalam tim (setiap orang bisa handle satu bagian)

---

## Pilar 2: Pengenalan Pola (Pattern Recognition)

### Definisi

**Pengenalan Pola** adalah kemampuan mengidentifikasi kesamaan, keteraturan, atau struktur yang berulang dalam data, masalah, atau situasi. Ketika Anda mengenali pola, Anda bisa menggunakan solusi yang sudah ada atau memprediksi apa yang akan terjadi.

### Intuisi Sederhana

Bayangkan Anda menonton prakiraan cuaca. Pembaca prakiraan mengatakan: "Besok akan hujan karena mendekati musim penghujan, dan pressure udara turun seperti sebelum hujan turun minggu lalu."

Orang itu **mengenali pola** dari data historis (musim penghujan selalu dengan hujan) dan kondisi saat ini (pressure turun). Dengan mengenali pola ini, mereka bisa memprediksi.

### Contoh 1: Pola dalam Kehidupan Sehari-hari

**Pola: Lalu Lintas Jam Tertentu**
- Jam 6-8 pagi: Macet (orang berangkat kerja/sekolah)
- Jam 12-1 siang: Agak normal (orang istirahat/makan siang)
- Jam 5-7 sore: Sangat macet (orang pulang kerja)

Ketika Anda **mengenali pola ini**, Anda bisa keputusan: "Saya berangkat jam 5.30 pagi, bukan jam 7 pagi, karena jam 7 selalu macet."

**Pola: Perubahan Cuaca**
- Pagi hari mendung → Siang akan panas → Sore akan hujan (pola musiman tertentu)

Ketika Anda mengenali pola ini, Anda membawa payung atau tidak pergi ke tempat yang rawan banjir.

### Contoh 2: Pola dalam Belajar

**Pola: Soal-Soal Ujian**

Jika Anda melihat beberapa ujian di masa lalu, Anda mungkin mengenali pola:
- 60% soal adalah tentang definisi & penjelasan (essay)
- 30% soal adalah calculation/problem-solving
- 10% soal adalah true-false

Ketika Anda **mengenali pola ini**, Anda bisa **menyesuaikan strategi belajar**:
- Fokus 60% waktu pada hafal konsep dan bisa menjelaskan
- Fokus 30% waktu pada latihan soal
- Fokus 10% waktu pada review/drill true-false

### Contoh 3: Pola dalam Data dan Kode

**Pola: Pendeteksian Spam Email**

Sistem email modern menggunakan machine learning untuk mendeteksi spam. Bagaimana? Dengan mengenali **pola** dari ribuan email spam:
- Kata-kata tertentu yang sering muncul di spam: "klik di sini", "gratis", "kaya", "investasi cepat"
- Struktur email: judul dengan huruf besar berlebihan, banyak tanda seru
- Pengirim: dari domain yang tidak dikenal

Ketika sistem mengenali **pola-pola ini**, sistem bisa bilang: "Email ini kemungkinan spam karena cocok dengan pola yang sudah kita lihat sebelumnya."

**Pola: Algoritma Pencarian**

Jika Anda ingin cari orang tertentu di antara 1000 orang:
- Pola 1: Cari satu per satu dari awal (inefficient, bisa mengambil 500 kali percobaan rata-rata)
- Pola 2: Bagi dua setiap kali (binary search, hanya 10 kali percobaan)

Ketika Anda **mengenali pola yang efisien**, Anda bisa gunakan pola itu berkali-kali.

### Kapan Menggunakan Pengenalan Pola?

Gunakan pengenalan pola ketika:
- ✓ Anda pernah menghadapi masalah serupa sebelumnya
- ✓ Ada data historis yang bisa Anda analisis
- ✓ Anda ingin memprediksi atau mengoptimalkan
- ✓ Ada struktur atau keteraturan yang bisa dimanfaatkan

---

## Pilar 3: Abstraksi (Abstraction)

### Definisi

**Abstraksi** adalah proses mengidentifikasi informasi yang **penting** untuk menyelesaikan masalah, dan **mengabaikan detail yang tidak relevan**. Dengan abstraksi, Anda fokus pada "big picture" daripada detail yang mengaburkan.

### Intuisi Sederhana

Bayangkan Anda melihat **peta kota**. Peta itu adalah **abstraksi** dari kota yang sebenarnya:
- Peta menunjukkan jalan-jalan utama, landmark penting (toko, rumah sakit, sekolah)
- Peta TIDAK menunjukkan setiap pohon, setiap orang, setiap mobil di jalan

Mengapa? Karena untuk keperluan navigasi, detail itu tidak penting. Yang penting adalah struktur jalan dan lokasi landmark.

Jika peta menunjukkan setiap detail kota (setiap rumah, setiap pohon, setiap orang), peta itu akan:
1. Sangat besar (tidak praktis)
2. Sangat kompleks (membingungkan)
3. Lambat untuk di-update

Dengan **abstraksi**, peta menjadi ringkas, clear, dan useful.

### Contoh 1: Abstraksi dalam Desain Produk

**Kasus: Merancang Antarmuka (UI) Aplikasi Belanja Online**

Anda perlu design halaman produk di aplikasi shopping.

**Tanpa Abstraksi** (detail terlalu banyak):
Anda mencoba show:
- Nama produk, harga, foto (semua angle, HD quality)
- Spesifikasi teknis (200 atribut: berat, dimensi, material, supplier info, production date)
- Semua review dari pelanggan (1000+ review dengan setiap detail)
- Proses pengiriman yang detail (setiap step dari warehouse ke pintu rumah)

Hasilnya? **Halaman terlalu panjang, user tidak tahu mau klik apa, bingung, tidak beli.**

**Dengan Abstraksi** (fokus pada essential):
Anda show:
- Foto produk yang nice, nama, harga (eye-catching, clear)
- Spesifikasi yang paling penting (ukuran, warna, material — atribut yang pembeli care tentang)
- Rating bintang + 5 review terbaik (bukan 1000 review)
- Pengiriman: "Gratis ongkir ke Jakarta. Tiba dalam 2-3 hari." (simple)

Hasilnya? **Halaman clean, user tahu apa yang penting, mudah decide, membeli!**

### Contoh 2: Abstraksi dalam Pemodelan Dunia Nyata

**Kasus: Sistem Manajemen Sekolah**

Anda diminta design sistem untuk mencatat data siswa.

**Tanpa Abstraksi** (terlalu detail):
Anda store:
- Nama lengkap (termasuk nama panggilan, nama ibu, nama nenek, dll)
- Alamat (nomor rumah, nomor RT, nomor RW, kode pos, GPS coordinate)
- Data orang tua (lengkap dengan nomor identitas, saldo rekening bank — pribadi!)
- Riwayat medis lengkap (dari bayi, setiap sakit apa, berapa kali minum obat)

Hasilnya? **Database besar, susah di-maintain, privacy issue, banyak data yang tidak berguna untuk sekolah.**

**Dengan Abstraksi** (fokus pada essential):
Anda store:
- Nama, NIS (nomor identitas siswa), Kelas, Tahun Ajaran
- Alamat (cukup kelurahan, tidak perlu detail RT/RW)
- Kontak orang tua (nama, nomor HP — untuk hubungi kalau emergency)
- Informasi medis relevan (alergi, kondisi kronis yang penting diketahui sekolah)

Hasilnya? **Database ringkas, mudah di-maintain, privacy lebih terjaga, fokus pada data yang sekolah butuh.**

### Contoh 3: Abstraksi dalam Kode (Fungsi)

**Kasus: Menulis Fungsi untuk Hitung Total Belanja**

**Tanpa Abstraksi** (kode mentah):
```
total = (harga_item_1 * qty_item_1) + (harga_item_2 * qty_item_2) + ... (repeat 100x)
total_dengan_tax = total * 1.1
total_dengan_diskon = total_dengan_tax - (total_dengan_tax * diskon)
```

Masalah: Sulit dibaca, sulit di-reuse, sulit diperbaiki kalau ada perubahan.

**Dengan Abstraksi** (fungsi):
```python
def calculate_total(items, tax_rate, discount_percent):
    subtotal = sum(item['price'] * item['qty'] for item in items)
    total_with_tax = subtotal * (1 + tax_rate)
    final_total = total_with_tax * (1 - discount_percent)
    return final_total
```

Manfaat:
- Kode lebih ringkas (5 baris vs 100 baris)
- Logika jelas (apa yang dilakukan fungsi)
- Mudah di-reuse (call fungsi ini dari mana saja)
- Mudah di-test dan di-debug

Abstraksi dalam bentuk **fungsi** menyembunyikan detail kompleks di balik nama yang sederhana dan meaningful.

### Kapan Menggunakan Abstraksi?

Gunakan abstraksi ketika:
- ✓ Ada detail yang membingungkan atau tidak relevan
- ✓ Anda ingin fokus pada "big picture"
- ✓ Ada kompleksitas yang bisa disederhanakan dengan layers (abstraction layers)
- ✓ Anda perlu mengkomunikasikan ide dengan jelas (simpel > kompleks)

---

## Pilar 4: Desain Algoritma (Algorithm Design)

### Definisi

**Algoritma** adalah serangkaian langkah-langkah yang jelas, terurut, dan dapat dieksekusi untuk menyelesaikan masalah atau mencapai tujuan. **Desain algoritma** adalah proses merancang langkah-langkah ini.

### Intuisi Sederhana

Bayangkan **resep masakan**. Resep adalah algoritma untuk masak hidangan:

```
RESEP MIE GORENG (Algoritma)

Bahan: mie mentah, telur, kecap, minyak, bawang putih, sayur

Langkah-langkah:
1. Rebus mie hingga setengah matang (jangan lalu) — 3 menit
2. Tiriskan mie, sisihkan
3. Panaskan minyak dalam wajan besar
4. Tumis bawang putih hingga wangi — 30 detik
5. Masukkan mie, aduk rata dengan bumbu — 2 menit
6. Buat lubang di tengah wajan, pecahkan telur, tunggu 1 menit
7. Aduk telur dengan mie rata — 1 menit
8. Tambah kecap, aduk rata — 30 detik
9. Cek rasa, tambah garam kalau perlu
10. Angkat ke piring, sajikan selagi panas

OUTPUT: Mie goreng yang siap dimakan!
```

Setiap langkah harus jelas dan terurut. Jika Anda skip langkah atau reverse urutan, hasilnya tidak akan sama.

### Contoh 1: Algoritma Mundane (Sehari-hari)

**Algoritma: Belajar Efektif untuk Ujian**

```
1. PLAN (2 hari sebelum ujian)
   - Tentukan materi apa saja yang akan diuji
   - Alokasikan waktu untuk setiap bab (prioritas: bab yang sulit lebih banyak waktu)
   
2. REVIEW (2 hari sebelumnya)
   - Baca bab 1, buat catatan singkat
   - Baca bab 2, bandingkan dengan bab 1 (cari hubungan)
   - Ulangi sampai semua bab
   
3. PRACTICE (1 hari sebelum ujian)
   - Kerjakan soal latihan/ujian tahun lalu
   - Jika salah, lihat solusi, pahami mengapa salah
   - Ulangi soal yang salah tadi
   
4. SLEEP & REST (malam hari)
   - Tidur minimal 7 jam (penting untuk memory consolidation)
   - Besok pagi makan sarapan bergizi
   
5. UJIAN (hari ujian)
   - Baca soal dengan teliti (jangan terburu-buru)
   - Kerjakan soal mudah dulu (confidence builder)
   - Kerjakan soal sulit dengan fokus (cegah stuck)
   - Review jawaban jika ada waktu

OUTPUT: Nilai ujian yang memuaskan!
```

Algoritma ini bukan "magic" — tapi menunjukkan langkah-langkah terstruktur yang terbukti efektif.

### Contoh 2: Algoritma untuk Cari Orang di Kerumunan

**Algoritma: Binary Search (untuk cari seseorang)**

Skenario: Anda di mall yang ramai, ingin ketemu teman bernama Budi yang tinggi badannya 170 cm.

**Algoritma Naive (tidak efisien):**
```
1. Start dari entrance mall
2. Lihat setiap orang: "Ini Budi?"
3. Jika ya, selesai
4. Jika tidak, lanjut ke orang berikutnya
5. Ulangi sampai ketemu

Komentar: Bisa memakan waktu 1-2 jam jika mall penuh!
```

**Algoritma Smart (efisien - Binary Search):**
```
1. Tentukan area search: Food court (tengah mall)
2. Tanya ke 5 orang di food court: "Kalian lihat orang tinggi 170cm bernama Budi?"
   - Jika jawab: "Dia sudah lewat ke atas", search hanya lantai atas (kurangi area separuh)
   - Jika jawab: "Aku lihat dia ke bawah", search hanya lantai bawah (kurangi area separuh)
3. Ulangi di area baru yang lebih kecil
4. Setiap iterasi, area search berkurang 50%

Komentar: Hanya perlu ~7 iterasi untuk cari di mall besar! (2^7 = 128)
```

Algoritma kedua jauh lebih efisien karena **desain yang cerdas**!

### Contoh 3: Algoritma Sorting (Mengurutkan Data)

**Problem**: Anda punya daftar 100 nama siswa yang acak, ingin diurutkan secara alfabetis.

**Algoritma 1: Bubble Sort (sederhana tapi lambat)**
```
1. Bandingkan nama ke-1 dengan nama ke-2
   - Jika nama ke-1 > nama ke-2 (abjad), swap
   - Jika nama ke-1 <= nama ke-2, keep
2. Bandingkan nama ke-2 dengan nama ke-3
   - Ulangi swap jika perlu
3. Lanjut sampai akhir list
4. Ulangi proses keseluruhan sampai tidak ada swap yang perlu (list sudah sorted)

Waktu: ~10.000 operasi untuk 100 data
```

**Algoritma 2: Quick Sort (lebih kompleks tapi cepat)**
```
1. Pilih satu nama sebagai "pivot" (misalnya nama di tengah-tengah)
2. Partition: Pisahkan nama-nama menjadi 2 grup:
   - Grup 1: Nama sebelum pivot (abjad lebih kecil)
   - Grup 2: Nama sesudah pivot (abjad lebih besar)
3. Ulangi sort untuk Grup 1 dan Grup 2 secara recursif
4. Selesai: List sudah sorted

Waktu: ~700 operasi untuk 100 data (14x lebih cepat!)
```

**Takeaway**: Algoritma yang berbeda bisa menyelesaikan masalah yang sama dengan efisiensi yang sangat berbeda!

### Kapan Menggunakan Desain Algoritma?

Gunakan desain algoritma ketika:
- ✓ Ada langkah-langkah yang perlu diikuti urutan tertentu
- ✓ Anda ingin proses yang efisien dan dapat direplikasi
- ✓ Ada banyak data atau iterasi yang perlu dikelola
- ✓ Anda ingin mengkomunikasikan cara solving ke orang lain

---

## Bagaimana Empat Pilar Ini Bekerja Bersama?

Mari lihat satu problem dan bagaimana keempat pilar bekerja bersama:

**Problem: "Saya ingin mengorganisir foto-foto liburan saya (1000 foto) supaya mudah dicari"**

| Pilar | Apa yang Dilakukan |
|-------|-------------------|
| **Dekomposisi** | Pecah problem: (1) kumpulkan semua foto, (2) sort by date, (3) kategorisasi by lokasi, (4) buat album per kategori, (5) backup |
| **Pengenalan Pola** | "Saya selalu foto food sebelum makan, photo location setelah sampai di tempat baru" → bisa otomatis sort berdasarkan pola waktu |
| **Abstraksi** | Fokus pada: tanggal, lokasi, tipe foto (food/landscape/people). Abaikan: kamera yang dipakai, setting technical (ISO, aperture, dll) |
| **Algoritma** | Langkah-langkah: (1) Import ke folder. (2) Sort by date. (3) Tag with location/category. (4) Create folders. (5) Backup to cloud. (6) Test akses dari device lain |

**Hasil**: Foto-foto terorganisir, mudah dicari, dan aman!

---

## Ringkasan Sub-Modul 1.2

### Poin-Poin Kunci:

✓ **Dekomposisi** = Pecah masalah besar jadi sub-problem
✓ **Pengenalan Pola** = Identifikasi kesamaan & keteraturan
✓ **Abstraksi** = Fokus pada penting, abaikan detail tidak relevan
✓ **Algoritma** = Desain langkah-langkah terstruktur

✓ **Keempat pilar saling melengkapi** — gunakan bersama untuk solve masalah kompleks

---

## Pertanyaan Reflektif

1. **Sebutkan satu problem dari kehidupan Anda yang bisa di-dekomposisi. Apa sub-problem-nya?**
   - Problem: _________________
   - Sub-problems: _________________, _________________, _________________

2. **Dalam belajar, pattern apa yang Anda lihat? (misalnya: soal yang sering keluar, tipe kesalahan yang sering Anda buat)**
   - Pattern 1: _________________
   - Pattern 2: _________________
   - Bagaimana Anda bisa manfaatkan pattern ini untuk belajar lebih baik? _________________

3. **Berikan contoh abstraksi dari dunia nyata. Apa yang Anda fokuskan? Apa detail yang Anda abaikan?**
   - Contoh: _________________
   - Yang difokuskan: _________________
   - Yang diabaikan: _________________

4. **Desain satu algoritma sederhana untuk problem yang Anda hadapi setiap hari. (misalnya: bangun pagi, persiapan sekolah, dll)**
   - Problem: _________________
   - Langkah-langkah: 
     1. _________________
     2. _________________
     3. _________________

---

## Referensi

1. **ISTE/CSTA (2020).** "Computational Thinking Leadership Toolkit" — Section on 4 Pillars
   - Link: https://csta.acm.org/

2. **Beecher, K. (2017).** "Computational Thinking: A Beginner's Guide" — Chapter 3-6 (dedicated chapter per pilar)
   - Catatan: Sangat accessible dengan contoh yang relatable

3. **MIT 6.0002 (OCW).** Lectures on algorithms and problem-solving
   - Link: https://ocw.mit.edu/courses/6-0002-introduction-to-computational-thinking-and-data-science-fall-2016/

4. **UC Berkeley CS10 (BJC Curriculum).** "Abstraction and Algorithms" Units
   - Link: https://bjc.berkeley.edu/

---

**Selanjutnya:** Buka **Sub-Modul 1.3** untuk melihat **CT dalam praktik** dengan studi kasus real-world!
