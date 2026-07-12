# Product Requirements Document (PRD)
## Portfolio Website — Miftahul Amri

**Versi:** 1.0
**Tanggal:** Juli 2026
**Author:** Miftahul Amri
**Status:** Draft — menunggu finalisasi visual reference dari Google Stitch

---

## 1. Latar Belakang & Tujuan

Portofolio versi lama menggunakan konsep terminal/CLI-first yang kuat secara identitas developer, tapi kurang ramah untuk audiens non-teknis (calon client instansi, sekolah, organisasi). Redesain ini bertujuan:

- Membuat landing page utama yang profesional, hangat, dan mudah dipahami siapa pun
- Menonjolkan project yang sudah dikerjakan, khususnya project untuk instansi/organisasi
- Mempertahankan identitas developer melalui fitur terminal, tapi sebagai **fitur tambahan (easter egg)**, bukan tampilan utama
- Menambahkan micro-interaction unik (hover photo-swap) sebagai signature experience

**Referensi desain:** Design system "Dicoding Asah" (warna, tipografi, shape) dikombinasikan dengan layout/komposisi custom hasil eksplorasi Google Stitch (asymmetric hero, elemen dekoratif, overlap illustration).

---

## 2. Target Audiens

| Audiens | Kebutuhan |
|---|---|
| Calon client (sekolah, ormawa, instansi) | Percaya cepat, lihat bukti kerja nyata, gampang kontak |
| Recruiter/HR teknis | Lihat tech stack, project kompleksitas, cara kerja |
| Sesama developer/komunitas | Apresiasi detail teknis, easter egg terminal |
| Dosen/penilai kompetisi (LIDM, dll) | Kredibilitas akademik & portofolio project |

---

## 3. Struktur Halaman & Konten

### 3.1 Navbar
- Logo/nama: "Miftahul Amri"
- Nav links: About, Education, Experience, Skills, Contact
- Icon toggle `>_` kecil di kanan navbar → membuka terminal overlay
- CTA pill button: "Let's Talk" / "Hire Me"

### 3.2 Hero Section
- Badge: "Available for freelance work"
- Headline 2 baris (EB Garamond): *"Built different."* / *"Shipped faster."* (baris kedua warna aksen oranye, italic)
- Subheading: bio singkat — mahasiswa Pendidikan Teknik Informatika UMS, Next.js developer, fokus digital product untuk sekolah & organisasi
- CTA: "View Projects" (primary) + "Contact Me" (secondary/outline)
- **Fitur unik — Hover Photo Swap:** foto ilustrasi (avatar flat-style) sebagai default state; saat di-hover, transisi crossfade ke foto asli. Perlu 2 aset gambar dengan dimensi & crop identik
- Komposisi asimetris: ilustrasi sedikit overlap ke area teks, elemen dekoratif (dotted line, badge miring), sesuai eksplorasi Stitch

### 3.3 Education Journey
Vertical list/rail, 3 entri:

| Institusi | Jenjang | Tahun |
|---|---|---|
| MTs Arafah Bitung | Junior High School | 2016–2019 |
| MAs Ibnu Taimiyah Bogor | Senior High School | 2019–2022 |
| Universitas Muhammadiyah Surakarta — Pendidikan Teknik Informatika | S1 | 2023–Sekarang (badge "Ongoing") |

### 3.4 Experience & Activities
Card list, campur pengalaman kerja + project:

1. **IT Helpdesk Staff (Intern)** — DSTI UMS — 2023–Sekarang
   Menangani SSO, email, dan akun portal mahasiswa. Sedang dikonversi menjadi kredit mata kuliah MBKM.
