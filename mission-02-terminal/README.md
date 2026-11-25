# Mission 2 — Become comfortable with the Terminal

## 1. Task / objective

The objective of Mission 2 was to practise basic macOS Terminal commands for navigating folders and managing files safely inside a `terminal-practice` directory, understand command flags and pipes, and check whether Homebrew is installed while understanding what package managers do.

## 2. Work completed

- Practised core Terminal commands (`pwd`, `ls`, `ls -l`, `cd`, `mkdir`, `touch`, `cp`, `mv`, `cat`) inside the assignment repository.
- Created the `terminal-practice` folder inside the repository and practised creating a file, writing a first line, appending a second line, confirming the contents with `cat`, making a backup copy, and renaming the backup.
- Compared normal `ls` with `ls -lah` to observe detailed output, hidden files, and human-readable sizes.
- Tested a pipe (`ls -l | head -n 5`) to display only the first five lines of a detailed listing.
- Checked the installed Homebrew version (`Homebrew 7.0.2`) and listed managed packages without installing or removing anything.

### Task 2.1 — Explore basic Terminal operations

| Operation / command name | What it does | What I observed |
|---|---|---|
| Current-directory display (`pwd`) | Prints the full path of the current working folder | Displayed `/Users/[redacted]/Documents/metabrainz/digital-detective-8523` |
| Directory listing (`ls`) | Lists visible files and folders in the current directory | Listed `README.md`, `evidence`, and `mission-00-setup` through `mission-08-final-report` |
| Detailed listing (`ls -l`) | Displays permissions, link count, owner, group, size in bytes, date, and name | Showed `README.md` as `1773` bytes (`-rw-r--r--@`) and folders starting with `d` (`drwxr-xr-x@`) |
| Change directory (`cd ..`) | Moves the shell to the parent folder (or another target folder) | Running `pwd` after `cd ..` showed `/Users/[redacted]/Documents/metabrainz` |
| Create directory (`mkdir`) | Creates a new folder | Created the `terminal-practice` folder inside the repository |
| Create empty file (`touch`) | Creates a new empty file if it does not already exist | Created `notes.txt` inside `terminal-practice` |
| Copy file (`cp`) | Duplicates a file to a new file name or location | Copied `notes.txt` to `notes-backup.txt` while keeping `notes.txt` intact |
| Move / rename file (`mv`) | Moves a file to another folder or renames it in place | Renamed `notes-backup.txt` to `notes-archive.txt`; `notes-backup.txt` was no longer present |
| Display file contents (`cat`) | Prints the text contents of a file to the Terminal | Printed both lines stored inside `notes.txt` |

### Task 2.2 — Practise file changes safely

Inside `terminal-practice/`, I created `notes.txt` with `touch notes.txt`, wrote one line using `>`, appended a second line using `>>`, verified both lines with `cat notes.txt`, copied it with `cp notes.txt notes-backup.txt`, and renamed the copy with `mv notes-backup.txt notes-archive.txt`. Both `notes.txt` and `notes-archive.txt` showed a size of `82` bytes in `ls -l`.

- **Difference between replacing a file's contents and adding text to the end:** Using single redirection (`>`) replaces (overwrites) whatever was already in the file, whereas double redirection (`>>`) appends new text to the end of the file without removing existing lines.
- **Difference between copying a file and moving a file:** Copying (`cp`) creates an independent duplicate so both the original and the copy exist, while moving (`mv`) relocates or renames the existing file so it only exists at the new name or path.
- **What information the current-directory display provides:** `pwd` shows the complete path from the root `/` down to the exact folder I am currently working in, which prevents running file commands in the wrong folder.
- **Why a directory-listing operation is useful:** `ls` lets me confirm which files and folders exist in a directory, verify whether a command succeeded, and inspect file sizes and permissions before making changes.

### Task 2.3 — Understand flags, paths, and pipes

- **Flags comparison (`ls` vs `ls -lah`):** Normal `ls` only showed the visible file and folder names (`README.md`, `evidence`, and mission folders). Adding `-l` showed the long detailed format (permissions, owner, size, modified timestamp); adding `-a` revealed hidden entries starting with `.` (`.`, `..`, and `.git`); and adding `-h` displayed sizes in human-readable units (`1.7K` instead of `1773` bytes, and `96B` / `480B`).
- **Absolute vs relative paths:** An absolute path starts from the root directory `/` and works from anywhere (for example, `/Users/[redacted]/Documents/metabrainz/digital-detective-8523/terminal-practice/notes.txt`), while a relative path starts from the current folder (for example, `terminal-practice/notes.txt` when inside the repository root).
- **Pipe (`ls -l | head -n 5`):** The pipe symbol `|` sends the standard output of the command on the left directly as input to the command on the right. Here, `ls -l` generated the full detailed listing of the repository root, and `head -n 5` filtered it to print only the first five lines (`total 8`, `README.md`, `evidence`, `mission-00-setup`, and `mission-01-computer-basics`).

### Task 2.4 — Understand package managers

Homebrew is already installed on my Mac (`Homebrew 7.0.2`). Running `brew list --formula` showed installed tools such as `gh`, `git`, and `htop` without installing or uninstalling anything. Package managers are useful because they let you install, update, and remove software and its required dependencies from one consistent command-line tool instead of searching for installers manually. They also help keep installed tools organized and up to date.

## 3. Commands / tools used

- `pwd` — Displayed the full working directory path.
- `ls`, `ls -l`, `ls -lah` — Listed folder contents in standard, detailed, all-files, and human-readable formats.
- `cd` — Changed between the repository root, parent directory, and `terminal-practice`.
- `mkdir -p` — Created the `terminal-practice` directory.
- `touch` — Created an empty `notes.txt` file.
- `echo` with `>` and `>>` — Wrote a line and appended a second line to `notes.txt`.
- `cat` — Printed the contents of `notes.txt`.
- `cp` and `mv` — Copied `notes.txt` to `notes-backup.txt` and renamed it to `notes-archive.txt`.
- `head -n 5` with `|` — Printed only the first five lines of `ls -l`.
- `brew --version` and `brew list --formula` — Checked Homebrew version and existing packages (read-only).

## 4. My understanding

Working in Terminal showed me that every GUI action like creating folders, copying files, or renaming backups has a direct text command. Flags such as `-l`, `-a`, and `-h` customize how much detail a command prints, and pipes (`|`) let small single-purpose tools work together by passing output from one command into another. Always checking `pwd` and `ls` helps make sure file edits happen only in the intended folder.

## 5. Difficulties faced

No major difficulties.

## 6. How I resolved them

Not applicable.

## 7. Evidence / files

- `mission-02-terminal/README.md` (command table, practice notes, flag/pipe explanations, and Homebrew check)
- `terminal-practice/notes.txt` (practice text file with two lines written via `>` and `>>`)
- `terminal-practice/notes-archive.txt` (copied and renamed backup file)

## 8. Commit details

- **Commit message:** `Complete Terminal and file management mission`
- **Branch:** `main`
- **Push status:** Pushed to `origin/main` on GitHub (`rudyy07/digital-detective-8523`)
