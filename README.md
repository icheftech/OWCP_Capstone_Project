🩺 FredMed: OWCP AI Patient Care Architecture

Houston Community College — ITAI-2277 Artificial Intelligence Capstone (Fall 2025)
Team Lead: ChefEL33
Faculty Mentor: Dr. Ayyagari

📘 Project Overview

FredMed is an AI-driven patient care coordination system designed to support injured federal workers under the OWCP (Office of Workers’ Compensation Programs).
The system leverages multiple AI domains—NLP, Computer Vision, and Intelligent Scheduling—to streamline case management, documentation, and diagnostics from injury to recovery.

This Capstone demonstrates an end-to-end AI pipeline:

Synthetic patient data simulation (privacy-safe).

Data ingestion and preprocessing pipeline.

Exploratory data analysis (EDA) for insights.

Modular backend built with FastAPI and Postgres.

Integration with LLM “copilot” agents for case assistance.

Vision module (future) for medical imaging quality review.

🎯 Objectives

Create a HIPAA-conscious AI system that manages and tracks patient recovery journeys.

Reduce OWCP claim denials by automating documentation and accelerating scheduling.

Provide each patient with a dedicated AI copilot agent for communication, updates, and guidance.

Deliver a fully functional MVP by Week 10 capable of handling synthetic case data and demonstrating real workflow automation.

🧠 AI Components
Module	Role	Technology
NAVA	Patient intake, daily symptom tracking	FastAPI + PostgreSQL
SCHEDULUS	Multi-clinic scheduling orchestrator	Python + Redis + Celery
DOCSCRIBE	LLM copilot for documentation & OWCP narrative drafting	GPT-4/Local LLM + RAG
IMAGUS	Medical imaging quality control (future)	PyTorch + MONAI
GUARDIAN	Compliance, audit, and PHI security	Role-based Access, Logging
SKOOLMAESTRO	Community learning (Skool integration)	Zapier Webhooks
TELEHUB	Telehealth coordination module	Zoom for Healthcare API
🧩 Current Milestone (Weeks 4–6)

Phase 02: Data Pipeline and Exploratory Analysis

Deliverables

✅ owcp_cases_raw.csv — 500 synthetic OWCP case records

🧹 owcp_cases_clean.csv — cleaned dataset (post-outlier handling)

📊 owcp_eda.ipynb — EDA notebook with statistics & visualizations

🧾 data_report.md — summary of cleaning, insights, and ethics

🗂 outliers.csv — flagged anomalies for validation demo

Key Data Insights

500 total records; 15 deliberate outliers (ages 5 & 120, missing fields, etc.)

Average patient age: 45 yrs | Mean recovery: 92 days | Approval rate: 92%

Common injury types: rotator cuff tears, meniscus injuries, back strains

Agencies: USPS 25%, DoD 20%, CBP 18%, VA 15%, others 22%

🧮 Repository Structure
fredmed-capstone/
│
├── backend/                # FastAPI app (routers, db, services)
├── frontend/               # Next.js patient/provider interface
├── data/
│   ├── owcp_cases_raw.csv
│   ├── owcp_cases_clean.csv
│   └── outliers.csv
├── notebooks/
│   ├── owcp_data_cleaning.ipynb
│   └── owcp_eda.ipynb
├── docs/
│   ├── data_report.md
│   ├── ARCHITECTURE.md
│   └── SECURITY_HIPAA_NOTES.md
├── scripts/
│   └── clean_data.py
└── README.md

🧰 Tech Stack

Core: Python 3.11, FastAPI, PostgreSQL, Pandas, NumPy, Matplotlib, Scikit-learn
Frontend: Next.js 14, React 18
LLM & AI: OpenAI GPT-4 (transitioning to open-source LLaMA 3/Claude 3.5)
Infra: Docker Compose, Redis, Celery, GitHub Actions (CI/CD planned)
Visualization: Matplotlib, Seaborn, Plotly
Compliance: Role-Based Access Control, Encrypted DB fields, Audit Logs

