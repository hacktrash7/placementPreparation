# Project Ideas (Pick 2-3, Build Them Properly)

A "project" recruiters care about is one that:

1. **Solves something real** (even if small).
2. **Has a public repo with a clean README**.
3. **Has a working demo** (live URL or screen recording).
4. **Has at least 5-6 commits over time** (not 1 dump commit).
5. **You can explain end-to-end** in 90 seconds.

You only need **2 such projects**. Three at most. Don't chase quantity — chase polish.

## Tier 1 — Easiest, highest ROI (pick 1)

### 1. Personal Portfolio Website
- **Stack**: HTML, CSS, JS. Optionally Tailwind or Bootstrap.
- **Pages**: Home (hero + about), Projects, Skills, Contact.
- **Hosted**: GitHub Pages → `<your-username>.github.io`.
- **Why**: lets you put a *real link* on the resume.
- **Difficulty**: 1/5.
- **Time**: 4-6 evenings.

### 2. Library Management CLI (or Inventory / Hostel Mess / Attendance)
- **Stack**: Python + SQLite + `click`/`rich`.
- **Schema**: 3-4 tables with foreign keys.
- **Features**: CRUD + reports + CSV import/export.
- **Why**: demonstrates SQL + Python + good design.
- **Difficulty**: 2/5.
- **Time**: 1-2 weeks of evenings.

## Tier 2 — Full-stack / data (pick 1 main project)

### 3. TaskFlow / Habit-Tracker / Expense-Tracker Web App
- **Stack**: Python + Flask + SQLite + Jinja2 + a sprinkle of JS.
- **Features**: user signup/login (hashed passwords), CRUD, filters.
- **Hosted**: Render / Railway / PythonAnywhere (free tiers).
- **Difficulty**: 3/5.
- **Time**: 3 weeks of evenings.

### 4. URL Shortener
- **Stack**: Flask + SQLite OR FastAPI + SQLite.
- **Features**: paste long URL → get short code; redirect on visit; show click counts.
- **Why**: tiny, finishable, shows you understand routes, DB, redirects.
- **Difficulty**: 2/5.
- **Time**: 1 week.

### 5. Data Dashboard (Streamlit) on a Public Dataset
- **Stack**: Pandas + Streamlit.
- **Datasets**: IPL, Spotify, COVID, Indian Census, Olympic medals.
- **Features**: filters, KPIs, 4-5 charts, downloadable filtered CSV.
- **Hosted**: share.streamlit.io.
- **Difficulty**: 2/5.
- **Time**: 1-2 weeks.

### 6. Movie / Book Recommendation System (simple)
- **Stack**: Pandas + scikit-learn (cosine similarity on TF-IDF of overview/genre).
- **UI**: Streamlit.
- **Why**: light ML, beginner-friendly, very impressive output.
- **Difficulty**: 3/5.
- **Time**: 1-2 weeks.

### 7. PDF / Notes Q&A Chatbot (Generative AI)
- **Stack**: LangChain or LlamaIndex + sentence-transformers + ChromaDB + Streamlit. LLM via Ollama (local Llama 3) or HuggingFace Inference API free tier.
- **Why**: "I built a RAG chatbot" is the *hot* fresher line in 2025-26.
- **Difficulty**: 4/5.
- **Time**: 2-3 weeks.

## Tier 3 — Stretch (only if you have time)

### 8. Mini E-commerce (Books / Coffee / Stationery)
- **Stack**: Flask + SQLite + Jinja2 + Bootstrap. Optional Stripe test mode for payments.
- **Features**: catalog, cart, checkout (test mode), order history, admin panel.
- **Difficulty**: 4/5.
- **Time**: 4-5 weeks.

### 9. Real-Time Chat
- **Stack**: Flask-SocketIO or Node + Socket.IO.
- **Features**: rooms, message history, basic auth.
- **Difficulty**: 4/5.
- **Time**: 3 weeks.

### 10. Resume Parser
- **Stack**: Python + `pdfplumber`/`pyPDF` + Streamlit + simple regex/spaCy for entity extraction (name, email, skills).
- **Why**: small + interesting, ties to HR/recruitment.
- **Difficulty**: 3/5.
- **Time**: 2 weeks.

### 11. Stock / Crypto Price Tracker
- **Stack**: Python + yfinance / CoinGecko API + Streamlit; SQLite for watchlist.
- **Features**: add tickers, daily fetch, simple moving averages, charts.
- **Difficulty**: 3/5.
- **Time**: 2 weeks.

### 12. Network Speed Test / Port Scanner / Mini-Tool
- **Stack**: Python + `socket` + `argparse`.
- **Why**: tiny, networking-flavour, useful talking point in CN interviews.
- **Difficulty**: 2/5.
- **Time**: 1 week.

## Recommended combos (pick one row)

| Profile                 | Combo                                                                 |
| ----------------------- | --------------------------------------------------------------------- |
| Generalist + safe       | Portfolio site + TaskFlow + Library CLI                               |
| Data-leaning            | Portfolio site + Streamlit Dashboard + Movie Recommender              |
| Modern AI-leaning       | Portfolio site + TaskFlow + PDF Q&A Bot                               |
| Web-dev leaning         | Portfolio site + TaskFlow + Mini E-commerce                           |
| Cloud-leaning           | Portfolio site + Streamlit Dashboard (on AWS) + URL Shortener (on AWS)|

## How to actually finish (the bit that matters)

1. **Pick the project the morning of Week 13** (or earlier).
2. **Write down 6-8 features** in `IDEAS.md` in the repo. Cross off as you ship.
3. **Commit every day you touch it**, even small.
4. **Deploy when 70% done.** Polish the rest live. Deploying triggers motivation.
5. **Write the README the day you deploy.**
6. **Record a 60-second screen capture** with OBS or Loom and put the link in the README + LinkedIn.

## Anti-patterns (avoid these "projects")

- Copy-pasted clones of YouTube tutorials with no original work.
- "Hello World" calculator / number-guessing scripts.
- A blockchain / metaverse / Web3 project you can't explain.
- Anything you uploaded but can't run locally yourself.
- A research paper you didn't actually write (interviewer will quiz you).

A small, well-built project beats a flashy half-finished one every single time.
