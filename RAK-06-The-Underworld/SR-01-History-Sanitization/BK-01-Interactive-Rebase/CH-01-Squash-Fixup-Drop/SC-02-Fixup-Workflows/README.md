# SC-02: Fixup Workflows (Silent History Refinement)

> **"Koreksi tanpa jejak. Jadikan setiap commit terlihat sempurna sejak awal."**

## 🔗 1. Source Link
- [Git Commit --fixup (Official)](https://git-scm.com/docs/git-commit#Documentation/git-commit.txt---fixupltcommitgt)

## 📖 2. Penjelasan (The What & The Why)
**Fixup** adalah varian dari squash yang secara otomatis menggabungkan perubahan ke commit sebelumnya dan secara instan **membuang** pesan commit barunya. Ini sangat berguna untuk perbaikan kecil seperti typo atau formatting yang tidak layak memiliki pesan commit sendiri.

## 🏗️ 3. Architecture Concept: The Invisible Patch
Bayangkan Anda sedang mengecat **Tembok**. Anda selesai mengecat satu sisi (Commit 1). Tiba-tiba Anda melihat ada sedikit noda yang tertinggal. Anda menutupinya dengan cat (Fixup). Hasil akhirnya adalah tembok yang terlihat seperti dicat dengan sempurna sekali jalan, tanpa ada yang tahu Anda sempat melakukan perbaikan kecil.

## 📊 4. Visual Graph (Mermaid)
Otomasi Fixup:

```mermaid
graph LR
    C1[Feature A] --> F1[fixup! Feature A]
    F1 -- autosquash --> C1_New[Feature A: Perfected]
    style C1_New fill:#dfd
```

## 🛠️ 5. Under-the-hood Mechanics
Perintah `git commit --fixup <hash>` membuat commit dengan pesan otomatis `fixup! <original message>`. Saat dijalankan dengan `git rebase -i --autosquash`, Git akan mencari pesan yang berawalan `fixup!` dan secara otomatis memindahkan baris tersebut tepat di bawah commit aslinya dengan instruksi `fixup` yang sudah terisi.

## 🧪 6. Practical CLI Lab
Alur kerja fixup modern:

```bash
# Melakukan perbaikan kecil tanpa mikir pesan
git add .
git commit --fixup HEAD

# Melakukan rebase otomatis (autosquash)
git rebase -i --autosquash HEAD~2
# (Editor akan muncul dengan susunan yang sudah benar, tinggal simpan)
```

## 🤝 7. Team Impact (Social Governance)
Mendorong penggunaan `fixup` berarti mengurangi "kebisingan" dalam notifikasi Pull Request. Reviewer tidak akan terdistraksi oleh rangkaian commit "fixed typo", "fixed again", "real fix this time" yang sering muncul di feed aktivitas.

## 🚑 8. The Rescue (Undo Tactics): Finding the lost fixup
Jika Anda melakukan fixup ke commit yang salah (salah hash):
1. Gunakan `git rebase -i` tanpa autosquash.
2. Pindahkan baris `fixup` secara manual ke posisi yang benar atau ubah kembali menjadi `pick` untuk membatalkan penggabungan otomatisnya.
