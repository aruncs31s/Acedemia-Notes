---
tags:
  - ect428
  - pyq
---
# ALL PYQ

### Q1
- Explain the necessary and sufficient conditions for identifying **local maxima** and **minima** of a function with a single input variable and no constraints

To identify the local maxima and minima of a function $f(x)$ with a single input variable and no constraints, you evaluate the **necessary and sufficient conditions** using calculus.

Here is the step-by-step mathematical explanation:

**1. The Necessary Condition** The necessary condition states that if a function has a relative maximum or minimum at a point $x^*$, its first derivative evaluated at that point must be zero.

- **Step:** Find the first derivative of the objective function $\frac{df(x)}{dx}$ (or $f'(x)$).
- **Step:** Set the first derivative to zero ($f'(x) = 0$) and solve for $x$ to find your stationary point(s), denoted as $x^*$.

**2. The Sufficient Condition** Once you have found a stationary point $x^*$, the sufficient condition tells you whether that point is a maximum, a minimum, or neither, based on its higher-order derivatives.

- **Step:** Find the second derivative of the function, $f''(x)$.
- **Step:** Substitute your stationary point $x^*$ into the second derivative:
    - **Local Minimum:** If $f''(x^*) > 0$ (positive), the point is a relative minimum.
    - **Local Maximum:** If $f''(x^*) < 0$ (negative), the point is a relative maximum.

**What if the second derivative is zero?** If $f''(x^*) = 0$, the standard second-derivative test is inconclusive, and you must check the next higher-order derivatives ($f'''(x)$, $f''''(x)$, etc.) until you find the first derivative $f^{(n)}(x^*)$ that does **not** equal zero.

- If $n$ is an **even** number and $f^{(n)}(x^*) > 0$, the point is a minimum.
- If $n$ is an **even** number and $f^{(n)}(x^*) < 0$, the point is a maximum.
- If $n$ is an **odd** number, the point is a **point of inflection** (meaning it is neither a maximum nor a minimum).