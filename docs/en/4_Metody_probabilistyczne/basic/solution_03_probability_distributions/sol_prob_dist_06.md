# Solution

## Task 6 — Binomial Model

### Problem Data
- Probability of producing a defective part: $p = 0.04$
- Probability of a working part: $q = 1 - p = 0.96$
- Number of trials (parts checked): $n = 10$
- Random variable $X$: number of defective parts in the sample.

---

### 1. Probability that exactly 2 parts are defective ($k = 2$)
We use the binomial distribution formula:
$$ P(X = k) = \binom{n}{k} \cdot p^k \cdot (1-p)^{n-k} $$

Substitute the given values:
$$ P(X = 2) = \binom{10}{2} \cdot (0.04)^2 \cdot (0.96)^8 $$

$$ \binom{10}{2} = \frac{10!}{2!(10-2)!} = \frac{10 \times 9}{2} = 45 $$

$$ P(X = 2) = 45 \cdot 0.0016 \cdot 0.721389 \approx 0.0519 $$

So, the probability is approximately **$5.19\%$**.

---

### 2. Probability that at least one part is defective ($k \ge 1$)
Calculating the probabilities for $1, 2, 3, \dots, 10$ is tedious. It is much easier to use the **complementary event**:
The opposite of "at least one defective" is "**zero defective parts**" ($k = 0$).

$$ P(X \ge 1) = 1 - P(X = 0) $$

Calculate $P(X = 0)$:
$$ P(X = 0) = \binom{10}{0} \cdot (0.04)^0 \cdot (0.96)^{10} = 1 \cdot 1 \cdot 0.664832 \approx 0.6648 $$

Now, subtract from 1:
$$ P(X \ge 1) = 1 - 0.6648 = 0.3352 $$

The probability of finding at least one defective part is approximately **$33.52\%$**.

---

### 3. Distribution Table and Visualization

| $k$ (Defective) | Probability $P(X=k)$ | Approximate Value |
|:---:|:---|:---:|
| **0** | $\binom{10}{0} (0.04)^0 (0.96)^{10}$ | $66.48\%$ |
| **1** | $\binom{10}{1} (0.04)^1 (0.96)^9$ | $27.70\%$ |
| **2** | $\binom{10}{2} (0.04)^2 (0.96)^8$ | $5.19\%$ |
| **3** | $\binom{10}{3} (0.04)^3 (0.96)^7$ | $0.58\%$ |
| **4+** | ... | $<0.05\%$ |

**Visualising the Distribution:**
```text
Probability (%)
 70 | ████████████████████████████████████████ (66.48%)
 60 |
 50 |
 40 |
 30 |
 20 | █████████████████ (27.70%)
 10 |
  0 |_███_(5.19%)_____________________________________
          k=0               k=1              k=2
```
