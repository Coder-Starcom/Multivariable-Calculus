# 📘 Theoretical Overview of Notebooks

This collection of notebooks explores **multivariable calculus and vector analysis**. Each notebook builds intuition through theory, visualization, and computation. Below is the **expanded theoretical background** with examples, interpretations, and applications.

---

## 01-gradient.ipynb

### 🌄 The Gradient

- **Definition**: For a scalar function $f(x,y)$, the gradient is:

$$\nabla f(x,y) = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \right)$$

- **Meaning**:

  - Points in the direction of **steepest ascent**.
  - Magnitude tells how fast the function increases in that direction.
  - In physics, gradient of potential = **force field**.

- **Example**:

$$f(x,y) = x^2 + y^2 \quad \Rightarrow \quad \nabla f(x,y) = (2x, 2y)$$

At $(1,2)$:

$$\nabla f(1,2) = (2,4)$$

→ Steepest ascent is toward $(2,4)$.

- **Physical Analogy**: Imagine a hill 🌄. The gradient points in the direction you'd climb fastest.

### ➡️ Directional Gradient

- **Definition**: For a unit vector $\mathbf{u}$:

$$D_{\mathbf{u}} f(x,y) = \nabla f(x,y) \cdot \mathbf{u}$$

- **Example**:  
  Gradient at $(1,2)$ is $(2,4)$.  
  If $\mathbf{u} = \left( \tfrac{1}{\sqrt{2}}, \tfrac{1}{\sqrt{2}} \right)$:

$$D_{\mathbf{u}} f(1,2) = (2,4) \cdot \left( \tfrac{1}{\sqrt{2}}, \tfrac{1}{\sqrt{2}} \right) = 3\sqrt{2}$$

→ Function increases at rate $3\sqrt{2}$ along diagonal.

---

## 02-partial_derivatives_and_chain_rule.ipynb

### 🔍 Partial Derivatives

- **Definition**: Rate of change of a function with respect to one variable, keeping others constant.
- **Example**:

$$f(x,y) = x^2y + \sin(y)$$

$$\frac{\partial f}{\partial x} = 2xy, \quad \frac{\partial f}{\partial y} = x^2 + \cos(y)$$

- **Interpretation**:
  - $\frac{\partial f}{\partial x}$: slope along $x$-axis.
  - $\frac{\partial f}{\partial y}$: slope along $y$-axis.

### 🔗 Chain Rule

- **General Formula**:

$$\frac{d}{dt} f(v(t)) = \nabla f(v(t)) \cdot \frac{dv}{dt}$$

- **Example**:  
  If $v(t) = (t, t^2)$, $f(x,y) = x^2 + y$:

$$f(v(t)) = f(t, t^2) = t^2 + t^2 = 2t^2$$

$$\frac{d}{dt} f(v(t)) = 4t$$

- **Physical Analogy**: A particle moving along a path 🚀 experiences change in temperature $f(x,y)$. The chain rule tells how fast the temperature changes along its trajectory.

---

## 03-curvature_divergence_and_curl.ipynb

### 🔵 Curvature

- **Definition**: Measures how sharply a curve bends.
- Formula:

$$k(t) = \frac{|x'(t)y''(t) - y'(t)x''(t)|}{\left( (x'(t))^2 + (y'(t))^2 \right)^{3/2}}$$

- **Example**: Circle $\mathbf{r}(t) = (\cos t, \sin t)$:

$$k(t) = 1$$

→ Constant curvature.

- **Analogy**: A straight road 🚗 has zero curvature, a sharp turn has high curvature.

### 🌬️ Divergence

- **Definition**: Measures **net outflow** of a vector field.
- Formula:

$$\nabla \cdot \mathbf{F} = \frac{\partial F_x}{\partial x} + \frac{\partial F_y}{\partial y}$$

- **Example**:  
  $\mathbf{F}(x,y) = (x,y)$:

$$\nabla \cdot \mathbf{F} = 1 + 1 = 2$$

→ Field expands outward everywhere.

- **Physical Analogy**: Divergence in fluid dynamics = how much fluid is **created or destroyed** at a point 💧.

### 🌀 Curl

- **Definition**: Measures **rotation** of a vector field.
- Formula (2D):

$$\nabla \times \mathbf{F} = \frac{\partial F_y}{\partial x} - \frac{\partial F_x}{\partial y}$$

- **Example**:  
  $\mathbf{F}(x,y) = (-y, x)$:

$$\nabla \times \mathbf{F} = 1 - (-1) = 2$$

→ Counterclockwise rotation.

- **Physical Analogy**: Curl in fluids = **vorticity** (local spinning of water, like a whirlpool 🌊).

---

## 04-laplacian.ipynb

### 🔥 The Laplacian

- **Definition**: Divergence of the gradient.

$$\nabla^2 f = \frac{\partial^2 f}{\partial x^2} + \frac{\partial^2 f}{\partial y^2}$$

- **Example**:  
  $f(x,y) = x^2 + y^2$:

$$\nabla^2 f = 2 + 2 = 4$$

→ Constant Laplacian.

- **Physical Interpretations**:
  - Heat conduction 🔥: Laplacian describes how temperature diffuses.
  - Electrostatics ⚡: Appears in Poisson's equation for electric potential.
  - Geometry 📐: Harmonic functions satisfy $\nabla^2 f = 0$.

---

## 05-jacobian.ipynb

### 🧩 The Jacobian

- **Definition**: Matrix of all first-order partial derivatives of a transformation.
- For $u = x^2 - y$, $v = xy$:

$$J = \begin{bmatrix} \frac{\partial u}{\partial x} & \frac{\partial u}{\partial y} \\ \frac{\partial v}{\partial x} & \frac{\partial v}{\partial y} \end{bmatrix} = \begin{bmatrix} 2x & -1 \\ y & x \end{bmatrix}$$

- Determinant:

$$\det(J) = 2x^2 + y$$

- **Interpretation**:

  - Describes local **scaling, rotation, and shear**.
  - Determinant = **area scaling factor** in 2D (volume in 3D).
  - If $\det(J) = 0$, transformation collapses dimensions (not invertible).

- **Example (Geometry)**:  
  Transformation doubles $x$, triples $y$:

$$J = \begin{bmatrix} 2 & 0 \\ 0 & 3 \end{bmatrix}, \quad \det(J) = 6$$

→ Area scaled by factor of 6.

- **Example (Physics)**:  
  Jacobian is used in **change of variables** in integrals, e.g., switching from Cartesian to polar coordinates.
