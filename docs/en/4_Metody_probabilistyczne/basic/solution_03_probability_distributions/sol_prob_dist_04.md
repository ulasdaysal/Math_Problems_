# Solution

## Task 4 — Poisson Model (Arrival of Events)

### 1. Description of the Random Experiment
The experiment consists of observing a web service over a given period of time (e.g., 1 hour) and counting the number of **error reports** received within that interval.

---

### 2. Sample Space ($\Omega$)
In the Poisson model, the number of events that can occur in a specific interval is theoretically unlimited (although extremely large numbers have infinitesimally small probabilities).

Therefore, the sample space consists of all non-negative integers:
$$ \Omega = \{0, 1, 2, 3, 4, \dots \} = \mathbb{N}_0 $$

---

### 3. Formula of the Probability Distribution
The probability of receiving exactly $k$ error reports in the given time interval follows a **Poisson distribution**:

$$ P(X = k) = \frac{\lambda^k e^{-\lambda}}{k!} $$

Where:
- $X$ is the random variable representing the number of error reports
- $k \in \{0, 1, 2, \dots \}$ (the integer number of events we are calculating the probability for)
- $\lambda = 3$ (the average number of events per interval)
- $e \approx 2.71828$ (Euler's number)

**Distribution Table ($\lambda = 3$):**

| $k$ (Number of reports) | Exact Formula | Approximate Value |
|:---:|:---:|:---:|
| **0** | $P(X=0) = \frac{3^0 e^{-3}}{0!} = e^{-3}$ | $4.98\%$ |
| **1** | $P(X=1) = \frac{3^1 e^{-3}}{1!} = 3e^{-3}$ | $14.94\%$ |
| **2** | $P(X=2) = \frac{3^2 e^{-3}}{2!} = \frac{9}{2}e^{-3}$ | $22.40\%$ |
| **3** | $P(X=3) = \frac{3^3 e^{-3}}{3!} = \frac{27}{6}e^{-3}$ | $22.40\%$ |
| **4** | $P(X=4) = \frac{3^4 e^{-3}}{4!} = \frac{81}{24}e^{-3}$ | $16.80\%$ |
| **5** | $P(X=5) = \frac{3^5 e^{-3}}{5!} = \frac{243}{120}e^{-3}$ | $10.08\%$ |
| **...** | ... | ... |

Notice how the probability peaks precisely around the average value ($\lambda = 3$).

---

### 4. Interpretation of Parameter $\lambda$
The parameter $\lambda$ (lambda) represents the **expected rate of occurrences** — the average number of times the event occurs in the specified continuous interval (in this case, $\lambda = 3$ error reports per hour). It is both the **expected value (mean)** and the **variance** of the variable in the Poisson distribution.
