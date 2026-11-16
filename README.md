# Naushifa Rasheed — Professional Engineering Portfolio & Admin Portal

A professional, high-performance web portfolio and administration portal built for **Naushifa Rasheed** (Computer Science Engineer | IoT & Robotics Specialist | ECC @ IEEE SB CE Kallooppara).

Includes a compiled **vector PDF resume** matching the certified credentials, dynamic project management, and a **password-secured admin control center** to customize avatar, bio description, projects, work experience, skills, and receive visitor inquiries.

---

## 🌟 Key Highlights & Features

### 1. 💼 Public Portfolio Front-End
- **Modern Responsive Design**: Sleek cyber-engineering aesthetic with dark & light theme modes, glassmorphic cards, smooth scrolling, and mobile drawer.
- **Hero & Avatar Showcase**: Dynamic headline, animated status pill (*"Open to Internships & Engineering Roles"*), animated circular avatar with glowing aura, and quick-download resume button.
- **Attached Resume Viewer**:
  - Direct 1-click download of `naushifa_rasheed_resume.pdf`.
  - In-browser interactive 2-column resume preview matching the uploaded PDF.
  - Print-to-paper / Save-as-PDF styling.
- **Skills Matrix**:
  - Highlighting **ESP32 Microcontrollers**, **Arduino IDE**, and **Arduino** from official credentials.
  - Visual proficiency bars and categorized skill filters (Microcontrollers, Embedded C/C++, Robotics, IoT Protocols).
- **Projects Showcase**:
  - Categorized filters (*Embedded & IoT*, *Robotics*, *Web & Systems*).
  - Detailed modal cards with tech tags, live demo links, and GitHub repository links.
- **Career Timeline**:
  - Dual-column vertical timeline for **Professional Experience** (IEEE SB CE Kallooppara, EVOLVE ROBOTICS LLP, Genzee Technologies LLP) and **Education** (APJ Abdul Kalam Technological University - KTU & College Of Engineering Kallooppara).
- **Interactive Contact Form**:
  - Direct contact information (Phone, Email, LinkedIn, Location).
  - Visitors can submit inquiries that are stored directly in the admin SQLite database.

---

### 2. 🔐 Secured Admin Portal (`/admin`)
- **Password-Secured Authentication**:
  - Uses standard **PBKDF2 with SHA-256 (100,000 iterations)** and cryptographically random unique salts.
  - Secure session token lifecycle with HttpOnly cookies and Bearer tokens.
  - Built-in **Change Password** dialog to update credentials at any time.
- **Avatar & Photo Manager**:
  - Upload custom photographs (JPG, PNG, WebP) with instant preview.
  - Preset avatar switcher (including custom high-res SVG engineer avatar).
- **Bio & Description Editor**:
  - Edit full name, professional headline, affiliation tagline, detailed bio description, location, and status.
- **Projects Management (CRUD)**:
  - Add new projects with title, category, tags, description, GitHub link, demo link, and featured toggle.
  - Edit existing projects.
  - Delete projects.
- **Experience & Education Management (CRUD)**:
  - Add/Edit/Delete work experiences and internships.
  - Add/Edit/Delete degrees and academic institutions.
- **Skills Management (CRUD)**:
  - Add/Edit/Delete skills with proficiency percentages and "Top Skill" homepage highlight.
- **Resume PDF Regeneration**:
  - 1-click button to recompile `naushifa_rasheed_resume.pdf` on the fly.
- **Contact Inquiries Inbox**:
  - Read incoming messages submitted by recruiters and collaborators.

---

## 🚀 How to Run the Application

The application is built using **Python 3 standard library** with zero external pip dependencies.

### 1. Launch the Server
Run the startup script:
```bash
./run.sh
```
Or directly:
```bash
python3 app.py
```

### 2. Access the Application
- **Public Portfolio**: [http://localhost:8000/](http://localhost:8000/) *(or port 8001 if 8000 is occupied)*
- **Secured Admin Portal**: [http://localhost:8000/admin](http://localhost:8000/admin)
- **Direct Resume PDF**: [http://localhost:8000/resume](http://localhost:8000/resume)

---

## 🔑 Default Admin Credentials

| Field | Value |
|---|---|
| **Portal URL** | `http://localhost:8000/admin` |
| **Username** | `admin` |
| **Password** | `adminPassword123!` |

> **Security Note**: Once logged in, click **"🔑 Change Password"** in the sidebar to set your own custom secure password.

---

## 📁 Project Structure

```
portfolio/
├── app.py                     # Python 3 Threading HTTP Server & REST API
├── database.py                # SQLite3 schema, migrations, PBKDF2 auth & helpers
├── generate_resume.py         # Pure Python PDF 1.4 vector resume compiler
├── portfolio.db               # SQLite database with all profile, project & message data
├── run.sh                     # Launch executable script
├── static/
│   ├── css/
│   │   ├── style.css          # Public portfolio styling (dark/light, responsive)
│   │   └── admin.css          # Admin portal styling
│   ├── js/
│   │   ├── main.js            # Frontend interactivity, dynamic API hydration
│   │   └── admin.js           # Admin portal dashboard, CRUD & upload handlers
│   ├── uploads/               # Stored uploaded avatars & project images
│   ├── default-avatar.svg     # Clean vector avatar for Naushifa Rasheed
│   └── naushifa_rasheed_resume.pdf # Compiled vector PDF resume
├── templates/
│   ├── index.html             # Public portfolio HTML
│   └── admin.html             # Secured Admin portal HTML
└── README.md                  # Documentation
```
