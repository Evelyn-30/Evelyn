# Classwork feedback 20261106

**Student:** Evelyn
**Classwork:** Classwork 20261106 — B2.2 Data structures
(arrays · ArrayLists)
**Date:** 2026-11-06 · **Marked:** 2026-11-06
**Answer language:** written in Java — accepted (full credit for correct content).

## Score

**83 / 100**

| Question | Score |
|---|---|
| Q1 — Reading arrays | 28/30 |
| Q2 — Writing array methods and a complete program | 18/30 |
| Q3 Part A — ArrayList | 37/40 |

Full marked pages: `Classwork20261106_marked_p1..p2.png`

## Feedback on incorrect answers

**Q1(b) — 8/10**
- The trace table is correct, but the output is **8 21**: `a[1] = 8`, `a[3] = 21`, not 6 8.

**Q2(b) — 8/20**
- `average()` is correct — that earns the method marks.
- But there is **no main method and no input**, so the program cannot run. The second loop also ends with `return`, which exits the method instead of printing.
- Build the complete program: `main` reads eight values, calls `average` once, prints the result, then loops and prints each value above it with `System.out.print`.

**Q3(c) — 9/12**
- The loop runs **forwards**. Removing an element shifts every later element one place left, so the element that moves into the removed index is never examined.
- Run backwards: `for (int i = nums.size() - 1; i >= 0; i--)` and call `nums.remove(i)`.

## What went well

- **Q1(a), Q1(c) — full marks.** Values, bounds and the runtime-error description are correct.
- **Q2(a) — 10/10.** Correct countEven: signature, loop, MOD test, counter and return in the right place.
- **Q3(a), Q3(b), Q3(d)(i) and Q3(d)(ii) — full marks.** The ArrayList trace, loop output and both explanations are correct.

## Next steps

- Always finish with a complete program: `main`, input, method call, output.
- Return after the loop, not inside it, unless you really want to stop early.
- When removing from an ArrayList, loop **backwards**.
