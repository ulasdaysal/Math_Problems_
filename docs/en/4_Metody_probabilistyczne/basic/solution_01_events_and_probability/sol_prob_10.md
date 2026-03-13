# Solution

## Task 10 — Events and Probabilities in Buffon's Needle Experiment

The sample space $\Omega = \{(X, \theta) \mid 0 \le X \le \frac{d}{2}, 0 \le \theta \le \frac{\pi}{2}\}$.
The total "area" of the sample space is $\frac{d}{2} \times \frac{\pi}{2} = \frac{\pi d}{4}$. Since $X$ and $\theta$ are uniformly distributed, the probability of an event is its area divided by $\frac{\pi d}{4}$.

### Events
* $A$ (the needle intersects one of the lines): This occurs when $X \le \frac{L}{2} \sin \theta$.
  The area is $\int_0^{\pi/2} \frac{L}{2} \sin \theta \,d\theta = \frac{L}{2} [-\cos \theta]_0^{\pi/2} = \frac{L}{2} (0 - (-1)) = \frac{L}{2}$.
  $P(A) = \frac{L/2}{\pi d / 4} = \frac{2L}{\pi d}$

* $B$ (the needle does not intersect any line): This is the complement of event $A$.
  $P(B) = 1 - P(A) = 1 - \frac{2L}{\pi d}$

* $C$ (the angle is smaller than $\frac{\pi}{6}$): The condition is $0 \le \theta < \frac{\pi}{6}$.
  Since $\theta$ is independent of $X$ and uniform on $[0, \frac{\pi}{2}]$,
  $P(C) = \frac{\pi / 6}{\pi / 2} = \frac{1}{3}$

* $D$ (the center of the needle is at a distance less than $\frac{d}{4}$ from the line): Condition is $0 \le X < \frac{d}{4}$.
  Since $X$ is independent and uniform on $[0, \frac{d}{2}]$,
  $P(D) = \frac{d / 4}{d / 2} = \frac{1}{2}$

* $E$ (the needle intersects a line and the angle is greater than $\frac{\pi}{4}$): Condition is $X \le \frac{L}{2} \sin \theta$ and $\theta \in (\frac{\pi}{4}, \frac{\pi}{2}]$.
  The area is $\int_{\pi/4}^{\pi/2} \frac{L}{2} \sin \theta \,d\theta = \frac{L}{2} [-\cos \theta]_{\pi/4}^{\pi/2} = \frac{L}{2} \left(0 - \left(-\frac{\sqrt{2}}{2}\right)\right) = \frac{L\sqrt{2}}{4}$.
  $P(E) = \frac{L\sqrt{2}/4}{\pi d/4} = \frac{L\sqrt{2}}{\pi d}$

* **Additional event definition**: $F$ - the needle is perfectly parallel to the parallel lines.
  This means $\theta = 0$. The probability of picking exactly $\theta = 0$ from a continuous uniform distribution is exactly $0$.
  $P(F) = 0$
