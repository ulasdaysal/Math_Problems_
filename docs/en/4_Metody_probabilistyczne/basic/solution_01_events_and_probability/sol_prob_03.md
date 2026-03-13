# Solution

## Task 3 — Drawing Cards

Let $\text{Deck}$ denote the set of 52 cards in a standard deck.

1. **Sample space $\Omega_1$ for drawing one card:**
   $$
   \Omega_1 = \{c \mid c \in \text{Deck}\}
   $$

2. **Sample space $\Omega_2$ for two consecutive draws with replacement:**
   $$
   \Omega_2 = \{(c_1, c_2) \mid c_1 \in \text{Deck}, c_2 \in \text{Deck}\}
   $$

3. **Sample space $\Omega_2'$ for two consecutive draws without replacement:**
   $$
   \Omega_2' = \{(c_1, c_2) \mid c_1 \in \text{Deck}, c_2 \in \text{Deck}, c_1 \neq c_2\}
   $$

4. **Number of elementary outcomes in both cases:**
   * One card: $|\Omega_1| = 52$
   * Two draws with replacement: $|\Omega_2| = 52 \times 52 = 2704$
   * Two draws without replacement: $|\Omega_2'| = 52 \times 51 = 2652$

5. **Briefly describe what an elementary outcome represents in these experiments:**
   An elementary outcome represents an ordered sequence of specific cards drawn from the deck. The sample spaces differ in whether the same card can appear twice in the sequence.
