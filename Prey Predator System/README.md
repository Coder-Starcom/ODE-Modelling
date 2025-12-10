# 🍽️ The Concept: Lotka-Volterra Model

The model describes a simple ecosystem where a population of prey (like rabbits 🐇) is hunted by a population of predators (like foxes 🦊). The key idea is that the rate of change for each population depends on the size of _both_ populations.

## 🐇 The Prey Population ($x$)

The prey population, $x(t)$, changes based on two main factors:

1.  **Natural Growth:** If there are no predators, the prey population grows exponentially (births).
2.  **Predation:** When prey and predators meet, the prey population decreases (deaths).

## 🦊 The Predator Population ($y$)

The predator population, $y(t)$, also changes based on two main factors:

1.  **Natural Decay:** If there is no food (prey), the predator population declines exponentially (deaths).
2.  **Feeding/Reproduction:** When predators successfully hunt prey, the predator population increases (births).

## 📝 The Coupled Equations

The model is defined by this system of two coupled first-order differential equations:

$$
\frac{dx}{dt} = x(a - by) \quad \text{(Prey)}
$$

$$
\frac{dy}{dt} = y(-c +dx) \quad \text{(Predator)}
$$

Where $a, b, c, d$ are positive constants:

| Coefficient | Equation        | Meaning                                                                                     |
| :---------- | :-------------- | :------------------------------------------------------------------------------------------ |
| $a$         | $\frac{dx}{dt}$ | **Prey Birth Rate:** The rate at which prey reproduce.                                      |
| $b$         | $\frac{dx}{dt}$ | **Predation Rate:** How often predators successfully kill prey.                             |
| $c$         | $\frac{dy}{dt}$ | **Predator Death Rate:** The rate at which predators die naturally.                         |
| $d$         | $\frac{dy}{dt}$ | **Conversion Rate:** How efficiently predators turn consumed prey into new predator births. |

---

# 🔄 The Dynamics: A Never-Ending Cycle

The most famous feature of the Lotka-Volterra model is that it produces **stable, periodic oscillations** 🌊. The populations rise and fall in a predictable, cyclical pattern:

1.  **Prey Boom:** When the predator population ($y$) is low, the prey population ($x$) grows rapidly (driven by $ax$).
2.  **Predator Follows:** As the prey population becomes abundant, the predators have plenty of food, so the predator population starts to grow (driven by $dxy$).
3.  **Prey Crash:** The large predator population eats the prey faster than they can reproduce, causing the prey population to crash (driven by $-bxy$).
4.  **Predator Crash:** With the prey population scarce, the predators starve, and their population crashes (driven by $-cy$).
5.  **Cycle Restarts:** With few predators left, the remaining prey can start to reproduce again, and the cycle begins anew.

The two populations are always out of sync: the predator peak always **lags behind** the prey peak 📈.

---

# 🚀 The Solution Method: RK4

Just like the love dynamics model, the Lotka-Volterra equations are **non-linear** (because of the $xy$ terms), which means they are very difficult (or impossible) to solve exactly with simple formulas.

This is where the **Fourth-Order Runge-Kutta (RK4) method** becomes essential! It allows us to accurately trace the path of the populations over time.

## 🛠️ Applying RK4 to Ecology

We treat the two equations as a coupled system, calculating the change for both $x$ and $y$ simultaneously at each time step $h$.

For a time step $h$, we calculate the new population values $x_{i+1}$ and $y_{i+1}$ from the current values $x_i$ and $y_i$:

$$
x_{i+1} = x_i + \frac{1}{6}(k_{x1} + 2k_{x2} + 2k_{x3} + k_{x4})
$$

$$
y_{i+1} = y_i + \frac{1}{6}(k_{y1} + 2k_{y2} + 2k_{y3} + k_{y4})
$$

We calculate the four slope estimates ($k_1$ through $k_4$) for both the prey ($x$) and the predator ($y$) equations, using the current values of _both_ $x$ and $y$ in the rate functions ($\frac{dx}{dt}$ and $\frac{dy}{dt}$) at every step.

By repeating this process many times, we generate a series of points that accurately map out the cyclical rise and fall of the prey and predator populations over a long period 🕰️.
