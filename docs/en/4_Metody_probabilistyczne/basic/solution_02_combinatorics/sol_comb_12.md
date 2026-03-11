# Solution

## Task 12 — Mixed Counting Problem

### 1. Student ID Codes

The ID format consists of 2 letters (from 5 possibilities: A,B,C,D,E) followed by 3 digits (from 10 possibilities: 0-9).

1. **How many identifiers are possible if letters and digits may repeat?**
   This combines two sequences with repetition.
   $$5^2 \times 10^3 = 25 \times 1,000 = 25,000$$

2. **How many identifiers are possible if letters may not repeat but digits may repeat?**
   This combines a k-permutation for letters and sequence with repetition for digits.
   $$P(5, 2) \times 10^3 = (5 \times 4) \times 1,000 = 20 \times 1,000 = 20,000$$

3. **How many identifiers are possible if neither letters nor digits may repeat?**
   This combines a k-permutation for letters and a k-permutation for digits.
   $$P(5, 2) \times P(10, 3) = (5 \times 4) \times (10 \times 9 \times 8) = 20 \times 720 = 14,400$$

---

### 2. Medal Assignment

12 runners, medals for gold, silver, bronze (3 distinct medals).

1. **In how many ways can the medals be assigned?**
   This is a k-permutation.
   $$P(12, 3) = \frac{12!}{9!} = 12 \times 11 \times 10 = 1,320$$

2. **Suppose two particular runners must both receive medals. In how many ways can the medals be assigned?**
   First, we assign 2 of the 3 available medals to the two particular runners. The number of ways to assign ordered medals to them is $P(3, 2) = 3 \times 2 = 6$.
   The remaining $1$ medal must be assigned to one of the remaining $10$ runners ($10$ ways).
   $$6 \times 10 = 60$$

---

### 3. Committee Selection

Committee of 4 people chosen from 10 students (6 men, 4 women).

1. **How many committees are possible?**
   Combination of 4 from 10.
   $$\binom{10}{4} = \frac{10 \times 9 \times 8 \times 7}{4 \times 3 \times 2 \times 1} = 210$$

2. **How many committees contain exactly two women?**
   Choose 2 from the 4 women, and 2 from the 6 men.
   $$\binom{4}{2} \times \binom{6}{2} = \left(\frac{4 \times 3}{2}\right) \times \left(\frac{6 \times 5}{2}\right) = 6 \times 15 = 90$$

3. **How many committees contain at least one woman?**
   Total committees minus committees with exactly *zero* women (all men).
   Committees with zero women (4 chosen from 6 men): $\binom{6}{4} = 15$.
   $$\binom{10}{4} - \binom{6}{4} = 210 - 15 = 195$$

---

### 4. Circular Seating

7 people round a round table.

1. **How many different seating arrangements are possible?**
   $$(7 - 1)! = 6! = 720$$

2. **In how many arrangements do two particular people sit next to each other?**
   Treat the two people as a single "block". There are 6 entities in the circle, so there are $(6 - 1)! = 5!$ circular permutations. Inside the block, the two individuals can switch seats in $2!$ ways.
   $$5! \times 2! = 120 \times 2 = 240$$

---

### 5. Passwords

A password of 5 characters from 10 digits and 26 letters (a total list of 36 distinct characters).

1. **How many passwords are possible if repetition is allowed?**
   $$36^5 = 60,466,176$$

2. **How many passwords are possible if no character may repeat?**
   $$P(36, 5) = \frac{36!}{31!} = 36 \times 35 \times 34 \times 33 \times 32 = 45,239,040$$

3. **Which counting model is used in each case?**
   - For case 1, where repetition is allowed, the **Sequence with repetition** model is used.
   - For case 2, where characters are distinct and order matters, the **k-Permutation (ordered selection without repetition)** model is used.
