# CH-01: Reconciliation Mastery (Pull vs Push)

> **"Git bukan lagi sekadar tempat menyimpan kode; ia adalah pusat kendali operasi infrastruktur."**

Selamat datang di garis depan operasional modern. Di sini kita mempelajari bagaimana Git menggerakkan infrastruktur melalui paradigma GitOps.

## 🧭 Navigasi Detail (Sections)

| Level | Topik | Deskripsi | Link |
| :--- | :--- | :--- | :--- |
| 🔄 **SC-01** | **ArgoCD Logic** | Mekanisme rekonsiliasi pull-based dan self-healing. | **[Jelajahi](./SC-01-ArgoCD-Sync-Logic/)** |
| 🚀 **SC-02** | **GH Actions Deploy** | Strategi deployment push-based menggunakan OIDC. | **[Jelajahi](./SC-02-GitHub-Actions-Deploy/)** |

---

## 🏗️ 1. Architecture Concept: The Mirror
Bayangkan sebuah **Cermin Ajaib**. Apa pun yang Anda gambar atau ubah pada pantulan di dalam cermin (Repositori Git), secara otomatis akan mewujud menjadi nyata di dunia fisik (Infrastruktur/Klaster). Jika seseorang mencoba mengubah dunia fisik secara manual tanpa melalui cermin, cermin tersebut akan "memperbaiki" dunia fisik kembali agar sesuai dengan pantulannya.

## 🧪 2. Quick Lab: Simulasi Drift
Bagaimana mendeteksi perbedaan antara Git dan kenyataan:

```bash
# Mengubah replika aplikasi secara deklaratif
sed -i 's/replicas: 1/replicas: 3/' deployment.yaml
git commit -m "ops: scale up replicas" && git push origin main

# Periksa status rekonsiliasi pada agent GitOps Anda
```

---
*Materi ini merupakan bagian dari **RAK-08: Matrix Intersection**.*
