# kursusaipercuma

Static marketing site for **Kursus Artificial Intelligence (AI) Percuma Sabah** — a free
basic-AI course run for the Malaysian public, primarily in Sabah.

- Live site: <https://kursusaipercuma.site/>
- Trainer profile: <https://kursusaipercuma.site/trainer.html>
- Repo: `edthix/kursusaipercuma` (public)
- Trainer: Ts.Gs. Mahadthir Hj. Asbollah, Kota Kinabalu, Sabah

## What the site is

A two-page, fully static promotional site. No backend, no database, no build step.

| Page | File | Purpose |
| --- | --- | --- |
| Laman Utama (home) | `index.html` | Hero, target audiences, syllabus, why-it-matters, agency list, photo gallery, media coverage, contact |
| Trainer | `trainer.html` | Trainer bio, work history, education, expertise, certifications, contact |

Content on `index.html`:

- **Hero** — "Kursus asas AI untuk rakyat Malaysia", 1,000+ peserta dilatih, CTA to register
  (`wa.me/60105836583`) and to the course section.
- **Siapa yang Sesuai** — Guru & Pendidik, Pelajar, Penjawat Awam, Usahawan, Umum.
- **Apa yang Akan Dipelajari** — Pengenalan kepada AI, Alatan AI Praktikal, Penggunaan AI dalam
  Kerja, Tips Produktiviti.
- **Mengapa Kursus Ini Penting?** — konteks Sabah, literasi AI, sokongan guru, agensi kerajaan,
  peluang kerjaya.
- **Agensi yang Telah Menjalankan Kursus** — 13 agency cards (KKRS, Yayasan Sabah, Pejabat Hasil
  Bumi Sabah, Kementerian Kesihatan, Sediafiat, UMS, Lembaga Pertubuhan Peladang, Dewan Usahawan
  Melayu Sabah, Taman-taman Sabah, Pejabat Daerah Putatan, IKSNita, Perpustakaan Tanjung Aru,
  Pejabat Daerah Nabawan) with course type and year.
- **Galeri Aktiviti Mengikut Agensi** — 11 per-agency photo carousels.
- **Liputan Media** — 13 press items with outlet, headline and date (Jun 2025 – Sep 2026).
- **Hubungi Kami** — phone, WhatsApp, location.

`trainer.html` carries the trainer's profile (`trainer-profile.png`), stats (25+ tahun
pengalaman, 1000+ guru dilatih, 10+ agensi), work history at Yayasan Sabah Group /
Prestariang Technology / Sabah Net, education (UPM), expertise areas and professional
certifications.

## Stack

- Plain HTML5, hand-written CSS inlined in each page, small vanilla JS (gallery carousels,
  image lightbox, keyboard/ESC close).
- No framework, no bundler, no package manager, no server-side code.
- Analytics: Google Analytics (`gtag.js`, measurement ID `G-R5Q51EJG7B`) on both pages.
- All imagery served from the repo: `img/` (4 activity photos) and `trainer-profile.png`.

## Deployment

Published by **GitHub Pages** directly from `main`:

| Setting | Value |
| --- | --- |
| Source | `main`, path `/` |
| Custom domain | `kursusaipercuma.site` (from `CNAME`) |
| HTTPS enforced | yes |
| Custom 404 | no |

DNS is Namecheap; the apex `kursusaipercuma.site` points at GitHub's four Pages A records
(`185.199.108.109/110/111.153`) and `www` is a CNAME to `edthix.github.io`.

**Publishing an edit:** commit to `main` (or open a PR). Pages rebuilds automatically; changes
appear within a minute or two. There is no manual deploy step.

> The repo must stay **public**. On a free GitHub plan a private repo disables Pages, and a
> disabled Pages site cannot provision a certificate for the custom domain — the site then
> serves HTTP only and the browser shows a `*.github.io` certificate name mismatch.

## Local preview

Any static file server works. From the repo root:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/
```

`index.html` and `trainer.html` are self-contained; opening them directly from disk also works,
though relative asset paths resolve best through the server above.

## Updating content

- **Text** — edit the HTML directly. Page copy is Malay; keep the tone consistent.
- **Agency list / stats / media items** — add a card block in the relevant section of
  `index.html`; the "10+" and "1,000+" figures in the hero/why-it-matters sections are plain
  text and must be bumped by hand when they change.
- **Photos** — drop the file in `img/` and add an `<img>` to the matching agency's gallery
  section.
- **SEO/social metadata** — each page has its own `title`, `description`, `keywords`,
  `og:*`/`twitter:*` and JSON-LD blocks near the top; canonical URLs are
  `https://kursusaipercuma.site/` and `https://kursusaipercuma.site/trainer.html`.

## Contact

- Phone / WhatsApp: +6010 583 6583
- Email: mahadthir@hotmail.com
- Location: Kota Kinabalu, Sabah, Malaysia
