# Solution

## Task 5 — Combinations

1. **A committee of 4 people is chosen from 12 students. How many committees are possible?**
   Order does not matter in a committee, so this is a combination.
   $$\binom{12}{4} = \frac{12!}{4! \times 8!} = \frac{12 \times 11 \times 10 \times 9}{4 \times 3 \times 2 \times 1} = 495$$

2. **How many committees contain a particular student?**
   If one specific student must be in the committee, we have 1 "guaranteed" spot, and we need to choose the remaining 3 members from the remaining 11 students.
   $$\binom{11}{3} = \frac{11!}{3! \times 8!} = \frac{11 \times 10 \times 9}{3 \times 2 \times 1} = 165$$

3. **How many committees contain at least one of two particular students?**
   Let the two particular students be A and B. We can use the complement method: Total combinations minus combinations that definitely do not contain A and B.
   Total committees without A and B (choosing 4 from the remaining 10): $\binom{10}{4} = 210$
   $$\binom{12}{4} - \binom{10}{4} = 495 - 210 = 285$$

4. **How many committees contain exactly two women if the group consists of 7 men and 5 women?**
   We must choose exactly 2 women from the group of 5 women, and the remaining 2 people from the group of 7 men.
   $$\binom{5}{2} \times \binom{7}{2} = \left(\frac{5 \times 4}{2 \times 1}\right) \times \left(\frac{7 \times 6}{2 \times 1}\right) = 10 \times 21 = 210$$
