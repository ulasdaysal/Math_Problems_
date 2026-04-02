# Solution

## Task 9 — Poisson Model

### Problem Data
- Average rate of requests per interval (1 hour): $\lambda = 5$
- Random variable $X$: number of requests in one hour.

**Why Poisson?**  
This is a Poisson distribution because we are modeling the number of discrete events (requests) occurring within a continuous, fixed interval of time (one hour), given a known average rate ($\lambda=5$).

The formula for the Poisson distribution is:
$$ P(X = k) = \frac{\lambda^k e^{-\lambda}}{k!} $$

**What does this formula mean?**  
- $\lambda^k$: The expected average rate ($\lambda$) raised to the power of the specific number of events we are calculating for ($k$).  
- $e^{-\lambda}$: A constant decay factor that scales the probability based on the average rate.  
- $k!$: Scales down the probability to account for the indistinguishability of the events.

---

### 1. Probability of exactly 3 requests ($k = 3$)
Substitute the given values into the formula ($\lambda = 5, k = 3$):
$$ P(X = 3) = \frac{5^3 e^{-5}}{3!} $$

$$ P(X = 3) \approx 0.1404 $$

The probability of receiving exactly 3 requests is approximately **$14.04\%$**.

---

### 2. Probability of at least one request ($k \ge 1$)
Calculating $P(X \ge 1)$ requires summing from $k=1$ to $\infty$:
$$ P(X \ge 1) = P(X=1) + P(X=2) + \dots $$

It is much simpler to use the complementary event: "**zero requests**" ($k = 0$).
$$ P(X \ge 1) = 1 - P(X = 0) $$

First, compute $P(X = 0)$:
$$ P(X = 0) = \frac{5^0 e^{-5}}{0!} = e^{-5} \approx 0.006738 $$

Now, subtract from 1:
$$ P(X \ge 1) = 1 - 0.006738 = 0.993262 $$

The probability of receiving at least one request is approximately **$99.33\%$**.

---

### 3. Distribution Table ($\lambda = 5$)

| $k$ (Number of requests) | Exact Formula | Approximate Value |
|:---:|:---:|:---:|
| **0** | $\frac{5^0 e^{-5}}{0!}$ | $0.67\%$ |
| **1** | $\frac{5^1 e^{-5}}{1!}$ | $3.37\%$ |
| **2** | $\frac{5^2 e^{-5}}{2!}$ | $8.42\%$ |
| **3** | $\frac{5^3 e^{-5}}{3!}$ | $14.04\%$ |
| **4** | $\frac{5^4 e^{-5}}{4!}$ | $17.55\%$ |
| **5** | $\frac{5^5 e^{-5}}{5!}$ | $17.55\%$ |
| **6** | $\frac{5^6 e^{-5}}{6!}$ | $14.62\%$ |
| **...** | ... | ... |
