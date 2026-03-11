# Solution

## Task 7 — k-Permutations (Ordered Selections Without Repetition)

1. **In how many ways can the first three places be assigned among 12 runners?**
   We are selecting 3 runners out of 12 and ordering them (gold, silver, bronze). This is an ordered selection without repetition.
   $$P(12, 3) = \frac{12!}{(12-3)!} = 12 \times 11 \times 10 = 1,320$$

2. **How many 4-digit numbers with distinct digits can be formed from the digits 1–9?**
   We are selecting 4 unique digits from a set of 9, and their arrangement matters (since $1234 \neq 4321$).
   $$P(9, 4) = \frac{9!}{(9-4)!} = 9 \times 8 \times 7 \times 6 = 3,024$$

3. **How many of these numbers are divisible by 5?**
   From the digits $1$ to $9$, a number is divisible by 5 only if it ends in 5.
   We affix the digit '5' to the last position (1 way). For the remaining 3 positions, we select from the 8 unused digits without repetition.
   $$1 \times P(8, 3) = \frac{8!}{(8-3)!} = 8 \times 7 \times 6 = 336$$
