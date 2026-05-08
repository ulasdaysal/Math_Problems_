# Problem 2 — Discrete Distribution from CDF

## Input Data: The CDF Table
The problem provides the following cumulative distribution values:

| $x$ | -1 | 0 | 2 | 4 | 6 |
|:---:|:---:|:---:|:---:|:---:|:---:|
| **$F(x)$** | 0.15 | 0.35 | 0.60 | 0.85 | 1.00 |

---

## 1. Probability Space and Random Variable
A simple way to construct a finite probability space $\Omega$ is to use the values of $X$ as the outcomes. Let:
- **Sample Space:** $\Omega = \{-1, 0, 2, 4, 6\}$
- **Probability Measure:** $P(\omega)$ is the probability mass at each point (derived in Task 2).
- **Random Variable:** $X(\omega) = \omega$ for all $\omega \in \Omega$.

---

> [!TIP]
> **Interactive Visualization:** You can explore this distribution dynamically, adjust the jump sizes, and see the PMF/CDF relationship in the [Interactive Solution App](./02_discrete_app.html).

---

## 2. Reconstruct the PMF
The PMF, $P(X=x)$, is found by calculating the "jumps" in the CDF: $P(X=x_i) = F(x_i) - F(x_{i-1})$.

| $x$ | $P(X=x)$ calculation | $P(X=x)$ |
|:---:|:---|:---:|
| -1 | $0.15 - 0$ | **0.15** |
| 0 | $0.35 - 0.15$ | **0.20** |
| 2 | $0.60 - 0.35$ | **0.25** |
| 4 | $0.85 - 0.60$ | **0.25** |
| 6 | $1.00 - 0.85$ | **0.15** |

## 3 & 4. Graphs of PMF and CDF
- **PMF Graph:** A "spike" or "lollipop" chart where the height of the line at each $x$ matches the probabilities above.
- **CDF Graph:** A step function (staircase). The graph is constant between values and "jumps" at $x = \{-1, 0, 2, 4, 6\}$. It is right-continuous, meaning the solid dot is on the left of each horizontal segment.

## 5. Jump Points
The CDF jumps at the values where $X$ has a non-zero probability. Based on the table, these points are:
$x \in \{-1, 0, 2, 4, 6\}$

## 6. Why Jump Size = Probability?
By definition, $F(x) = P(X \le x)$. If we look at a specific point $a$:
$$F(a) = P(X < a) + P(X = a)$$
The value just before the jump is $F(a^-) = P(X < a)$. Therefore, the difference (the jump) is:
$$F(a) - F(a^-) = P(X = a)$$

## 7–12. Computing Probabilities
Let's use example values (e.g., $a=2, b=4$) to demonstrate the logic:

### 8. $P(X \le a)$
This is exactly the definition of the CDF.
**Example:** $P(X \le 2) = F(2) = \mathbf{0.60}$

### 9. $P(X < a)$
The value of the CDF immediately to the left of $a$.
**Example:** $P(X < 2) = F(0) = \mathbf{0.35}$

### 10. $P(X = a)$
The jump size at $a$.
**Example:** $P(X = 2) = 0.60 - 0.35 = \mathbf{0.25}$

### 11. $P(a < X \le b)$
The change in the CDF between the two points.
**Example:** $P(0 < X \le 4) = F(4) - F(0) = 0.85 - 0.35 = \mathbf{0.50}$

### 12. $P(X > a)$
Using the complement rule.
**Example:** $P(X > 2) = 1 - F(2) = 1 - 0.60 = \mathbf{0.40}$

## 13. Comparison: PMF vs. CDF
- **Immediate from PMF:** The individual probability of a specific outcome $P(X=x)$. It is easier to see the "mode" (most likely value) and the shape of the distribution's density.
- **Immediate from CDF:** Percentiles and interval probabilities. It is much faster to calculate $P(X \le x)$ or $P(a < X \le b)$ because you only need one or two subtractions rather than summing multiple PMF values.

## 14. Application Extension
To extend an application (like a Python script or Excel tool) to accept CDF input:
- **Validation:** Ensure the CDF values are non-decreasing and end at $1.0$.
- **Conversion:** Implement a loop where `PMF[i] = CDF[i] - CDF[i-1]` (with `CDF[-1] = 0`).
- **Search:** Use a binary search or "Look Up" function so that for any input $x$, the program returns the value of the CDF for the largest $x_i \le x$.
