# Solution

## Task 10 — Urn Models

The urn contains a total of $5 + 4 + 3 = 12$ balls.

1. **Three balls are drawn without replacement. How many samples are possible if order is ignored?**
   We are selecting a subset of 3 balls out of 12 (since each ball is drawn physically, we treat them as distinct elements for the sample space). This is a combination.
   $$\binom{12}{3} = \frac{12!}{3! \times 9!} = \frac{12 \times 11 \times 10}{6} = 220$$

2. **How many samples contain exactly two red balls?**
   We must choose exactly $2$ out of the $5$ red balls, and $1$ out of the $7$ non-red balls (blue and green).
   Order doesn't matter:
   $$\binom{5}{2} \times \binom{7}{1} = 10 \times 7 = 70$$

3. **Three balls are drawn and the order of colors is recorded. How many outcomes are possible?**
   Assuming treating individual balls as distinct to keep probabilities uniform, we select 3 balls out of 12 respecting order. This is a k-permutation:
   $$P(12, 3) = 12 \times 11 \times 10 = 1,320$$

4. **How many outcomes contain exactly two red balls?**
   The positions of the two red balls can be chosen in $\binom{3}{2} = 3$ ways. E.g., $(R, R, X), (R, X, R), \text{ or } (X, R, R)$.
   For any specific arrangement pattern, the number of ways to pick the actual 2 red balls in order is $P(5, 2) = 5 \times 4 = 20$.
   The number of ways to pick the 1 non-red ball is $P(7, 1) = 7$.
   $$3 \times 20 \times 7 = 420$$
