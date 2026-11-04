# 🐾 PawMart: The Serverless Odyssey

Platform e-commerce petshop berbasis **Full-Stack Serverless** yang menjual produk hewan: makanan, obat, mainan, dan alat perawatan. Dibuat sebagai proyek perkuliahan.

![Next.js](https://img.shields.io/badge/Next.js_16-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)
![Cloudinary](https://img.shields.io/badge/Cloudinary-3448C5?style=for-the-badge&logo=cloudinary&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel_Edge-000000?style=for-the-badge&logo=vercel&logoColor=white)

## 📦 Kategori Produk

| Kategori | Contoh |
|---|---|
| 🍖 Makanan Hewan | Dry food, wet food, snack |
| 💊 Obat Hewan | Vitamin, obat cacing, antijamur |
| 🧸 Mainan Hewan | Bola, tali, scratcher |
| ✂️ Alat Perawatan | Sisir, shampo, gunting kuku |

## 🏛️ Arsitektur 4 Pilar

| Pilar | Teknologi | Peran |
|---|---|---|
| 1. Presentation & Logic | Next.js 16 (App Router) | UI, Server Components, Route Handlers |
| 2. Data Persistence | Supabase (PostgreSQL) | Database produk, kategori, pesanan, Auth, RLS |
| 3. Media Delivery | Cloudinary CDN | Penyimpanan & optimasi gambar produk |
| 4. Hosting & Edge | Vercel Edge Network | Deployment, CI/CD, distribusi global |

```
Browser ──► Vercel Edge ──► Next.js 16 ──┬──► Supabase (PostgreSQL)
                                          └──► Cloudinary (gambar)
```

## 🚀 Setup Lokal

**Prasyarat:** Node.js ≥ 20, Git, akun Supabase & Cloudinary.

```bash
# 1. Clone repositori
git clone https://github.com/<username>/<nama-repo>.git
cd <nama-repo>

# 2. Install dependensi
npm install

# 3. Siapkan environment variable
cp .env.example .env.local
# Lalu isi semua nilai di .env.local

# 4. Jalankan server development
npm run dev
```

Buka <http://localhost:3000>.

> ⚠️ **Jangan pernah commit `.env.local`.** Hanya `.env.example` yang boleh masuk repositori.

## 🌿 Aturan Git Branch (4 Langkah)

1. **Sinkronisasi:** mulai dari `dev` yang terbaru.
   ```bash
   git checkout dev && git pull origin dev
   ```
2. **Cabang fitur:** buat branch dengan prefix `feature/`, `fix/`, atau `docs/`.
   ```bash
   git checkout -b feature/katalog-produk
   ```
3. **Commit:** gunakan Conventional Commits.
   ```bash
   git commit -m "feat: tambah halaman katalog makanan hewan"
   ```
4. **Pull Request:** push, lalu buat PR ke `dev`. Setelah di-review dan lolos, `dev` digabung ke `main` untuk rilis ke Vercel Production.

> 🚫 Dilarang push langsung ke `main`.

## 🔐 Keamanan

- Semua kredensial disimpan di `.env.local` (di-ignore Git) dan di Vercel Environment Variables.
- `SUPABASE_SERVICE_ROLE_KEY` dan `CLOUDINARY_API_SECRET` hanya boleh dipakai di sisi server.
- Aktifkan Row Level Security (RLS) pada semua tabel Supabase.

## 📄 Lisensi

Proyek perkuliahan. Hak cipta © 2026.