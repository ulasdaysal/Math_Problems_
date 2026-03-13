# Solution

## Task 1 — Coin Tossing

### 1. One Coin Toss ($\Omega_1$)

**Complete Tree Diagram:**

```text
START
 │
 ├── H
 └── T
```

* **Sample Space:** $\Omega_1 = \{H, T\}$ (where $H$ stands for Heads and $T$ stands for Tails)
* **Number of Elementary Outcomes:** $|\Omega_1| = 2^1 = 2$

### 2. Two Coin Tosses ($\Omega_2$)

When we toss the coin a second time, each of the previous outcomes branches out into 2 new possibilities.

**Complete Tree Diagram:**

```text
START
 │
 ├── H
 │   ├── H  ->  (H,H)
 │   └── T  ->  (H,T)
 │
 └── T
     ├── H  ->  (T,H)
     └── T  ->  (T,T)
```

* **Sample Space:** $\Omega_2 = \{(H,H), (H,T), (T,H), (T,T)\}$
* **Number of Elementary Outcomes:** $|\Omega_2| = 2^2 = 4$

### 3. Three Coin Tosses ($\Omega_3$)

When we toss the coin a third time, each of the previous outcomes branches out into 2 new possibilities.

**Complete Tree Diagram:**

```text
START
 │
 ├── H
 │   ├── H
 │   │   ├── H  ->  (H,H,H)
 │   │   └── T  ->  (H,H,T)
 │   └── T
 │       ├── H  ->  (H,T,H)
 │       └── T  ->  (H,T,T)
 │
 └── T
     ├── H
     │   ├── H  ->  (T,H,H)
     │   └── T  ->  (T,H,T)
     └── T
         ├── H  ->  (T,T,H)
         └── T  ->  (T,T,T)
```

* **Sample Space:** $\Omega_3 = \{(H,H,H), (H,H,T), (H,T,H), (H,T,T), (T,H,H), (T,H,T), (T,T,H), (T,T,T)\}$
* **Number of Elementary Outcomes:** $|\Omega_3| = 2^3 = 8$

### 5. What an Elementary Outcome Represents

An elementary outcome represents a single specific ordered sequence of coin toss results (e.g., getting Heads on the first toss, Tails on the second, and Heads on the third).