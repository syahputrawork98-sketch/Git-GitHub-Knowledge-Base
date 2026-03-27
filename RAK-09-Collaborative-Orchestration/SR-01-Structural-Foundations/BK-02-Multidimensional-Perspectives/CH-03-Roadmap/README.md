# 🕒 CH-03: The Roadmap View (Timeline & Milestones)

> **"Melihat masa depan tidak butuh bola kristal, cukup Roadmap yang terukur."**

## 🔗 1. Source Link
- [GitHub: Viewing your project's roadmap](https://docs.github.com/en/issues/planning-and-tracking-with-projects/customizing-your-views/viewing-your-projects-roadmap)
- [GitHub: Filtering your roadmap](https://docs.github.com/en/issues/planning-and-tracking-with-projects/customizing-your-views/filtering-and-sorting-project-items#roadmap-view)

## 📖 2. Penjelasan (The What & The Why)
**Roadmap View** adalah visualisai baris waktu (*Timeline*) dari item di proyek Anda. Tampilan ini menggunakan input dari **Date Fields** (Start Date, Target Date) untuk menampilkan durasi dan urutan pekerjaan.
- **Strategic Visualization**: Melihat proyek dari ketinggian "Helikopter".
- **Dependency Tracking**: Memahami mana fitur yang harus selesai sebelum fitur lain dimulai.
- **Release Coordination**: Mengatur peluncuran produk berdasarkan target waktu yang realistis.

## 🏗️ 3. Architecture Concept: The Construction Schedule
Bayangkan membangun sebuah **Gedung Pencakar Langit**.
- Anda tidak bisa memasang jendela sebelum fondasi selesai. 
- Roadmap menunjukkan urutan tersebut. 
- Senior Engineer menggunakan Roadmap untuk mendeteksi potensi keterlambatan sejak dini dan berkomunikasi dengan manajemen puncak mengenai estimasi waktu penyelesaian yang akurat.

## 📊 4. Visual Layout (The Timeline Strip)
```text
Item A [=========] (Feb 1 - Feb 15)
Item B       [=========] (Feb 10 - Feb 25)
Item C             [===========] (Feb 20 - Mar 10)
                 ▲
                 Today Line
```

## 🧪 5. CLI Labs (Date Field Updates)
Gunakan GitHub CLI untuk mengubah tanggal pengerjaan item agar Roadmap selalu akruat.
```bash
# Update Start Date (Custom Date Field)
gh project item-edit [PROJECT_NUMBER] --id [ITEM_ID] --field-id [DATE_FIELD_ID] --date "2024-03-01"
```

## 🛠️ 6. Under-the-hood Mechanics
Roadmap View merender data berbasis metadata atribut waktu pada setiap item issue/PR. Secara teknis, GitHub menghitung selisih hari antara dua field tanggal (Start/Target) untuk menggambar baris waktu secara dinamis yang diperbarui seketika saat data berubah.

## 🤝 7. Team Impact
Memberikan **Predictability** (Ketelanjuran). Seluruh ekosistem tim, mulai dari Developer hingga Pemasaran (*Marketing*), bisa menyelaraskan jadwal mereka berdasarkan data yang ada di Roadmap proyek pusat.

## 🚑 8. Senior Tip: Milestone Markers
Gunakan fitur **"Milestone Markers"** di dalam Roadmap View. Ini memberikan garis vertikal yang jelas untuk memisahkan fase proyek (misal: "Alpha Release", "Beta Launch", "Gold Master"). Tanpa marker, Roadmap hanyalah deretan batang waktu tanpa tujuan akhir yang jelas.
