# Solution

## Task 10 — Multinomial Model

### Problem Data
We are drawing $n = 6$ candies independently.
There are three categories of outcomes (flavors) with the following probabilities:
- Strawberry ($k_1$): $p_1 = 0.40$
- Lemon ($k_2$): $p_2 = 0.35$
- Mint ($k_3$): $p_3 = 0.25$

*(Check: $0.40 + 0.35 + 0.25 = 1.00$)*

---

### Probability of obtaining exactly 3 strawberry, 2 lemon, and 1 mint
The specific counts we want are:
- $k_1 = 3$
- $k_2 = 2$
- $k_3 = 1$

*(Check: $3 + 2 + 1 = 6 = n$)*

The multinomial formula is:
$$ P(X_1=k_1, X_2=k_2, X_3=k_3) = \frac{n!}{k_1! \cdot k_2! \cdot k_3!} (p_1)^{k_1} (p_2)^{k_2} (p_3)^{k_3} $$

Substitute the given values:
$$ P(3, 2, 1) = \frac{6!}{3! \cdot 2! \cdot 1!} \cdot (0.40)^3 \cdot (0.35)^2 \cdot (0.25)^1 $$

**Step-by-step calculation:**
1. **Factorial part (Multinomial Coefficient):**
   $$ \frac{720}{6 \cdot 2 \cdot 1} = \frac{720}{12} = 60 $$
   *(This means there are 60 different valid ordering sequences of drawing 3 strawberry, 2 lemon, and 1 mint)*

2. **Probability products:**
   $$ (0.40)^3 = 0.064 $$
   $$ (0.35)^2 = 0.1225 $$
   $$ (0.25)^1 = 0.25 $$

3. **Bring it all together:**
   $$ P(3, 2, 1) = 60 \cdot 0.064 \cdot 0.1225 \cdot 0.25 $$
   $$ P(3, 2, 1) = 60 \cdot 0.00196 $$
   $$ P(3, 2, 1) = 0.1176 $$

The probability of drawing exactly this combination of candies is **$11.76\%$**.
