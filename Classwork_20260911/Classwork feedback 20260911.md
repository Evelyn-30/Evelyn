# Classwork feedback 20260911

**Student:** Evelyn
**Classwork:** Classwork 01 — B2.1 Programming Fundamentals (variables, data types, substring manipulation)
**Date:** 2026-09-11
**Marked:** 2026-09-14

## Score

**31 / 100**

| Question | Score |
|---|---|
| Q1 — data types, naming, print vs println | 9/12 |
| Q2 — string manipulation (tracing) | 7/14 |
| Q3 — scope of variables + tracing | 4/16 |
| Q4 — debugging and scope | 0/14 |
| Q5 — program using all data types | 11/20 |
| Q6 — substring-manipulation program | 0/24 |

Note: `Classwork01_20260911_marked_p1.png` and `_p2.png` in this folder show
every mark and deduction in place on your script.

## Feedback on incorrect answers

**Q1 (b) (-3 marks)**
- The second and fourth items are wrong: `firstPlace` is **VALID** (it starts
  with a letter and is not a keyword) and `studentName` is **VALID** as well.
  You marked all four INVALID.
- No reasons were given, and the question says *"State, **giving a reason**, …"*.

**Q1 (c) — correct.** Both output lines are right:
```
Hello World
!
```
and your explanation of `print()` vs `println()` is right too.

**Q2 (a) (-2 marks)**
- You wrote `21`; the correct answer is `22`. `"Information"` (11) + the space
  (1) + `"Technology"` (10) = 22.

**Q2 (d) (-2 marks)**
- You wrote "should start from a number to 12" — that describes `substring`
  syntax rather than giving the output. `s.substring(12)` takes everything from
  index 12 **to the end**, so the output is `Technology`.

**Q2 (e) (-2 marks)**
- You wrote `12,21`. `indexOf` returns a **single integer** — the starting index
  of the match, which is `12`. (`println` prints `12`, not two numbers.)

**Q2 (h) (-1 mark)**
- You described what `replace()` does rather than giving the output. The answer
  is the whole new string: `Computer Technology`. Note that `replace` changes
  the *pattern* `"Information"` into `"Computer"` and leaves the rest untouched.

**Q3 (a) — no trace table on the script (-10 marks)**
- You answered Q3 (b) but there is **no trace table** anywhere on either page.
  The question asks you to *"complete the trace table to show the value of each
  variable and the output at every step"* — worth 10 marks.
- The expected values: `x` = 5, 8, 8, 8, 8, 8, 8; `y (global)` = 2 throughout;
  `y (local)` = –, –, 10, 10, 13, 13, –; outputs `Inside update(): 8 10`,
  `Inside modify(): 8 13`, `Outside: 8 2`.

**Q3 (b) (-2 marks)**
- You correctly explained what local and global variables are. To answer *why the
  two printed values differ*, you also need to say what the values **are**: inside
  `update()` the name `y` refers to the local variable (`10`), and the global `y`
  is never changed, so `main()` prints `2`.

**Q4 (a) (-6 marks)**
- "`increaseScore` is invalid" is not the reason. The problem is the line
  `int score = score + 10;`. It is **self-referential**: `int score` declares a
  new *local* variable, and the `score` on the right-hand side refers to that
  same local variable, which has not yet been given a value. The compiler
  reports *"variable score might not have been initialized"*.

**Q4 (b) (-8 marks)**
- You wrote `increase Score` and `10 + 0`, which is not a method. The expected
  answer removes the `int` so that the name refers to the field:
  ```java
  static void increaseScore() {
      score = score + 10;
  }
  ```
  The output is `Final score: 10`.

**Q5 (-9 marks)**
- All five data types are declared — that part is worth full marks. Deductions:
  - `char letter = "A";` uses **double quotes**. A `char` takes **single**
    quotes: `char letter = 'A';` (double quotes are for `String`).
  - `System.out.println(age, name, height);` is not valid Java — `println`
    takes a **single** argument. Use `+` to join them:
    `System.out.println(age + " " + name + " " + height);`. This is exactly the
    concatenation the question asks for, and it was missing.
  - `is_student` uses an underscore; Java variables use camelCase (`isStudent`).
  - You used `println` only; the question asks for a **mixture** of `print()`
    and `println()`.
  - Only one value is output, and no expected output is shown.

**Q6 — only (a) attempted, and incorrect (-24 marks)**
- `fullName.substring(1, 15)` is not right. `fullName` is
  `"  Michael Jackson  "` (two leading spaces). `substring(1, 15)` starts one
  character *before* the `M` and stops in the middle of "Jackson", giving
  `` " Michael Jacks" ``.
- (a) asks you to remove the leading/trailing spaces — that is `trim()`.
  The rest of the program then follows from the trimmed name.
- (b)–(f) were not attempted. Note the question specifically requires
  `substring()`, `indexOf()`, `toUpperCase()`, `replace()` and `+`.

## What went well

- Q1 (a): all four data types correct.
- **Q1 (c) is fully correct** — both output lines *and* the explanation. This was
  a trap question (`print`/`println` mixed, with the `!` landing on line 2) and
  you handled it.
- Q2: `charAt(6)`, `substring(0, 11)` and `indexOf("xyz") = -1` were all correct.
- Q5: you are the only student who used `boolean`, `char`, `int`, `double` **and**
  `String` — the data-type knowledge is clearly there.

## Next steps

1. **Answer every question.** Q3 (a) (10 marks) and Q6 (b)–(f) (24 marks) were
   not attempted — that is a third of the paper.
2. **`char` uses single quotes** (`'A'`); double quotes are for `String`.
3. **`println` takes one argument** — join values with `+`.
4. `substring(n)` goes from index `n` to the end of the string.
5. When a string has leading spaces, `trim()` it first, or every index will be off.

---
_Marks and margin notes are also marked up on your scanned script
(`Classwork01_20260911_marked_p1.png`, `_p2.png`)._
