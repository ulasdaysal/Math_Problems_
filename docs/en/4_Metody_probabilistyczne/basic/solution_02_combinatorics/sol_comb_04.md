# Solution

## Task 4 — Circular Permutations

1. **In how many ways can 7 people sit around a round table?**
   For a circular arrangement of $n$ distinct objects, the number of ways is $(n-1)!$.
   $$(7 - 1)! = 6! = 720$$

2. **In how many ways can they sit if two particular people must sit next to each other?**
   Treat the two people as a single "block". Now we have 6 entities (5 individual people + 1 block) to arrange in a circle.
   The number of circular permutations for 6 entities is $(6 - 1)! = 5!$.
   Within the block, the two people can switch places in $2!$ ways.
   $$5! \times 2! = 120 \times 2 = 240$$

3. **In how many ways can they sit if those two people must sit opposite each other?**
   Place the first particular person at the table (only 1 way because the table is circular and absolute position doesn't matter).
   The seat directly opposite them is entirely fixed for the second particular person (1 way).
   There are 5 remaining seats for the other 5 people, who can now be arranged linearly since the positions are distinct relative to the first two persons.
   $$5! = 120$$
