# Solution

## Task 2 — Permutations

1. **In how many ways can 8 different books be arranged on a shelf?**
   This is a basic permutation of 8 distinct objects.
   $$P_8 = 8! = 40,320$$

2. **In how many ways can 8 people sit in a row if two particular people must sit next to each other?**
   Treat the two particular people as a single "block" or "super-person". 
   Now we have 7 entities (6 individual people + 1 block) to arrange, which can be done in $7!$ ways.
   Within the block, the two people can be arranged in $2!$ ways.
   By the product rule, the total number of ways is:
   $$7! \times 2! = 5,040 \times 2 = 10,080$$

3. **In how many ways can they sit if those two people must not sit next to each other?**
   We can use the complement method: subtract the number of ways they sit together from the total number of unrestricted arrangements.
   Total arrangements = $8!$
   Arrangements where they sit together = $7! \times 2!$
   $$8! - (7! \times 2!) = 40,320 - 10,080 = 30,240$$

4. **In how many ways can 10 questions in a test be ordered if the first question is fixed?**
   Since the first position is already occupied by a specific question, we only need to arrange the remaining 9 questions in the remaining 9 spots.
   $$P_9 = 9! = 362,880$$
