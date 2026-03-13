# Solution

## Task 3 — Drawing Cards

Let $\text{Deck}$ denote the set of 52 cards in a standard deck.

### 1. One Card Drawn ($\Omega_1$)

**Conceptual Tree Diagram:**

The tree has 52 branches from START.

```text
START
 │
 ├── A♣
 ├── 2♣
 │   ...
 └── K♠
```

* **Sample Space:** $\Omega_1 = \{c \mid c \in \text{Deck}\}$
* **Number of Elementary Outcomes:** $|\Omega_1| = 52$

### 2. Two Cards Drawn With Replacement ($\Omega_2$)

Each of the 52 initial outcomes branches into 52 new possibilities because the card is returned to the deck.

**Conceptual Tree Diagram:**

```text
START
 │
 ├── A♣  ->  (A♣,A♣), (A♣,2♣), ..., (A♣,K♠)
 ├── 2♣  ->  (2♣,A♣), (2♣,2♣), ..., (2♣,K♠)
 │   ...
 └── K♠  ->  (K♠,A♣), (K♠,2♣), ..., (K♠,K♠)
```

* **Sample Space:** $\Omega_2 = \{(c_1, c_2) \mid c_1 \in \text{Deck}, c_2 \in \text{Deck}\}$
* **Number of Elementary Outcomes:** $|\Omega_2| = 52 \times 52 = 2704$

### 3. Two Cards Drawn Without Replacement ($\Omega_2'$)

Each of the 52 initial outcomes branches into 51 new possibilities because the drawn card cannot be drawn again.

**Conceptual Tree Diagram:**

```text
START
 │
 ├── A♣  ->  (A♣,2♣), (A♣,3♣), ..., (A♣,K♠)
 ├── 2♣  ->  (2♣,A♣), (2♣,3♣), ..., (2♣,K♠)
 │   ...
 └── K♠  ->  (K♠,A♣), (K♠,2♣), ..., (K♠,Q♠)
```

* **Sample Space:** $\Omega_2' = \{(c_1, c_2) \mid c_1 \in \text{Deck}, c_2 \in \text{Deck}, c_1 \neq c_2\}$
* **Number of Elementary Outcomes:** $|\Omega_2'| = 52 \times 51 = 2652$

### 5. What an Elementary Outcome Represents

An elementary outcome represents an ordered sequence of specific cards drawn from the deck. The sample spaces differ in whether the same card can appear twice in the sequence.
