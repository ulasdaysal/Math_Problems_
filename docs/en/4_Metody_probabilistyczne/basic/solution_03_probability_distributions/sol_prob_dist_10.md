# Solution

## Task 10 — Multinomial Model

### Problem Data
We are drawing $n = 6$ candies independently.
There are three categories of outcomes (flavors) with the following probabilities:
- Strawberry ($k_1$): $p_1 = 0.40$
- Lemon ($k_2$): $p_2 = 0.35$
- Mint ($k_3$): $p_3 = 0.25$

*(Check: $0.40 + 0.35 + 0.25 = 1.00$)*

**Why Multinomial?**  
This is a multinomial distribution because we are making a fixed number of independent draws ($n=6$) and classifying the results into more than two distinct and mutually exclusive categories (three candy flavors).

---

### Probability of obtaining exactly 3 strawberry, 2 lemon, and 1 mint
The specific counts we want are:
- $k_1 = 3$
- $k_2 = 2$
- $k_3 = 1$

*(Check: $3 + 2 + 1 = 6 = n$)*

The multinomial formula is:
$$ P(X_1=k_1, X_2=k_2, X_3=k_3) = \frac{n!}{k_1! \cdot k_2! \cdot k_3!} (p_1)^{k_1} (p_2)^{k_2} (p_3)^{k_3} $$

**What does this formula mean?**  
- $\frac{n!}{k_1! \cdot k_2! \cdot k_3!}$: The Multinomial Coefficient, representing all the different valid ways to order this specific combination of candies.  
- $(p_i)^{k_i}$: The individual probability of drawing flavor $i$ exactly $k_i$ times.  

Substitute the given values:
$$ P(3, 2, 1) = \frac{6!}{3! \cdot 2! \cdot 1!} \cdot (0.40)^3 \cdot (0.35)^2 \cdot (0.25)^1 $$

$$ P(3, 2, 1) \approx 0.1176 $$

The probability of drawing exactly this combination of candies is **$11.76\%$**.


