# AI-Assistantttttttt
# 📄 ATS Resume Checker

A Streamlit app that scores your resume for ATS (Applicant Tracking System) compatibility and gives specific, prioritized improvements using Google's Gemini Flash model.

## Features
- Upload a resume as **PDF, DOCX or TXT**
- Optional **job description** for tailored scoring and missing keywords
- Overall ATS score (0-100) plus section scores
- Strengths, missing keywords, and prioritized fixes with example rewrites
- Quick rule-based checks (contact info, sections, length, quantified results)
- Download the report as JSON

## Run locally
```bash
git clone https://github.com/<your-username>/ats-resume-checker.git
cd ats-resume-checker
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

Get a free API key at https://aistudio.google.com/apikey, then either paste it in the app sidebar or set it:

```bash
export GEMINI_API_KEY="your-key"     # Windows PowerShell: $env:GEMINI_API_KEY="your-key"
streamlit run app.py
```

Alternatively create `.streamlit/secrets.toml` (never commit it):
```toml
GEMINI_API_KEY = "your-key"
```

## Deploy on Streamlit Community Cloud
1. Push this repo to GitHub (public, or private with access granted).
2. Go to https://share.streamlit.io and sign in with GitHub.
3. Click **Create app** → select your repo, branch `main`, main file `app.py`.
4. Open **Advanced settings → Secrets** and add: `GEMINI_API_KEY = "your-key"`
5. Click **Deploy**.

## Notes
- Scanned/image-only PDFs can't be read (ATS systems can't either). Use a text-based PDF or DOCX.
- The model name can be changed in the sidebar (default: `gemini-2.5-flash`).
- Resume text is sent to the Gemini API; the app itself stores nothing.
- The score is an AI estimate, not the output of a real employer ATS.
