# Solution

## Task 8 — Sequences with Repetition

1. **How many 5-digit PIN codes are possible if digits may repeat?**
   Each of the 5 positions can be any of the 10 digits (0 through 9).
   $$10^5 = 100,000$$

2. **How many such codes contain at least one repeated digit?**
   We find the complement: total possible PIN codes minus PIN codes with *no* repeated digits.
   Total codes: $10^5 = 100,000$
   Codes with no repeated digits (k-permutation): $P(10, 5) = 10 \times 9 \times 8 \times 7 \times 6 = 30,240$
   $$100,000 - 30,240 = 69,760$$

3. **How many such codes have all digits different?**
   As calculated above, this is an ordered selection without repetition from 10 digits.
   $$P(10, 5) = \frac{10!}{(10-5)!} = 10 \times 9 \times 8 \times 7 \times 6 = 30,240$$
