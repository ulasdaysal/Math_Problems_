# Solution

## Task 6 — Events and Probabilities in Coin Tossing

Since the coin is fair, for all $n$, every elementary outcome in $\Omega_n$ has probability $\frac{1}{|\Omega_n|}$.
* For 1 toss: $P(\omega) = \frac{1}{2}$
* For 2 tosses: $P(\omega) = \frac{1}{4}$
* For 3 tosses: $P(\omega) = \frac{1}{8}$

### One Coin Toss
* $A_1$ (heads): $A_1 = \{H\}$. $P(A_1) = \frac{1}{2}$
* $B_1$ (tails): $B_1 = \{T\}$. $P(B_1) = \frac{1}{2}$
* $C_1$ (not tails): $C_1 = \{H\}$. $P(C_1) = \frac{1}{2}$

### Two Coin Tosses
* $A_2$ (exactly one head): $A_2 = \{(H,T), (T,H)\}$. $P(A_2) = \frac{2}{4} = \frac{1}{2}$
* $B_2$ (at least one head): $B_2 = \{(H,H), (H,T), (T,H)\}$. $P(B_2) = \frac{3}{4}$
* $C_2$ (both same): $C_2 = \{(H,H), (T,T)\}$. $P(C_2) = \frac{2}{4} = \frac{1}{2}$

### Three Coin Tosses
* $A_3$ (exactly two heads): $A_3 = \{(H,H,T), (H,T,H), (T,H,H)\}$. $P(A_3) = \frac{3}{8}$
* $B_3$ (at least one tail): $B_3 = \Omega_3 \setminus \{(H,H,H)\}$. $P(B_3) = \frac{7}{8}$
* $C_3$ (all three same): $C_3 = \{(H,H,H), (T,T,T)\}$. $P(C_3) = \frac{2}{8} = \frac{1}{4}$

* **Additional event definition**: $D_3$ - the first toss is heads.
  $D_3 = \{(H,H,H), (H,H,T), (H,T,H), (H,T,T)\}$. $P(D_3) = \frac{4}{8} = \frac{1}{2}$
