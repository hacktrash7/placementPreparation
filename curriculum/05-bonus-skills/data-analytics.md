# Data Analytics with Python (Pandas + a Dashboard)

If "build a website" feels intimidating, **data analytics** is the friendliest "modern skill" you can add. Many service MNCs (TCS BFSI, Infosys BPM, Cognizant analytics units) recruit explicitly for analyst tracks.

## Goal of this module (2-3 weeks)

Build **one clean Jupyter notebook + one Streamlit dashboard** analysing a public dataset and host on GitHub.

## Topic roadmap

### Week 1 — Numpy + Pandas

- NumPy arrays (basic ops, vectorisation).
- Pandas `Series` and `DataFrame`.
- Reading: `pd.read_csv`, `read_excel`, `read_json`.
- Selection: `df["col"]`, `df.loc[...]`, `df.iloc[...]`, boolean masks.
- Cleaning: `df.dropna`, `df.fillna`, `df.duplicated`, `df.replace`.
- Grouping: `df.groupby("col").agg(...)`, pivot tables (`pd.pivot_table`).
- Joining: `pd.merge`, `pd.concat`.
- Dates: `pd.to_datetime`, `.dt.year/.month/.day`.

### Week 2 — Visualisation

- Matplotlib: `plt.plot`, `plt.bar`, `plt.hist`, `plt.scatter`.
- Seaborn: `sns.heatmap`, `sns.barplot`, `sns.lineplot`, `sns.pairplot`.
- Customisation: titles, labels, colours, figsize.

### Week 3 — Storytelling + Streamlit

- Write a story: question → data → analysis → finding.
- **Streamlit** in 1 hour: `st.title`, `st.write`, `st.dataframe`, `st.line_chart`, `st.selectbox`, `st.slider`.
- Deploy to **Streamlit Cloud** (free).

## Free dataset ideas

- **IMDB movies** (Kaggle).
- **Spotify Top Songs** (Kaggle).
- **COVID-19 data** (OWID).
- **Indian Census 2011** (Kaggle / data.gov.in).
- **Olympic medals history** (Kaggle).
- **IPL dataset** (Kaggle) — great if interviewer likes cricket.

## A sample analysis (IPL example)

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

m = pd.read_csv("matches.csv")
d = pd.read_csv("deliveries.csv")

# Q1: Top 10 wicket-takers
top_bowlers = (
    d[d["dismissal_kind"].notna()]
    .groupby("bowler")
    .size()
    .sort_values(ascending=False)
    .head(10)
)
top_bowlers.plot(kind="bar", title="Top 10 IPL Wicket Takers")
plt.tight_layout(); plt.savefig("top_bowlers.png")

# Q2: Win % by team batting first vs chasing
m["winner_batted_first"] = m["winner"] == m["toss_winner"]
# ... and so on
```

## Streamlit dashboard skeleton

```python
import streamlit as st
import pandas as pd

st.set_page_config(page_title="IPL Dashboard", layout="wide")
st.title("IPL Insights Dashboard")

df = pd.read_csv("matches.csv")

team = st.selectbox("Team", sorted(df["team1"].unique()))
team_matches = df[(df["team1"] == team) | (df["team2"] == team)]

st.metric("Total Matches", len(team_matches))
st.metric("Wins",          (team_matches["winner"] == team).sum())

st.line_chart(team_matches.groupby("season").size().rename("matches"))
st.dataframe(team_matches.tail(20))
```

Run with:

```bash
pip install streamlit pandas matplotlib seaborn
streamlit run app.py
```

Then deploy by connecting to GitHub on **share.streamlit.io** — done in 5 minutes.

## Project deliverables (push these to GitHub)

```
ipl-insights/
├── README.md         (problem, dataset, screenshots, deploy link)
├── notebook.ipynb    (your full analysis with 8-10 questions answered)
├── app.py            (Streamlit dashboard)
├── requirements.txt
├── data/             (or a download script if dataset is large)
└── images/           (saved plots)
```

## Resume bullets

```
Data Analytics — Built 'IPL Insights' dashboard: Python + Pandas
                 analysis of 16 IPL seasons; Streamlit web dashboard
                 deployed at <url>. Tools: pandas, seaborn, matplotlib.

                 Live demo: ipl-insights.streamlit.app
                 GitHub  : github.com/<you>/ipl-insights
```

That's a recruiter-credible "data" line — and it links to a *clickable* live demo, which most freshers lack.
