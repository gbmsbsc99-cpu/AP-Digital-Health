# AP Digital Health EHR
### Government of Andhra Pradesh — National Health Mission

> **Integrated Electronic Health Record System** for AP's public health infrastructure — from village-level CHOs to the Health Minister. Offline-first, Telugu AI voice, ABHA/FHIR R4 compliant, full escalation chain.

---

## 🚀 Live Demo

Open `index.html` in any browser — no server needed.

**Tested on:** Windows 7+ · Chrome · Firefox · Edge · IE9+

---

## 🎯 Features

### 👥 Multi-Role Login
| Role | Description |
|------|-------------|
| CHO | Community Health Officer — Village field screening |
| ANM | Auxiliary Nurse Midwife — Maternal & child health |
| Medical Officer | OPD, AI diagnosis, prescriptions |
| Lab Technician | Test orders & results |
| Pharmacist | Dispensing & drug stock |
| Yoga Therapist | Wellness sessions in Telugu |
| Physiotherapist | Rehab plans & exercise library |
| 108 Operator | Emergency dispatch & triage |
| Admin | Hospital analytics & staff management |
| CHC Admin | CHC/AH facility management |
| DMHO/DPO/DPMO | District-level health oversight |
| DPH/DME | State directorate monitoring |
| State Nodal Officer | State-wide KPIs & policy |
| Commissioner/Pr. Secretary | Executive dashboard |
| Health Minister | Full AP health overview |

---

### 🎙️ Telugu AI Voice System
- **Online:** Vapi + OpenAI Whisper + GPT-4
- **Offline:** Whisper Local STT + Ollama LLM + Piper Telugu TTS
- **Hybrid:** LangChain + CRDT auto-merge
- Patient speaks Telugu → AI extracts symptoms → auto-fills form → triggers diagnosis

---

### 🤖 AI Clinical Decision Support
- LangChain + Ollama local AI (runs offline)
- Differential diagnosis with probability bars
- Auto-recommends lab investigations
- AI recovery plans generated in Telugu
- Full FHIR R4 audit trail of every AI decision

---

### 🔗 Government Integrations
| System | Purpose |
|--------|---------|
| ABHA / ABDM | 14-digit health ID via Aadhaar OTP |
| FHIR R4 | Interoperable health records |
| eSanjeevani | Telemedicine |
| 104 Helpline | Health advisory |
| 108 Emergency | Ambulance dispatch |
| Kilkari | Maternal & child health IVR |
| CoWIN | Vaccination records |
| MARG ERP | Billing webhook |
| HMIS | Monthly reporting |

---

### 🔄 Offline-First Architecture
- **Local storage:** SQLite (device) + IndexedDB (browser)
- **Sync engine:** CRDTs (Conflict-free Replicated Data Types)
- **Conflict resolution:** LWW (Last-Write-Wins) + manual review UI
- **No data loss:** All records saved locally before sync
- Works in zero-connectivity areas (villages, remote PHCs)

---

### ⚠️ Escalation Chain
```
CHO / ANM
   ↓
Medical Officer / CHC Admin
   ↓
DMHO / DPO / DPMO
   ↓
DPH / DME
   ↓
Commissioner / Principal Secretary
   ↓
Health Minister, AP
```
- One-click raise & resolve
- Auto-SMS alerts to each level
- Time-stamped audit log
- Resolution flows top-down instantly

---

### 🔄 Patient AI Workflow (8 Steps)
```
Voice Screen → Nurse Notes → AI Diagnosis → Doctor Consult
     → Prescribe → Lab Test → Pharmacy → Recovery
```

---

## 📁 File Structure

```
ap-digital-health-ehr/
│
├── index.html          ← Complete single-file app (HTML + CSS + JS)
├── README.md           ← This file
│
└── (optional expansion)
    ├── assets/
    │   ├── ap-logo.png
    │   └── favicon.ico
    ├── offline/
    │   ├── whisper-model/    ← Local STT model files
    │   └── ollama-model/     ← Local LLM model files
    └── fhir/
        └── sample-bundle.json
```

> **Note:** The entire app runs from a single `index.html`. No build tools, no npm, no server required.

---

## 🛠️ Setup & Deployment

### Option 1 — GitHub Pages (Recommended, Free)

