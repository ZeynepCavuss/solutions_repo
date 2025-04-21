# Problem 2
# Escape Velocities and Cosmic Velocities

## Motivation

The concept of escape velocity is essential to understand the conditions required to overcome the gravitational influence of a celestial body. The first, second, and third cosmic velocities represent thresholds for orbital motion, escaping a planet, and escaping a star system, respectively. These principles are fundamental in space exploration, including satellite launches, planetary missions, and potential interstellar travel.

---

## First Cosmic Velocity (Orbital Velocity)

The first cosmic velocity is the minimum velocity required for an object to remain in a stable circular orbit around a celestial body without any additional propulsion.

$$
v_1 = \sqrt{\frac{GM}{R}}
$$

Where:

- \( G \): Gravitational constant \( = 6.67430 \times 10^{-11} \, \text{m}^3\,\text{kg}^{-1}\,\text{s}^{-2} \)
- \( M \): Mass of the celestial body (in kg)
- \( R \): Distance from the center of the celestial body to the object (in meters)

---

## Second Cosmic Velocity (Escape Velocity)

The second cosmic velocity is the minimum velocity required for an object to escape the gravitational field of a celestial body without further propulsion.

$$
v_2 = \sqrt{\frac{2GM}{R}} = \sqrt{2} \cdot v_1
$$

Where all symbols are as previously defined.

---

## Third Cosmic Velocity (Interstellar Velocity)

The third cosmic velocity is the minimum velocity required to escape not only a planet’s gravity but also the gravitational influence of its parent star (e.g., the Sun).

For Earth-based calculations:

$$
v_3 = \sqrt{v_{\text{escape, Sun}}^2 + v_{\text{orbital, Earth}}^2}
$$

Where:

- \( v_{\text{escape, Sun}} \): Escape velocity from the Sun at Earth’s orbital distance
- \( v_{\text{orbital, Earth}} \): Earth’s orbital velocity around the Sun

This formula combines the required velocity to escape both Earth and the Sun, assuming the spacecraft is initially moving with Earth's orbital speed.

---

## Python Script: Cosmic Velocity Calculator

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
G = 6.67430e-11  # gravitational constant in m^3 kg^-1 s^-2

# Celestial bodies: (mass in kg, radius in meters)
bodies = {
    'Earth':   {'mass': 5.972e24, 'radius': 6.371e6},
    'Mars':    {'mass': 6.417e23, 'radius': 3.3895e6},
    'Jupiter': {'mass': 1.898e27, 'radius': 6.9911e7}
}

# Calculate velocities
results = {}
for body, data in bodies.items():
    M = data['mass']
    R = data['radius']
    v1 = np.sqrt(G * M / R)
    v2 = np.sqrt(2 * G * M / R)
    results[body] = {'v1': v1, 'v2': v2}

# Plotting
labels = list(results.keys())
v1_vals = [results[b]['v1'] for b in labels]
v2_vals = [results[b]['v2'] for b in labels]

x = np.arange(len(labels))
width = 0.35

fig, ax = plt.subplots()
ax.bar(x - width/2, v1_vals, width, label='First Cosmic Velocity (m/s)')
ax.bar(x + width/2, v2_vals, width, label='Second Cosmic Velocity (m/s)')

ax.set_ylabel('Velocity (m/s)')
ax.set_title('Cosmic Velocities of Celestial Bodies')
ax.set_xticks(x)
ax.set_xticklabels(labels)
ax.legend()

plt.grid(True, linestyle='--', alpha=0.5)
plt.tight_layout()
plt.show()
```