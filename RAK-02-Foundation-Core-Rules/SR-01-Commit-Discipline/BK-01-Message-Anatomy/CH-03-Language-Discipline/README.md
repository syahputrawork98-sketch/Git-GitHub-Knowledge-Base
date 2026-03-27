# 🗣️ CH-03: Language Discipline (Imperative Mood)

> **"Katakan pada Git apa yang harus dia lakukan, bukan yang baru saja Anda lakukan."**

## 🔗 1. Source Link
- [How to Write a Git Commit Message: Imperative Mood](https://cbea.ms/git-commit/#imperative)
- [Pro Git: Commit Guidelines](https://git-scm.com/book/en/v2/Distributed-Git-Contributing-to-a-Project#_commit_guidelines)

## 📖 2. Penjelasan (The What & The Why)
Standar emas industri menggunakan **Imperative Mood** (Modus Perintah). Kalimat ini harus melengkapi pernyataan: *"If applied, this commit will [subject]"*.
- **Add** (Benar) vs **Added** (Salah)
- **Fix** (Benar) vs **Fixed** (Salah)
- **Change** (Benar) vs **Changed** (Salah)

Penggunaan bahasa Inggris lebih disarankan di proyek kolaboratif, namun yang paling penting adalah konsistensi di seluruh tim.

## 🏗️ 3. Architecture Concept: The Instruction Manual
Bayangkan Git sebagai **Robot Asisten**. Commit Anda adalah daftar instruksi baginya.
- Robot! **Tambah** fitur X! (**feat: add feature X**)
- Robot! **Hapus** bug Y! (**fix: remove bug Y**)
Jika Anda menulis "Sudah menambahkan fitur X", bagi robot itu hanyalah cerita sejarah, bukan sebuah perintah operasional.

## 📊 4. Comparison Table (Correct vs Incorrect)
| Context | Imperative (Correct) | Past Tense (Incorrect) | Reason |
| :--- | :--- | :--- | :--- |
| Fitur baru | `feat(api): add jwt` | `feat(api): added jwt` | Git treats commits as actions. |
| Bug fix | `fix(auth): redirect user` | `fix(auth): fixed redirection` | Consistency in history logs. |
| Refactor | `refactor: clean loops` | `refactor: cleaned up loops` | Shorter and more direct. |

## 🧪 5. CLI Labs (Standardizing Subject)
Subject tidak boleh diakhiri dengan titik (`.`) dan harus selalu baris kecil (lowercase) untuk konsistensi visual.
```bash
# Contoh subjek yang sangat buruk
git commit -m "Udah benerin bugs login page."

# Contoh subjek senior
git commit -m "fix(login): resolve padding overflow"
```

## 🛠️ 6. Under-the-hood Mechanics
Software Git secara internal menggunakan imperative mood saat menghasilkan commit buatan mesin. Contohnya: `Merge branch 'main'` atau `Revert 'feat: add ui'`. Dengan menyamakan gaya bahasa, sejarah proyek akan terpadu secara utuh.

## 🤝 7. Team Impact
Menggunakan imperative mood dan meniadakan titik membantu pembaca log (`git log --oneline`) memindai informasi dengan kecepatan tinggi (Cognitive Scanning). Semua pesan dimulai dengan kata kerja aksi yang seragam.

## 🚑 8. Senior Tip: Spell Checking
Sangat disarankan menggunakan ekstensi seperti **Code Spell Checker** di VSCode atau git hooks untuk mengecek ejaan. Kesalahan ejaan di sejarah Git tidak bisa dihapus dengan mudah setelah di-push.
