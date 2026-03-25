# 🕰️ Git & GitHub: The Architecture of Time & Collaboration

> **"Git is not a save button; it is a high-precision time machine for code."**

## 📖 Apa itu Version Control? (The What)
**Version Control** (khususnya Git) adalah sistem yang mencatat perubahan pada sebuah berkas atau sekumpulan berkas dari waktu ke waktu sehingga Anda dapat kembali ke versi spesifik di masa lalu. Git tidak sekadar menyimpan perbedaan teks (*diff*), melainkan melestarikan utuhnya struktur file (*Snapshots*) ke dalam basis objek terenkripsi (DAG - Directed Acyclic Graph).

Dalam ekosistem *The Learning Matrix*, Git-GitHub-Knowledge-Base mewakili paradigma **History Immutability & Collaboration Governance**: tentang bagaimana menjahit inovasi dari ratusan pengembang menjadi satu kesatuan sejarah yang rapi dan dapat dipertanggungjawabkan.

---

## 🎯 Mengapa Kita Menggunakan Version Control? (The Why)
Kolaborasi perangkat lunak tanpa tata kelola versi adalah resep bencana arsitektural:
1.  **Single Source of Truth**: Menjamin ada satu versi kode yang menjadi rujukan mutlak (Main Branch).
2.  **Experimentation Safety**: Memungkinkan pengembang bereksperimen di lorong waktu paralel (Branching) tanpa merusak jalur produksi utama.
3.  **Traceability**: Mengetahui siapa, kapan, dan mengapa sebuah baris kode diubah (Git Blame/Log).
4.  **Team Governance**: Melalui GitHub Pull Request, kita bisa menanamkan kebijakan gerbang (Code Review) untuk menjaga standar kualitas sebelum kode disatukan.

---

## 🧭 Visi Arsitektural: The Art of Versioning & Merging
Repositori ini membedah Version Control melalui tiga lensa utama:
1. **Git Internals**: Memahami mekanisme penyimpanan objek (Blobs, Trees, Commits, Tags).
2. **Branching Strategies**: Desain alur kerja tim (GitFlow, GitHub Flow, Trunk-based Development).
3. **Collaboration Policy**: Tata kelola ulasan kode, kebijakan *gatekeeper*, dan otomatisasi kait (*Git Hooks*).

## 🧬 Jalur Matriks: Matrix Cross-Path (The What)
Sesuai konstitusi `00-Mapping-Road`, hub ini adalah persilangan:
- **Sumbu-Y**: Semua Bahasa (Version Control Logic).
- **Sumbu-X**: RAK-01 (Language) ➡️ **RAK-07 (Version Control Hub)** ➡️ RAK-08 (Orchestration).

Di sini kita belajar **"Bahwa menulis kode itu mudah, tetapi mengelola riwayat perubahan kode di tengah kepungan kolaborator adalah kedaulatan sesungguhnya"**.

---

## 🏗️ Struktur 8-Rak (The Taxonomy)
1. **RAK-01: Anatomy & Landscape** (VCS History, Centralized vs Distributed, Git Data Model).
2. **RAK-02: Foundation & Core Rules** (Basic Commands: Init, Add, Commit, Status, Log, Diff).
3. **RAK-03: Evolution & Interfacing** (Branching & Merging, 3-way Merge, Conflict Resolution, Remote Repositories).
4. **RAK-04: Core Mechanics & Internals** (Git Objects: Sha-1, Blobs, Trees, Commits; The .git Directory).
5. **RAK-05: Ecosystem & Tooling** (GitHub/GitLab/Bitbucket, GUI Clients, IDE Integrations, CLI Aliases).
6. **RAK-06: The Underworld** (Advanced Git: Rebase vs Merge, Cherry-pick, Stash, Reset vs Revert, Reflog).
7. **RAK-07: Specialization** (Branching Strategies: GitFlow, Trunk-based; Git Hooks, LFS, Submodules).
8. **RAK-08: Matrix Intersection** (The Bridge: How Git automates RAK-08 AI Orchestration through GitOps).

---

## 📊 Status Proyek
Detail status per Rak dapat dilihat di [status.md](./status.md).

> [!NOTE]
> Proyek ini mengikuti standar dokumentasi **Gold Standard PPM V4**.

- `README.md` adalah pendahuluan ini.
- `docs/` berisi dokumentasi pendukung (pemetaan, aturan, referensi).
- `RAK-xx/` berisi semua rak utama.

## Dokumentasi
- [docs/root-governance.md](./docs/root-governance.md)