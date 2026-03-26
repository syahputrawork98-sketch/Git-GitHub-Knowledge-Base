# 🕰️ Git & GitHub: The Architecture of Time & Collaboration (Senior Edition)

> **"Git is not a save button; it is a high-precision time machine for code."**

## 📖 Apa itu Version Control? (The What)
**Version Control** (khususnya Git) adalah sistem yang mencatat perubahan pada sebuah berkas atau sekumpulan berkas dari waktu ke waktu sehingga Anda dapat kembali ke versi spesifik di masa lalu. Git tidak sekadar menyimpan perbedaan teks (*diff*), melainkan melestarikan utuhnya struktur file (*Snapshots*) ke dalam basis objek terenkripsi (**DAG - Directed Acyclic Graph**).

Dalam ekosistem *The Learning Matrix*, Git-GitHub-Knowledge-Base mewakili paradigma **History Immutability & Collaboration Governance**: tentang bagaimana menjahit inovasi dari ratusan pengembang menjadi satu kesatuan sejarah yang rapi, bersih, dan dapat dipertanggungjawabkan di level **Senior Engineer**.

---

## 🎯 Mengapa Kita Menggunakan Version Control? (The Why)
Kolaborasi perangkat lunak tanpa tata kelola versi adalah resep bencana arsitektural:
1.  **Single Source of Truth**: Menjamin ada satu versi kode yang menjadi rujukan mutlak (Main Branch).
2.  **Experimentation Safety**: Memungkinkan pengembang bereksperimen di lorong waktu paralel (Branching) tanpa merusak jalur produksi utama.
3.  **Auditability & Traceability**: Menelusuri sejarah perubahan hingga ke akar objek untuk keamanan dan debugging tingkat lanjut.
4.  **Disaster Recovery**: Memulihkan kode dari kesalahan fatal menggunakan mekanisme internal (`reflog`, `fsck`).

---

## 🏗️ Struktur 8-Rak (The Taxonomy)
Pengetahuan di sini disusun untuk membawa Anda dari pemula hingga penguasaan level Senior:

1.  **RAK-01: Anatomy & Landscape** (Sejarah VCS, Filosofi Snapshots vs Deltas, Teori DAG).
2.  **RAK-02: Foundation & Core Rules** (Atomic Commits, Conventional Commits, GPG Signing).
3.  **RAK-03: Evolution & Interfacing** (Advanced Branching, Conflict Resolution, 3-way Merge Internals).
4.  **RAK-04: Core Mechanics & Internals** (Plumbing commands, .git folder internals, Zlib compression).
5.  **RAK-05: Ecosystem & Tooling** (GitHub Advanced: PR Delegation, Actions API, Organization Governance).
6.  **RAK-06: The Underworld** (Interactive Rebase, History Sanitization, Disaster Recovery).
7.  **RAK-07: Specialization** (Git Hooks automation, Git LFS, Submodules vs Subtrees).
8.  **RAK-08: Matrix Intersection** (GitOps, Infrastructure as Code versioning, AI Integration).

---

## 📊 Status Proyek
Detail status per Rak dapat dilihat di [status.md](./status.md).

> [!NOTE]
> Proyek ini mengikuti standar dokumentasi **Git Mastery Gold Standard (GMGS)**.

- `README.md`: Pendahuluan & Visi Senior.
- `docs/`: Dokumentasi pendukung (Governance & Blueprint).
- `RAK-xx/`: Materi granular berdasarkan rak.

## Dokumentasi
- [docs/root-governance.md](./docs/root-governance.md)