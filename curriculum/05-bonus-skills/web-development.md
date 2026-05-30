# Web Development Basics (Optional Track)

Pick this track only if you enjoy visual output. It is by far the **easiest way to have a deployable project** that recruiters can *click on*.

## Goal of this module (3-4 weeks of evenings)

Build & deploy **one full-stack web app** with:
- A frontend in HTML + CSS + a sprinkle of JavaScript.
- A backend in Python (Flask) or Node.js (Express).
- A small DB (SQLite).
- Deployed on Vercel / Render / Railway (free tiers).

## Path A — Static front-end only (1 week)

If web-dev intimidates you, start here. You'll learn:

### HTML — structure (1-2 days)
- Tags: `<h1>...<h6>`, `<p>`, `<a>`, `<img>`, `<ul>/<ol>/<li>`, `<div>`, `<span>`, `<table>`, `<form>`, `<input>`, `<button>`.
- Semantic tags: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`.
- Attributes: `id`, `class`, `href`, `src`, `alt`, `target`.

### CSS — styling (2 days)
- Selectors: tag, `.class`, `#id`, descendant, attribute.
- Box model: content / padding / border / margin.
- Flexbox basics (`display: flex`, `justify-content`, `align-items`, `gap`).
- Grid basics (`display: grid`, `grid-template-columns`).
- Responsive: media queries.

### JavaScript — interactivity (2-3 days)
- Syntax similar to Python; let / const / var.
- DOM: `document.getElementById`, `addEventListener`, `innerText`, `classList.add/remove`.
- Arrays, objects, basic loops.
- `fetch()` for HTTP requests.

### Project 1: Personal portfolio website
Static page with: hero, about, skills, projects, contact. Host it on **GitHub Pages** (free, github.io URL).
Resume bullet:
```
Personal portfolio — github.com/<you> — built with HTML, CSS, JS;
deployed at <you>.github.io showcasing 4 projects.
```

## Path B — Full-stack with Flask (2-3 weeks)

After comfort with Path A, add a backend.

### Flask (Python) — minimal app

```python
# app.py
from flask import Flask, request, render_template, redirect, url_for
import sqlite3

app = Flask(__name__)

def db():
    conn = sqlite3.connect("data.db")
    conn.row_factory = sqlite3.Row
    return conn

@app.route("/")
def index():
    rows = db().execute("SELECT * FROM tasks ORDER BY id DESC").fetchall()
    return render_template("index.html", tasks=rows)

@app.route("/add", methods=["POST"])
def add():
    title = request.form["title"]
    conn = db()
    conn.execute("INSERT INTO tasks (title) VALUES (?)", (title,))
    conn.commit()
    return redirect(url_for("index"))

if __name__ == "__main__":
    app.run(debug=True)
```

```bash
pip install flask
python app.py        # serves at http://localhost:5000
```

### Concepts to learn

- Routes (`@app.route`).
- Templates (`Jinja2`): `{{ var }}`, `{% for %}`, `{% if %}`.
- Static folder for CSS / JS.
- Forms (GET/POST), input validation.
- Session / cookies basics.
- SQL queries from Python with `sqlite3` or `flask-sqlalchemy`.

### Deployment options

- **Render.com** — free web service tier; easy GitHub integration.
- **Railway.app** — free credit, push to deploy.
- **Vercel** — best for static + Next.js; you can also deploy a Flask app via *Vercel Python runtime*.
- **Streamlit Cloud** — if you don't even want HTML; one-file deployment from a `.py` Streamlit script.

### Project 2: To-Do app with login

Tables: `users(id, username, password_hash)`, `tasks(id, user_id, title, done)`.

Features:
- Register / login (hash passwords with `bcrypt`).
- CRUD on tasks per user.
- Filter completed / pending.
- Responsive styling.

Resume bullet:
```
TaskFlow — Flask + SQLite full-stack to-do web app with user auth,
hashed passwords, and CRUD. Deployed on Render. github.com/<you>/taskflow
```

## Path C — Modern (React / Next.js) — only if time permits

Skip this for placement prep — keep it for after offers. Service MNCs do *not* require React. Product companies do.

## What to put on resume

Choose **one** track and one project. Don't fake skills you can't demonstrate. Sample skill block:

```
Web Dev — HTML, CSS, JavaScript, Flask. Built and deployed 'TaskFlow',
          a multi-user task manager (Python + SQLite + Jinja2 templates).
```
