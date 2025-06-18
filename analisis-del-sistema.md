## 4. Análisis del Sistema

Consideramos el sistema de Lorenz:

$$
\begin{cases}
\dot{x} = \sigma(y - x) \\
\dot{y} = x(\rho - z) - y \\
\dot{z} = xy - \beta z
\end{cases}
$$

---

#### 1) Puntos fijos o de equilibrio del sistema

Los puntos fijos se obtienen despejando:

$$
\dot{x} = \dot{y} = \dot{z} = 0
$$

Del siguiente sistema:

$$
\begin{cases}
\sigma(y - x) = 0 \Rightarrow y = x \\
x(\rho - z) - y = 0 \Rightarrow x(\rho - z - 1) = 0 \\
xy - \beta z = 0 \Rightarrow z = \frac{x^2}{\beta}
\end{cases}
$$

- Si $x = 0$: entonces $y = 0, z = 0$ → $P_0 = (0, 0, 0)$  
- Si $x \neq 0$: entonces $z = \rho - 1$, y sustituyendo:

$$
x = \pm \sqrt{\beta(\rho - 1)}
$$

Por lo tanto, quedarían de la siguiente manera:

$$
P_0 = (0, 0, 0), \quad P_{\pm} = \left( \pm \sqrt{\beta(\rho - 1)}, \pm \sqrt{\beta(\rho - 1)}, \rho - 1 \right)
$$

---

#### 2) Divergencia del sistema

El campo vectorial es:

$$
\vec{F} = (\sigma(y - x), x(\rho - z) - y, xy - \beta z)
$$

La divergencia es:

$$
\nabla \cdot \vec{F} = \frac{\partial F_x}{\partial x} + \frac{\partial F_y}{\partial y} + \frac{\partial F_z}{\partial z} = -\sigma - 1 - \beta
$$

Podemos interpretar que cuando la divergencia es negativa significa que el sistema es disipativo, es decir, con el tiempo el volumen en el espacio de fase se contrae.

---

#### 3) Integral de flujo

Por teorema de divergencia:

$$
\frac{dV(t)}{dt} = \iint_{S(t)} \vec{F} \cdot d\vec{S} = \iiint_{V(t)} \nabla \cdot \vec{F} \, dV = (\nabla \cdot \vec{F}) V(t)
$$

Al sustituir queda:

$$
\frac{dV}{dt} = -(\sigma + 1 + \beta) V
$$

---

#### 4) Solución de la ecuación para $V(t)$

La siguiente ecuación diferencial:

$$
\frac{dV}{dt} = \lambda V, \quad \text{con } \lambda = -(\sigma + 1 + \beta)
$$

Se resuelve por el método de variables sepradas y queda:

$$
\int \frac{dV}{V} = \int \lambda \, dt \Rightarrow \ln |V| = \lambda t + C \Rightarrow V(t) = V_0 e^{\lambda t}
$$

Como $\lambda < 0$, entonces el volumen del espacio de fase con el tiempo decrece exponencialmente.

---

#### 5) ¿El sistema es conservativo?

Para empezar, definimos que un sistema es conservativo si:

$$
\nabla \cdot \vec{F} = 0
$$

Y en este caso tenemos que:

$$
\nabla \cdot \vec{F} = -(\sigma + 1 + \beta) \neq 0
$$

Por lo tanto el sistema no es conservativo, es disipativo.

---

#### 6) Análisis de fase

El sistema de Lorenz presenta un comportamiento caótico para ciertos parámetros, como por ejemplo:

$$
\rho = 28,\quad \sigma = 10,\quad \beta = \frac{8}{3}
$$

Este comportamiento se manifiesta en un atractor singular llamado **atractor de Lorenz**, que es un conjunto fractal hacia donde convergen las trayectorias.

Podemos ayudarnos visualmente con las siguientes gráficas: 

- 2D: $x(t)$ vs $y(t)$, $y(t)$ vs $z(t)$  
- 3D: $(x(t), y(t), z(t))$

---

#### 7) Estabilidad local cerca del origen

La matriz Jacobiana en $(0, 0, 0)$ es:

$$
J =
\begin{bmatrix}
-\sigma & \sigma & 0 \\
\rho & -1 & 0 \\
0 & 0 & -\beta
\end{bmatrix}
$$

Los autovalores son:

- $\lambda_1 = -\beta$  
- $\lambda_{2,3}$: raíces del polinomio:

$$
\lambda^2 + (\sigma + 1)\lambda + \sigma(\rho - 1) = 0
$$

Para $\rho > 1$, al menos uno de los autovalores tiene parte real positiva.
Podemos decir entonces que el origen del sistema es un punto de silla inestable.

---
