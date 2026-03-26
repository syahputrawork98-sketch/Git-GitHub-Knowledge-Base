# SC-01: Blob Storage Mechanics (The Immutable Atom)

> **"Di dalam Git, konten adalah identitas. Nama file hanyalah label sementara."**

## 🔗 1. Source Link
- [Git Objects - Blobs](https://git-scm.com/book/en/v2/Git-Internals-Git-Objects)

## 📖 2. Penjelasan (The What & The Why)
**Blob (Binary Large Object)** adalah unit penyimpanan terkecil dalam Git. Ia hanya menyimpan konten mentah dari sebuah file. Git tidak menyimpan nama file, izin akses, atau stempel waktu di dalam objek Blob. Jika Anda memiliki dua file berbeda nama dengan isi yang persis sama, Git hanya akan menyimpan **satu** objek Blob.

## 🏗️ 3. Architecture Concept: The Content Hash
Bayangkan sebuah **Bank Sperma Data**. Setiap sampel (file) diberi label berdasarkan DNA-nya (Hash). Tidak peduli siapa pemiliknya atau apa namanya, jika DNA-nya sama, sampel tersebut dianggap identik dan hanya membutuhkan satu tempat penyimpanan.

## 📊 4. Visual Graph (Mermaid)
Proses Transformasi File ke Blob:

```mermaid
graph LR
    File[File: hello.txt] -- content extraction --> Raw[Raw Data: 'Hello World']
    Raw -- header prepended --> Headered["blob 11\0Hello World"]
    Headered -- Zlib Compression --> Compressed[Deflated Data]
    Compressed -- SHA-1 Calculation --> Hash[Hash: b45ef8...]
```

## 🛠️ 5. Under-the-hood Mechanics
Secara internal, Git membuat header untuk setiap blob: `blob <size>\0`. 
- `blob`: Tipe objek.
- `<size>`: Ukuran konten dalam byte.
- `\0`: Karakter null sebagai pemisah.
Git menggabungkan header ini dengan konten asli, lalu menghitung SHA-1 dari gabungan tersebut untuk menentukan nama objeknya.

## 🧪 6. Practical CLI Lab
Melihat anatomi blob mentah:

```bash
# Membuat blob dan menyimpannya ke database
echo "test content" | git hash-object -w --stdin

# Memverifikasi keberadaan file di .git/objects
# (Gunakan 2 karakter pertama hash sebagai folder)
ls .git/objects/d6/
```

## 🤝 7. Team Impact (Social Governance)
Mekanisme ini membuat Git sangat efisien dalam menangani **Redundansi**. Dalam proyek besar dengan banyak file duplikat (misal: gambar yang sama di folder berbeda), Git LFS atau mekanisme internal Git akan menghemat ruang disk secara signifikan bagi seluruh tim.

## 🚑 8. The Rescue (Undo Tactics): Recovering Orphan Blobs
Jika Anda melakukan `git add` tapi tidak pernah melakukan `commit`, blob tersebut tetap ada di database sebagai "orphan". Anda bisa menemukannya via `git fsck --lost-found` dan melihat isinya untuk memulihkan kode yang belum sempat di-commit.
