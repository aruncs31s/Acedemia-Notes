*How the state of a dynamic system evolves from one time instant to another.*

$$
\Phi(t) = e^{At}
$$


For a linear state-space system:

$$\dot{x}(t)=Ax(t)+Bu(t)$$

where:

* $x(t)$ = state vector
* $A$ = system matrix
* $B$ = input matrix
* $u(t)$ = input vector

the **State Transition Matrix** is denoted by $\Phi(t)$ and is defined as:

$$\Phi(t)=e^{At}$$

It relates the initial state $x(0)$ to the state at time $t$:

$$x(t)=\Phi(t)x(0)$$

for the zero-input case ($u(t)=0$).

### Physical Meaning

The STM tells us **how the system states move with time** due to the system dynamics alone. It is analogous to the solution $e^{at}$ of a first-order differential equation.

### Properties of State Transition Matrix

1. **Identity at $$t=0$$**

$$\Phi(0)=I$$

2. **Inverse Property**

$$\Phi^{-1}(t)=\Phi(-t)$$

3. **Composition Property**

$$\Phi(t_1+t_2)=\Phi(t_1)\Phi(t_2)$$

4. **Differential Equation**

$$\frac{d}{dt}\Phi(t)=A\Phi(t)$$

### How to Calculate STM

For a constant matrix $A$:

$$\Phi(t)=e^{At} =I+At+\frac{A^2t^2}{2!}+\frac{A^3t^3}{3!}+\cdots$$

### Example

Let

$$A= \begin{bmatrix} 0 & 1\\ -2 & -3 \end{bmatrix}$$

Then the STM is:

$$\Phi(t)=e^{At}$$

which can be found using the matrix exponential (or Laplace transform methods).

### Importance in Control Systems

The State Transition Matrix is used to:

* Solve state equations.
* Determine system response from initial conditions.
* Analyze stability.
* Design controllers and observers.
* Study controllability and observability.

In short, **the State Transition Matrix is the matrix equivalent of the exponential solution $e^{at}$ for scalar differential equations and describes the time evolution of the state vector in state-space analysis.**