# 🏷️ CH-01: Field Types (Dimensions)

> **"Data adalah inti dari visibilitas. Tanpa field yang tepat, proyek hanyalah daftar buta."**

## 🔗 1. Source Link
- [GitHub: About fields in GitHub Projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects/understanding-fields/about-fields)
- [GitHub: Creating custom fields](https://docs.github.com/en/issues/planning-and-tracking-with-projects/understanding-fields/managing-custom-fields)

## 📖 2. Penjelasan (The What & The Why)
**Field** adalah satuan data terkecil yang bisa ditambahkan ke dalam sebuah item proyek (Issue/PR). GitHub Projects membagi field menjadi dua kategori besar:
1.  **Standard Fields**: Judul, Assignees, Labels, Repository, Milestone.
2.  **Custom Fields**: Field yang kita buat sendiri (Contoh: "Priority", "Start Date", "Estimate").

## 🏗️ 3. Architecture Concept: Multidimensional Cubes
Bayangkan setiap tugas adalah sebuah **Kotak**. 
- Tanpa field, Anda hanya punya tumpukan kotak. 
- Dengan Field, Anda bisa mengiris (*Slice*) tumpukan itu berdasarkan warna (Priority), berat (Estimate), atau tanggal kadaluarsa (Start Date).

## 📊 4. Visual Comparison (Field Types)
| Type | Use Case | Power |
| :--- | :--- | :--- |
| **Single Select** | Status, Priority, Risk | Visual grouping & Kanban columns. |
| **Number** | Estimate, Cost, Points | Summation & Metrics (Insights). |
| **Date** | Deadline, Start Date | Timeline & Roadmap visualization. |
| **Text** | Notes, Client Name | Searchable metadata. |

## 🧪 5. CLI Labs (Managing Fields)
Anda bisa mengelola field menggunakan GitHub CLI (`gh`).
```bash
# Melihat daftar field di sebuah project
gh project field-list [PROJECT_NUMBER] --owner [OWNER]

# Membuat custom field baru (Single Select)
gh project field-create [PROJECT_NUMBER] --owner [OWNER] --name "Impact" --data-type "SINGLE_SELECT"
```

## 🛠️ 6. Under-the-hood Mechanics
Secara internal, GitHub menggunakan schema JSON yang fleksibel untuk menyimpan custom fields di level Organization/User, bukan di level Repository. Ini memungkinkan satu Project untuk menggabungkan data dari banyak repository sekaligus (*Cross-repo visibility*).

## 🤝 7. Team Impact
Mendefinisikan field yang baku menciptakan **Common Language**. Tim tidak lagi berdebat apakah sesuatu itu "PENTING" atau "MENDESAK", karena ada field **Priority** (P1, P2, P3) yang disepakati bersama.

## 🚑 8. Senior Tip: Iterative Evolution
Jangan membuat terlalu banyak field di awal. Mulailah dengan field minimal (Status, Priority, Estimate). Tambahkan field baru hanya jika Anda benar-benar butuh data tersebut untuk ditarik ke dalam laporan atau visualisasi Roadmap.
