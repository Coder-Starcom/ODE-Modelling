# 💖 Modeling Dynamics of Love

The core idea is to represent the intensity of feeling each person has for the other as a variable that changes over time. We use a system of **coupled differential equations** to describe this change.

## 💑 The Variables

- $R(t)$: Romeo's love (or hate) for Juliet at time $t$.
  - $R > 0$: Love 🥰
  - $R < 0$: Hate 😠
- $J(t)$: Juliet's love (or hate) for Romeo at time $t$.
  - $J > 0$: Love 😍
  - $J < 0$: Hate 😡

## 📝 The Equations

The rate of change of each person's feeling is influenced by their own current feeling and the feeling of their partner. A general linear model looks like this:

$$
\frac{dR}{dt} = aR + bJ
$$

$$
\frac{dJ}{dt} = cR + dJ
$$

Where $a, b, c, d$ are **coupling coefficients** that represent their personality types and how they react to love:

| Coefficient | Meaning                                                   |
| :---------- | :-------------------------------------------------------- |
| $a$         | Romeo's reaction to his _own_ feelings (self-reliance).   |
| $b$         | Romeo's reaction to _Juliet's_ feelings (responsiveness). |
| $c$         | Juliet's reaction to _Romeo's_ feelings (responsiveness). |
| $d$         | Juliet's reaction to her _own_ feelings (self-reliance).  |

By changing these coefficients, we can model different relationship types, like "Cautious Lovers," "Eager Beavers," or "Hermits" 🐢.

---

# 🚀 The Solution Method: RK4

Since these differential equations are often complex and don't have simple analytical solutions, we use numerical methods like the **Fourth-Order Runge-Kutta (RK4) method** to approximate the solution over time.

RK4 is a powerful tool for stepping forward in time to find the next value of $R$ and $J$ based on their current values and the rates of change ($\frac{dR}{dt}$ and $\frac{dJ}{dt}$).

## 🔢 The RK4 Formula

If we have a general differential equation $\frac{dy}{dt} = f(t, y)$, the RK4 method calculates the next value $y_{i+1}$ from the current value $y_i$ using a weighted average of four estimates of the slope ($k_1, k_2, k_3, k_4$):

$$
y_{i+1} = y_i + \frac{1}{6}(k_1 + 2k_2 + 2k_3 + k_4)
$$

Where $h$ is the time step:

1.  $k_1 = h \cdot f(t_i, y_i)$ (Slope at the start)
2.  $k_2 = h \cdot f(t_i + \frac{h}{2}, y_i + \frac{k_1}{2})$ (Slope at the midpoint, using $k_1$)
3.  $k_3 = h \cdot f(t_i + \frac{h}{2}, y_i + \frac{k_2}{2})$ (Slope at the midpoint, using $k_2$)
4.  $k_4 = h \cdot f(t_i + h, y_i + k_3)$ (Slope at the end, using $k_3$)

## 🔄 Applying RK4 to Love Dynamics

Since we have _two_ coupled equations ($\frac{dR}{dt}$ and $\frac{dJ}{dt}$), we must calculate four $k$ values for $R$ and four $k$ values for $J$ in parallel for each time step.

For a time step $h$, the new values $R_{i+1}$ and $J_{i+1}$ are calculated as:

$$
R_{i+1} = R_i + \frac{1}{6}(k_{R1} + 2k_{R2} + 2k_{R3} + k_{R4})
$$

$$
J_{i+1} = J_i + \frac{1}{6}(k_{J1} + 2k_{J2} + 2k_{J3} + k_{J4})
$$

This process is repeated iteratively to trace the trajectory of their feelings over time, showing whether they end up in a stable, loving relationship, a cycle of ups and downs, or mutual destruction 💔.
