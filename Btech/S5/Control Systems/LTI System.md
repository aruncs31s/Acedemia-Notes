---
tags:
  - btech
  - s5
  - control_system
---
>[!Note] Def
> **An LTI system is a system that satisfies the properties of linearity (superposition) and time invariance, meaning its response to a shifted input is an equally shifted version of the original response.**

A **Linear Time-Invariant (LTI) system** is a system that satisfies **two properties**:

1. **Linear**
2. **Time-invariant**

Let's understand them separately.

* * *

## 1. What does "Linear" mean?

A system is **linear** if it obeys the **principle of superposition**.

That means it satisfies:

### Addition

If

$$x_1(t)\rightarrow y_1(t)$$

and

$$x_2(t)\rightarrow y_2(t)$$

then

$$x_1(t)+x_2(t)\rightarrow y_1(t)+y_2(t)$$

### Scaling

If

$$x(t)\rightarrow y(t)$$

then

$$ax(t)\rightarrow ay(t)$$

for any constant $a$.

Together:

$$\boxed{ a x_1(t)+b x_2(t) \rightarrow a y_1(t)+b y_2(t) }$$

This is called **superposition**.

### Simple example

Suppose a system is

$$y(t)=2x(t)$$

If

$$x(t)=3$$

then

$$y(t)=6.$$

If we double the input:

$$2x(t)=6$$

then

$$y(t)=12=2(6).$$

So it is linear.

* * *

## 2. What does "Time-Invariant" mean?

This part is easier than the name makes it sound.

A system is **time-invariant** if its behavior does **not change with time**.

In other words, if you delay the input, the output is delayed by exactly the same amount.

Suppose

$$x(t)\rightarrow y(t)$$

Now delay the input by $t_0$:

$$x(t-t_0)$$

For a time-invariant system, the output must become

$$\boxed{y(t-t_0)}$$

So:

$$\boxed{ x(t)\rightarrow y(t) \quad\Rightarrow\quad x(t-t_0)\rightarrow y(t-t_0) }$$

### Example

Consider

$$y(t)=2x(t).$$

Original:

$$x(t)\rightarrow 2x(t)$$

Delayed input:

$$x(t-t_0)$$

Output:

$$2x(t-t_0)$$

which is exactly

$$y(t-t_0).$$

Therefore, it is **time-invariant**.
