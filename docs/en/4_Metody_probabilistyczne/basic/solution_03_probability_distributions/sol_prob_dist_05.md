# Solution

## Task 5 — Multinomial Model (Categories of Outcomes)

### 1. Description of the Random Experiment
The experiment consists of a player rolling a **standard 6-sided die 5 independent times**. The outcome of each roll is classified into one of three distinct and mutually exclusive categories based on the result:
- **Category 1:** small numbers $\{1, 2\}$
- **Category 2:** medium numbers $\{3, 4\}$
- **Category 3:** large numbers $\{5, 6\}$

---

### 2. Sample Space
Instead of tracking individual die rolls, the Multinomial model tracks the **counts of occurrences** for each category.

Let:
- $k_1$ = number of times "small numbers" are rolled
- $k_2$ = number of times "medium numbers" are rolled
- $k_3$ = number of times "large numbers" are rolled

The sample space $\Omega$ represents all valid combinations of counts $(k_1, k_2, k_3)$ such that their sum equals the total number of rolls ($n=5$):

$$ \Omega = \{ (k_1, k_2, k_3) \in \mathbb{N}_0^3 : \sum_{i=1}^3 k_i = 5 \} $$

For example, $(5, 0, 0)$ means all 5 rolls were small numbers. $(1, 2, 2)$ means 1 small, 2 medium, and 2 large numbers.

---

### 3. The Multinomial Distribution
The probability of obtaining a specific combination of counts $(k_1, k_2, k_3)$ is given by the Multinomial formula (a generalization of the binomial theorem):

$$ P(X_1 = k_1, X_2 = k_2, X_3 = k_3) = \frac{n!}{k_1! \cdot k_2! \cdot k_3!} \cdot (p_1)^{k_1} (p_2)^{k_2} (p_3)^{k_3} $$

Where:
- $n = 5$ (total rolls)
- $p_1, p_2, p_3$ are the probabilities of rolling into categories 1, 2, and 3 on a single roll.
- $k_1, k_2, k_3$ are the specific outcome counts we are calculating the probability for.

---

### 4. Interpretation of Parameters
The parameters governing this probability distribution are:

* **$n$ (Number of trials):** 
  $n=5$. It signifies the total number of independent experiments (rolls) conducted.
* **$p_1$ (Probability of Category 1):**
  $p_1 = \frac{2}{6} = \frac{1}{3}$. It is the fixed probability of obtaining a small number $\{1, 2\}$ on a single independent roll.
* **$p_2$ (Probability of Category 2):**
  $p_2 = \frac{2}{6} = \frac{1}{3}$. It is the fixed probability of obtaining a medium number $\{3, 4\}$.
* **$p_3$ (Probability of Category 3):**
  $p_3 = \frac{2}{6} = \frac{1}{3}$. It is the fixed probability of obtaining a large number $\{5, 6\}$.

*(Note: The sum of the probabilities corresponding to all categories must exactly equal 1: $p_1 + p_2 + p_3 = 1$)*
