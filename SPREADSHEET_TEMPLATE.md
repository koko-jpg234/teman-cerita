# Template Spreadsheet "Teman Cerita"
## Google Sheets - 4 Tab Interaktif

---

## TAB 1: Profil Ringkas
**Tujuan:** Ringkasan identitas & pola umum pengguna

| Kolom | Isi | Catatan |
|-------|-----|---------|
| Nama Panggilan | [Input pengguna] | Bisa samaran, tidak perlu nama asli |
| Rentang Usia | 17-22 / 23-26 / 27-30 | Checkbox atau dropdown |
| Tanggal Isi | HARI INI | Gunakan `=TODAY()` |
| Email (Opsional) | — | Hanya untuk reminders pribadi, tidak disimpan di cloud publik |
| **Ringkasan Pola Tidur** | — | (Diisi otomatis dari Tab 2, rata-rata 4 minggu) |
| **Ringkasan Aktivitas Harian** | — | (Diisi otomatis dari Tab 2) |
| **Pemicu Cemas Utama (Top 3)** | — | (Diisi otomatis dari Tab 3) |
| **Kekuatan & Hal Baik** | [Uraian singkat] | Dari LANGKAH 6 analisis pola |
| **Area Perhatian** | [Uraian singkat] | Tanpa label diagnosis |
| **Catatan Profesional** | PILIHAN: Ya / Tidak / Mungkin | Alasan dijelaskan dalam e-book Bagian B |

**Rumus Contoh (Google Sheets):**
```
Rata-rata jam tidur = AVERAGE('Mood & Kebiasaan Harian'!C2:C31)
Total hari aktivitas fisik ≥3 = COUNTIF('Mood & Kebiasaan Harian'!H2:H31,">=3")
```

---

## TAB 2: Mood & Kebiasaan Harian (Template 30 Hari)

**Header:**
| Tanggal | Jam Tidur | Kualitas Tidur (1-5) | Mood (1-5) | Energi (1-5) | Level Cemas (1-5) | Pemicu Utama | Aktivitas Fisik (menit) | Layar (jam) | Catatan Bebas |
|--------|-----------|----------------------|-----------|--------------|-------------------|--------------|------------------------|-------------|---------------|

**Penjelasan Skala:**

- **Jam Tidur** (tulisan jam, misal "7.5"): Target ideal 7-9 jam
- **Kualitas Tidur (1-5):**
  - 1 = Sangat buruk (sering bangun, mimpi buruk)
  - 5 = Sangat baik (nyenyak, segar pagi)
- **Mood (1-5):**
  - 1 = Sangat sedih/murung
  - 5 = Sangat senang/ceria
- **Energi (1-5):**
  - 1 = Sangat lelah, tidak bisa gerak
  - 5 = Penuh energi
- **Level Cemas (1-5):**
  - 1 = Tidak ada cemas
  - 5 = Sangat cemas/panik
- **Pemicu Utama**: Opsional, singkat (misal "deadline", "konflik keluarga", "nggak ada")
- **Aktivitas Fisik (menit)**: Olahraga, jalan kaki, dll
- **Layar (jam)**: Screen time media sosial/TikTok/IG/Games
- **Catatan Bebas**: Apa yang ingin dicatat (opsional)

**Rumus Otomatis (Google Sheets):**

```
ROW 2-31: Tanggal (isi manual atau =SEQUENCE(30,1,TODAY()-29,1))

ROW 33 (Rata-rata Minggu 1):
Jam Tidur = AVERAGE(C2:C8)
Kualitas = AVERAGE(D2:D8)
Mood = AVERAGE(E2:E8)
Energi = AVERAGE(F2:F8)
Cemas = AVERAGE(G2:G8)

ROW 34-36: Minggu 2, 3, 4 (rumus serupa)

ROW 37 (Rata-rata 30 Hari):
Jam Tidur = AVERAGE(C2:C31)
Kualitas = AVERAGE(D2:D31)
Mood = AVERAGE(E2:E31)
Energi = AVERAGE(F2:F31)
Cemas = AVERAGE(G2:G31)
```

