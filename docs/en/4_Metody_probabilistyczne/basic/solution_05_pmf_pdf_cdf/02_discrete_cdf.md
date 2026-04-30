# Problem 2 — Discrete Distribution Given by a CDF Table

## Introduction 
In Task 1, we started with individual "probability masses" (the PMF). This time, we are working backwards: we are given the "accumulated snowball" of probabilities (the **Cumulative Distribution Function**, or **CDF**) and must derive the corresponding rules underlying the experiment.

---

## Part 1: The Probability Space and Random Variable

### The Random Experiment
Let us imagine a deck of **20 special cards** shuffled thoroughly. A player draws one card at random. The number printed on the card determines their payoff.

### The Sample Space ($\Omega$)
The **sample space** is simply the physical act of drawing one of the 20 distinct cards.
$$ \Omega = \{ c_1, c_2, \dots, c_{20} \} $$

### The Random Variable ($X$) and its Support
The random variable $X$ maps the physical card to its numerical payoff. The problem gives us the points at which the CDF changes its values, which tells us exactly the possible numbers printed on the cards.
$$ \text{Support of } X = \{-1, 0, 2, 4, 6\} $$

By looking ahead at the jumps in the CDF (which we calculate in Part 2), we can establish exactly how many of each card exist in the deck:
* 3 cards of value -1 ($3/20 = 0.15$)
* 4 cards of value 0 ($4/20 = 0.20$)
* 5 cards of value 2 ($5/20 = 0.25$)
* 5 cards of value 4 ($5/20 = 0.25$)
* 3 cards of value 6 ($3/20 = 0.15$)

---

## Part 2: Reconstructing the PMF

The CDF $F(x)$ shown in the table gives us the probability accumulated *up to and including* $x$.
$F(x)$:
* $x = -1 \implies 0.15$
* $x = 0 \implies 0.35$
* $x = 2 \implies 0.60$
* $x = 4 \implies 0.85$
* $x = 6 \implies 1.00$

To find the individual probability masses $P(X=x)$ (the **PMF**), we simply calculate the difference between the current accumulated total and the previous total:

1. **At $x = -1$:** It's the first jump. $P(X = -1) = 0.15 - 0.00 = 0.15$
2. **At $x = 0$:** $P(X = 0) = F(0) - F(-1) = 0.35 - 0.15 = 0.20$
3. **At $x = 2$:** $P(X = 2) = F(2) - F(0) = 0.60 - 0.35 = 0.25$
4. **At $x = 4$:** $P(X = 4) = F(4) - F(2) = 0.85 - 0.60 = 0.25$
5. **At $x = 6$:** $P(X = 6) = F(6) - F(4) = 1.00 - 0.85 = 0.15$

**The Reconstructed PMF Table:**
| $x$ | -1 | 0 | 2 | 4 | 6 |
|---|---|---|---|---|---|
| **$P(X = x)$** | 0.15 | 0.20 | 0.25 | 0.25 | 0.15 |

*(You can verify this in the updated interactive HTML application!)*

---

## Part 3: Identifying the Jumps

**Where does the CDF jump?**
The CDF jumps precisely at the values in the support: $x \in \{-1, 0, 2, 4, 6\}$. 

**Why does jump size equal the probability?**
The CDF $F(x)$ represents the total probability accumulated up to the number $x$. As our "snowball" rolls rightward along the number line, it picks up no extra snow (probability) if there are no values. Thus, the graph is a flat horizontal line. But the moment it rolls exactly over a possible value in our support, it instantly absorbs that value's specific probability mass. Graphically, this is expressed as an instant vertical "jump." Therefore, the height of the jump is strictly equal to the PMF at that value: $P(X=x) = F(x) - F(x^-)$.

---

## Part 4: Computing Probabilities

Let's compute probabilities **using only the CDF values**, without referring to our derived PMF table. For these examples, let's substitute target parameters $a = 2$ and $b = 4$.

### 1. Less than or equal to: $P(X \le a)$
**Target:** $P(X \le 2)$
The CDF is defined as exactly this! We just read the value from the table.
**Result:** $F(2) = 0.60$

### 2. Strictly less than: $P(X < a)$
**Target:** $P(X < 2)$
To get the probability *strictly less* than 2, we must look at the accumulated value right before 2. In discrete distributions, this means evaluating the CDF at the largest support value prior to 2, which is 0.
$P(X < 2) = F(0) = 0.35$
**Result:** $0.35$

### 3. Equality: $P(X = a)$
**Target:** $P(X = 2)$
We find the size of the jump exactly at $x=2$ by subtracting the CDF just prior to 2 from the CDF at 2.
$P(X = 2) = F(2) - F(0) = 0.60 - 0.35 = 0.25$
**Result:** $0.25$

### 4. Interval: $P(a < X \le b)$
**Target:** $P(0 < X \le 4)$
To find the probability inside an interval open on the left and closed on the right, the absolute best tool is the CDF, which gives this instantly string via $F(b) - F(a)$.
$F(4) - F(0) = 0.85 - 0.35 = 0.50$
**Result:** $0.50$

### 5. Strictly greater than: $P(X > a)$
**Target:** $P(X > 2)$
We use the complement rule. "Greater than 2" is the opposite of "Less than or equal to 2".
$P(X > 2) = 1 - P(X \le 2) = 1 - F(2) = 1 - 0.60 = 0.40$
**Result:** $0.40$

---

## Part 5: Comparing PMF and CDF

When solving practical problems, choosing between the PMF and the CDF depends entirely on the question you are being asked.

* **When to use PMF:** The PMF is immediate and explicitly clear when asking "What is the probability of exactly this outcome?" ($P(X=x)$). It is the building block. However, if asked for an interval or a "greater than" question, you are forced to do a lot of repetitive addition.
* **When to use CDF:** The CDF is incredible at answering threshold questions ("less than or equal to") and interval boundaries ($P(a < X \le b)$) instantly with one subtraction. However, to find the probability of a single exact point, you have to subtract two adjacent CDF values instead of just reading a single number.
