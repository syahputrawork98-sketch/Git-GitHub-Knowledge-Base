# CH-01: Time Travel After Loss (The Black Box - Reflog)

> **"Di dalam Git lokal, tidak ada yang benar-benar hilang selama bumi masih berputar."**

## 🔗 1. Source Link
- [Git Internals - Reflog (Official)](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History#_reflog)

## 📖 2. Penjelasan (The What & The Why)
**Reflog (Reference Log)** adalah rekaman lokal dari setiap kali `HEAD` berpindah posisi di komputer Anda. Jika Anda berbuat kesalahan seperti menghapus cabang, melakukan rebase yang berantakan, atau `reset --hard` ke lokasi yang salah, Reflog adalah satu-satunya alat yang bisa membawa Anda kembali ke detik sebelum bencana terjadi. Ia adalah pangkalan data "langkah kaki" Anda di dalam repositori.

## 🏗️ 3. Architecture Concept: The Black Box
Bayangkan sebuah **Kotak Hitam Pesawat** (Flight Data Recorder). Pilot mungkin melakukan manuver yang salah dan menabrak gunung (kehilangan sejarah di DAG). Kotak hitam merekam setiap pergerakan kemudi. Dengan mengintip data tersebut, tim investigasi (Anda) bisa memutar waktu kembali ke menit ke-45 saat pesawat masih berada di jalur yang benar.

## 📊 4. Visual Graph (Mermaid)
Reflog vs Main Branch:

```mermaid
graph TD
    RefLog[Reflog Entry: @{0}] --> HeadNow[Current HEAD]
    RefLog1[Reflog Entry: @{1}] --> HeadPrev[Last Known Good Position]
    RefLog1 -- recovery path --> Restore[Resurrected Commit/Branch]
    style HeadPrev fill:#dfd
```

## 🛠️ 5. Under-the-hood Mechanics
Git menyimpan log ini dalam file teks di `.git/logs/refs/heads/`. Setiap entri mencatat Hash SHA-1 lama dan baru setiap kali cabang tersebut berubah. Reflog bersifat lokal; ia tidak pernah di-push ke GitHub. Reflog biasanya bertahan selama 30 hingga 90 hari sebelum dihapus oleh `git gc`.

## 🧪 6. Practical CLI Lab
Melakukan perjalanan waktu untuk mengembalikan cabang yang terhapus:

```bash
# Skenario: Anda menghapus cabang fitur secara tidak sengaja
# git branch -D feat/vital-feature

# Melihat sejarah pergerakan HEAD
git reflog

# Menemukan Hash commit sebelum cabang dihapus (misal: HEAD@{5})
# git reset --hard HEAD@{5}

# Memulihkan cabang dari titik tersebut
git checkout -b feat/vital-feature-recovered
```

## 🤝 7. Team Impact (Social Governance)
Reflog memberikan **Psikologi Keamanan** kepada pengembang. Dengan mengetahui bahwa mereka bisa memulihkan keadaan darurat secara mandiri, pengembang lebih berani bereksperimen dengan operasi teknis tingkat tinggi (seperti rebase) tanpa takut merusak pekerjaan berhari-hari.

## 🚑 8. The Rescue (Undo Tactics): Undoing the Undo
Jika Anda melakukan `reset --hard` dari reflog tapi ternyata tujuannya salah lagi:
```bash
# Periksa reflog kembali
git reflog

# HEAD@{0} sekarang adalah hasil reset yang salah. 
# HEAD@{1} adalah posisi sebelum Anda melakukan reset yang salah tadi.
git reset --hard HEAD@{1}
```
