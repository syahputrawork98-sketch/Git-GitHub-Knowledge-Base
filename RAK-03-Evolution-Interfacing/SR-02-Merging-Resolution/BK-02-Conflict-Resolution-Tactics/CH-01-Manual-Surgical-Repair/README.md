# CH-01: Manual Conflict Surgical Repair (The Anatomy of Disagreement)

> **"Konflik bukanlah bencana; ia adalah permintaan klarifikasi dari Git."**

## 🔗 1. Source Link
- [Resolving Merge Conflicts (Official)](https://git-scm.com/book/en/v2/Git-Tools-Advanced-Merging#_basic_merge_conflicts)

## 📖 2. Penjelasan (The What & The Why)
**Merge Conflict** terjadi ketika dua cabang mengubah baris yang sama di file yang sama dengan cara yang berbeda, sehingga Git tidak bisa memutuskan secara otomatis mana yang harus diambil. Anda harus melakukan "pembedahan manual" untuk memilih, menggabungkan, atau menulis ulang baris tersebut agar sejarah bisa berlanjut.

## 🏗️ 3. Architecture Concept: The Surgery
Bayangkan Anda adalah seorang **Ahli Bedah**. Dua donor memberikan jaringan (kode) untuk area yang sama. Anda harus menjahit baris-baris tersebut secara hati-hati agar tubuh (aplikasi) tidak menolaknya. Anda membersihkan "luka" (marker konflik) dan merapikan jahitannya.

## 📊 4. Visual Graph (Mermaid)
Penanda Konflik Internal:

```text
<<<<<<< HEAD (Current Branch)
Isi baris dari cabang Anda
=======
Isi baris dari cabang yang digabung
>>>>>>> incoming-branch
```

## 🛠️ 5. Under-the-hood Mechanics: The 3 Stages of Index
Saat terjadi konflik, pangkalan data objek Git sebenarnya menyimpan TIGA versi file sekaligus di dalam *Index*:
1. **Stage 1**: Leluhur bersama (Common Ancestor).
2. **Stage 2**: Versi lokal Anda (`ours`).
3. **Stage 3**: Versi yang masuk (`theirs`).
Anda bertugas menyatukan ketiganya menjadi versi final.

## 🧪 6. Practical CLI Lab
Strategi cepat memilih sisi dalam konflik massal:

```bash
# Mengambil versi KITA (ours) untuk seluruh file yang konflik
git checkout --ours <file_name>

# Mengambil versi MEREKA (theirs) untuk seluruh file yang konflik
git checkout --theirs <file_name>

# Menandai konflik telah selesai dibedah
git add <file_name>
```

## 🤝 7. Team Impact (Social Governance)
Konflik besar sering kali merupakan tanda dari **Communication Breakdown**. Jika dua orang mengerjakan modul yang sama pada saat yang sama, tim harus mempertimbangkan koordinasi yang lebih baik atau dekomposisi modul yang lebih kecil.

## 🚑 8. The Rescue (Undo Tactics): Reset to Clean State
Jika Anda merasa kacau saat menyelesaikan puluhan konflik dan ingin menyerah untuk istirahat sejenak:
```bash
# Membatalkan seluruh proses merge dan kembali ke commit terakhir yang stabil
git merge --abort
```
