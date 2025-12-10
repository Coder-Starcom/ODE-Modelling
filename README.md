# Lotka–Volterra & Dynamics of Love ❤️🦊🌱

## Overview

This project explores two types of **interacting systems**:

1. **Lotka–Volterra Predator–Prey Model** 🐇🦊
2. **Love Dynamics Model (Romeo & Juliet)** 💑

Both are described by **ordinary differential equations (ODEs)** and share similar mathematical structure, showing how **mutual interactions lead to oscillatory or equilibrium behavior**.

---

## **1. Lotka–Volterra Predator–Prey Model** 🌱🦊

$$
\begin{cases}
\frac{dx}{dt} = ax - bxy \\
\frac{dy}{dt} = -cy + dxy
\end{cases}
$$

- (x) — Prey population 🌱
- (y) — Predator population 🦊
- (a) — Prey growth rate
- (b) — Predation rate
- (c) — Predator death rate
- (d) — Predator growth efficiency

**Dynamics:**

- Populations **oscillate out of phase** (prey peaks before predator).
- **Equilibrium point**: ($$x^* = \frac{c}{d}, \; y^* = \frac{a}{b}$$).
- Different parameters produce:

  - Gentle oscillations
  - Boom-and-bust cycles
  - Predator or prey dominance

**Applications in Semesters:**

- **Sem 2 (ODE):** Analytical solutions, equilibrium analysis
- **Sem 3 (Numerical Methods):** Phase plots, conserved quantities, visualization

---

## **2. Love Dynamics Model (Romeo & Juliet)** 💑

$$
\begin{cases}
\frac{dJ}{dt} = a J + b R \\
\frac{dR}{dt} = c J + d R
\end{cases}
$$

- (J(t)) — Juliet’s affection for Romeo
- (R(t)) — Romeo’s affection for Juliet
- (a, d) — self-reaction (self-love, self-doubt)
- (b, c) — response to partner’s feelings

**Dynamics:**

- Positive feedback ((b,c > 0)) → mutual love grows, can oscillate before stabilizing 💖
- Negative feedback ((b,c < 0)) → jealousy or avoidance, leading to oscillations or decline 💔
- Similar to Lotka–Volterra, **interactions drive the dynamics**

---

## **3. Connection Between Models**

- Both systems are **interacting ODEs**
- Both exhibit **oscillations and equilibrium points**
- Predator–prey → survival and resource dependence
- Love model → emotional response and mutual influence
- Analysis techniques (phase plots, stability, conserved quantities) **apply to both**

---

## **4. Test Cases**

- **Lotka–Volterra:** 5 scenarios with different growth and predation rates, showing stable oscillations, predator dominance, and boom-bust cycles 🌱🦊
- **Love Model:** Different combinations of (a,b,c,d) illustrate mutual attraction, oscillatory love, or decline ❤️💔

---

## **5. Academic Context**

- **Sem 2 (ODE):** Analytical study of linear and nonlinear systems, equilibrium analysis
- **Sem 3 (Numerical Methods):** Simulation, phase trajectories, and visualization of dynamic systems

---

## **Fun Note** 🎉

- Lotka–Volterra shows **survival dynamics in nature**, while the love model shows **emotional dynamics in human relationships**.
- Both teach us how **interactions, feedback, and timing** create cycles, stability, or chaos in real systems.
