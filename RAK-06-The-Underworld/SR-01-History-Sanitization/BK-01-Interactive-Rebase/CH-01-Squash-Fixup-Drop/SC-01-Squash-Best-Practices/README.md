# SC-01: Squash Best Practices (The Art of Compression)

> **"Koleksi commit Anda adalah narasi. Jangan biarkan draf kasar mengganggu pembaca."**

## 🔗 1. Source Link
- [Git Rebase - Interactive (Official)](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History#_interactive_rebasing)

## 📖 2. Penjelasan (The What & The Why)
**Squashing** adalah proses menggabungkan beberapa commit menjadi satu. Ini digunakan untuk membersihkan sejarah fitur sebelum digabungkan ke cabang utama. Tujuannya adalah untuk mengubah "bagaimana saya bekerja" menjadi "apa yang saya kerjakan".

## 🏗️ 3. Architecture Concept: The Editor's Desk
Bayangkan Anda sedang menulis **Novel**. Anda menulis bab 1, lalu menemukan typo (commit 2), lalu mengubah nama karakter (commit 3). Sebelum mengirimkannya ke penerbit, Anda menggabungkan semuanya menjadi "Bab 1: Selesai". Penerbit tidak perlu tahu berapa kali Anda salah ketik.

## 📊 4. Visual Graph (Mermaid)
Workflow Penyatuan Fitur:

```mermaid
graph LR
    W1[Work 1] --> W2[Typo]
    W2 --> W3[Work 2]
    subgraph Development
        W1, W2, W3
    end
    W1, W2, W3 -- Squash --> Final[Clean Feature Commit]
    style Final fill:#dfd
```

## 🛠️ 5. Under-the-hood Mechanics
Saat Anda memilih `squash` dalam list rebase, Git mengambil snapshot dari commit tersebut, menggabungkannya dengan commit sebelumnya, dan membuka editor untuk membiarkan Anda menulis pesan commit baru yang mencakup seluruh perubahan tersebut.

## 🧪 6. Practical CLI Lab
Mensimulasikan squash:

```bash
# Melakukan rebase interaktif
git rebase -i HEAD~3

# Ganti 'pick' menjadi 'squash' (atau 's') pada baris kedua dan ketiga
# Simpan dan tulis pesan commit final
```

## 🤝 7. Team Impact (Social Governance)
Sejarah yang di-squash sangat membantu dalam **Bisecting** (mencari bug). Jika satu commit berisi satu fitur utuh yang lulus tes, akan jauh lebih mudah untuk mengidentifikasi kapan sebuah bug diperkenalkan daripada mencari di antara ribuan commit kecil yang "setengah jadi".

## 🚑 8. The Rescue (Undo Tactics): Undoing a Squash
Jika Anda salah meng-squash dan kehilangan detail pesan yang penting:
```bash
# Gunakan reflog untuk kembali ke posisi sebelum rebase
git reflog
git reset --hard HEAD@{n}
```
