# Solution

## Task 2 — Hypergeometric Model (Sampling from a Batch)

### 1. Description of the Random Experiment
The experiment consists of simultaneously **drawing 4 components** at random, **without replacement**, from a warehouse containing a total of 20 components, of which 5 are defective and 15 are functional.

---

### 2. Sample Space ($\Omega$)
Let $X$ be the random variable representing the **number of defective components** in our sample of 4.

Since there are 5 defective components in total and we are drawing 4, the sample space (in terms of the number of defective items) is simply the set of possible values for $X$:

$$ \Omega_X = \{0, 1, 2, 3, 4\} $$

---

### 3. Possible Values of the Random Variable
As indicated by the sample space above, the possible values the random variable $X$ can take are **0, 1, 2, 3,** and **4**.

---

### 4. Probability Distribution
**Why Hypergeometric?**
This is a hypergeometric distribution because it models the probability of a specific number of successes (defective components) over a fixed number of draws ($n=4$), but **without replacement** from a finite population ($N=20$). Unlike the Binomial model, the probability changes dynamically with each draw!

The formula to compute the probability of drawing exactly $k$ defective components is:

$$ P(X = k) = \frac{\binom{K}{k} \cdot \binom{N - K}{n - k}}{\binom{N}{n}} $$

**What does this formula mean?**  
- $\binom{K}{k}$: The number of ways to pick $k$ defective components from the total $K$ available defective components.
- $\binom{N - K}{n - k}$: The number of ways to pick the remaining working components from the available working components.
- $\binom{N}{n}$: The total possible number of ways to pick any $n$ components from the entire pool of $N$ components.

Where:
- $N = 20$ (Total number of components)
- $K = 5$ (Total number of defective components)
- $n = 4$ (Number of components drawn)
- $k \in \{0, 1, 2, 3, 4\}$ (Number of defective components obtained)

**Distribution Table:**

| $k$ (Defective drawn) | Exact Value Formula | Approximate Probability |
|:---:|:---:|:---:|
| **0** | $\frac{\binom{5}{0} \cdot \binom{15}{4}}{\binom{20}{4}} = \frac{1 \cdot 1365}{4845}$ | $\approx 28.17\%$ |
| **1** | $\frac{\binom{5}{1} \cdot \binom{15}{3}}{\binom{20}{4}} = \frac{5 \cdot 455}{4845}$ | $\approx 46.96\%$ |
| **2** | $\frac{\binom{5}{2} \cdot \binom{15}{2}}{\binom{20}{4}} = \frac{10 \cdot 105}{4845}$ | $\approx 21.67\%$ |
| **3** | $\frac{\binom{5}{3} \cdot \binom{15}{1}}{\binom{20}{4}} = \frac{10 \cdot 15}{4845}$ | $\approx 3.10\%$ |
| **4** | $\frac{\binom{5}{4} \cdot \binom{15}{0}}{\binom{20}{4}} = \frac{5 \cdot 1}{4845}$ | $\approx 0.10\%$ |

**Visualising the Distribution:**

```text
Probability (%)
 50 |                                   ███████ (46.96%)
 40 |
 30 |           ███████ (28.17%)
 20 |                                                   ███████ (21.67%)
 10 |                                                                           ███████ (3.10%)
  0 |___________|___________________|___________________|___________________|___________ ██ (0.10%)
          k = 0               k = 1               k = 2               k = 3        k = 4
```

---

### 5. Definition of "Success"
In the context of this specific model, a **"success"** is defined as **selecting a defective component**. We track this category because it represents the specific characteristic (the $K$ parameter) defined in our Hypergeometric distribution model.
