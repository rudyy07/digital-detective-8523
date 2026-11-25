# Mission 4 — How programs run

## 1. Task / objective

The objective of Mission 4 was to write and run a one-line Python 3 program (`hello.py`) that prints `Hello from Python`, and to compare how compilers and interpreters translate and execute programs.

## 2. Work completed

- Created `mission-04-programs/hello.py` containing `print("Hello from Python")`.
- Executed the script in Terminal using `python3 mission-04-programs/hello.py` and verified that it printed `Hello from Python`.
- Completed the compiler vs interpreter comparison table and wrote a short explanation of their differences.

### Task 4.1 — Create and run a Python program

Command run:
```bash
python3 mission-04-programs/hello.py
```

Observed output:
```text
Hello from Python
```

### Task 4.2 — Compare compiler and interpreter

| Point | Compiler | Interpreter |
|---|---|---|
| When translation / execution happens | Translates the entire source code before the program is run. | Reads and executes instructions at runtime without producing a standalone binary first. |
| Typical output | Machine code or an executable file (or bytecode) saved to disk. | Direct program output as instructions run step by step. |
| One example | C (`gcc` / `clang`) | Python (`python3` / CPython) |
| One advantage | The compiled program usually runs faster because translation is already done. | Easier to test small changes quickly and see errors immediately at runtime. |

As shown in the comparison table, a compiler translates a whole program ahead of time into another form such as machine code before you run it, while an interpreter reads and carries out instructions while the program is running. This means compiled programs typically run faster once built, whereas interpreted workflows let you edit a script like `hello.py` and run it right away with `python3`. In practice, many language implementations combine both ideas—for example, standard Python (`CPython`) first compiles `.py` source code into bytecode and then interprets that bytecode inside the Python virtual machine.

## 3. Commands / tools used

- `python3 mission-04-programs/hello.py` — Ran the Python script with Python 3 (`Python 3.14.6`) and checked its output.
- Text editor — Wrote `hello.py` and documented the comparison in `README.md`.

## 4. My understanding

Writing `hello.py` and running it directly with `python3` showed me how fast the edit-and-run cycle is when you do not have to run a separate build step first. Understanding compilers and interpreters also explains why some languages produce standalone executable files while others run through a runtime tool, and why modern runtimes often mix compilation (to bytecode) with interpretation.

## 5. Difficulties faced

No major difficulties.

## 6. How I resolved them

Not applicable.

## 7. Evidence / files

- `mission-04-programs/hello.py` (one-line Python 3 program printing `Hello from Python`)
- `mission-04-programs/README.md` (program output and compiler/interpreter comparison)

## 8. Commit details

- **Commit message:** `Compare compilers and interpreters`
- **Branch:** `main`
- **Push status:** Pushed to `origin/main` on GitHub (`rudyy07/digital-detective-8523`)
