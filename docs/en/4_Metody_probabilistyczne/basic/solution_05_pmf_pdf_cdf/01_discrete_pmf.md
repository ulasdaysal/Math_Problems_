# Problem 1 — Discrete Distribution Given by a PMF Table

## Introduction to the Formal Model
Before we begin calculating numbers, we must first build a formal mathematical space that models our experiment. 

### The Random Experiment
Imagine a simple carnival game. A dealer holds an opaque bag containing exactly **20 wooden tokens**. You reach in without looking and draw a single token to determine your prize (or penalty).

* The bag contains:
  * 2 Red tokens (lose 2 points)
  * 5 Blue tokens (0 points)
  * 6 Green tokens (win 1 point)
  * 4 Yellow tokens (win 3 points)
  * 3 Gold tokens (win 5 points)

### The Sample Space ($\Omega$)
The **sample space** is the set of all elementary outcomes of this experiment. An elementary outcome ($\omega$) is simply the physical act of pulling *one specific token* out of the bag.
$$ \Omega = \{ \omega_1, \omega_2, \dots, \omega_{20} \} $$
There are 20 tokens, so there are 20 completely distinct elementary outcomes.

### The Random Variable ($X$) and its Support
A **random variable** is simply a translator. It looks at the physical outcome (the wooden token) and translates it into a number according to a strict rule.
Let $X$ be the number of points won. Our translator $X$ maps tokens to numbers:
* If $\omega$ is a Red token, $X(\omega) = -2$
* If $\omega$ is a Green token, $X(\omega) = 1$
* ...and so on.

The **support** of the random variable is the set of all *possible translations* (all possible numerical values $X$ can take). Do not confuse this with the 20 physical tokens ($\Omega$).
$$ \text{Support of } X = \{-2, 0, 1, 3, 5\} $$

---

## Task 1: Validating the Probability Distribution

The probability of landing on a specific score $x$, denoted as $P(X = x)$, is called the **Probability Mass Function (PMF)**. 

To verify if the table given is mathematically valid, two rules must absolutely hold:
1. **No negative probabilities:** Every probability must be $\ge 0$. (Check: All values are between 0.10 and 0.30. Rule passed).
2. **The "Everything" rule:** The sum of all probabilities must exactly equal $1.00$ (representing 100% certainty that *something* in the support happens).

Let's test rule #2:
$$ \sum P(X = x) = 0.10 + 0.25 + 0.30 + 0.20 + 0.15 = 1.00 $$
Both conditions are met. This is a perfectly valid probability distribution.

---

## Task 2: The Probability Mass Function (PMF)

The PMF represents the probability of the random variable equalling a specific target value exact.

**Table Representation:**
| $x$ | -2 | 0 | 1 | 3 | 5 |
|---|---|---|---|---|---|
| **$P(X = x)$** | 0.10 | 0.25 | 0.30 | 0.20 | 0.15 |

**Graphical Representation:**
A PMF for a discrete variable is best drawn as a "stem plot" or "needle plot." Vertical lines sprout from the $x$-axis, with the height exactly equal to the probability.

*(See the attached interactive HTML application to visualize this!)*

---

## Task 3: The Cumulative Distribution Function (CDF)

The CDF, denoted as $F(x)$, asks a different question: "What is the probability that my outcome will be **less than or equal to** $x$?"
$$ F(x) = P(X \le x) $$

Think of the CDF as a snowball rolling towards the right along the $x$-axis. As it rolls over each possible value in the support, it picks up (accumulates) all the probabilities it has seen so far.

**Constructing the CDF:**
* If $x < -2$ (before we hit the first token): We have accumulated nothing. $F(x) = 0$.
* At $x = -2$: We accumulate $0.10$. So for $-2 \le x < 0$, $F(x) = 0.10$.
* At $x = 0$: We accumulate another $0.25$. New total $= 0.10 + 0.25 = 0.35$.
* At $x = 1$: We accumulate another $0.30$. New total $= 0.35 + 0.30 = 0.65$.
* At $x = 3$: We accumulate another $0.20$. New total $= 0.65 + 0.20 = 0.85$.
* At $x = 5$: We accumulate the final $0.15$. New total $= 0.85 + 0.15 = 1.00$.

So, formally:
$$ F(x) = 
\begin{cases} 
0.00 & \text{for } x < -2 \\
0.10 & \text{for } -2 \le x < 0 \\
0.35 & \text{for } 0 \le x < 1 \\
0.65 & \text{for } 1 \le x < 3 \\
0.85 & \text{for } 3 \le x < 5 \\
1.00 & \text{for } x \ge 5 
\end{cases} 
$$

### The Graph and Jumps of the CDF

The graph of a discrete CDF forms a series of flat steps ("staircase shape"), moving to the right and always going upwards. 

**How are the jumps related to the PMF?**
At each number in our support ($\{-2, 0, 1, 3, 5\}$), the graph instantly jumps up. 
**The size of each vertical jump is exactly equal to the probability mass (PMF) at that point.**
For instance, at $x=1$, the graph jumps from $0.35$ up to $0.65$. The distance of that jump is $0.30$, which precisely equals $P(X=1)$. In places where probability is zero (like $x=2$), the graph is completely flat (no jump).

---

## Task 4: Computing Probabilities

Let's compute probabilities using our tools. We will evaluate specific target values for $a$ and $b$ in each example to demonstrate how the formulas work.

### 1. Equality: $P(X = a)$
**Target:** $P(X = 1)$
We look straight at the PMF table for the column $x=1$.
**Result:** $0.30$

### 2. Less than or equal to: $P(X \le a)$
**Target:** $P(X \le 1)$
This is the literal definition of the CDF evaluated at 1! So we can just take $F(1)$.
**Result:** $0.65$

### 3. Strictly less than: $P(X < a)$
**Target:** $P(X < 1)$
This includes all probabilities *before* we hit 1. We look at the support values strictly smaller than 1: these are -2 and 0.
$P(X < 1) = P(X = -2) + P(X = 0) = 0.10 + 0.25$
**Result:** $0.35$

### 4. Interval: $P(a < X \le b)$
**Target:** $P(0 < X \le 3)$
This wants only the values *after* 0 and *up to and including* 3. The only support values here are 1 and 3.
Using PMF: $P(X = 1) + P(X = 3) = 0.30 + 0.20 = 0.50$
**Result:** $0.50$

### 5. Greater than or equal to: $P(X \ge a)$
**Target:** $P(X \ge 1)$
This requires values 1, 3, and 5. Time for a shortcut using the **complement rule**. 
$P(X \ge 1) = 1 - P(X < 1) = 1 - 0.35 = 0.65$.
**Result:** $0.65$

---

## Task 5: Comparing direct PMF vs CDF Readings

We can get the same results regardless of which tool we use. 
Let's re-verify the interval probability: $P(0 < X \le 3)$

* **Using PMF Tables (Addition):** We sum the individual probabilities inside the interval.
  $P(X=1) + P(X=3) = 0.30 + 0.20 = 0.50$.
* **Using CDF (Subtraction):** We can use the magic interval formula: $P(a < X \le b) = F(b) - F(a)$.
  $F(3) - F(0) = 0.85 - 0.35 = 0.50$.

**Conclusion:** Both methods yield an exact match ($0.50$). The CDF acts as a convenient cumulative shortcut!