**Conditional Formatting (Optional):**
- Jika Mood ≤ 2 → Highlight kuning (untuk awareness)
- Jika Cemas ≥ 4 → Highlight merah muda (perlu strategi coping)
- Jika Energi ≤ 2 → Highlight abu-abu (indikator butuh istirahat)

---

## TAB 3: Pemicu & Strategi Coping

**Header:**
| No | Pemicu Cemas | Frekuensi (kapan biasanya) | Intensitas Saat Ini (1-5) | Respons Saat Ini | Strategi Alternatif | Status Dicoba |
|----|--------------|---------------------------|-------------------------|-----------------|---------------------|----------------|

**Contoh Isi:**

| No | Pemicu Cemas | Frekuensi | Intensitas | Respons Saat Ini | Strategi Alternatif | Status |
|----|--------------|-----------|-----------|-----------------|---------------------|--------|
| 1 | Deadline akademik | Akhir bulan | 4 | Panic, tidur larut malam | Buat to-do, napas 4-7-8 tiap 30 min | Belum dicoba |
| 2 | Konflik pertemanan | Random, sewaktu-waktu | 3 | Overthink, withdraw | Jurnal, telepon teman dekat | Sudah 2x |
| 3 | Khawatir masa depan | Malam hari | 3 | Scroll TikTok/IG lama | Grounding 5-4-3-2-1, tidur jam 11 | Baru 1x |

**Strategi Alternatif (Pilihlah dari daftar ini atau sesuaikan):**

1. **Napas 4-7-8**: Tarik napas 4 detik, tahan 7, hembuskan 8. Ulangi 4x. (2-3 menit)
2. **Grounding 5-4-3-2-1**: 
   - 5 hal yang bisa dilihat
   - 4 hal yang bisa disentuh
   - 3 hal yang bisa didengar
   - 2 hal yang bisa dicium
   - 1 hal yang bisa dicicipi
   (Totalnya 3-5 menit)
3. **Jurnal**: Tulis apa yang terpikirkan, 10 menit bebas.
4. **Gerak tubuh**: Jalan, stretching, push-up, dance 5-15 menit.
5. **Hubungi orang tepercaya**: Telepon/chat teman atau keluarga.
6. **Istirahat terencana**: Set alarm 1-2 jam "me time" tanpa guilt.
7. **Music/Podcast**: Dengarkan musik menenangkan atau podcast favorit.
8. **Atur jadwal**: Buat list prioritas hari itu, jadi tidak overwhelming.

**Kolom "Status Dicoba":**
- Belum dicoba
- Sudah 1x
- Sudah 2-3x
- Rutin (sudah 4+ x)
- Tidak cocok

---

## TAB 4: Rencana 7 Hari

**Header:**
| Hari | Tanggal | Aksi 1 (Pagi/Siang) | Aksi 2 (Sore/Malam) | Catatan/Hambatan | Selesai? |
|-----|---------|-------------------|-------------------|------------------|----------|

**Prinsip Rencana:**
- **Realistis**: 1-2 aksi per hari, tidak lebih.
- **Spesifik**: Bukan "olahraga" tapi "jalan 20 menit jam 6 pagi" atau "yoga youtube 15 menit jam 7 malam".
- **Terukur**: Punya target waktu, durasi jelas.
- **Fleksibel**: Jika tidak bisa, tulis hambatan, jangan hapus.

**Contoh Rencana (dari jawaban pengguna):**

