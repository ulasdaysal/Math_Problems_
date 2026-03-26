# Solution

## Task 3 — Geometric Model (Waiting for the First Event)

### 1. Description of the Random Experiment
The experiment consists of checking sequentially printed pages one by one. The observation continues indefinitely until a page containing a **printing error** appears.

---

### 2. Sample Space ($\Omega$)
The sample space $\Omega$ represents the sequence of trials until the first success (first error) occurs.

Let $S$ represent a success (finding an error) and $F$ represent a failure (finding a good page).
If we need $k$ trials to find the first error, the sequence consists of $k-1$ failures followed by $1$ success:

$$ \Omega = \{S, FS, FFS, FFFS, FFFFS, \dots \} $$

Or in terms of the random variable $X$ (number of trials):
$$ \Omega_X = \{1, 2, 3, 4, 5, \dots \} = \mathbb{N}^+ $$

---

### 3. Probability Distribution
This follows a **Geometric Distribution**. The probability that the first error appears exactly on the $k$-th page means we must have $k-1$ non-error pages followed by $1$ error page.

Using $p$ as the probability of an error on any given page:
* $P(S) = p$
* $P(F) = 1 - p$

The probability distribution is given by:

$$ P(X = k) = (1 - p)^{k-1} \cdot p $$

Where:
- $X$ is the random variable (the trial number of the first success)
- $k \in \{1, 2, 3, \dots\}$

**Example Sequence of Probabilities:**

| $k$ (Trial of 1st error) | Sequence | Probability $P(X=k)$ |
|:---:|:---:|:---|
| **1** | $S$ | $p$ |
| **2** | $FS$ | $(1-p)p$ |
| **3** | $FFS$ | $(1-p)^2p$ |
| **4** | $FFFS$ | $(1-p)^3p$ |
| **...** | ... | ... |
| **$k$** | $F \dots FS$ ($k-1$ F's) | $(1-p)^{k-1}p$ |

---

### 4. Definition of "Success"
In this geometric model, the **"success"** is the occurrence of the event we are waiting for. Here, **a success is defined as encountering a printing error**. This is the event that terminates our sequence of observations.
