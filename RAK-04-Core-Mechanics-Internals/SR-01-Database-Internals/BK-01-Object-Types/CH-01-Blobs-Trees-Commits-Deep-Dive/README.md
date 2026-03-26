# CH-01: The Internal Trinity (Blobs, Trees, & Commits)

> **"Git bukan sekadar pelacak file; ia adalah database objek berbasis konten."**

Selamat datang di pendalaman teknis paling radikal dalam Git. Di sini kita membedah atom-atom yang membangun sejarah Anda.

## 🧭 Navigasi Detail (Sections)

| Level | Topik | Deskripsi | Link |
| :--- | :--- | :--- | :--- |
| 💎 **SC-01** | **Blob Storage** | Mekanisme immutable atom dan kompresi Zlib. | **[Jelajahi](./SC-01-Blob-Storage-Mechanics/)** |
| 🌳 **SC-02** | **Tree Hierarchy** | Logika pemetaan nama file dan struktur pohon direktori. | **[Jelajahi](./SC-02-Tree-Hierarchy-Logic/)** |
| ⚓ **SC-03** | **Commit Graph** | Penjangkaran waktu dan integritas graf (DAG). | **[Jelajahi](./SC-03-Commit-Graph-Integrity/)** |

---

## 🏗️ 1. Architecture Concept: The Content-Addressable Filing Cabinet
Bayangkan sebuah **Lemari Arsip** raksasa. Anda tidak memberi label laci dengan nama file, melainkan dengan **Sidik Jari** (Hash) dari isinya. Jika dua file memiliki isi yang sama, mereka berbagi satu sidik jari yang sama di dalam lemari. Ini membuat Git sangat efisien dalam menyimpan data yang berulang.

## 🧪 2. Quick Lab: Membedah Objek Mentah
Gunakan perintah *Plumbing* untuk mengintip ke dalam jantung Git:

```bash
# Membuat objek blob secara manual
echo "hello world" | git hash-object -w --stdin

# Melihat tipe objek dari hash
git cat-file -t <hash>

# Melihat isi objek secara manusiawi
git cat-file -p <hash>
```

---
*Materi ini merupakan bagian dari **RAK-04: Core Mechanics & Internals**.*
