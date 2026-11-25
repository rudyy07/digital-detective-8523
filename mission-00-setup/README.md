# Mission 0 — Create your GitHub workspace

## 1. Task / objective

The objective of Mission 0 was to verify that Python 3 and Git are installed on my Mac, create a local project folder named `digital-detective-8523` using the last four digits of my USN (`8523`), set up the required mission folders and placeholder files, write a root `README.md`, and publish the repository as a public repository on GitHub.

## 2. Work completed

- Checked the installed versions of Python 3 and Git in macOS Terminal.
- Created the local folder `digital-detective-8523` and initialized Git with `main` as the default branch.
- Created all mission folders (`mission-00-setup` through `mission-08-final-report`), the `evidence/` directory, and the required placeholder files (`README.md` in each mission folder, `mission-04-programs/hello.py`, and `mission-05-numbers-data/number_converter.py`).
- Wrote the root `README.md` with the project title, USN (`2392608523`), mission index links, and a note explaining that missions are completed and committed one by one.
- Created a public repository named `digital-detective-8523` on GitHub under the account `rudyy07`, connected the local repository to it, and pushed the Mission 0 setup files.

## 3. Commands / tools used

- `python3 --version` — Checked the installed Python 3 version (`Python 3.14.6`).
- `git --version` — Checked the installed Git version (`git version 2.55.0`).
- `mkdir -p` — Created the repository folder, all nine mission folders, and `evidence/`.
- `touch` — Created the initial empty mission `README.md` files, Python placeholder files, and `evidence/.gitkeep`.
- `git init -b main` — Initialized a new Git repository with `main` as the starting branch.
- `gh repo create` — Created the public GitHub repository `rudyy07/digital-detective-8523` and linked it as `origin`.
- `git add` and `git commit` — Staged and committed the setup files.
- `git push -u origin main` — Pushed the local `main` branch to GitHub.
- macOS Terminal and a text editor — Used to run commands and edit Markdown files.

## 4. My understanding

A Git repository is a project folder tracked by version control so that changes to files can be saved as history (commits) and synced with an online copy on GitHub. Organizing the repository into separate folders for each mission keeps notes, code, and evidence for every topic neatly separated instead of mixing everything in the root folder. This makes it easy for me to work step by step and easy for my instructor to check each mission.

## 5. Difficulties faced

No major difficulties.

## 6. How I resolved them

Not applicable.

## 7. Evidence / files

- `README.md` (root project overview and mission index)
- `mission-00-setup/README.md` (this setup report)
- `mission-01-computer-basics/README.md` through `mission-08-final-report/README.md` (empty mission files ready for upcoming missions)
- `mission-04-programs/hello.py` (empty placeholder file)
- `mission-05-numbers-data/number_converter.py` (empty placeholder file)
- `evidence/.gitkeep` (keeps the `evidence/` folder tracked in Git until screenshots or outputs are added)

## 8. Commit details

- **Commit message:** `Set up Digital Detective mission structure`
- **Branch:** `main`
- **Remote repository:** `https://github.com/rudyy07/digital-detective-8523` (public)
