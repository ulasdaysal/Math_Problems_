# Solution

## Task 1 — Binomial Model (Quality Control)

### 1. Description of the Random Experiment
The experiment consists of checking **3 consecutive screws** produced in the factory. Each screw is inspected independently to determine if it is **good (G)** or **defective (D)**. 

---

### 2. Sample Space ($\Omega$)
The sample space $\Omega$ contains all possible sequences of outcomes for the 3 inspected screws.

**Probability Tree Diagram:**

```text
START
 │
 ├── G
 │   ├── G
 │   │   ├── G  ->  (G,G,G)
 │   │   └── D  ->  (G,G,D)
 │   └── D
 │       ├── G  ->  (G,D,G)
 │       └── D  ->  (G,D,D)
 │
 └── D
     ├── G
     │   ├── G  ->  (D,G,G)
     │   └── D  ->  (D,G,D)
     └── D
         ├── G  ->  (D,D,G)
         └── D  ->  (D,D,D)
```

$\Omega = \{(G,G,G), (G,G,D), (G,D,G), (G,D,D), (D,G,G), (D,G,D), (D,D,G), (D,D,D)\}$

$|\Omega| = 2^3 = 8$

---

### 3. Probabilities of Elements of the Sample Space
Let $p$ be the probability of a screw being defective ($P(D) = p$).
Thus, the probability of a good screw is $q = 1 - p$ ($P(G) = 1 - p$).

Because the checks are independent, we multiply the individual probabilities:

| Outcome $\omega$ | Description | Probability $P(\omega)$ | Number of Defective ($k$) |
|:---:|:---|:---|:---:|
| $(G,G,G)$ | All 3 screws are good | $(1-p)^3$ | 0 |
| $(G,G,D)$ | First 2 good, 3rd defective | $(1-p)^2 \cdot p$ | 1 |
| $(G,D,G)$ | 1st good, 2nd defective, 3rd good | $(1-p)^2 \cdot p$ | 1 |
| $(D,G,G)$ | 1st defective, next 2 good | $(1-p)^2 \cdot p$ | 1 |
| $(G,D,D)$ | 1st good, next 2 defective | $(1-p) \cdot p^2$ | 2 |
| $(D,G,D)$ | 1st and 3rd defective | $(1-p) \cdot p^2$ | 2 |
| $(D,D,G)$ | 1st and 2nd defective | $(1-p) \cdot p^2$ | 2 |
| $(D,D,D)$ | All 3 screws are defective | $p^3$ | 3 |

---

### 4. Definition of "Success"
In probability modeling, a **"success"** does not necessarily mean a positive or desirable outcome; it simply refers to the specific characteristic we are tracking or counting.

In this model, since we are interested in the number of defective screws, **a "success" is defined as drawing a defective screw.**
- Probability of success: $p$
- Probability of failure: $1-p$
