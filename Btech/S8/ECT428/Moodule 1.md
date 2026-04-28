---
tags:
  - main
  - module_1
  - ect428
---

# Module 1
  - [ ] Engineering applications of optimization
  - [ ] Formulating design problems as mathematical programming
  - [ ] Classifying problems (linear, convex, non-convex)
  - [ ] Classical optimization for unconstrained (single & multivariable)
  - [ ] Constrained problems & KKT conditions

**1. Formulating an Optimization Problem** The goal of optimization is to **find the conditions that give the maximum or minimum value of a function**. **To formulate a problem**, you must follow these steps:
- **Define the Design Variables ($X$):** These are the quantities that you can change or control in the design process.
- **Define the Objective Function ($f(x)$):** This is the scalar criterion you want to optimize—such as maximizing mechanical efficiency or profit, or minimizing distance, cost, or weight.
- **Define the Constraints:** These are the restrictions that must be satisfied for the design to be acceptable. Constraints can be _behavioral_ (functional limitations on the system's performance) or _geometric/side constraints_ (physical limitations on the variables themselves, like material availability or transportability).

---

2. **Single-Variable Optimization** For unconstrained problems with a single variable, you will use classical calculus to find local maxima and minima:
- **Necessary Condition:** Find the stationary points by taking the first derivative of the objective function and setting it to zero ($f'(x) = 0$).
- **Sufficient Condition:** Evaluate the second derivative ($f''(x)$) at that stationary point.
	- If $f''(x) > 0$ (positive), the point is a **local minimum**.
	- If $f''(x) < 0$ (negative), the point is a **local maximum**.
	- If $f''(x) = 0$, it could be a point of inflection (neither maximum nor minimum), meaning you must check the next non-zero higher-order derivative.

## KKT (Karush-Kuhn-Tucker) Conditions
For constrained optimization problems, the KKT conditions provide a way to find optimal solutions. They are a generalization of the method of Lagrange multipliers and include both necessary and sufficient conditions for optimality. The KKT conditions are as follows:
- **Stationarity:** The gradient of the Lagrangian must be zero at the optimal point.
- **Primal Feasibility:** The constraints must be satisfied at the optimal point.
- **Dual Feasibility:** The Lagrange multipliers associated with the inequality constraints must be non-negative.
- **Complementary Slackness:** For each inequality constraint, either the constraint is active (equal to zero) or the corresponding Lagrange multiplier is zero.

