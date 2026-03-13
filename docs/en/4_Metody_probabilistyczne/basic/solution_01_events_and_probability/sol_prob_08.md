# Solution

## Task 8 — Events and Probabilities in Card Drawing

A standard deck has 52 cards (13 ranks, 4 suits).
* $|\Omega_1| = 52$
* $|\Omega_2| = 52 \times 52 = 2704$ (with replacement)
* $|\Omega_2'| = 52 \times 51 = 2652$ (without replacement)

### One Card Drawn
* $A_1$ (heart): There are 13 hearts. $P(A_1) = \frac{13}{52} = \frac{1}{4}$
* $B_1$ (king): There are 4 kings. $P(B_1) = \frac{4}{52} = \frac{1}{13}$
* $C_1$ (not a face card): Face cards are J, Q, K (12 total). Non-face cards = $52 - 12 = 40$. $P(C_1) = \frac{40}{52} = \frac{10}{13}$

### Two Cards Drawn (with replacement)
* $A_2$ (both are hearts): $|A_2| = 13 \times 13 = 169$. $P(A_2) = \frac{169}{2704} = \frac{1}{16}$
* $B_2$ (both have the same rank): 13 possible ranks $\times$ 4 cards per rank $\times$ 4 cards per rank. $|B_2| = 13 \times 4 \times 4 = 208$. $P(B_2) = \frac{208}{2704} = \frac{1}{13}$
* $C_2$ (at least one is an ace): It's easier to find the complement (no aces). $48 \times 48 = 2304$. $P(\text{no aces}) = \frac{2304}{2704} = \frac{144}{169}$. $P(C_2) = 1 - \frac{144}{169} = \frac{25}{169}$

### Two Cards Drawn (without replacement)
* $A_3$ (both are hearts): $|A_3| = 13 \times 12 = 156$. $P(A_3) = \frac{156}{2652} = \frac{1}{17}$
* $B_3$ (both have the same rank): 13 ranks $\times$ 4 choices for the first $\times$ 3 choices for the second. $|B_3| = 13 \times 4 \times 3 = 156$. $P(B_3) = \frac{156}{2652} = \frac{1}{17}$
* $C_3$ (one king and one queen, in any order): $4 \text{ kings} \times 4 \text{ queens} \times 2 \text{ (orders)} = 32$. $P(C_3) = \frac{32}{2652} = \frac{8}{663}$

* **Additional event definition**: $D$ - both cards are of the same color (e.g., both red or both black).
  There are 26 reds and 26 blacks. Total outcomes without replacement: $(26 \times 25) + (26 \times 25) = 1300$.
  $P(D) = \frac{1300}{2652} = \frac{25}{51}$
