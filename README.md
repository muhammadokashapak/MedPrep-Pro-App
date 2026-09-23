# 🩺 MedPrep Pro — Serverless Medical Board Prep Engine & Cloud Testing Hub

<div align="center">

[![React](https://img.shields.io/badge/React-18.3-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev)
[![Vite](https://img.shields.io/badge/Vite-5.2-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev)
[![Neon](https://img.shields.io/badge/Neon-Serverless%20Postgres-00E599?style=for-the-badge&logo=postgresql&logoColor=black)](https://neon.tech)
[![Capacitor](https://img.shields.io/badge/Capacitor-Mobile%20Ready-119EFF?style=for-the-badge&logo=capacitor&logoColor=white)](https://capacitorjs.com)
[![License](https://img.shields.io/badge/License-MIT-emerald?style=for-the-badge)](LICENSE)
[![Author](https://img.shields.io/badge/Author-Muhammad%20Okasha-blueviolet?style=for-the-badge)](https://github.com/muhammadokashapak)

<p align="center">
  <strong>Comprehensive Medical Licensing Examination Platform (USMLE Step 1, FCPS Part 1, PLAB, AMC) Powered by Serverless Cloud Architecture</strong>
</p>

[📖 Overview](#-overview) •
[🏛️ Cloud Architecture](#-cloud-architecture) •
[✨ Core Capabilities](#-core-capabilities) •
[📂 Directory Structure](#-directory-structure) •
[🚀 Quickstart](#-quickstart--configuration) •
[👨‍💻 Author](#-author--connect)

---

</div>

## 📖 Overview

**MedPrep Pro** is an enterprise medical examination preparation platform tailored for physicians preparing for global licensing and residency entry boards including **USMLE Step 1 & 2CK**, **FCPS Part 1**, **PLAB/UKMLA**, and **AMC**.

Featuring a hybrid **Serverless Cloud Architecture** backed by **Neon PostgreSQL** and client-side offline fallbacks via **Capacitor**, the application allows candidates to access tens of thousands of peer-reviewed clinical vignettes, high-yield spaced repetition flashcards, and personalized performance telemetry across all devices.

---

## 🏛️ Cloud Architecture

```mermaid
graph TD
    subgraph Client Layer
        M[Mobile Device - Android/iOS via Capacitor] --> APP[React 18 Single-Page Application]
        W[Desktop Web Browser] --> APP
    end

    subgraph Data Pipeline & Storage
        APP --> CACHE[(Local SQLite / IndexedDB Offline Storage)]
        APP -->|Secure Serverless Queries| NEON[(Neon Serverless PostgreSQL Database)]
        NEON --> QB[Question Bank & Clinical Vignette Repositories]
        NEON --> USR[User Progression, Badges & Historical Telemetry]
    end

    subgraph Intelligence & Scripts
        OCR[Document OCR Ingestion Scripts] --> AI[Gemini / AI Question Formatter]
        AI --> NEON
    end
```

---

## ✨ Core Capabilities

- 🌐 **Global Multi-Board Compatibility:** Modular question banks for FCPS, USMLE, PLAB, and national licensing boards.
- ⚡ **Serverless PostgreSQL Database:** Instant auto-scaling query infrastructure powered by Neon DB with near-zero cold starts.
- 📴 **Dual Offline/Online Operation:** Automatically caches active question sets locally, allowing uninterrupted study on hospital rounds or during travel.
- 🔄 **Spaced Repetition Flashcards (SRS):** Built-in Leitner-style active recall cards for rapid pharmacology drug mechanisms, microbiology algorithms, and clinical pearls.
- 📈 **Telemetry & Diagnostics:** Real-time percentile scoring against candidate cohorts with granular breakdown by clinical organ system.

---

## 📂 Directory Structure

```
MedPrep-Pro-App/
│
├── android/                   # Native Android Studio project & Gradle bindings
├── books/                     # Reference syllabus textbooks & ingestion sources
├── database/                  # SQL schema migrations & seed datasets
├── scripts/                   # Automated MCQ generation & formatting scripts
├── src/                       # React 18 application source code
│   ├── components/            # Exam modals, timers, question cards
│   ├── services/              # Neon database client & offline synchronization
│   ├── App.jsx                # Application root router
│   └── index.css              # Custom medical UI styling
├── capacitor.config.json      # Mobile deployment specifications
├── package.json               # Node.js dependencies
└── README.md                  # VIP Master Architecture Documentation
```

---

## 🚀 Quickstart & Configuration

### 1. Installation
```bash
git clone https://github.com/muhammadokashapak/MedPrep-Pro-App.git
cd MedPrep-Pro-App

npm install
```

### 2. Configure Environment Variables
Create a `.env` file in the project root:
```env
VITE_NEON_DATABASE_URL=postgresql://user:password@ep-sample.us-east-2.aws.neon.tech/medprep?sslmode=require
VITE_GEMINI_API_KEY=your_gemini_api_key_here
```

### 3. Launch Development Server
```bash
npm run dev
```

---

## 👨‍💻 Author & Connect

**Muhammad Okasha**  
*AI & Medical Technology Software Architect*  
- **GitHub:** [@muhammadokashapak](https://github.com/muhammadokashapak)
- **Repository:** [MedPrep-Pro-App](https://github.com/muhammadokashapak/MedPrep-Pro-App)

---

## 📄 License
This project is licensed under the [MIT License](LICENSE).
