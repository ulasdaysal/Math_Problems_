# Solution

## Task 8 — Geometric Model

### Problem Data
- Probability of a compilation error (success): $p = 0.1$
- Probability of no error (failure): $q = 1 - p = 0.9$
- Random variable $X$: the trial number of the **first** error.

**Why Geometric?**  
This is a geometric distribution because we are conducting a sequence of independent trials (compilations) and we are specifically interested in the number of trials required to achieve the **first** success (a compilation error).

The probability of getting the first success exactly on the $k$-th trial follows the Geometric distribution:
$$ P(X = k) = (1-p)^{k-1} \cdot p $$

**What does this formula mean?**  
- $(1-p)^{k-1}$: The probability of getting $(k-1)$ consecutive failures (error-free compilations) right before the error.  
- $p$: The probability of getting that single success (compilation error) exactly on the $k$-th trial.

---

### 1. Probability that the first error appears on the 4th compilation ($k = 4$)
This means there were exactly 3 successful (error-free) compilations followed by 1 error.

Substitute the values:
$$ P(X = 4) = (0.9)^{4-1} \cdot 0.1 = (0.9)^3 \cdot 0.1 $$

The probability is **$7.29\%$**.

---

### 2. Probability that it appears no later than the 3rd compilation ($k \le 3$)
This means the first error can appear on the 1st, 2nd, or 3rd compilation. 
We simply sum these mutually exclusive probabilities:
$$ P(X \le 3) = P(X = 1) + P(X = 2) + P(X = 3) $$

Calculate each:
- $P(X = 1) = 0.1$
- $P(X = 2) = 0.9^1 \cdot 0.1 = 0.09$
- $P(X = 3) = 0.9^2 \cdot 0.1 = 0.081$

Sum them:
$$ P(X \le 3) = 0.1 + 0.09 + 0.081 = 0.271 $$

**Alternative Method (Recommended):**
Using the complementary event (no errors in the first 3 trials):
$$ P(X \le 3) = 1 - P(\text{no errors in 3 trials}) = 1 - (0.9)^3 = 0.271 $$

The probability is **$27.10\%$**.

---

### 3. Distribution Table and Visualization

| $k$ (Trial of 1st error) | Exact Formula | Approximate Probability |
|:---:|:---|:---:|
| **1** | $0.1$ | $10.00\%$ |
| **2** | $0.9^1 \cdot 0.1$ | $9.00\%$ |
| **3** | $0.9^2 \cdot 0.1$ | $8.10\%$ |
| **4** | $0.9^3 \cdot 0.1$ | $7.29\%$ |
| **5** | $0.9^4 \cdot 0.1$ | $6.56\%$ |
| **...** | ... | ... |

*(The probability decreases steadily as the number of error-free trials increases)*
