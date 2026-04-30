# Problem 3 — The Binomial Distribution $\mathit{Bin}(n, p)$

## Introduction
While the previous tasks looked at isolated tables of probabilities, the formal study of statistics relies heavily on *families* of distributions. These families are driven by mathematical formulas and tuning knobs called "parameters". The most fundamental discrete family is the **Binomial Distribution**.

---

## Part 1: The Formal Engineering of the Model

### 1. The Random Experiment ($n$ Bernoulli Trials)
Imagine you are a quality control manager at a smartphone battery factory. You randomly select a batch of $n$ batteries off the assembly line. Each battery has exactly the same probability $p$ of being defective (a "success" in statistical counting logic, even if it's practically a failure!). Crucially, testing one battery tells you absolutely nothing about the next; they are mathematically **independent**. A single test with a Yes/No outcome is called a **Bernoulli trial**. Repeating it $n$ times creates our Binomial experiment.

### 2. The Sample Space ($\Omega$)
The sample space is the set of all possible sequences of tests. 
If we define an elementary outcome $\omega$ as a specific chronological sequence of testing $n$ batteries (e.g., $D$ for defective, $G$ for good), for $n=3$, an outcome could be $\omega = (D, G, D)$. 
Formally, $\Omega = \{D, G\}^n$. 

### 3. The Random Variable $X$
The random variable $X$ ignores the specific chronological order of the sequence and merely counts the **total number of successes** (defective batteries) in the batch.
* If $\omega = (D, G, D)$, then $X(\omega) = 2$.
* If $\omega = (G, G, G)$, then $X(\omega) = 0$.

### 4. The Support of $X$
Because you test exactly $n$ items, the minimum number of successes is 0 (all good), and the maximum is $n$ (all defective).
$$ \text{Support of } X = \{0, 1, 2, \dots, n\} $$

---

## Part 2: Formulating the PMF and CDF

### The Probability Mass Function (PMF)
To find the probability of exactly $k$ successes, we must count how many unique sequences contain exactly $k$ successes. We use the binomial coefficient $\binom{n}{k}$, and multiply it by the physical probability of any one of those specific sequences occurring ($p^k (1-p)^{n-k}$).

$$ P(X = k) = \binom{n}{k} p^k (1-p)^{n-k} \quad \text{for } k \in \{0, 1, \dots, n\} $$

### The Cumulative Distribution Function (CDF)
The CDF accumulates these probabilities up to a threshold $x$:

$$ 
F(x) = P(X \le x) = \sum_{k=0}^{\lfloor x \rfloor} \binom{n}{k} p^k (1-p)^{n-k} 
$$

---

## Part 3: Graphical Shape and Parameter Shifts

*(See the attached interactive application to visually construct and overlay these shifts!)*

**1. What happens when we fix $n$ and increase $p$ (Probability of Success)?**
* The PMF graph represents the "mass" of probability. As $p$ increases from a tiny number towards $1$, the entire bulk of the graph slides from the left side (near 0) towards the right side (near $n$). 
* For $p < 0.5$, the distribution is **right-skewed** (a long tail to the right).
* For $p = 0.5$, it is **perfectly symmetrical**.
* For $p > 0.5$, it is **left-skewed**.
* In the CDF, a higher $p$ means the "staircase" stays flat longer and surges upwards much later on the right side.

**2. What happens when we fix $p$ and increase $n$ (Number of Trials)?**
* As $n$ grows, the support widens since higher numbers of successes become physically possible.
* The "center" of the distribution moves to the right because the expected number of successes is $n \cdot p$.
* The bell-shaped curve spreads out, becoming wider and flatter. This "spreading bell curve" visual is exactly what drives the legendary Central Limit Theorem!

---

## Part 4: Computing Probabilities

Let's assume we are testing $n = 10$ items, and the probability of a defect is $p = 0.2$. Let's compute some target probabilities.

### 1. Exactly $k$ successes: $P(X = k)$
**Target:** $k = 3$
* **Direct PMF:** We plug directly into the formula.
  $P(X = 3) = \binom{10}{3} (0.2)^3 (0.8)^7 = 120 \cdot 0.008 \cdot 0.2097 \approx 0.2013$
* **Using CDF:** $F(3) - F(2) \approx 0.8791 - 0.6778 = 0.2013$

### 2. Less than or equal to $k$: $P(X \le k)$
**Target:** $k = 3$
* **Using CDF:** This is the literal definition of the CDF. We read it instantly. 
  $F(3) \approx 0.8791$
* **Direct PMF:** We are forced to add everything up manually: $P(X=0) + P(X=1) + P(X=2) + P(X=3)$. The CDF acts as a huge time-saver here.

### 3. Greater than or equal to $k$: $P(X \ge k)$
**Target:** $k = 3$
Using the complement rule with the CDF avoids adding up 8 different PMF components!
$P(X \ge 3) = 1 - P(X < 3) = 1 - F(2) \approx 1 - 0.6778 = 0.3222$

### 4. Interval: $P(a \le X \le b)$
**Target:** $P(2 \le X \le 4)$
Using the CDF:
$P(2 \le X \le 4) = F(4) - F(1) \approx 0.9672 - 0.3758 = 0.5914$

*(Notice how in discrete calculus, "less than or equal to 4, but strictly greater than 1" flawlessly captures exactly the set $\{2, 3, 4\}$.)*

---

## Part 5: Practical Applications of the Binomial Model

The Binomial model is one of the most widely used distributions in the world. It perfectly models any scenario answering a simple question: "Out of $n$ attempts, how many will succeed?"

1. **Quality Control:** Counting the exact number of defective microchips in a random batch sample of 1,000.
2. **Medical Trials:** Tracking the number of patients who experience a specific side effect out of $n$ participants undergoing a clinical trial.
3. **Sales & Marketing:** Calculating the probability that exactly $k$ out of $n$ people who receive an email newsletter will click on the tracking link.
4. **Voting & Polling:** Modeling how many people out of $n$ randomly sampled individuals will declare support for a specific political candidate.
