# Solution

## Task 7 — Events and Probabilities in Die Rolling

Since the die is fair, each elementary outcome is equally likely.
* For 1 roll: $|\Omega_1| = 6$, $P(\omega) = \frac{1}{6}$
* For 2 rolls: $|\Omega_2| = 36$, $P(\omega) = \frac{1}{36}$
* For 3 rolls: $|\Omega_3| = 216$, $P(\omega) = \frac{1}{216}$

### One Die Roll
* $A_1$ (even): $A_1 = \{2, 4, 6\}$. $P(A_1) = \frac{3}{6} = \frac{1}{2}$
* $B_1$ (greater than 4): $B_1 = \{5, 6\}$. $P(B_1) = \frac{2}{6} = \frac{1}{3}$
* $C_1$ (at most 3): $C_1 = \{1, 2, 3\}$. $P(C_1) = \frac{3}{6} = \frac{1}{2}$

### Two Die Rolls
* $A_2$ (sum equals 7): $A_2 = \{(1,6), (2,5), (3,4), (4,3), (5,2), (6,1)\}$. $P(A_2) = \frac{6}{36} = \frac{1}{6}$
* $B_2$ (both results the same): $B_2 = \{(1,1), (2,2), (3,3), (4,4), (5,5), (6,6)\}$. $P(B_2) = \frac{6}{36} = \frac{1}{6}$
* $C_2$ (sum is at least 10): 
  Sums equals 10: $(4,6), (5,5), (6,4)$
  Sum equals 11: $(5,6), (6,5)$
  Sum equals 12: $(6,6)$
  $C_2$ has $3 + 2 + 1 = 6$ outcomes. $P(C_2) = \frac{6}{36} = \frac{1}{6}$

### Three Die Rolls
* $A_3$ (sum equals 10): Possible sets of three numbers that sum to 10 are: $\{1,3,6\}$ (6 perms), $\{1,4,5\}$ (6 perms), $\{2,2,6\}$ (3 perms), $\{2,3,5\}$ (6 perms), $\{2,4,4\}$ (3 perms), $\{3,3,4\}$ (3 perms). $|A_3| = 6+6+3+6+3+3 = 27$. $P(A_3) = \frac{27}{216} = \frac{1}{8}$
* $B_3$ (exactly two rolls give the same number): There are 6 ways to choose the duplicated number, 5 ways to choose the other number, and 3 ways to position the latter. $|B_3| = 6 \times 5 \times 3 = 90$. $P(B_3) = \frac{90}{216} = \frac{5}{12}$
* $C_3$ (two twos and one three): The combinations are $(2,2,3), (2,3,2), (3,2,2)$. $|C_3| = 3$. $P(C_3) = \frac{3}{216} = \frac{1}{72}$

* **Additional event definition**: $D_3$ - all three rolls are different.
  $|D_3| = 6 \times 5 \times 4 = 120$. $P(D_3) = \frac{120}{216} = \frac{5}{9}$
