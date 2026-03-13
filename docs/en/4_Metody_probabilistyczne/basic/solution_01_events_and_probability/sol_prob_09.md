# Solution

## Task 9 — Events and Probabilities in Weekly Weather Observation

Total number of outcomes in $\Omega_7$ is $3^7 = 2187$. The days are independent, and each state $\{S, C, R\}$ occurs with probability $\frac{1}{3}$.

### Events
* $A$ (entire weekend is sunny): Saturday and Sunday must be $S$ (probability $\frac{1}{3} \times \frac{1}{3} = \frac{1}{9}$). The other 5 days can be any weather. As subset sizes: $|A| = 3^5$.
  $P(A) = \frac{3^5}{3^7} = \frac{1}{9}$

* $B$ (Wednesday, Thursday, and Friday are all rainy): Those 3 days must be $R$.
  $P(B) = \left(\frac{1}{3}\right)^3 = \frac{1}{27}$

* $C$ (at least one day is sunny): Easiest to use the complement. The event "no day is sunny" has probability $\left(\frac{2}{3}\right)^7$.
  $P(C) = 1 - \left(\frac{2}{3}\right)^7 = 1 - \frac{128}{2187} = \frac{2059}{2187}$

* $D$ (no rainy day occurs during the week): Every day must be $S$ or $C$ (2 choices per day).
  $P(D) = \left(\frac{2}{3}\right)^7 = \frac{128}{2187}$

* $E$ (exactly two days are sunny): Using the binomial probability framework, we choose 2 out of 7 days to be $S$, and the other 5 are not $S$.
  $P(E) = \binom{7}{2} \left(\frac{1}{3}\right)^2 \left(\frac{2}{3}\right)^5 = 21 \cdot \frac{1}{9} \cdot \frac{32}{243} = \frac{672}{2187} = \frac{224}{729}$

* **Additional event definition**: $F$ - the weather is exactly the same on all 7 days.
  $F = \{(S,S,S,S,S,S,S), (C,C,C,C,C,C,C), (R,R,R,R,R,R,R)\}$.
  $P(F) = \frac{3}{2187} = \frac{1}{729}$