| Hari | Tanggal | Aksi 1 | Aksi 2 | Catatan | Selesai? |
|-----|---------|---------|---------|---------|----------|
| Senin | 8 Oct | Tidur jam 11 malam | Olahraga 15 menit (YouTube yoga) | Sudah biasa | ✓ |
| Selasa | 9 Oct | Jurnal pagi (5 menit) | Chat teman lama | Perlu alarm | ✓ |
| Rabu | 10 Oct | Tidur jam 11 malam | Grounding 5-4-3-2-1 (jika cemas) | Jika perlu saja | ? |
| Kamis | 11 Oct | Makan sarapan sebelum jam 8 | Istirahat 1 jam tanpa HP | Biasanya lupa | ? |
| Jumat | 12 Oct | Tidur jam 11 malam | Video call keluarga | Biasanya jam 8 malam | ? |
| Sabtu | 13 Oct | Olahraga 30 menit | Buat meal prep seminggu | Coba yang baru | ? |
| Minggu | 14 Oct | Tidur jam 11 malam | Refleksi minggu (jurnal) | Siapkan rencana minggu depan | ? |

**Rumus Progress (Optional):**
```
Total Selesai = COUNTIF(F2:F8,"✓")
% Selesai = ROUND((COUNTIF(F2:F8,"✓")/7)*100,0)&"%"
```

---

## Instruksi Setup Google Sheets

1. **Buat file baru** di [sheets.google.com](https://sheets.google.com)
2. **Rename 4 tab** sesuai di atas (klik kanan tab → Rename)
3. **Di Tab 1 (Profil):**
   - Format header tebal, background warna biru muda
   - Freeze row 1
   - Set lebar kolom auto-fit
4. **Di Tab 2 (Mood & Kebiasaan):**
   - Freeze row 1 + kolom A
   - Ganti cell formula untuk tanggal otomatis
   - Tambah conditional formatting
   - Buat summary row minggu & bulan dengan rumus
5. **Di Tab 3 (Pemicu & Strategi):**
   - Buat dropdown "Strategi Alternatif" dari daftar di atas
   - Buat dropdown "Status Dicoba"
   - Sortable by intensity
6. **Di Tab 4 (Rencana 7 Hari):**
   - Format setiap hari punya background warna berbeda (pastels)
   - Centang "Selesai?" bisa jadi checkbox (Insert → Checkbox)
   - Freeze row 1

**Sharing Setting:**
- Buka "Share" → Ubah ke "Anyone with the link can view"
- Jangan biarkan edit (read-only) untuk keamanan data
- Atau buat versi "template" di repository GitHub yang bisa di-download pengguna

---

## Catatan Privasi & Keamanan

✅ **Data ini paling sensitif**, termasuk mood, tidur, dan pola cemas.
- Minta pengguna **tidak menggunakan nama asli** (gunakan nickname/samaran).
- **Jangan simpan di cloud publik** tanpa persetujuan eksplisit.
- Jika pengguna ingin bagikan hasil ke teman/keluarga, hanya bagikan Tab 1 (Profil Ringkas).
- Tarik data secara berkala ke komputer lokal, jangan tinggal di Google Drive selamanya.

---

## Maintenance & Update

- **Setiap bulan:** Buat sheet baru Tab 2 untuk bulan berikutnya (copy rumus)
- **Setiap minggu:** Review Tab 2 summary minggu
- **Setiap 3 bulan:** Update Tab 3 (Pemicu & Strategi) jika ada perubahan
- **Setiap 6 bulan:** Review keseluruhan pola, siapkan rencana baru Tab 4

---

**Disclaimer:**
Spreadsheet ini **alat bantu refleksi diri**, BUKAN alat diagnosis. Jika Anda merasa ada pola yang mengganggu kehidupan sehari-hari, segera hubungi profesional kesehatan mental (psikolog, psikiater, atau layanan konseling kampus/Puskesmas).

**Nomor Bantuan Indonesia:**
- 119 ext. 8 (Layanan Kesehatan Jiwa Kemenkes)
- IGD/Rumah Sakit terdekat
- Konseling kampus (jika mahasiswa)
