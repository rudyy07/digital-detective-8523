# Mission 5 — Numbers and data

## 1. Task / objective

The objective of Mission 5 was to practise manual number-system conversions (decimal, binary, and hexadecimal), verify the calculations using Python 3, build a beginner-friendly `number_converter.py` script and test it with at least three positive numbers, and explain how text is stored using ASCII and UTF-8.

## 2. Work completed

- Completed step-by-step manual conversions for all seven questions in Task 5.1 and explained the positional-value method.
- Verified every conversion in Python 3 using built-in functions (`bin()`, `int()`, and `hex()`).
- Created and tested `mission-05-numbers-data/number_converter.py` with three positive inputs (`13`, `25`, and `255`).
- Documented ASCII, UTF-8, the ASCII codes of `A` and `a`, why encoding standards are needed, and an example character outside basic ASCII.

### Task 5.1 — Convert numbers by hand

**Positional-value method:** In any number base $b$, each digit position from right to left has a place value equal to $b^0, b^1, b^2, b^3, \dots$ (units, base, base squared, and so on). To convert binary (base 2) or hexadecimal (base 16) to decimal (base 10), multiply each digit by its place value and add the results together. To convert decimal to binary, repeatedly divide by 2 and read the remainders from bottom to top.

| Question | Your working and answer |
|---|---|
| Convert decimal 13 to binary. | Divide repeatedly by 2: `13 / 2 = 6` rem `1`; `6 / 2 = 3` rem `0`; `3 / 2 = 1` rem `1`; `1 / 2 = 0` rem `1`. Reading remainders bottom to top gives **`1101`**. |
| Convert decimal 25 to binary. | Divide repeatedly by 2: `25 / 2 = 12` rem `1`; `12 / 2 = 6` rem `0`; `6 / 2 = 3` rem `0`; `3 / 2 = 1` rem `1`; `1 / 2 = 0` rem `1`. Reading remainders bottom to top gives **`11001`**. |
| Convert binary 1010 to decimal. | `(1 × 2^3) + (0 × 2^2) + (1 × 2^1) + (0 × 2^0) = (1 × 8) + (0 × 4) + (1 × 2) + (0 × 1) = 8 + 0 + 2 + 0 =` **`10`**. |
| Convert binary 1101 to decimal. | `(1 × 2^3) + (1 × 2^2) + (0 × 2^1) + (1 × 2^0) = (1 × 8) + (1 × 4) + (0 × 2) + (1 × 1) = 8 + 4 + 0 + 1 =` **`13`**. |
| Convert hexadecimal A to decimal. | In hex, `A = 10` in the `16^0` (ones) place: `10 × 16^0 = 10 × 1 =` **`10`**. |
| Convert hexadecimal 1F to decimal. | In hex, `F = 15`: `(1 × 16^1) + (15 × 16^0) = 16 + 15 =` **`31`**. |
| Convert binary 1111 to hexadecimal. | First find the value of the 4-bit group: `(1 × 8) + (1 × 4) + (1 × 2) + (1 × 1) = 15`. In hexadecimal, `15` is **`F`**. |

### Task 5.2 — Verify using Python

| Expression tested | Python output | Matches manual calculation? |
|---|---|---|
| `bin(13)` | `'0b1101'` | Yes (`1101`; `0b` is Python's binary prefix) |
| `bin(25)` | `'0b11001'` | Yes (`11001`) |
| `int("1010", 2)` | `10` | Yes (`10`) |
| `int("1101", 2)` | `13` | Yes (`13`) |
| `int("A", 16)` | `10` | Yes (`10`) |
| `int("1F", 16)` | `31` | Yes (`31`) |
| `hex(int("1111", 2))` | `'0xf'` | Yes (`F`; `0x` is Python's hexadecimal prefix) |
| `hex(31)` | `'0x1f'` | Yes (`1F` in decimal is `31`) |

### Task 5.3 — Build a small number converter

I created `mission-05-numbers-data/number_converter.py` and ran it from Terminal with three positive integers:

| Test number | Binary output | Hexadecimal output |
|---|---|---|
| `13` | `0b1101` | `0xd` |
| `25` | `0b11001` | `0x19` |
| `255` | `0b11111111` | `0xff` |

**How the Python functions work:**
- `input()` displays a prompt to the user and reads whatever the user types as a text string.
- `int()` converts that text string into a whole-number integer so Python can work with it numerically.
- `bin()` takes an integer and returns its binary representation as a string starting with `0b`.
- `hex()` takes an integer and returns its hexadecimal representation as a string starting with `0x`.

### Task 5.4 — How is text stored?

- **ASCII:** A 7-bit character-encoding standard (codes `0` to `127`) that represents basic English letters, digits, punctuation marks, and control characters.
- **UTF-8:** A variable-length encoding for Unicode that stays compatible with ASCII for the first `128` characters while using 1 to 4 bytes to represent characters from almost every writing system, symbols, and emojis.
- **ASCII decimal values (verified in Python with `ord()`):**
  - Uppercase `A`: `65`
  - Lowercase `a`: `97`
- **Why an encoding standard is needed:** Computers only store binary numbers (`0`s and `1`s), so a shared encoding standard is needed to map every letter or symbol to an agreed numeric code so different programs and devices display the same text.
- **One character outside basic ASCII:** The Indian Rupee sign `₹` (Unicode code point `8377` in decimal, checked with `ord("₹")`).

## 3. Commands / tools used

- `python3 -c '...'` — Ran Python verification expressions for `bin()`, `int(..., 2)`, `int(..., 16)`, `hex()`, and `ord()`.
- `python3 mission-05-numbers-data/number_converter.py` — Tested the number converter with inputs `13`, `25`, and `255`.
- Python built-in functions `input()`, `int()`, `bin()`, `hex()`, and `ord()`.

## 4. My understanding

Inside a computer, both numbers and text are stored using bits (`0` and `1`). Binary (base 2) matches how hardware stores bits, while hexadecimal (base 16) gives humans a shorter way to read groups of four bits. Character encodings such as ASCII and UTF-8 turn letters and symbols into consistent numbers so text can be saved and shared reliably.

## 5. Difficulties faced

No major difficulties.

## 6. How I resolved them

Not applicable.

## 7. Evidence / files

- `mission-05-numbers-data/number_converter.py` (Python script converting a decimal integer to binary and hexadecimal)
- `mission-05-numbers-data/README.md` (manual steps, Python checks, converter test results, and text-encoding answers)

## 8. Commit details

- **Commit message:** `Build number converter and practise data representation`
- **Branch:** `main`
- **Push status:** Pushed to `origin/main` on GitHub (`rudyy07/digital-detective-8523`)
