# Naushifa Rasheed — Engineering Portfolio & Auto-Synced ATS Resume

A zero-backend, single-page web portfolio and encrypted administration portal built for **Naushifa Rasheed** (Computer Science Engineer | Embedded Systems, IoT & Robotics | ECC @ IEEE SB CE Kallooppara).

Everything is powered by static HTML5/CSS3/JavaScript and a single `portfolio.json` datastore—deployable directly on **GitHub Pages**, **Vercel**, or **Netlify** with live GitHub API cloud sync and an **automatic, print-ready ATS resume builder**.

---

## Key Features

### 1. Automatic Live-Synced Resume & Clean PDF Export
- **100% Data-Driven**: Every detail in the resume—full name, headline, contact links, executive summary, **all technical skills** (grouped by category with top skills highlighted), **all positions & internships**, **all education records**, and **featured engineering projects**—is compiled dynamically from the portfolio state (`portfolio.json` / Admin Portal).
- **Real-Time Updates**: Whenever you add, edit, or delete any profile field, skill, position, education entry, or project in the Admin Portal, the resume updates immediately.
- **Zero-Blank-Page PDF Export**: Clicking **Print / Save as PDF** applies dedicated `@media print` A4 page rules that collapse all non-resume sections from the document flow, producing a crisp, clean 1–2 page ATS-friendly PDF with no extra blank pages.

### 2. Public Cyber-Engineering Portfolio
- **Dark & Light Themes**: Seamless theme toggle saved to `localStorage`.
- **Customizable Hero Avatar & Multi-Photo Grid**: Supports 5 layout arrangements (*Hologram Circle*, *Rounded Tech Card*, *Cyber Hexagon*, *Dual Staggered Grid*, and *2×2 Quad Tech Grid*) plus customizable floating status badges.
- **Filterable Skills & Projects**: Interactive category pills for *Microcontrollers & Hardware*, *Programming Languages*, *IoT & Networking*, *Robotics & Systems*, and *Web & Systems*.
- **Career & Academic Timelines**: Chronological timelines for **Positions & Experience** and **Education**.
- **Contact Form**: Captures visitor inquiries directly into the Admin Portal inbox.

### 3. SSH-Grade Secured Admin Portal (`#admin`)
- **Zero-Plaintext Authentication**: Credentials are verified client-side using the Web Crypto API with **PBKDF2-HMAC-SHA256 (100,000 iterations)** and unique cryptographic salts. Always prompts for credentials upon entering `#admin`.
- **Full CRUD Management**: Edit personal profile & avatar photos (file upload to Base64 or image URL), projects, positions/experience, education records, technical skills, and admin username/password.
- **GitHub Cloud Sync (Fine-Grained PAT)**: Connect a GitHub **Fine-Grained Personal Access Token** (`github_pat_...`) with `Contents: Read and write` permission to push `portfolio.json` updates directly to your repository so changes go live globally.

---

## Project Structure

```text
├── index.html        # Complete Public Portfolio, Live ATS Resume & Admin Portal
├── portfolio.json    # Structured JSON datastore (auth hash, profile, skills, experience, education, projects)
└── README.md         # Documentation
```

---

## Quick Start & Deployment

### Local Preview
Because `index.html` fetches `portfolio.json` over HTTP, serve the directory using any static server:

```bash
python3 -m http.server 8000
```
Then open `http://localhost:8000` in your browser.

### Deploy on GitHub Pages
1. Push `index.html`, `portfolio.json`, and `README.md` to your GitHub repository.
2. Go to **Settings → Pages** and select your branch (e.g., `main` / `/root`).
3. Once live, click **Admin** in the navigation bar (or append `#admin` to your URL), log in, and open the **GitHub Cloud Sync** tab to link your Fine-Grained Personal Access Token (`github_pat_...`) for 1-click live publishing.