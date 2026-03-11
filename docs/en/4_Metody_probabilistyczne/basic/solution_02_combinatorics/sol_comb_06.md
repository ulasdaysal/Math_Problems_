# Solution

## Task 6 — Combinations in Card Problems

A standard deck contains 52 cards (13 hearts, 39 non-hearts, 12 face cards, 40 non-face cards).

1. **In how many ways can 5 cards be drawn so that the hand contains exactly 2 hearts?**
   We select exactly 2 cards from the 13 available hearts, and the remaining 3 cards from the 39 available non-hearts.
   $$\binom{13}{2} \times \binom{39}{3} = 78 \times 9,139 = 712,842$$

2. **In how many ways can a 5-card hand contain at least one heart?**
   Using the complement method, we subtract the number of hands with no hearts from the total number of possible 5-card hands.
   Total hands: $\binom{52}{5} = 2,598,960$
   Hands with zero hearts (all 5 drawn from the 39 non-hearts): $\binom{39}{5} = 575,757$
   $$\binom{52}{5} - \binom{39}{5} = 2,598,960 - 575,757 = 2,023,203$$

3. **In how many ways can a 5-card hand contain no face cards (J, Q, K)?**
   There are 3 face cards in each of the 4 suits, making 12 face cards in total. Thus, there are 40 non-face cards. To get a hand with no face cards, we must draw all 5 cards from the 40 non-face cards.
   $$\binom{40}{5} = \frac{40!}{5! \times 35!} = 658,008$$
