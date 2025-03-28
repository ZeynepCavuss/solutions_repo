# Problem 1
# Investigating the Range as a Function of the Angle of Projection

## 1. Theoretical Foundation

Projectile motion is governed by Newton's laws and kinematic equations. The motion can be broken into two components:

- **Horizontal Motion:** Constant velocity motion
- **Vertical Motion:** Motion under constant acceleration due to gravity

The equations of motion are derived as follows:

$$ x(t) = v_0 \cos(\theta) t $$
$$ y(t) = v_0 \sin(\theta) t - \frac{1}{2} g t^2 $$

where:
- $v_0$ is the initial velocity,
- $\theta$ is the angle of projection,
- $g$ is the acceleration due to gravity,
- $x(t)$ and $y(t)$ describe the projectile's position at time $t$.

The time of flight is given by:

$$ T = \frac{2 v_0 \sin(\theta)}{g} $$

The horizontal range is then:

$$ R = \frac{v_0^2 \sin(2\theta)}{g} $$

This equation shows that the range depends on both the initial velocity and the launch angle.

## 2. Useful Formulas and Definitions

- **Maximum Height:**
  $$ H = \frac{v_0^2 \sin^2(\theta)}{2g} $$
- **Time of Flight:**
  $$ T = \frac{2 v_0 \sin(\theta)}{g} $$
- **Optimal Range Angle:**
  The range is maximized when $ \theta = 45^\circ $.

## 3. Example Calculations

### Example 1: Finding the Range of a Projectile

**Given:**
- $ v_0 = 20 \text{ m/s} $
- $ g = 9.81 \text{ m/s}^2 $
- $ \theta = 30^\circ $

**Solution:**

Using the range formula:

$$ R = \frac{(20)^2 \sin(60^\circ)}{9.81} $$
$$ R \approx 35.3 \text{ m} $$

### Example 2: Finding the Maximum Height

For the same values:

$$ H = \frac{(20)^2 \sin^2(30^\circ)}{2(9.81)} $$
$$ H \approx 5.1 \text{ m} $$

## 4. Computational Implementation

To visualize the relationship between range and angle, we implement a Python simulation:

```python
import numpy as np
import matplotlib.pyplot as plt

g = 9.81  # Gravity (m/s^2)
v0 = 20   # Initial velocity (m/s)
angles = np.linspace(0, 90, 100)
range_values = (v0**2 * np.sin(np.radians(2 * angles))) / g

plt.plot(angles, range_values, label="Range vs. Angle")
plt.xlabel("Launch Angle (degrees)")
plt.ylabel("Range (m)")
plt.title("Projectile Range as a Function of Angle")
plt.legend()
plt.grid()
plt.show()
```

## 5. Discussion and Real-World Applications

- The idealized model assumes no air resistance. In real-world applications (e.g., sports, engineering), drag significantly affects projectile motion.
- The maximum range occurs at $45^\circ$, but wind and terrain can shift this value.
- Understanding projectile motion is crucial in ballistics, sports physics, and aerospace engineering.

---