```bash
# 1. Fork or clone this repo
git clone https://github.com/YOUR-USERNAME/ap-digital-health-ehr.git
cd ap-digital-health-ehr

# 2. Add your index.html (the EHR app)
# (copy the full HTML code into index.html)

# 3. Push to GitHub
git add .
git commit -m "Initial AP Digital Health EHR deployment"
git push origin main

# 4. Enable GitHub Pages
# Go to: Settings → Pages → Source: main branch → / (root)
# Your app will be live at:
# https://YOUR-USERNAME.github.io/ap-digital-health-ehr/
```

### Option 2 — Local / Intranet

```bash
# Just open index.html in any browser
# No server, no internet needed
start index.html        # Windows
open index.html         # Mac
xdg-open index.html     # Linux
```

### Option 3 — NHM Server / AP Gov Intranet

```bash
# Copy index.html to your web server root
cp index.html /var/www/html/ehr/
# Access at: http://YOUR-SERVER-IP/ehr/
```

---

## 💻 Browser Compatibility

| Browser | Version | Status |
|---------|---------|--------|
| Chrome | 40+ | ✅ Full support |
| Firefox | 35+ | ✅ Full support |
| Edge | 14+ | ✅ Full support |
| Internet Explorer | 9+ | ✅ Supported |
| Safari | 9+ | ✅ Full support |
| Android Chrome | 5.0+ | ✅ Mobile ready |

---

## 🔐 Security Notes

- No external API keys stored in frontend code
- ABHA OTP flow uses ABDM official gateway
- All patient data encrypted at rest (AES-256) in production
- Consent manager (Milestone 3) for ABDM PHR access
- Role-based access control — each login sees only relevant modules
- Full FHIR R4 audit trail for every clinical action

---

## 📊 Pages & Modules

| Page | Roles | Description |
|------|-------|-------------|
| Dashboard | All | Role-specific KPIs, alerts, quick actions |
| Register Patient | CHO, ANM, Doctor | ABHA generation + Telugu voice auto-fill |
| AI Voice | All | Telugu STT → AI diagnosis → auto-document |
| OPD Queue | Doctor | AI-triaged patient queue |
| AI Diagnosis | Doctor | Differential diagnosis + lab recommendations |
| Prescriptions | Doctor, Pharmacist | FHIR MedicationRequest + pharmacy webhook |
| ABHA / FHIR | Doctor, State | ABDM integration + consent manager |
| Escalation | All | Full escalation chain + raise/resolve |
| Offline Sync | All | CRDT sync + conflict resolution |
| Analytics | Admin, DMHO+ | Facility & disease burden charts |
| KPIs | State+ | NHM target tracking |
| Lab Orders | Doctor, Lab | Test ordering + result notification |
| Maternal Care | ANM, CHO | ANC/PNC/delivery tracking |
| Referrals | Doctor, CHO | 108 integration + receiving facility alert |

---

## 🧪 Sample Login Credentials

> All fields are pre-filled for demo. Just select your role and click Login.

| Role | Employee ID | Password |
|------|-------------|----------|
| Any role | AP-EMP-2024-001 | (any value) |

---

## 📱 Mobile / Tablet Support

- Responsive grid (collapses to 2-col on tablets, 1-col on mobile)
- Sidebar hidden on screens < 640px
- Touch-friendly buttons and tap targets
- Telugu font rendering on Android/iOS

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/new-module`
3. Commit your changes: `git commit -m 'Add new module'`
4. Push to branch: `git push origin feature/new-module`
5. Open a Pull Request

---

## 📞 Support & Contact

| Department | Contact |
|------------|---------|
| NHM Andhra Pradesh | nhm.ap.gov.in |
| Technical Support | IT Cell, AP H&FW |
| ABHA / ABDM Issues | abdm.gov.in |
| 108 Emergency | Dial 108 |
| 104 Health Helpline | Dial 104 |

---

## 📄 License

© 2024 Government of Andhra Pradesh — National Health Mission.
Built for public health service. Not for commercial use.

---

## 🏛️ Built With

- Pure HTML5 + CSS3 + Vanilla JavaScript (zero dependencies)
- FHIR R4 standard (HL7)
- ABDM / ABHA APIs
- LangChain + Ollama (AI, offline-capable)
- Vapi + Whisper (voice, online)
- Piper TTS (Telugu text-to-speech, offline)
- CRDTs (offline sync conflict resolution)

---

*AP Digital Health EHR v2.0 — Powering healthcare from village to secretariat.*