🔒 Ethical & Compliance Framework

Synthetic Data Only used for training and testing.

No PHI stored in any open environment.

Planned deployment to HIPAA-eligible cloud (AWS HealthLake or Azure HealthData) with BAA.

LLMs operate in human-in-the-loop mode—clinicians validate all outputs.

📅 Project Timeline
Week	Phase	Deliverable
1–2	Planning & Architecture	Proposal + Repo Skeleton
3	Synthetic Data Creation	500-record OWCP dataset
4–6	Data Pipeline & EDA	✅ Cleaning + Analysis
7–8	Backend Integration	FastAPI + Database + LLM Stub
9–10	Full MVP & Demo	HIPAA portal simulation
11–12	Presentation	Final report + live showcase
🧑‍💻 Team & Collaboration
Role	Name	Responsibilities
Product Lead / AI Orchestrator	Chef Brown	System design, architecture, coding
Clinical Advisor	Dr. Costello (DC)	Medical logic, data validation
AI Copilot Engineer	TBD	RAG integration, LLM fine-tuning
Frontend Dev	TBD	UX & patient portal interface
Compliance Lead	Guardian Agent	Security, audit, ethical reviews
🚀 Getting Started (Dev)
# clone repo
git clone https://github.com/icheftech/OWCP_Capstone_Project.git
cd fredmed-capstone

# run backend + db
docker compose up --build

# access
API: http://localhost:8000/health
Web: http://localhost:3000

🧾 License

Educational Use Only — No PHI.
MIT License © 2025 ChefEL33 / FredMed LLC.

---

## 🔍 Data Ethics & Sources Appendix

**Data Origin:**  
All records in this project are **synthetic and anonymized**.  
No personally identifiable information (PII) or protected health information (PHI) was collected, stored, or transmitted at any stage.

**Generation Process:**  
The dataset was created using a controlled prompt-based generator (Claude 3.5) with statistical parameters derived from publicly available health injury statistics and OWCP claim patterns.  
Each record simulates realistic case features, including injury type, agency, approval status, and recovery timelines.

**Validation & Integrity Checks:**
- Outliers were deliberately included to test data-cleaning and validation logic.
- Statistical distributions were cross-checked against U.S. Bureau of Labor Statistics injury reports (2022–2023) for realism.
- All data transformations and visualizations comply with educational fair use and ethical research standards.

**Usage Notice:**  
This dataset is for **academic and research demonstration only**.  
It is not to be used in live medical, diagnostic, or administrative decision systems without formal HIPAA and BAA compliance audits.

> 💡 Tip: If you only need to explore the data pipeline (not the full app),
> just open `/notebooks/owcp_eda.ipynb` in Google Colab.



---

## 🎨 UI/UX Design

### FredMed Patient Care Portal Dashboard

Comprehensive UI design for the OWCP Patient Care Portal created with Figma Make.

**Figma Make Project:** [OWCP Patient Care Portal Dashboard](https://www.figma.com/make/3jKn9pW39p4LXRZjpAdKSY/OWCP-Patient-Care-Portal-Dashboard)

**Features:**
- 🏥 Landing page with FredMed branding and agent overview
- 📊 Provider dashboard with compliance tracking and analytics
- 🤖 8 AI Agent modules (NAVA, SCHEDULUS, DOCSCRIBE, TELEHUB, IMAGUS, GUARDIAN, SKOOLMAESTRO, INSIGHTS)
- 📱 Responsive design for desktop and mobile
- 🔒 HIPAA-compliant design patterns with role-based access controls
- 🎨 Professional medical AI aesthetic with teal/cyan color scheme
- 📈 Data visualization components for patient timelines and compliance metrics

**Generated Code:**
The Figma Make project includes React/TypeScript components ready for implementation in the frontend.
