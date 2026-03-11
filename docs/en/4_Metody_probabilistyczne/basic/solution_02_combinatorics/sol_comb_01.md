# Solution

## Task 1 — Recognizing Counting Models

For each situation, we determine the appropriate combinatorial model based on whether order matters, if all objects are used, and if objects or repetitions are allowed.

1. **Arranging 7 students in a line.**
   * **Model:** Permutation
   * **Reason:** We are arranging *all* 7 students, order matters, and there is no repetition.

2. **Choosing 4 members of a committee from 12 people.**
   * **Model:** Combination
   * **Reason:** We are selecting a subset of people (not all of them), and the order in which we select committee members does not matter.

3. **Assigning gold, silver, and bronze medals among 15 athletes.**
   * **Model:** k-permutation (ordered selection without repetition)
   * **Reason:** We are choosing a subset (3 out of 15), order matters (gold is different from silver/bronze), and an athlete cannot receive more than one medal of these types (no repetition).

4. **Forming a 6-digit PIN code.**
   * **Model:** Sequence with repetition
   * **Reason:** We choose 6 digits, order matters, and digits can be repeated.

5. **Arranging the letters of the word BANANA.**
   * **Model:** Permutation with repeated elements
   * **Reason:** We are arranging all letters, but some letters are identical (e.g., three 'A's, two 'N's) and therefore indistinguishable.

6. **Seating 6 people around a round table.**
   * **Model:** Circular permutation
   * **Reason:** People are arranged in a circle where only their relative positions matter, and rotations are considered the same arrangement.
