# Solution

## Task 11 — Modeling Outcomes

### 1. Distinguishable vs Indistinguishable Objects

A box contains 4 red, 4 blue, and 3 green balls (11 total).

1. **How many linear arrangements of all 11 balls are possible if balls of the same color are treated as indistinguishable?**
   This is a permutation with repeated elements (a multiset permutation).
   $$\frac{11!}{4! \times 4! \times 3!} = \frac{39,916,800}{24 \times 24 \times 6} = 11,550$$

2. **How many arrangements are possible if every ball is individually labeled?**
   If every ball is distinct, it is a standard permutation of 11 objects.
   $$11! = 39,916,800$$

3. **Explain why the answers in parts (1) and (2) are different.**
   In part (1), swapping the positions of two balls of the same color produces the exact same recorded outcome because the observer cannot tell them apart. In part (2), the observer will notice the swap of $R_1$ and $R_2$, hence there are more ways to arrange them since every swap creates a new valid sequence.

---

### 2. Recording Order vs Ignoring Order

Three balls are drawn without replacement from the same box.

1. **How many outcomes are possible if only the set of colors is recorded (order ignored)?**
   We only care about combinations of colors. Since we need to pick 3 balls, and we have at least 3 balls of each of the 3 available colors, this is equivalent to drawing 3 items from 3 types with replacement (combinations with repetition). 
   Possible combinations: {R,R,R}, {B,B,B}, {G,G,G}, {R,R,B}, {R,R,G}, {B,B,R}, {B,B,G}, {G,G,R}, {G,G,B}, {R,B,G}.
   Total number of multisets: $\binom{3+3-1}{3} = \binom{5}{3} = 10$.

2. **How many outcomes are possible if the sequence of colors is recorded?**
   There are $3$ colors to choose from for each of the $3$ positions. Since we have enough balls of each color to fill all $3$ positions without exhausting a color, we can form sequences with repetition.
   $$3^3 = 27$$

3. **Explain why recording the order changes the counting model.**
   When recording order, the sequence $(R, B, R)$ and $(R, R, B)$ lead to two mathematically distinct outcomes. If order is ignored, we only observe that "two reds and one blue were drawn", so they map to the same outcome set $\{R, R, B\}$.

---

### 3. PIN Code vs Number

1. **How many different 4-digit PIN codes are possible if repetition is allowed?**
   $$10^4 = 10,000$$

2. **Consider 4-digit numbers, where the first digit cannot be zero. How many such numbers exist?**
   $9 \times 10^3 = 9,000$

3. **Explain why a PIN code and a 4-digit number are counted using different rules.**
   A proper integer number cannot start with $0$ (e.g., $0123$ is just $123$, a 3-digit number). A PIN code is a *sequence string* of characters rather than an integer, therefore characters like $0$ are perfectly valid at the very first position.

4. **Explain why the codes 1234 and 4321 must be treated as different outcomes.**
   For a PIN string, the position of each digit matters strictly. The system verifies exactly which digit was typed first, second, etc. They represent two completely different passwords because they are a sequence, not an unordered combination.
