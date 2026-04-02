# Solution

## Task 7 — Hypergeometric Model

### Problem Data
We are drawing elements **without replacement** from a finite set.
- Total number of bulbs: $N = 12 + 3 = 15$
- Total defective bulbs: $K = 3$
- Total working bulbs: $N - K = 12$
- Number of bulbs drawn: $n = 5$
- Random variable $X$: number of defective bulbs in our draw.

---

### Probability that exactly 2 defective bulbs are drawn ($k = 2$)
We use the hypergeometric distribution formula:
$$ P(X = k) = \frac{\binom{K}{k} \cdot \binom{N - K}{n - k}}{\binom{N}{n}} $$

Substitute the values:
$$ P(X = 2) = \frac{\binom{3}{2} \cdot \binom{12}{3}}{\binom{15}{5}} $$

**Step-by-step Calculation:**
1. From 3 defective, choose 2:
   $$ \binom{3}{2} = 3 $$
2. From 12 working, choose 3 (since $5 - 2 = 3$):
   $$ \binom{12}{3} = \frac{12 \times 11 \times 10}{3 \times 2 \times 1} = \frac{1320}{6} = 220 $$
3. Total ways to draw 5 from 15:
   $$ \binom{15}{5} = \frac{15 \times 14 \times 13 \times 12 \times 11}{5 \times 4 \times 3 \times 2 \times 1} = 3003 $$

Now plug them into the formula:
$$ P(X = 2) = \frac{3 \cdot 220}{3003} = \frac{660}{3003} \approx 0.2198 $$

The probability that exactly 2 defective bulbs are chosen is approximately **$21.98\%$**.

---

### 3. Distribution Table and Visualization

| $k$ (Defective drawn) | Exact Value Formula | Approximate Probability |
|:---:|:---:|:---:|
| **0** | $\frac{\binom{3}{0} \cdot \binom{12}{5}}{\binom{15}{5}} = \frac{1 \cdot 792}{3003}$ | $\approx 26.37\%$ |
| **1** | $\frac{\binom{3}{1} \cdot \binom{12}{4}}{\binom{15}{5}} = \frac{3 \cdot 495}{3003}$ | $\approx 49.45\%$ |
| **2** | $\frac{\binom{3}{2} \cdot \binom{12}{3}}{\binom{15}{5}} = \frac{3 \cdot 220}{3003}$ | $\approx 21.98\%$ |
| **3** | $\frac{\binom{3}{3} \cdot \binom{12}{2}}{\binom{15}{5}} = \frac{1 \cdot 66}{3003}$ | $\approx 2.20\%$ |

**Visualising the Distribution:**
```text
Probability (%)
 50 |                                   ███████ (49.45%)
 40 |
 30 |           ███████ (26.37%)
 20 |                                                   ███████ (21.98%)
 10 |                                                                           ███████ (2.20%)
  0 |___________|___________________|___________________|___________________|___________
          k = 0               k = 1               k = 2               k = 3
```
