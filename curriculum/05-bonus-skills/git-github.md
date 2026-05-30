# Git, GitHub & Linux Shell Basics

Every fresher who has a clean GitHub looks **2 years more experienced** than one who doesn't. This module is *quick* — finish in a week.

## Part A — Git fundamentals

### What Git does

Git tracks changes to your files. Imagine "save game" snapshots of your project that you can rewind to, branch from, and share.

### The 10 commands you'll use 95% of the time

```bash
# 1. Configure once
git config --global user.name  "Your Name"
git config --global user.email "you@example.com"

# 2. Initialise a repo in current folder
git init

# 3. Clone an existing repo
git clone https://github.com/user/repo.git

# 4. See what changed
git status
git diff

# 5. Stage and commit
git add file.py            # or .  to add everything
git commit -m "Add login screen"

# 6. View history
git log --oneline -n 10

# 7. Connect to remote (first time)
git remote add origin https://github.com/user/repo.git
git branch -M main
git push -u origin main

# 8. Subsequent push/pull
git push
git pull

# 9. Branching
git checkout -b feature/login   # create + switch
git switch main                 # switch back
git merge feature/login         # merge into current

# 10. Undo basics
git restore file.py             # discard local changes
git reset HEAD file.py          # unstage
```

### The mental model

```
┌──────────────┐   git add   ┌──────────────┐   git commit   ┌──────────────┐
│ Working dir  │ ──────────► │ Staging area │ ─────────────► │ Local repo   │
└──────────────┘             └──────────────┘                └──────┬───────┘
                                                                    │
                                                                    │ git push
                                                                    ▼
                                                            ┌──────────────┐
                                                            │ Remote repo  │
                                                            │ (GitHub)     │
                                                            └──────────────┘
```

### Branching strategy for solo projects

- `main` — always working code.
- `feature/<name>` — work on features.
- Merge feature → main when stable.

### `.gitignore` essentials

Add a `.gitignore` to every project. Standard entries for Python:

```
__pycache__/
*.pyc
.venv/
.env
.DS_Store
.idea/
*.sqlite3
```

## Part B — GitHub (the platform)

### Things to set up right away

1. **Username**: clean — e.g., `johnsmith` not `xX_dark_lord_99_Xx`.
2. **Avatar**: real photo or a neutral icon.
3. **Bio**: "CSE undergrad | Python, SQL | placement-ready 2026" (or similar).
4. **Pinned repos**: 4-6 of your best.
5. **Profile README**: a special repo named `<your-username>/<your-username>` with a Markdown bio. Pinned at the top of your profile.

### Repo hygiene

Every repo on your profile must have:

- **README.md** explaining: what it does, why, how to run, screenshots, tech stack.
- **License** (MIT is fine).
- **Topics/tags** (`python`, `sqlite`, `flask`).
- **Working code** — recruiters do clone + run sometimes.
- **A few commits over time**, not 1 dump commit. Looks more genuine.

### Sample minimal README

```markdown
# Library Management CLI

A Python command-line tool to add books, register members, issue and return books — backed by SQLite.

## Features
- Add / search / delete books
- Issue & return with due dates
- Reports: top-borrowed, overdue members

## Run

    git clone https://github.com/.../library-cli.git
    cd library-cli
    python -m venv .venv && source .venv/bin/activate
    pip install -r requirements.txt
    python main.py

## Tech
Python 3.11, SQLite, rich (for CLI tables).

## Author
Your Name — [LinkedIn](...) — [Portfolio](...)
```

## Part C — Linux & shell quick start (1-2 days)

The minimum every SE/IT services fresher should know:

```bash
pwd                 # current directory
ls -la              # list (incl. hidden)
cd path             # change dir; cd .. up; cd ~ home; cd - last
mkdir name          # make folder
touch file.py       # create empty file
cp a b              # copy
mv a b              # move/rename
rm file             # delete (careful!)
rm -rf folder       # remove folder recursively

cat file            # show file
head -n 20 file
tail -n 20 file
less file           # pager (q to exit)

grep "TODO" -r .    # search recursively
find . -name "*.py" # find files

chmod +x script.sh  # make executable
./script.sh

ps aux | grep python
kill -9 <PID>

# Piping & redirection
ls | wc -l                 # count files
cat data.csv | head -5
sort file | uniq -c
python script.py > out.txt 2>&1
```

Permissions in one line:

```
rwxr-xr--   = 754   = owner: read+write+execute, group: read+execute, others: read.
```

## Part D — A 1-week mini-plan

| Day | What you do                                                     |
| --- | --------------------------------------------------------------- |
| 1   | Install Git + create GitHub account. Push a "hello world" repo. |
| 2   | Make your first README. Add `.gitignore`. Practice add/commit.  |
| 3   | Learn branching: create feature branch, merge it.               |
| 4   | Linux basics: navigate, view, find, grep, pipes.                |
| 5   | Build your profile: bio, avatar, profile README, pin repos.     |
| 6   | Migrate 2 old projects (even Week-1 Python scripts) to GH with READMEs. |
| 7   | Submit a PR to a small public repo (typo fix, doc tweak) — looks great on profile. |

## Resume line example

```
Git & GitHub — Manage all personal projects via Git; comfortable with
               branching, merging, pull requests. Active profile:
               github.com/<your-username> (6 repos, README + license).
Linux        — Daily use of bash for navigation, file management,
               grep/find, redirection, simple shell scripts.
```
