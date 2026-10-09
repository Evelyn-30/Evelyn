# Classwork feedback 20261009

**Student:** Evelyn
**Classwork:** Classwork 20261009 — B2.3 Programming Constructs
(functions · selection · repetition · library functions incl. `Random`)
**Date:** 2026-10-09 · **Marked:** 2026-10-09
**Answer language:** Java (required for DP1).

## Score

**77 / 100**

| Question | Score |
|---|---|
| Q1 — Reading functions and loops | 28/30 |
| Q2 — Library functions: the `Random` class | 13/30 |
| Q3 — Writing a complete program (Collatz) | 36/40 |

Full marked pages: `Classwork20261009_marked_DP1_20261009_Evelyn_p1..p3.png`

**Q3 is the best section of this paper** — 36/40, and your `main` avoids the trap almost everybody
else fell into. Q2 is where the marks went.

## Feedback on incorrect answers

**Q1 (d) — 4/6**
- Both halves of the contrast are stated correctly. What is missing is the *"an example of each
  **from this question**"* requirement: use `countUp()` for the `void` case (it returns nothing, it
  only prints) and `area()` or `label()` for the value case.
- Also, "like int / String" reads as though `int` and `String` are things a `void` method does. A
  `void` method's return type is literally `void` — it hands nothing back.

**Q2 (a) (i) — 0/2**
- `nextInt(6)` returns **0 to 5**, not 1 to 6. The argument is the **upper bound** and it is **not
  included** — slide 42 calls this `[0, <upper_bound>)`.

**Q2 (a) (ii) — 0/2**
- The program prints **1 to 6** (that is 0–5 with 1 added), not 2 to 7.

**Q2 (a) (iii) — 1/2**
- The loop runs four times — correct. The other half of the mark is that each call produces a **new**
  random value.

**Q2 (a) (iv) — 0/4**
- This part asks for the **advantages of using library functions** (slide 38), not for code. You
  wrote a `Random` example instead, so no marks could be awarded.
- The answer wanted: **reuse of code** (essential functions are common to many applications, so they
  do not have to be written again) and **improve reliability** (library code is thoroughly tested and
  can be relied on).

**Q2 (b) (i) — 1/5**
- Three problems in four lines:
  1. `roll()` takes **no parameter** — you wrote `roll(6)`.
  2. `rnd.nextInt(6);` on its own throws the number away; nothing is done with it.
  3. `return rnd;` returns the **`Random` object**, not an `int`. The method is declared
     `int roll()`, so this will not compile.
- Correct: `public static int roll() { return rnd.nextInt(6) + 1; }`

**Q2 (c) (i) — 1/3**
- The range — with "upper bound not included" — is right. The second half of the question ("describe
  the **shape**") was not answered: it is a **circle of radius 0.5 centred at (0.5, 0.5)**. The 0.25
  in the test is r².

**Q2 (c) (iii) — 1/3**
- "More accurate" is not the reason. `cnt` and `N` are both `int`, so `4 * cnt / N` uses **integer
  division** and the fractional part is discarded. Writing `4.0` makes Java use `double` arithmetic.

**Q3 (c) — 4/6**
- Correct as far as it goes: `for` needs to know how many turns the loop will take, `while` does not.
- Add the positive half — the loop has to keep going **until a condition becomes true** (`n == 1`),
  and that is exactly what a condition-controlled loop is for.

**Q3 (d) — 14/16**
- Very good. Keeping `n` untouched in `current` is exactly the right move — it means `steps(n)` still
  works, and your sequence comes out complete (`6 3 10 5 16 8 4 2 1`).
- Two small things:
  1. `System.out.print(":")` puts a stray `:` on the screen before the sequence. Delete it.
  2. The question asks you to **show the expected output for 6 and 7** — neither was written down.

## What went well

- **Q3 is a strong section.** `nextTerm`, `steps` and `main` are all correct — including the
  "keep the original value" trick that Alex, Henry and Frankie all missed.
- **Q2 (b) (ii)** — calling `roll()` five times in a loop and joining with a space is exactly right.
- **Q2 (c) (ii)** — your answer is short but complete: the point ratio approximates the area ratio,
  `circle/square ≈ π/4`, so `π ≈ 4 × cnt/N`. That is a full-mark answer.
- **Q1 (a), (b), (c)** — all three outputs exact.

## Next steps

1. **Learn the `Random` API precisely.** This is the single biggest loss on the paper (Q2(a)(i)(ii)
   and Q2(b)(i) together are 8 marks). Know by heart:
   - `nextInt(n)` → whole number in **`[0, n)`** — the bound is **excluded**;
   - `nextDouble()` → `[0.0, 1.0)`;
   - to get 1–6: `rnd.nextInt(6) + 1`.
2. **Read what the question is actually asking.** Q2(a)(iv) asked for *advantages of library
   functions* and got code; Q1(d) asked for *examples from this question* and got none. Two parts
   scored 0 for answering a different question.
3. **Integer division.** Whenever a literal meets `int` variables and the answer must be a fraction,
   write one of them as a `double` (`4.0`, not `4`).
4. **Finish the paper.** Q3(d) asked for two expected outputs; that is a mark given away.
