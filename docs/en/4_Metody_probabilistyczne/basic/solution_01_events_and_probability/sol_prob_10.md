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

<br>

### Experiment Visualization (Python Simulation)

To better understand and visualize this concept, we can simulate Buffon's Needle experiment using Python. The following script simulates dropping the needle thousands of times and visualizes the results, providing an experimental approximation of the probabilities and $\pi$.

```python
import numpy as np
import matplotlib.pyplot as plt

def simulate_buffons_needle(num_drops=10000, d=2.0, L=1.0):
    # d: distance between lines
    # L: length of the needle
    
    # 1. Generate random center positions X in [0, d/2]
    X = np.random.uniform(0, d/2, num_drops)
    
    # 2. Generate random angles theta in [0, pi/2]
    theta = np.random.uniform(0, np.pi/2, num_drops)
    
    # Check intersection condition
    # The needle crosses a line if X <= (L/2) * sin(theta)
    crosses = X <= (L / 2) * np.sin(theta)
    
    # Calculate probabilities
    p_A = np.sum(crosses) / num_drops
    
    # Estimate Pi based on P(A) = 2L / (pi * d) => pi = 2L / (P(A) * d)
    if p_A > 0:
        pi_estimate = (2 * L) / (p_A * d)
    else:
        pi_estimate = 0
        
    # Visualization
    plt.figure(figsize=(10, 6))
    
    # Plot non-crossing drops
    plt.scatter(theta[~crosses], X[~crosses], color='blue', alpha=0.5, label='No Intersection', s=5)
    
    # Plot crossing drops
    plt.scatter(theta[crosses], X[crosses], color='red', alpha=0.5, label='Intersection', s=5)
    
    # Plot the theoretical boundary: X = (L/2) * sin(theta)
    theta_line = np.linspace(0, np.pi/2, 100)
    X_line = (L / 2) * np.sin(theta_line)
    plt.plot(theta_line, X_line, color='black', linewidth=2, label='Boundary: X = (L/2)*sin(θ)')
    
    plt.xlim(0, np.pi/2)
    plt.ylim(0, d/2)
    plt.xlabel('Angle (θ) in radians')
    plt.ylabel('Distance from center to line (X)')
    plt.title(f"Buffon's Needle Simulation ({num_drops} drops)\nEstimated π ≈ {pi_estimate:.4f}")
    plt.legend()
    plt.grid(True)
    plt.show()

# Run the simulation
simulate_buffons_needle()
```
