# Solution

## Task 4 — Weekly Weather Observation

### 1. One Day Observation ($\Omega_1$)

**Complete Tree Diagram:**

```text
START
 │
 ├── S
 ├── C
 └── R
```

* **Sample Space:** $\Omega_1 = \{S, C, R\}$
* **Number of Elementary Outcomes:** $|\Omega_1| = 3^1 = 3$

### 2. Two Consecutive Days ($\Omega_2$)

When observing for a second day, each of the previous outcomes branches out into 3 new possibilities.

**Complete Tree Diagram:**

```text
START
 │
 ├── S
 │   ├── S  ->  (S,S)
 │   ├── C  ->  (S,C)
 │   └── R  ->  (S,R)
 │
 ├── C
 │   ├── S  ->  (C,S)
 │   ├── C  ->  (C,C)
 │   └── R  ->  (C,R)
 │
 └── R
     ├── S  ->  (R,S)
     ├── C  ->  (R,C)
     └── R  ->  (R,R)
```

* **Sample Space:** $\Omega_2 = \{(w_1, w_2) \mid w_1, w_2 \in \{S, C, R\}\}$
* **Number of Elementary Outcomes:** $|\Omega_2| = 3^2 = 9$

### 3. Seven Consecutive Days ($\Omega_7$)

When we observe weather for seven days, the tree would have 7 levels and branch out into $3^7 = 2187$ paths.

**Conceptual Tree Diagram Framework:**

```text
START
 │
 ├── S  ->  (S,S,S,S,S,S,S), ..., (S,R,R,R,R,R,R)
 ├── C  ->  (C,S,S,S,S,S,S), ..., (C,R,R,R,R,R,R)
 └── R  ->  (R,S,S,S,S,S,S), ..., (R,R,R,R,R,R,R)
```

* **Sample Space:** $\Omega_7 = \{(w_1, w_2, \dots, w_7) \mid w_i \in \{S, C, R\}\}$
* **Number of Elementary Outcomes:** $|\Omega_7| = 3^7 = 2187$

### 5. What an Elementary Outcome Represents

An elementary outcome in $\Omega_7$ is an ordered sequence of 7 weather states, corresponding to the specific weather conditions observed on each of the seven consecutive days.
