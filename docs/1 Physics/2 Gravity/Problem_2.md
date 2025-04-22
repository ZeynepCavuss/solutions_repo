
## Motivation

Escape velocity is the speed required for an object to break free from a celestial body's gravitational influence. The concept extends to three "cosmic velocities":

1. **First cosmic velocity**: Orbit a planet
2. **Second cosmic velocity**: Escape a planet
3. **Third cosmic velocity**: Escape the star system

---

## First Cosmic Velocity (Orbital Velocity)

Minimum speed required to maintain a stable circular orbit around a celestial body:

$$
v_1 = \sqrt{\frac{G M}{R}}
$$

Where:

- $G = 6.67430 \times 10^{-11}\,\mathrm{m}^3\!\,\mathrm{kg}^{-1}\!\,\mathrm{s}^{-2}$ is the **gravitational constant**.
- $M$ is the **mass of the celestial body** (in kilograms).
- $R$ is the **distance from the center of the celestial body to the object** (in meters).


---

## Second Cosmic Velocity (Escape Velocity)

Minimum speed required to leave a celestial body entirely without returning:

$$
v_2 = \sqrt{\frac{2 G M}{R}} = \sqrt{2} \cdot v_1
$$

---

## Third Cosmic Velocity (Interstellar Velocity)

Speed needed to escape both Earth and the Sun’s gravity:

$$
v_3 = \sqrt{v_{\text{escape\_sun}}^2 + v_{\text{orbital\_earth}}^2}
$$

Where:

- $v_{\text{escape\_sun}}$ is the escape velocity from the Sun at Earth's orbit.
- $v_{\text{orbital\_earth}}$ is Earth's orbital speed around the Sun.


---

## Python Code: Compute and Visualize Cosmic Velocities

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
G = 6.67430e-11  # m^3 kg^-1 s^-2

# Planet data: mass (kg), radius (m)
bodies = {
    "Earth": {"mass": 5.972e24, "radius": 6.371e6},
    "Mars": {"mass": 6.417e23, "radius": 3.3895e6},
    "Jupiter": {"mass": 1.898e27, "radius": 6.9911e7}
}

results = {}

for name, data in bodies.items():
    M = data["mass"]
    R = data["radius"]
    v1 = np.sqrt(G * M / R)
    v2 = np.sqrt(2 * G * M / R)
    results[name] = {"v1": v1, "v2": v2}

# Plotting
```
