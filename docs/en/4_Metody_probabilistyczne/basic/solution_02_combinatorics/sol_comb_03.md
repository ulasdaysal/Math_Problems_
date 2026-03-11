# Solution

## Task 3 — Permutations with Repeated Elements

1. **How many distinct arrangements of the word MISSISSIPPI are possible?**
   The word has 11 letters in total: 1 M, 4 I, 4 S, and 2 P.
   The number of distinct permutations is:
   $$\frac{11!}{1! \times 4! \times 4! \times 2!} = \frac{39,916,800}{1 \times 24 \times 24 \times 2} = 34,650$$

2. **How many distinct arrangements of STATISTICS are possible?**
   The word has 10 letters in total: 3 S, 3 T, 1 A, 2 I, 1 C.
   The number of distinct permutations is:
   $$\frac{10!}{3! \times 3! \times 1! \times 2! \times 1!} = \frac{3,628,800}{6 \times 6 \times 1 \times 2 \times 1} = 50,400$$

3. **How many of the arrangements of STATISTICS start with the letter S?**
   If the first letter is fixed as 'S', we only need to arrange the remaining 9 letters: 2 S, 3 T, 1 A, 2 I, 1 C.
   The number of distinct permutations for these remaining 9 letters is:
   $$\frac{9!}{2! \times 3! \times 1! \times 2! \times 1!} = \frac{362,880}{2 \times 6 \times 1 \times 2 \times 1} = 15,120$$