2. **Website Developer** — MI Muhammadiyah Gambiranom ([mimgambiranom.site](https://mimgambiranom.site))
   Full school website dengan CMS admin panel — Next.js, Prisma, PostgreSQL, Vercel.
3. **Website Developer** — IMM Siti Munjiyah FKIP UMS ([imm-simun.ums.ac.id](https://imm-simun.ums.ac.id))
   Website organisasi kemahasiswaan.

Setiap card: role, organisasi, rentang tahun, deskripsi singkat, link "Visit Site" bila tersedia.

> **Catatan:** Bisa ditambah project personal (RoboMind, SETARA, Our Moments) di section terpisah "Side Projects" jika ingin menonjolkan sisi eksperimen teknis — opsional, perlu konfirmasi apakah mau ditampilkan di halaman utama atau di halaman `/projects` terpisah.

### 3.5 Skills / Tech Stack
Grouped badge pills:

- **Languages:** JavaScript, HTML, CSS
- **Frameworks:** Next.js, React, Vite
- **Database:** MySQL, PostgreSQL
- **Tools & Infra:** Docker, VS Code, Git
- **AI Tools:** Hermes Agent, OpenCode CLI, AI-assisted workflow
- **Design:** Canva

### 3.6 Certifications
Grid 5 kartu sertifikat (placeholder — perlu diisi data asli):

| # | Nama Sertifikat | Issuer | Tahun |
|---|---|---|---|
| 1 | *TBD* | *TBD* | *TBD* |
| 2 | *TBD* | *TBD* | *TBD* |
| 3 | *TBD* | *TBD* | *TBD* |
| 4 | *TBD* | *TBD* | *TBD* |
| 5 | *TBD* | *TBD* | *TBD* |

> Karena mayoritas skill didapat otodidak, bisa dipertimbangkan menambahkan section kecil "Self-Taught & Continuous Learning" sebagai pelengkap narasi, bukan cuma sertifikat formal.

### 3.7 Contact / Footer
- Background dark navy (#101828)
- Heading ajakan kontak
- Link: Email, GitHub, Instagram
- Hint kecil: "Psst — coba icon terminal di navbar"
- Copyright line

### 3.8 Terminal Easter Egg (Overlay)
- Trigger: klik icon `>_` di navbar, atau shortcut keyboard (`` ` `` atau `Cmd/Ctrl+K`)
- Muncul sebagai modal/overlay di atas halaman (bukan halaman terpisah)
- Command tersedia minimal: `/help`, `/profile`, `/projects`, `/experience`, `/skills`, `/contact`, `/clear`
- Style tetap konsisten dark terminal seperti versi lama, tapi frame-nya lebih playful (rounded corner, soft shadow) menyesuaikan tone baru yang lebih hangat

---

## 4. Fitur Fungsional

| Fitur | Prioritas | Keterangan |
|---|---|---|
| Landing page responsif (desktop, tablet, mobile) | Must-have | Grid collapse ke 1 kolom di mobile |
| Hover photo-swap di hero | Must-have | Signature interaction |
| Terminal overlay dengan command list | Must-have | Dipertahankan dari versi lama |
| Smooth scroll & scroll-triggered animation | Should-have | Fade-in/slide-up per section saat scroll |
| Dark mode toggle | Nice-to-have | Opsional, karena base sudah cream/warm |
| Contact form (bukan cuma mailto link) | Should-have | Perlu backend/email service kalau mau functional |
| CMS/admin untuk update project & sertifikat tanpa redeploy | Nice-to-have | Bisa pakai lightweight CMS atau hardcode + JSON config dulu |

---

## 5. Tech Stack

Konsisten dengan stack yang biasa digunakan (Next.js + Prisma + Vercel):

| Layer | Teknologi | Alasan |
|---|---|---|
| Framework | Next.js (App Router) | SEO-friendly, familiar, cocok untuk static + dynamic content |
| Styling | Tailwind CSS | Cepat implementasi design token dari Asah (warna, spacing, rounded) |
| Animasi | Framer Motion | Untuk hover photo-swap, scroll animation, terminal overlay transition |
| Font | EB Garamond + Inter (Google Fonts / self-hosted) | Sesuai design system Asah |
| Data project/sertifikat | JSON/Markdown config lokal di awal → bisa migrasi ke DB nanti | Simple, gampang di-maintain sendiri |
| Database (opsional, jika ada contact form/CMS) | PostgreSQL + Prisma | Konsisten dengan stack project lain |
| Hosting | Vercel | Sudah familiar, custom domain sudah ada (`miftahsh.my.id`) |
| Icon | Lucide Icons | Ringan, konsisten dengan estetika flat |
| Ilustrasi | Custom flat illustration (dibuat via AI image gen / Canva, disesuaikan warna brand) | Konsisten dengan gaya Asah |

---

## 6. Non-Functional Requirements

- **Performance:** Lighthouse score target 90+ di semua kategori (terutama karena illustration-heavy, perlu optimasi image — pakai `next/image`, format WebP/AVIF)
- **Accessibility:** Kontras warna cream-navy sudah cukup baik, tapi perlu dicek ulang untuk teks abu-abu (#636262) di atas cream — pastikan AA compliant
- **SEO:** Meta tags, Open Graph image, sitemap.xml
- **Responsiveness:** Mobile-first breakpoint testing, terutama untuk komposisi hero yang asimetris (perlu simplifikasi di mobile)

---

## 7. Hal yang Masih Perlu Dikonfirmasi

1. Visual reference final dari Google Stitch (menunggu lampiran)
2. Apakah project personal (RoboMind, SETARA, dll) masuk halaman utama atau halaman terpisah
3. Data 5 sertifikasi asli (nama, issuer, tahun) — saat ini masih placeholder
4. Apakah contact form perlu functional (kirim email) atau cukup link mailto/WhatsApp
5. Aset foto asli untuk hover-swap (dimensi & crop yang konsisten dengan ilustrasi)

---

## 8. Milestone (Usulan)

| Fase | Scope | Estimasi |
|---|---|---|
| 1 | Setup project, design token (Tailwind config dari Asah), font | 1-2 hari |
| 2 | Build Hero + Navbar + hover photo-swap | 2-3 hari |
| 3 | Build Education, Experience, Skills, Certifications section | 3-4 hari |
| 4 | Build Terminal overlay (reuse logic dari versi lama) | 2 hari |
| 5 | Responsive pass + animasi scroll | 2 hari |
| 6 | Testing, SEO, deploy ke Vercel | 1 hari |
