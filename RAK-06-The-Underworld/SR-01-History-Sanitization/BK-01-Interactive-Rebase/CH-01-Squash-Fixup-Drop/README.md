# CH-01: History Sculpting (Squash, Fixup, & Drop)

> **"Jangan biarkan sejarah Anda kotor oleh commit 'typo' atau 'test'. Pahatlah sejarah yang bercerita."**

Selamat datang di bengkel pemahatan sejarah. Di sini kita menggunakan alat bedah interaktif untuk menciptakan narasi commit yang profesional.

## 🧭 Navigasi Detail (Sections)

| Level | Topik | Deskripsi | Link |
| :--- | :--- | :--- | :--- |
| 💎 **SC-01** | **Squash Best Practices** | Seni kompresi commit untuk efisiensi narasi. | **[Jelajahi](./SC-01-Squash-Best-Practices/)** |
| 🛠️ **SC-02** | **Fixup Workflows** | Otomasi perbaikan senyap menggunakan `--autosquash`. | **[Jelajahi](./SC-02-Fixup-Workflows/)** |

---

## 🏗️ 1. Architecture Concept: The Time Sculptor
Bayangkan Anda adalah seorang **Pematung Waktu**. Saat bekerja, Anda membuat banyak potongan kasar dan sampah di sekitar patung Anda (commit kecil/test). Sebelum memamerkan patung tersebut di galeri (Push to Main), Anda memahat dan membersihkan sampah-sampah tersebut, sehingga yang tersisa hanyalah hasil karya yang halus dan bermakna.

## 🧪 2. Quick Lab: Merapikan 3 Commit Terakhir
Operasi dasar pembedahan sejarah:

```bash
# Memulai rebase interaktif
git rebase -i HEAD~3

# Ganti 'pick' menjadi 's' (squash) atau 'f' (fixup) pada editor teks yang muncul.
```

---
*Materi ini merupakan bagian dari **RAK-06: The Underworld**.*
