# Problem 1
# Water Surface Interference Patterns Analysis

## Introduction to Wave Interference

Wave interference is a fundamental phenomenon in wave physics where two or more waves overlap and combine to form a resultant wave. The principle of superposition states that when multiple waves coincide at the same point in space, the resultant displacement is the algebraic sum of the individual wave displacements. This document explores the interference patterns formed by water waves emanating from point sources positioned at the vertices of a regular polygon.

## Key Concepts and Formulas

### Single Wave Disturbance

A circular wave on a water surface from a point source located at $(x_0, y_0)$ can be described by:

$$\eta(x, y, t) = \frac{A}{\sqrt{r}} \cdot \cos(kr - \omega t + \phi)$$

Where:
- $\eta(x, y, t)$ represents the displacement of the water surface at point $(x, y)$ and time $t$
- $A$ is the amplitude of the wave
- $k = \frac{2\pi}{\lambda}$ is the wave number, related to wavelength $\lambda$
- $\omega = 2\pi f$ is the angular frequency, related to frequency $f$
- $r = \sqrt{(x - x_0)^2 + (y - y_0)^2}$ is the distance from the source to point $(x, y)$
- $\phi$ is the initial phase angle

### Principle of Superposition

When multiple waves overlap, the total displacement at any point is the sum of individual displacements:

$$\eta_{\text{sum}}(x, y, t) = \sum_{i=1}^{N} \eta_i(x, y, t)$$

Where $N$ is the number of wave sources.

### Constructive and Destructive Interference

- **Constructive interference** occurs when waves combine to create a larger amplitude. This happens when waves are approximately in phase.
- **Destructive interference** occurs when waves combine to create a smaller amplitude or cancel each other out. This happens when waves are approximately out of phase.

The path difference $\Delta r$ between two sources determines the type of interference:
- Constructive interference: $\Delta r = n\lambda$ (where $n = 0, 1, 2, ...$)
- Destructive interference: $\Delta r = (n+\frac{1}{2})\lambda$ (where $n = 0, 1, 2, ...$)

## Analysis of Interference Patterns for a Regular Polygon

For this analysis, we'll examine the interference patterns created by wave sources placed at the vertices of a regular polygon. We'll focus on three cases:
1. Equilateral triangle (3 vertices)
2. Square (4 vertices)
3. Regular pentagon (5 vertices)

### Mathematical Formulation

For a regular polygon with $N$ vertices centered at the origin, the coordinates of each vertex can be calculated as:

$$
x_i = R \cdot \cos\left(\frac{2\pi i}{N}\right)
$$

$$
y_i = R \cdot \sin\left(\frac{2\pi i}{N}\right)
$$


Where:
- $R$ is the radius of the circumscribed circle of the polygon
- $i$ ranges from 0 to $N-1$

The total wave displacement at any point $(x, y)$ at time $t$ is:

$$\eta_{\text{sum}}(x, y, t) = \sum_{i=0}^{N-1} \frac{A}{\sqrt{r_i}} \cdot \cos(kr_i - \omega t + \phi_i)$$

Where:
- $r_i = \sqrt{(x - x_i)^2 + (y - y_i)^2}$ is the distance from the $i$-th source to point $(x, y)$
- $\phi_i$ is the initial phase of the $i$-th source

## Python Implementation and Visualization

Let's implement the analysis in Python to visualize the interference patterns for various source arrangements, including both 2D heatmaps and 3D surface plots, with animations.

## Single Source

![alt text](single_source_wave.gif)

![alt text](<single source_3d_animation.gif>)

-----

## Two Sources

![alt text](two_sources_interference.gif)

![alt text](<two sourced3D.gif>)

## Triangle Sources

![alt text](3_sources_interference.gif)

![alt text](triangle_3d_animation.gif)

## Square Sources

![alt text](4_sources_interference.gif)

![alt text](square_3d_animation.gif)

## Results and Analysis

### Single Source Analysis

When examining the wave pattern from a single source:

