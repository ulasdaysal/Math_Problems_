# Solution

## Task 9 — Digit Restrictions

1. **How many 5-digit numbers exist?**
   A 5-digit number cannot start with $0$ (otherwise it would be a 4-digit number or shorter).
   The first digit can be any of $1-9$ ($9$ choices).
   The remaining four digits can each be any of $0-9$ ($10$ choices each).
   $$9 \times 10^4 = 9 \times 10,000 = 90,000$$

2. **How many of them are even?**
   An even number must end in $0, 2, 4, 6, \text{ or } 8$ ($5$ choices).
   The first digit must be $1-9$ ($9$ choices).
   The remaining three middle digits can be anything ($10$ choices each).
   $$9 \times 10^3 \times 5 = 9 \times 1000 \times 5 = 45,000$$

3. **How many contain no repeated digits?**
   This is equivalent to choosing $5$ distinct digits.
   The first digit cannot be $0$ ($9$ choices).
   The second digit can be any of the remaining $9$ digits (including $0$, but excluding the first digit).
   The third digit has $8$ choices, the fourth has $7$, and the fifth has $6$.
   $$9 \times 9 \times 8 \times 7 \times 6 = 27,216$$

4. **How many contain at least one repeated digit?**
   By the complement principle: Total 5-digit numbers minus 5-digit numbers with *no* repeated digits.
   $$90,000 - 27,216 = 62,784$$
