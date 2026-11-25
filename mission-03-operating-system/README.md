# Mission 3 — Understand the operating system

## 1. Task / objective

The objective of Mission 3 was to inspect my macOS environment using Terminal commands without publishing private details, understand running processes and process identifiers (PIDs), compare absolute and relative paths, read file permissions without modifying system permissions, and explain the core responsibilities of an operating system.

## 2. Work completed

- Inspected macOS version, kernel/architecture, current user identity (redacted), disk storage space, and a live system activity snapshot.
- Viewed running processes and their PIDs using `ps` and `top`.
- Navigated between the repository root and `terminal-practice/` to observe absolute vs relative paths.
- Checked file permissions on `terminal-practice/notes.txt` using `ls -l` without changing any permissions.
- Completed the permissions table and the operating-system responsibilities table.

### Task 3.1 — Explore your operating system

| Information explored | What it tells you | Your observation (privacy-safe) |
|---|---|---|
| Operating system / system details (`sw_vers`, `uname -srm`) | Shows the OS name, version, kernel, and CPU architecture | `macOS 27.2.1` (`BuildVersion: 26B131`), kernel `Darwin 27.2.0 arm64` |
| Current account identity (`whoami`) | Shows which local user account the Terminal session is running as | `[redacted]` |
| Available and used storage (`df -h /`) | Shows total capacity, used space, and available free space on the mounted root filesystem | Total `460Gi`, system volume `13Gi` used, `225Gi` available on `/` |
| System activity snapshot (`top -l 1 -n 5`) | Gives a quick summary of total processes, CPU usage, and physical memory usage | `560 total` processes (`3 running, 557 sleeping`), CPU `4.65% user, 10.41% sys, 84.93% idle`, `15G used` memory |

### Task 3.2 — Understand processes

- **What is a process?** A process is an active instance of a program currently loaded in memory and managed by the operating system.
- **What does the PID column represent?** PID stands for Process Identifier — a unique number assigned by the operating system to track and manage each running process.
- **Two examples of processes observed on my computer:**
  1. `launchd` (PID `1`) — macOS background system manager that starts and manages other services.
  2. `zsh` (PID `54488`) — the Terminal shell process running my commands (and `mdworker_shared`, PID `54487`, a background Spotlight indexing process).

### Task 3.3 — Understand paths and permissions

When navigating from the repository root into `terminal-practice` and running `pwd`, the displayed path changed from `/Users/[redacted]/Documents/metabrainz/digital-detective-8523` to `/Users/[redacted]/Documents/metabrainz/digital-detective-8523/terminal-practice`.

- **Absolute path vs relative path:** An absolute path gives the complete location starting from the root `/` directory and works from any current folder. A relative path describes a location relative to whichever folder you are currently inside.
  - **Absolute path example:** `/Users/[redacted]/Documents/metabrainz/digital-detective-8523/terminal-practice/notes.txt`
  - **Relative path example:** `terminal-practice/notes.txt` (when working inside `digital-detective-8523`)

Running `ls -l terminal-practice/notes.txt` produced:
`-rw-r--r--@ 1 [redacted] staff 82 Nov 25 09:10 terminal-practice/notes.txt`

The first character `-` means it is a regular file. The next three characters (`rw-`) show the **owner's** permissions: the owner can **read (`r`)** and **write (`w`)** the file, and **cannot execute (`-`)** it.

| Permission | Meaning | Example |
|---|---|---|
| `r` — Read | Allows a file's contents to be read (or a folder's names to be listed). | Reading `notes.txt` with `cat` |
| `w` — Write | Allows a file to be modified or a folder's contents to be changed. | Appending a line to `notes.txt` |
| `x` — Execute | Allows a file to be run as a program; on a directory, allows entering/traversing it. | Running a shell script or using `cd` into a folder |

### Task 3.4 — Explain operating-system responsibilities

| OS responsibility | Your explanation | Example |
|---|---|---|
| Process management | Starts, schedules, pauses, and stops running programs while assigning CPU time and PIDs. | Running `zsh`, `top`, and background daemons like `launchd` at the same time |
| Memory management | Allocates RAM to active processes, keeps their memory isolated, and reclaims memory when they close. | Tracking `15G` used physical memory across running apps and services |
| Device management | Communicates with and controls hardware components such as the keyboard, display, and SSD using drivers. | Sending keystrokes from the Mac keyboard to the Terminal window |
| File management | Organizes data into files and directories on storage drives and tracks file metadata and free space. | Storing `notes.txt` inside `terminal-practice/` and reporting `225Gi` available in `df -h` |
| User interface / shell | Provides a way for users to interact with the computer using windows/icons (GUI) or typed commands (CLI). | Typing `ls` and `pwd` in `zsh` inside macOS Terminal |
| Security and permissions | Controls which user account can read, write, or execute files and keeps user accounts separate. | `notes.txt` allowing write access (`rw-`) to the owner `[redacted]` and read-only (`r--`) to others |

## 3. Commands / tools used

- `sw_vers` — Displayed macOS product name, version, and build number.
- `uname -srm` — Displayed kernel name (`Darwin`), kernel version, and hardware architecture (`arm64`) without printing the computer hostname.
- `whoami` — Checked the active user account name (kept redacted here).
- `df -h /` — Showed human-readable used and available disk space on `/`.
- `top -l 1 -n 5` — Captured a one-sample snapshot of processes, CPU usage, and memory usage.
- `ps -eo pid,comm` — Listed process IDs (PIDs) and command names.
- `pwd`, `cd`, and `ls -l` — Checked absolute vs relative paths and inspected owner file permissions.

## 4. My understanding

The operating system acts as the coordinator between the user, applications, and hardware. Even when the laptop seems idle, hundreds of processes (`560` in my snapshot) are running or sleeping with unique PIDs, sharing CPU and memory safely. File permissions (`r`, `w`, `x`) and user accounts ensure that files can only be read, modified, or executed by authorized users.

## 5. Difficulties faced

No major difficulties.

## 6. How I resolved them

Not applicable.

## 7. Evidence / files

- `mission-03-operating-system/README.md` (privacy-redacted OS observations, process notes, path/permission checks, and OS responsibilities table)

## 8. Commit details

- **Commit message:** `Document operating system and file management`
- **Branch:** `main`
- **Push status:** Pushed to `origin/main` on GitHub (`rudyy07/digital-detective-8523`)
