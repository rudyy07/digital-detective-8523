# Mission 6 — Git and GitHub

## 1. Task / objective

The objective of Mission 6 was to practise the core Git workflow (`git status`, `git add`, `git commit`, `git log`), create a separate branch named `update-about`, update the root `README.md` with a "My Learning" section on that branch, open a Pull Request into `main` on GitHub, inspect the changed file in the PR, and build a glossary of essential Git commands.

## 2. Work completed

- Practised inspecting repository status, staging files, committing changes, and viewing commit history.
- Created a new branch `update-about` using `git switch -c update-about`.
- Updated the root `README.md` on `update-about` by adding a `## My Learning` section with three actual concepts learned across Missions 0–5.
- Committed the change on `update-about` (`5be8880`) and pushed the branch to GitHub (`origin/update-about`).
- Opened Pull Request #1 from `update-about` into `main` on GitHub and inspected its changed file (`README.md`, `+6` lines).
- Left PR #1 **OPEN (not merged)** because the assignment instructs to merge only if requested by the instructor, and switched back to `main`.

### Task 6.1 — Understand the basic Git workflow

| Git operation | What it does in your own words |
|---|---|
| Check repository status (`git status`) | Shows the current branch and lists untracked, modified, and staged files. |
| Stage selected changes (`git add`) | Marks specific modified or new files in the staging area to be included in the next commit. |
| Create a commit (`git commit`) | Saves a permanent snapshot of all staged changes to the local Git history with a message. |
| View commit history (`git log`) | Displays past commits in reverse chronological order with their commit ID, author, date, and message. |

**Difference between staging and committing:** Staging (`git add`) prepares and selects which changes you want in the next snapshot—you can still adjust staged files before saving. Committing (`git commit`) permanently records those staged changes as a new version in the repository's history.

### Task 6.2 & 6.3 — Branch and Pull Request

- **Branch created:** `update-about` (commit `5be8880` — `Add My Learning section to root README`)
- **Pull Request:** [#1 — Add My Learning section to root README](https://github.com/rudyy07/digital-detective-8523/pull/1) (`update-about` → `main`)
- **Changed files inspected in PR:** `README.md` (`+6` additions, `0` deletions)
- **PR status:** **Open (not merged)** — kept unmerged as instructed unless the instructor asks to merge it.

**What a branch and a Pull Request are, and why they are useful:** A branch is an independent line of development where you can make and test changes without disturbing the main working version (`main`). A Pull Request is a GitHub review request asking to merge changes from one branch into another, showing the exact line-by-line diff. Together, they let team members work on different features at the same time, review each other's changes before merging, and avoid breaking `main`.

### Task 6.4 — Git command glossary

| Command | One-line explanation in my own words |
|---|---|
| `git init` | Initializes a new local Git repository in the current folder. |
| `git status` | Checks the active branch and which files are untracked, modified, or staged. |
| `git add` | Adds selected file changes to the staging area before committing. |
| `git commit` | Records staged changes as a new snapshot in the local commit history. |
| `git log` | Lists previous commits made in the repository. |
| `git branch` | Lists existing branches or creates/deletes a branch. |
| `git switch` | Switches the working directory to another branch (or creates one with `-c`). |
| `git push` | Uploads local commits and branches to the remote repository on GitHub. |
| `git pull` | Downloads and merges new commits from the remote repository into the current local branch. |

## 3. Commands / tools used

- `git switch -c update-about` — Created and switched to the `update-about` branch.
- `git status` — Checked modified and staged files before committing.
- `git add README.md` and `git commit -m "Add My Learning section to root README"` — Staged and committed the root README update on `update-about`.
- `git push -u origin update-about` — Published the `update-about` branch to GitHub.
- `gh pr create` and `gh pr view` — Created Pull Request #1 targeting `main` and inspected its status and changed files.
- `git switch main` — Switched back to `main` to document Mission 6.
- `git log`, `git branch`, and `git pull` — Checked commit history, branches, and remote sync.

## 4. My understanding

Using branches and Pull Requests separates work-in-progress edits from the stable `main` branch. Even when working alone on an assignment, creating `update-about` and opening a Pull Request made it easy to review the exact diff (`+6` lines in `README.md`) on GitHub before deciding whether to merge.

## 5. Difficulties faced

No major difficulties.

## 6. How I resolved them

Not applicable.

## 7. Evidence / files

- `mission-06-git-github/README.md` (Git workflow explanations, branch/PR details, and command glossary)
- Remote branch `update-about` on GitHub (`https://github.com/rudyy07/digital-detective-8523/tree/update-about`)
- Pull Request #1 on GitHub (`https://github.com/rudyy07/digital-detective-8523/pull/1`, status: `OPEN`)

## 8. Commit details

- **Commit message:** `Complete Git and GitHub collaboration mission`
- **Branch:** `main`
- **Push status:** Pushed to `origin/main` on GitHub (`rudyy07/digital-detective-8523`)
