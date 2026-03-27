# 📏 CH-02: Structural Formatting (50/72 Rule)

> **"Pesan commit harus seramping koran dan sejelas buku."**

## 🔗 1. Source Link
- [Linus Torvalds on Commit Messages](https://github.com/torvalds/linux/pull/17#issuecomment-5654674)
- [How to Write a Git Commit Message](https://cbea.ms/git-commit/)

## 📖 2. Penjelasan (The What & The Why)
Struktur pesan commit bukan sekadar soal gaya. Konsistensi dalam baris baru (newlines) dan panjang karakter memastikan pesan bisa ditampilkan dengan benar di CLI (`git log`), GitHub UI, dan IDE.
- **Header**: Maksimal 50 karakter (agar tidak terpotong di UI).
- **Body**: Maksimal 72 karakter per baris (agar tidak melebar saat diindentasi oleh Git).
- **Separator**: Baris kosong antara Header, Body, dan Footer.

## 🏗️ 3. Architecture Concept: The Three-Tier Building
Bayangkan sebuah kurikulum belajar:
1.  **Header**: Judul Bab (Singkat & Padat).
2.  **Body**: Penjelasan Isi Bab (Detail & Alasan).
3.  **Footer**: Referensi & Tugas (Metadata tambahan).

## 📊 4. Visual Layout
```text
feat(auth): add login with google oauth2       <-- 50 chars max
                                               <-- blank line
This feature allows users to sign in using their google account.
We use passport.js for handling the oauth2 flow with identity 
provider.                                      <-- 72 chars max per line
                                               <-- blank line
Closes #123                                    <-- Footer (Metadata)
```

## 🧪 5. CLI Labs (Multi-line Commits)
Jangan gunakan `-m` berulang kali. Gunakan editor `git commit` agar lebih rapi.
```bash
# Buka editor default (vim/nano/vscode)
git commit

# Atau gunakan pesan multi-line via terminal
git commit -m "feat(ui): add dark mode toggle" \
           -m "The toggle allows users to switch between light and dark themes. Preferences are saved in local storage." \
           -m "Closes #456"
```

## 🛠️ 6. Under-the-hood Mechanics
Git secara internal akan mengindentasi pesan commit sebanyak 4 spasi saat menjalankan `git log`. Jika line length Anda melebihi 72-80 karakter, teks akan berantakan dan sulit dibaca di terminal berukuran standar (80 kolom).

## 🤝 7. Team Impact
Struktur yang konsisten memudahkan rekan kerja melakukan pencarian (`git grep`) di dalam pesan commit tanpa harus berurusan dengan format yang tidak menentu.

## 🚑 8. Senior Tip: The Body's Purpose
Gunakan body untuk menjelaskan **MENGAPA** perubahan dibuat, bukan **BAGAIMANA**. Kode itu sendiri sudah menjelaskan "bagaimana" perubahannya, tetapi sejarah Git harus menyimpan alasan di balik keputusan tersebut.
