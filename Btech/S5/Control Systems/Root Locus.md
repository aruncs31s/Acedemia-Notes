---
tags:
  - ect307
---
## Root Locus
Q: A unity feedback control system has open-loop transfer function $G(s) = \frac{K}{s(s^2+4s+13)}$. Sketch the root locus

Solutions :

### **Step 1: To locate poles & zeros**

The poles of open-loop transfer function are the roots of the equation

$$s(s^2 + 4s + 13) = 0$$

$$s = \frac{-4 \pm \sqrt{4^2 - 4 * 13}}{2} = -2 \pm j3$$

_The poles are lying at_ $s=0$, $-2+j3$, $-2-j3$


## **Step 2: To find the root locus on real axis**

_There is only one pole on real axis at the origin. Hence if we choose any point on the negative real axis the to the right of that point the total number of real poles and zeros is one , which is an odd number. Hence entire negative real axis will be part of root locus_


_If right side of test points have odd numbers of zeros & poles – root locus exists_

_If right side of test points have even numbers of zeros & poles – root locus does not exist_



## **Step 3: To find angles of asymptotes and centroid**

Since there are 3 poles, the number of root locus branches are three

$$Angle\ of\ asymptotes = \frac{\pm 180^\circ(2q + 1)}{n - m}$$

_Where,_

$n = \text{number of poles}$

$m = \text{number of zeros}$

$q = 0, 1, 2, \dots n-m$

_Here_ $n = 3$, $m = 0$

_when_ $q = 0$,  $Angles = \frac{\pm 180^\circ(1)}{3} = \pm 60^\circ$

_when_ $q = 1$, $Angles = \frac{\pm 180^\circ(3)}{3} = \pm 180^\circ$

_when_ $q = 2$,  $Angles = \frac{\pm 180^\circ(5)}{3} = \pm 300^\circ$

_when_ $q = 3$, $Angles = \frac{\pm 180^\circ(7)}{3} = \pm 420^\circ$

$$Centroid = \frac{\text{sum of poles } - \text{ sum of zeros}}{n - m}$$

$$= \frac{0 - 2 + j3 - 2 - j3 - 0}{3 - 0} = -\frac{4}{3} = -1.33$$


## **Step 4: To find the break away and break in points**

- **Closed loop TF** $= \frac{C(s)}{R(s)} = \frac{G(s)}{1 + G(s)H(s)}$
    
    $= \frac{\frac{K}{s(s^2 + 4s + 13)}}{1 + \frac{K}{s(s^2 + 4s + 13)} * 1} = \frac{K}{s(s^2 + 4s + 13) + K}$
    
- **Characteristic equation is** $\rightarrow s(s^2 + 4s + 13) + K = 0$
    
    $K = -s^3 - 4s^2 - 13s$
    
- **Differentiating the equation w.r.t. s and equate to zero we get,**
    
    $\frac{dK}{ds} = -(3s^2 + 8s + 13) = 0$
    
    $3s^2 + 8s + 13 = 0$
    
    $s = \frac{-8 \pm \sqrt{8^2 - 4 * 3 * 13}}{2 * 3} = -1.33 \pm j1.6$
    
- **Lets check for the value of K**
    
    - when $s = -1.33 + j1.6, K = -(-1.33 + j1.6)^3 - 4(-1.33 + j1.6)^2 - 13(-1.33 + j1.6) \neq$ positive & real
        
    - when $s = -1.33 - j1.6, K = -(-1.33 - j1.6)^3 - 4(-1.33 - j1.6)^2 - 13(-1.33 - j1.6) \neq$ positive & real
        
- **Conclusion:** Since the value of K for s values, are not real & positive. The root locus has neither break away or break in point.


**Step 5: To find the angle of departure**

Let us consider the complex pole $P_2$

- $\theta_1 = 123^\circ$ (or _another method_ $\theta_1 = 180^\circ - \tan^{-1}\frac{3}{2} = 123.7^\circ$)
    
- $\theta_2 = 90^\circ$
    
- **Angle of departure from complex pole $P_2$** $= 180^\circ - (\theta_1 + \theta_2)$
    
    $= 180^\circ - (123^\circ + 90^\circ)$
    
    $= -33^\circ$
    
- **Angle of departure from complex pole $P_3$** $= +33^\circ$



## **Step 6: To find the crossing point on imaginary axis**

- **Characteristic equation is** $\rightarrow s^3 + 4s^2 + 13s + K = 0$
    
- **Substitute** $s = j\omega$
    
    $-j\omega^3 - 4\omega^2 + 13j\omega + K = 0$
    

|**On equating imaginary part to zero we get**|**On equating real part to zero we get**|
|---|---|
|$-\omega^3 + 13\omega = 0$|$-4\omega^2 + K = 0$|
|$\omega = \pm \sqrt{13} = \pm 3.6$|$K = 4\omega^2$|
||$K = 4 * 13 = 52$|

- **Conclusion:** The crossing point of root locus is $\pm j3.6$. The value of K at this crossing point is $K=52$ (limiting value of K for the stability of the system).