
# Bug Notes — Lecture 8

## 1. Average Calculation Bug

- **Evidence:** Expected 90.0 for [80, 90, 100], but buggy code gives 135.0. A single mark can cause ZeroDivisionError.
- **Cause:** The code divides by `len(marks) - 1`.
- **Fix:** Divide by `len(marks)`.

## 2. Pass Boundary Bug

- **Evidence:** A mark of 40 is incorrectly treated as failing.
- **Cause:** The code uses `>` instead of `>=`.
- **Fix:** Use `mark >= PASS_MARK`.

## 3. Distinction Grade Bug

- **Evidence:** A score of 95 returns "First" instead of "Distinction".
- **Cause:** The `>= 60` condition is checked before `>= 90`.
- **Fix:** Check `average >= 90` first.
