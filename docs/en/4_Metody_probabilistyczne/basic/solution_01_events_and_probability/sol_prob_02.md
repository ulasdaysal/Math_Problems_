# Solution

## Task 2 — Rolling a Die

### 1. One Die Roll ($\Omega_1$)

**Complete Tree Diagram:**

```text
START
 │
 ├── 1
 ├── 2
 ├── 3
 ├── 4
 ├── 5
 └── 6
```

* **Sample Space:** $\Omega_1 = \{1, 2, 3, 4, 5, 6\}$
* **Number of Elementary Outcomes:** $|\Omega_1| = 6^1 = 6$

### 2. Two Die Rolls ($\Omega_2$)

When we roll the die a second time, each of the 6 previous outcomes branches out into 6 new possibilities. To keep the diagram brief but complete (without abbreviations), the final outcomes are grouped horizontally.

**Complete Tree Diagram:**

```text
START
 │
 ├── 1  ->  (1,1), (1,2), (1,3), (1,4), (1,5), (1,6)
 ├── 2  ->  (2,1), (2,2), (2,3), (2,4), (2,5), (2,6)
 ├── 3  ->  (3,1), (3,2), (3,3), (3,4), (3,5), (3,6)
 ├── 4  ->  (4,1), (4,2), (4,3), (4,4), (4,5), (4,6)
 ├── 5  ->  (5,1), (5,2), (5,3), (5,4), (5,5), (5,6)
 └── 6  ->  (6,1), (6,2), (6,3), (6,4), (6,5), (6,6)
```

* **Sample Space:** $\Omega_2 = \{(1,1), (1,2), \dots, (6,5), (6,6)\}$
* **Number of Elementary Outcomes:** $|\Omega_2| = 6^2 = 36$

### 3. Three Die Rolls ($\Omega_3$)

When we roll the die a third time, each of the 36 previous outcomes branches out into 6 new possibilities.

**Conceptual Tree Diagram Framework:**

```text
START
 │
 ├── 1  ->  (1,1,1), (1,1,2), ..., (1,6,5), (1,6,6)
 ├── 2  ->  (2,1,1), (2,1,2), ..., (2,6,5), (2,6,6)
 ├── 3  ->  (3,1,1), (3,1,2), ..., (3,6,5), (3,6,6)
 ├── 4  ->  (4,1,1), (4,1,2), ..., (4,6,5), (4,6,6)
 ├── 5  ->  (5,1,1), (5,1,2), ..., (5,6,5), (5,6,6)
 └── 6  ->  (6,1,1), (6,1,2), ..., (6,6,5), (6,6,6)
```

* **Sample Space:** $\Omega_3 = \{(x, y, z) \mid x, y, z \in \{1, 2, 3, 4, 5, 6\}\}$
* **Number of Elementary Outcomes:** $|\Omega_3| = 6^3 = 216$

### 5. What an Elementary Outcome Represents

An elementary outcome represents an ordered sequence of numbers that appeared on the top face of the die in consecutive rolls.