1. **Circular Symmetry**: The pattern shows perfect circular symmetry, with concentric rings of crests and troughs radiating outward.

2. **Amplitude Decay**: The wave amplitude decreases as $1/\sqrt{r}$ with distance from the source, following the conservation of energy as the wave spreads out.

3. **Phase Progression**: The phase of the wave progresses radially outward, with adjacent crests separated by one wavelength.

4. **No Interference**: With only one source, there is no interference pattern - the displacement at any point is determined solely by the distance from the source and the wave properties.

### Two Sources Interference

The two-source interference pattern reveals several key features:

1. **Hyperbolic Nodal Lines**: We observe hyperbolic lines of destructive interference where the path difference between waves from the two sources equals $(n+\frac{1}{2})\lambda$, creating nodal lines.

2. **Constructive Interference**: Along the perpendicular bisector of the line connecting the two sources, we see constructive interference because waves arrive with equal path lengths.

3. **Standing Wave Pattern**: Between the sources, a standing wave pattern forms, with alternating regions of constructive and destructive interference.

4. **Symmetry**: The pattern exhibits symmetry about both the line connecting the sources and the perpendicular bisector of that line.

### Equilateral Triangle (3 Sources)

When we analyze the interference pattern from three sources arranged in an equilateral triangle:

1. **Three-fold Rotational Symmetry**: The pattern shows three-fold rotational symmetry, reflecting the geometry of the source arrangement.

2. **Nodal Lines**: We observe lines of destructive interference (nodes) radiating from the center in three primary directions, bisecting the angles between adjacent sources.

3. **Central Interference**: At the center of the triangle, all three waves arrive with equal path lengths, leading to constructive interference if the sources are in phase.

4. **Hyperbolic Patterns**: Between pairs of sources, we observe hyperbolic patterns of constructive and destructive interference. These hyperbolas represent points of constant path difference between any two sources.

5. **Complex Interaction Regions**: The regions where interference patterns from all three pairs of sources overlap create complex interference structures with distinctive amplitude patterns.

### Square (4 Sources)

With sources arranged at the vertices of a square:

1. **Four-fold Symmetry**: The interference pattern exhibits four-fold rotational symmetry.

2. **Nodal Structure**: Four primary nodal lines emerge from the center, creating a distinctive "cross" pattern of destructive interference.

3. **Central Region**: The center shows complex interference behavior that depends on the relative phases of the sources. With all sources in phase, we observe strong constructive interference.

4. **Fringe Patterns**: The interference fringes between any two adjacent sources form more intricate patterns compared to the triangle case, with additional interference effects from the other two sources.

5. **Secondary Maxima**: Regions of secondary constructive interference appear between the primary nodal lines, creating a checkerboard-like pattern in some areas.

### Regular Pentagon (5 Sources)

With five sources arranged in a regular pentagon:

1. **Five-fold Symmetry

## Time Evolution and Phase Effects

The interference patterns evolve over time as the waves propagate. At any fixed point in space, the displacement oscillates as the phases of the contributing waves change with time. The animation demonstrates this dynamic behavior.

Additionally, we can explore the effect of introducing phase differences between the sources:


## Conclusion

This analysis demonstrates how wave interference patterns emerge from multiple coherent sources arranged in regular polygonal configurations. These patterns exhibit symmetries that reflect the geometrical arrangement of the sources and show both constructive and destructive interference regions.

The mathematical formulation based on the principle of superposition allows us to predict and visualize these complex patterns. The visualization tools provided in this document can be extended to explore different source configurations, wavelengths, and phase relationships.

Understanding these interference patterns has applications in various fields, including:
- Acoustic design and noise cancellation
- Optical systems and holography
- Antenna array design in telecommunications
- Seismic wave analysis

By manipulating the number of sources, their relative positions, and phases, we can engineer specific interference patterns for practical applications.

[COLAB LINK](https://colab.research.google.com/drive/1icTpSweIKJ4YhCPco-I5R4p4PUzlqDEP?usp=sharing)



