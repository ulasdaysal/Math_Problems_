# Problem 4 — The Geometric Distribution $\mathit{Geo}(p)$

## Introduction
The Binomial distribution models the number of successes in a *fixed* number of trials. But what if we don't fix the number of trials? What if we just keep trying **until** we succeed? This completely different framing leads us to the **Geometric Distribution**.

---

## Part 1: The Formal Engineering of the Model

### 1. The Random Experiment (Waiting for Success)
Imagine you are playing a difficult level in a video game. Every time you attempt the level, you have a probability $p$ of clearing it (a "success"). If you fail, you simply hit restart and try again. You keep playing, over and over, until you finally beat the level once, at which point you stop.

### 2. The Sample Space ($\Omega$)
The sample space consists of all possible chronological sequences of Failures ($F$) ending in exactly one Success ($S$).
* Beating it immediately: $\omega_1 = (S)$
* Failing once, then beating it: $\omega_2 = (F, S)$
* Failing twice, then beating it: $\omega_3 = (F, F, S)$
* And so on...

Formally, the sample space is infinite: $\Omega = \{S, FS, FFS, FFFS, \dots\}$.

### 3. The Random Variable $X$
The random variable $X$ maps the sequence to a simple integer: the **total number of attempts** required to obtain the first success.
* If $\omega = (F, F, S)$, then $X = 3$ (it took 3 trials).
* If $\omega = (S)$, then $X = 1$ (it took 1 trial).

### 4. The Infinite Support
The support of $X$ is the set of all positive integers:
$$ \text{Support of } X = \{1, 2, 3, 4, \dots\} $$
**Why is it infinite?** Theoretically, there is no hard upper limit. No matter how many times you fail, it is mathematically possible (even if extremely improbable) to fail one more time. You could, in theory, be trapped failing forever. Therefore, the support must unbounded.

---

## Part 2: Formulating the PMF and CDF

### The Probability Mass Function (PMF)
To find the probability that it takes exactly $k$ trials ($X=k$), we need exactly $k-1$ consecutive failures followed immediately by $1$ success. Because the trials are independent, we multiply their probabilities:
$$ P(X = k) = (1-p)^{k-1} \cdot p \quad \text{for } k \in \{1, 2, 3, \dots\} $$

*(Note: Some textbooks define Geometric as the number of extra *failures* before the first success, which has a support starting at $0$. We are using the standard "total trials" definition starting at $1$.)*

### The Cumulative Distribution Function (CDF)
The CDF accumulates the probabilities of terminating on or before trial $k$. Through the geometric series sum, this simplifies beautifully:
$$ F(k) = P(X \le k) = 1 - (1-p)^k $$

---

## Part 3: Graphical Shape and Parameter Shifts

*(See the interactive comparison application to visually manipulate these shapes!)*

**How does the shape change as $p$ shifts?**
* **The "J" Shape:** The Geometric PMF always starts at its absolute maximum peak at $x=1$ (since $P(X=1) = p$, and subsequent values multiply by $(1-p)$ which is less than 1), and then strictly decays downwards towards zero. 
* **When $p$ is large (closer to 1):** The probability of succeeding immediately is huge. The graph drops off a cliff. The "tail" is very short. 
* **When $p$ is small (closer to 0):** The probability of failing is high. The initial peak is low, and the graph decays very, very slowly, extending an incredibly long "heavy tail" infinitely to the right. 

---

## Part 4: Computing Probabilities & Interpreting the Tail

Let's assume our probability of success is $p = 0.2$. Let's set some targets: $k=3, a=2, b=4$.

### 1. Exactly $k$ trials: $P(X = k)$
**Target:** $k = 3$ (Exactly 3 attempts)
$P(X = 3) = (1 - 0.2)^{3-1} \cdot 0.2 = (0.8)^2 \cdot 0.2 = 0.64 \cdot 0.2 = 0.128$

### 2. Less than or equal to $k$: $P(X \le k)$
**Target:** $k = 3$ (3 attempts or fewer)
Using the CDF formula is instant:
$F(3) = 1 - (0.8)^3 = 1 - 0.512 = 0.488$

### 3. Greater than $k$ (The Tail Probability): $P(X > k)$
**Target:** $k = 3$ (More than 3 attempts)
$P(X > 3) = 1 - F(3) = 1 - (1 - (0.8)^3) = (0.8)^3 = 0.512$

**Interpretation of the Tail:** Notice that $P(X > k) = (1-p)^k$. This makes perfect logical sense! The *only* way you need more than $k$ trials is if you strictly failed your first $k$ attempts. The probability of $k$ consecutive failures is simply $(1-p)^k$. 

### 4. Interval: $P(a \le X \le b)$
**Target:** $P(2 \le X \le 4)$
Using the CDF:
$P(2 \le X \le 4) = F(4) - F(1) = [1 - (0.8)^4] - [1 - (0.8)^1] = (0.8)^1 - (0.8)^4 = 0.8 - 0.4096 = 0.3904$

---

## Part 5: Practical Applications of the Geometric Model

The Geometric model perfectly fits scenarios of "Waiting Times" or "Time to First Failure/Success" in discrete steps:

1. **Server Requests:** How many times a client must ping a congested server until it finally receives a successful response.
2. **Quality Assurance:** Testing items on an assembly line one by one; how many items must you test until you inevitably find the first defective one.
3. **Job Hunting:** How many interviews a candidate must attend until they receive their first job offer.
4. **Gambling:** How many times a gambler must spin a roulette wheel until they finally hit "00" for the first time.
