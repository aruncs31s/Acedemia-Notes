---
tags:
  - ect307
---

Here is the extracted content from the image, that's it:

### Complex Gain Analysis

- $G(j\omega) = a + jb$
- $|G(j\omega)| = \sqrt{a^2 + b^2}$
- $\angle G(j\omega) = \tan^{-1} \frac{b}{a}$
- $\frac{1}{|G(j\omega)|} = \frac{1}{\sqrt{a^2 + b^2}}$
- $\angle \frac{1}{G(j\omega)} = -\tan^{-1} \frac{b}{a}$

### Vector Rotation of "j" Operator

|**Positive Powers**|**Negative Powers**|
|---|---|
|$j = 90^\circ$|$\frac{1}{j} = j^{-1} = -90^\circ$|
|$j^2 = 180^\circ$|$\frac{1}{j^2} = j^{-2} = -180^\circ$|
|$j^3 = 270^\circ$|$\frac{1}{j^3} = j^{-3} = -270^\circ$|
|$j^4 = 360^\circ$|$\frac{1}{j^4} = j^{-4} = -360^\circ$|


The term **$04\omega$** should actually be **$0.4\omega$**. Here is the step-by-step breakdown of how that term is derived from the transfer function $G(j\omega)$:

### 1. The Transfer Function

The given transfer function is:

$$G(j\omega) = \frac{10}{j\omega(1 + 0.4j\omega)(1 + 0.1j\omega)}$$

### 2. Understanding the Phase Angle Formula

The phase angle $\varphi$ of a transfer function is the sum of the angles of the numerator minus the sum of the angles of the denominator:

$$\angle G(j\omega) = \angle(\text{Numerator}) - \angle(\text{Denominator})$$

- **Numerator (10):** A constant has an angle of **$0^\circ$**.
    
- **Denominator Term 1 ($j\omega$):** This is a pure imaginary number ($j\omega$). Its angle is **$+90^\circ$**. Since it is in the denominator, it becomes **$-90^\circ$**.
    
- **Denominator Term 2 ($1 + 0.4j\omega$):** This is in the form $(a + jb)$, where $a=1$ and $b=0.4\omega$. Its angle is $\tan^{-1}(\frac{b}{a}) = \tan^{-1}(\frac{0.4\omega}{1}) = \tan^{-1}(0.4\omega)$. Since it is in the denominator, it becomes **$-\tan^{-1}(0.4\omega)$**.
    
- **Denominator Term 3 ($1 + 0.1j\omega$):** Similarly, this has an angle of $\tan^{-1}(0.1\omega)$. In the denominator, it becomes **$-\tan^{-1}(0.1\omega)$**.
    

### 3. Combining the Angles

Putting it all together:

$$\varphi = 0^\circ - 90^\circ - \tan^{-1}(0.4\omega) - \tan^{-1}(0.1\omega)$$

$$\varphi = -90^\circ - \tan^{-1}(0.4\omega) - \tan^{-1}(0.1\omega)$$

The **$0.4\omega$** comes directly from the $0.4j\omega$ term in the denominator. The image simply missed the decimal point between the '0' and the '4'.

