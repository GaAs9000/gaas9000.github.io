---
title: Math285 Final Review
summary: This is the review note for Math285 Final (Spring 2025) by Jiashen Ren.
date: 2025-05-01
author: Jiashen Ren
type: docs
math: true
tags:
  - Math285
---



## Q2:Frobenius method

### Sample Problem

Consider the differential equation

$$2x^2y'' + 3x(x+1)y' - 6y = 0. \qquad \text{(DE)}$$

a) Verify that $x_0 = 0$ is a regular singular point of (DE).

b) Determine the general solution of (DE) on $(0, \infty)$.

c) Using the result of b), state the general solution of (DE) on $(-\infty, 0)$ and on $\mathbb{R}$.

### Background Knowledge

1. **singular point and regular singular point** 

    * $$P(x)y'' + Q(x)y' + R(x)y = 0$$

      if $P(x_0) = 0$, $x_0$ is a singular point

    * $$y'' + p(x)y' + q(x)y = 0$$  
  
      $p(x) = \frac{Q(x)}{P(x)}$,  $q(x) = \frac{R(x)}{P(x)}$
      If $x_0$ is a singular point, and $(x-x_0)p(x)$ and $(x-x_0)^2q(x)$ are finite as $x \to x_0$, then $x_0$ is a regular singular point.

2. Frobenius method

    $$F(r) = r^2 + (P_0 - 1)r + q_0$$

    $P_0 = \lim_{x \to x_0} xp(x)$ and $q_0 = \lim_{x \to x_0} x^2q(x)$

    Solve for $r_1, r_2$

    $$y(x) = (x-x_0)^{r} \sum_{n=0}^{\infty} a_n (x-x_0)^n$$

    Substitute $y(x)$, $y'(x)$, $y''(x)$ into the ODE to solve for $a_n$

    You should obtain a relationship between $a_n$ and $a_{n+1}$ 
    Then solve the sequence

### Solution

a) 
The explicit form of (DE) is

$$y'' + \frac{3(x+1)}{2x}y' - \frac{3}{x^2}y = 0$$

$p(x) := \frac{3}{2} \frac{1}{x} + \frac{3}{2}$ has a pole of order 1 at 0, and $q(x) := -\frac{3}{x^2}$ has a pole of order 2 at 0.  This shows that 0 is a regular singular point of (DE).

b)
**1. Verification of Regular Singular Point and Calculation of Indicial Equation:**

*   **Explicit Form:** First, rewrite the original differential equation (DE) into the standard form:
    $$y'' + p(x)y' + q(x)y = 0$$

    to obtain $p(x)$ and $q(x)$.

*   **Order of Poles:** By observation, $p(x)$ has a pole of order 1 at $x=0$, and $q(x)$ has a pole of order 2 at $x=0$. This confirms that $x=0$ is a regular singular point.
*   **Indicial Equation:** Calculate $p_0$ and $q_0$:

    $$p_0 = \lim_{x \to 0} \left[ x \cdot p(x) \right] = \frac{3}{2}$$

    $$q_0 = \lim_{x \to 0} \left[ x^2 \cdot q(x) \right] = -3$$
    Then, construct the indicial equation:

    $$r^2 + (p_0 - 1)r + q_0 = 0$$

    $$r^2 + (1/2)r - 3 = 0$$

    Solve this quadratic equation to get the roots: $r_1 = 3/2$ and $r_2 = -2$.

**2. Constructing Series Solutions:**

*   **Two Linearly Independent Solutions:** Since the difference between the roots $r_1 - r_ 2 = 3/2 - (-2) = 7/2$ is not an integer, the Frobenius method guarantees two linearly independent series solutions, in the form:

    $$y_1(x) = x^{3/2} \sum_{n=0}^{\infty} a_n x^n = \sum_{n=0}^{\infty} a_n x^{n+3/2}$$ 

    $$y_2(x) = x^{-2} \sum_{n=0}^{\infty} b_n x^n = \sum_{n=0}^{\infty} b_n x^{n-2}$$

    where \(a_0 = b_0 = 1\) (normalization condition).

**3. Solving for the First Solution y1(x):**

*   **Substitute into Original Equation:** Substitute the series forms of \(y_1(x)\), \(y_1'(x)\), and \(y_1''(x)\) into the original differential equation.
*   **Combine Series:** Combine coefficients of like powers of \(x\).
*   **Recurrence Relation:** By setting the coefficients of each power of \(x\) to zero, obtain the recurrence relation for the coefficients \(a_n\):
    $$
    a_n = -\frac{3(2n + 1)}{2n(2n + 7)} a_{n-1}
    $$
*   **Calculate Coefficients:** Starting from \(a_0 = 1\), use the recurrence relation to calculate \(a_1, a_2, a_3, \ldots\).
*   **Write \(y_1(x)\):** Substitute the calculated coefficients into the series expression for \(y_1(x)\).

**4. Solving for the Second Solution \(y_2(x)\):**

*   **Repeat Steps:** Repeat the above process for \(y_2(x)\) (substitution, combination, recurrence).
*   **Recurrence Relation:** Obtain the recurrence relation for \(b_n\):
    $$
    b_n = \frac{3(n - 3)}{n(2n - 7)} b_{n-1}
    $$
*   **Calculate Coefficients:** Starting from \(b_0 = 1\), use the recurrence relation to calculate \(b_1, b_2, b_3, \ldots\). Note that \(b_3, b_4, \ldots\) are zero.
*   **Write \(y_2(x)\):** Substitute the calculated coefficients into the series expression for \(y_2(x)\).

**5. General Solution:**

Finally, the general solution of the differential equation is the linear combination of \(y_1(x)\) and \(y_2(x)\):

$$
y(x) = C_1 y_1(x) + C_2 y_2(x)
$$

where \(C_1\) and \(C_2\) are arbitrary constants.

---
**Alternative solution:**

---
