# Module 5: State Space Analysis

- **State space from differential equation** ⭐⭐⭐⭐⭐
- **State space from transfer function** ⭐⭐⭐⭐
- **State transition matrix** ⭐⭐⭐⭐
- **Controllability & Observability** ⭐⭐⭐⭐
- **Transfer function from state equations** ⭐⭐⭐


Imp:
- https://youtu.be/NbxYeWael1c?si=Ay8Bqrk8tTTt_3zk: for the second state variable question


## Important Recurring Questions
Questions of the form **"Obtain the state-space representation / state model"** appear repeatedly in Module 5.

### Examples from Previous Year Questions (PYQs)
* **2023 Q19(a):** Obtain the state model of the given electrical network.
* **2023 Q20(a):** Obtain the state variable matrix in phase variable form for a differential equation.
* **2022 Q19(a):** Obtain the state model for the electrical network shown.
* **2021 Q19(a):** Given a transfer function, draw its signal flow graph in phase variable form and represent it in state variable form.

---

## Example Problem: Converting Differential Equation to State-Space Representation (Phase Variable Form)
*This is a classic 7-mark problem frequently asked in KTU exams.*

### Problem Statement
Obtain the state-space representation (state model) for the system described by the differential equation:
$$
\frac{d^3y}{dt^3}+6\frac{d^2y}{dt^2}+11\frac{dy}{dt}+10y=8u(t)
$$

### Solution & Derivation

#### Step 1: Define the Phase Variables
Let the output $y(t)$ and its derivatives be defined as state variables (phase variables):
$$
x_1 = y
$$
$$
x_2 = \dot{y} = \frac{dy}{dt}
$$
$$
x_3 = \ddot{y} = \frac{d^2y}{dt^2}
$$

#### Step 2: Differentiate the State Variables
Taking the first derivatives of our state variables:
$$
\dot{x}_1 = \dot{y} = x_2
$$
$$
\dot{x}_2 = \ddot{y} = x_3
$$
$$
\dot{x}_3 = \dddot{y}
$$

#### Step 3: Express $\dot{x}_3$ in terms of State Variables and Input
From the given differential equation:
$$
\dddot{y} + 6\ddot{y} + 11\dot{y} + 10y = 8u(t)
$$

Rearranging the equation to solve for the highest derivative $\dddot{y}$ (which is $\dot{x}_3$):
$$
\dddot{y} = -10y - 11\dot{y} - 6\ddot{y} + 8u(t)
$$

Substitute the defined state variables into the equation:
$$
\dot{x}_3 = -10x_1 - 11x_2 - 6x_3 + 8u(t)
$$

#### Step 4: Write the State Equation in Matrix Form
The system of state equations is:
$$
\begin{aligned}
\dot{x}_1 &= 0\cdot x_1 + 1\cdot x_2 + 0\cdot x_3 + 0\cdot u \\
\dot{x}_2 &= 0\cdot x_1 + 0\cdot x_2 + 1\cdot x_3 + 0\cdot u \\
\dot{x}_3 &= -10x_1 - 11x_2 - 6x_3 + 8u
\end{aligned}
$$

In vector-matrix form ($\dot{X} = AX + Bu$):
$$
\begin{bmatrix}
\dot{x}_1 \\
\dot{x}_2 \\
\dot{x}_3
\end{bmatrix} = 
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
-10 & -11 & -6
\end{bmatrix}
\begin{bmatrix}
x_1 \\
x_2 \\
x_3
\end{bmatrix} + 
\begin{bmatrix}
0 \\
0 \\
8
\end{bmatrix}
u(t)
$$

#### Step 5: Write the Output Equation
The output is $y = x_1$. In matrix form ($Y = CX + Du$):
$$
Y = \begin{bmatrix} 1 & 0 & 0 \end{bmatrix}
\begin{bmatrix}
x_1 \\
x_2 \\
x_3
\end{bmatrix} + [0]u
$$

Thus, the state model parameters are:
- **State Matrix ($A$):**
  $$
  A = \begin{bmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ -10 & -11 & -6 \end{bmatrix}
  $$
- **Input Matrix ($B$):**
  $$
  B = \begin{bmatrix} 0 \\ 0 \\ 8 \end{bmatrix}
  $$
- **Output Matrix ($C$):**
  $$
  C = \begin{bmatrix} 1 & 0 & 0 \end{bmatrix}
  $$
- **Transmission Matrix ($D$):**
  $$
  D = 0
  $$

---
> [!TIP]
> **Exam Strategy:** Memorizing this conversion procedure is highly beneficial since converting differential equations into state equations is a staple question for KTU setters. Pay special attention to the signs in the bottom row of matrix $A$ (they are the coefficients of the differential equation in reverse order with negative signs).
