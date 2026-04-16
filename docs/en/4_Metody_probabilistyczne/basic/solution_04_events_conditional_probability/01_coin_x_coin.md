# Problem 1 — Coin × Coin: Discovering Formalism

## Introduction to the formal model

Before we begin marking outcomes or interpreting matrices, we must first build a formal mathematical space that models our experiment. 

The experiment consists of tossing a coin twice. The fundamental concept here is the **sample space**, denoted by $\Omega$. The sample space is the set of all possible elementary outcomes of the experiment. An elementary outcome is the most precise description of what can physically happen, leaving no room for further distinction.

For a single coin toss, the outcomes are Heads ($H$) or Tails ($T$). For two tosses, an elementary outcome must specify the result of the *first* toss and the result of the *second* toss. 

Therefore, our sample space is the Cartesian product of the single-toss options:
$$ \Omega = \{H, T\} \times \{H, T\} $$

This gives us exactly four elementary outcomes:
$$ \Omega = \{(H, H), (H, T), (T, H), (T, T)\} $$

### The Graphical Representation

The problem provides a 2x2 grid representing this sample space. We must rigorously map our sample space $\Omega$ onto this grid. 

In mathematics, Cartesian products are often represented on axes. Let the vertical axis represent the outcome of the **first toss**, and let the horizontal axis represent the outcome of the **second toss**. 

```text
       Second Toss
        H   T
      +---+---+
 T  H |HH |HT |
 o    +---+---+
 s  T |TH |TT |
 s    +---+---+
 1
```

Any *event* is formally defined as a **subset** of the sample space ($A \subseteq \Omega$). By marking specific cells with an `X`, we are visually constructing these subsets. The empty cells `.` represent outcomes that do not belong to the event.

---

## Part A — Marking Events

We will translate each descriptive statement into a formal subset of $\Omega$ and then display its graphical representation.

### 1. Exactly one head

**Conceptual Analysis:** The phrase "exactly one" imposes a strict condition. If the first toss is $H$, the second *must* be $T$. If the first toss is $T$, the second *must* be $H$. 
**Formal Set:** $E_1 = \{(H, T), (T, H)\}$
**Graphical Representation:** We place an `X` in the top-right cell and the bottom-left cell.

```text
  H T
H . X
T X .
```

### 2. Both tosses are the same

**Conceptual Analysis:** Here we are looking for the diagonal of our Cartesian matrix. The first outcome dictates the second outcome. Either both are $H$, or both are $T$.
**Formal Set:** $E_2 = \{(H, H), (T, T)\}$
**Graphical Representation:** We place an `X` on the main diagonal (top-left and bottom-right).

```text
  H T
H X .
T . X
```

### 3. At least one head

**Conceptual Analysis:** "At least one" is a classic phrase in probability that typically suggests a union of conditions: exactly one head OR two heads. Alternatively, it can be viewed through the complement: the only situation that is *excluded* is when there are zero heads (i.e., exactly two tails). 
**Formal Set:** $E_3 = \{(H, H), (H, T), (T, H)\} = \Omega \setminus \{(T, T)\}$
**Graphical Representation:** We mark everywhere except the bottom-right cell.

```text
  H T
H X X
T X .
```

### 4. The first toss is tails

**Conceptual Analysis:** This statement specifies a condition for the first toss but leaves the second toss completely free. The second toss can be either $H$ or $T$. In our grid definition where the first toss is the vertical axis, this corresponds to marking an entire row.
**Formal Set:** $E_4 = \{(T, H), (T, T)\}$
**Graphical Representation:** We mark the entire bottom row.

```text
  H T
H . .
T X X
```

### 5. The second toss is heads

**Conceptual Analysis:** Analogous to the previous event, this imposes a strict condition on the second toss while the first toss acts as a free variable. This corresponds to a column in our grid.
**Formal Set:** $E_5 = \{(H, H), (T, H)\}$
**Graphical Representation:** We mark the entire left column.

```text
  H T
H X .
T X .
```

---

## Part B — Interpretation

Here, we must reverse the process. We are given the subsets visually, and we must translate them back into mathematical sets, and finally into natural language descriptions.

### Case 1

**Given Representation:**
```text
  H T
H X X
T . .
```

**Conceptual Analysis:** 
1. We observe that the entire top row is marked.
2. Let's read the elementary outcomes from the marked cells: The top-left cell is $(H, H)$ and the top-right cell is $(H, T)$. 
3. The formal subset is $C_1 = \{(H, H), (H, T)\}$.
4. What do these two pairs have in common? The first element in both pairs is $H$. The second element varies ($H$ or $T$). 
5. Therefore, the restrictive condition applies only to the first toss. 

**Interpretation:** The event represented is **"The first toss is heads"**.

---

### Case 2

**Given Representation:**
```text
  H T
H . X
T X .
```

**Conceptual Analysis:** 
1. We observe the counter-diagonal is marked.
2. Reading the cells gives us the subset: top-right is $(H, T)$, and bottom-left is $(T, H)$.
3. The formal subset is $C_2 = \{(H, T), (T, H)\}$.
4. In both tuples, the elements are different. Furthermore, in both tuples, the letter $H$ appears exactly one time. 

**Interpretation:** This is identical to Event 1 from Part A. The event can be described as **"Exactly one head occurs"** or equivalently **"The two tosses yield different results"**.
