# 🏢 Yokohama ILUO Skill Assessment & QA Exam Portal

> **Enterprise Employee Certification & Anti-Cheating Assessment System**  
> Built for Yokohama Off-Highway Tires (OHT) Quality Assurance Department.

---

## 🌟 Key Features

### 1. 🎯 Multi-Level Skill Assessment
- **L Level Certification** (20 Questions - Basic Skill Verification)
- **U Level Certification** (30 Questions - Independent Operational Mastery)
- **O Level Certification** (40 Questions - Advanced Trainer & Expert Standard)
- **Balanced Category Engine**: Automatically balances questions proportionally across **Safety & Environment**, **CI & TPM**, and **QA & Process Technical** topics.
- **Strict Section Isolation**: Candidates receive questions mapped strictly to their assigned Quality Control section (e.g. *Final Finish QA*, *Tire Building QA*, *Tire Curing QA*, *Preparatory QA*, *Solid Tire QA*, *Warehouse QA*, *FID Inspector QA*, *Final Finish RRO & ALT QA*).

### 2. 🛡️ Tab-Switch Anti-Cheating & Proctoring System
- **Real-Time Window Focus Monitoring**: Detects whenever a candidate leaves the exam window or switches tabs.
- **Progressive Security Warnings**: Displays warning modals on Warning 1 & 2.
- **Automated Termination**: Automatically terminates and submits the exam upon the **3rd tab switch** with status set to `Terminated (Tab Switch Violations)`.

### 3. 📁 Automated Word (.docx) Question Importer & Bank Manager
- **Bulk .docx Importer**: Drag-and-drop Word documents (`.docx`) directly in the browser to extract MCQs, options (A, B, C, D), section headers, and category tags.
- **Interactive Question Manager**: Add, edit, delete, or filter questions by Level (`L`, `U`, `O`) and QC Section.
- **Master Question Bank**: Pre-loaded with 712+ verified MCQs parsed from 24 official Yokohama QA Word documents.

### 4. 📊 Real-Time Admin Dashboard & Analytics
- **Live Metric Cards**: Total registered employees, completed assessments, in-progress tests, pass rate %, average score %, and tab-switch security alerts.
- **Visual Analytics**: Dynamic Chart.js breakdown of score distributions and section compliance.
- **Employee Directory & Results Table**: Search candidate records by Employee ID, Name, or Department with instant reset options.

### 5. 📥 Single-Click Excel Report Export
- **Audit-Ready Excel Download**: Generates ISO 45001 & TPM compliant Excel reports containing employee IDs, names, DOJ, section, skill level, U mark, L mark, O mark, total score, percentage, tab switch warnings, and attempt timestamps.

### 6. ✉️ OTP-Based Admin Security
- **Email OTP Authentication**: Secure 6-digit one-time password delivered via Gmail SMTP STARTTLS.
- **30-Second Expiry Window**: Single-use token expiry to protect administrative functions.

### 7. ☁️ Dual-Sync Cloud Database Persistence
- **Local Storage Speed**: Instant zero-lag browser storage for candidates taking exams.
- **Upstash Redis Cloud DB Integration**: Asynchronous dual-sync ensures candidate scores, custom question edits, and admin resets persist permanently across all factory computers and Vercel serverless deployments.

---

## 🛠️ Technology Stack

| Layer | Technologies Used |
| :--- | :--- |
| **Frontend** | HTML5, Vanilla JavaScript (ES6+), Vanilla CSS3 (Custom Design System, Glassmorphism) |
| **Libraries** | [Chart.js](https://www.chartjs.org/) (Data Visualization), [SheetJS XLSX](https://sheetjs.com/) (Excel Export), [Mammoth.js](https://github.com/margvb/mammoth.js) (DOCX Parsing) |
| **Backend** | Node.js, Express.js, Nodemailer (Gmail SMTP STARTTLS) |
| **Database** | Upstash Cloud Redis (Serverless Key-Value Store) |
| **Deployment** | Vercel Serverless Platform |

---

## 📁 Project Structure

```
ILUO MCQ TO Excel sheet/
├── index.html                   # Single-Page Application (SPA) Layout & Router Views
├── app.js                       # Core Portal Engine, Router, Exam Logic & Cloud Sync
├── data.js                      # Compiled Master Employee Directory & Question Bank
├── server.js                    # Express Node.js Server, Gmail SMTP OTP & Cloud API
├── styles.css                   # Premium Responsive CSS Design System
├── vercel.json                  # Production Vercel Deployment Configuration
├── package.json                 # Node.js Dependencies & Run Scripts
├── parse_true_qc_master.py      # Python Parser for 24 Official Word (.docx) Question Files
├── build_data.py                # Data Compiler Script (generates data.js)
├── parsed_true_qc_master.json   # Parsed Master Question Dataset
└── QC question/                 # Folder containing all 24 Official Word Documents (.docx)
```

---

## 🚀 Quick Start (Local Development)

### 1. Prerequisites
- Node.js (v16 or higher)
- Python 3.8+ (for re-parsing Word documents)

### 2. Installation
Clone the repository and install dependencies:
```bash
git clone https://github.com/ReubenGeoffrey/yokohama-iluo-portal.git
cd yokohama-iluo-portal
npm install
```

### 3. Environment Variables Setup
Create a `.env` file in the root directory:
```env
PORT=8080
SESSION_SECRET=yokohama_iluo_qa_secret_2026
ADMIN_EMAIL=reubengeoffrey16@gmail.com

# SMTP Configuration (Gmail)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=
SMTP_PASS=

# Upstash Redis Cloud Database Credentials
UPSTASH_REDIS_REST_URL=
UPSTASH_REDIS_REST_TOKEN=
```

### 4. Run Server Locally
Start the Node.js development server:
```bash
npm start
```
Open **[http://localhost:8080](http://localhost:8080)** in your browser.

---

## 🌐 Deploying to Vercel

1. Push your repository to **GitHub**.
2. Connect your repository on **[Vercel](https://vercel.com/new)**.
3. Select **Other** as the Framework Preset.
4. Add the **Environment Variables** in Vercel Project Settings (`SMTP_USER`, `SMTP_PASS`, `ADMIN_EMAIL`, `UPSTASH_REDIS_REST_URL`, `UPSTASH_REDIS_REST_TOKEN`).
5. Click **Deploy**.

---

## 📄 License & Commercial Rights

Copyright © 2026 Yokohama Off-Highway Tires (OHT) / Reuben Geoffrey.  
All Rights Reserved. Enterprise License & Source Code.
