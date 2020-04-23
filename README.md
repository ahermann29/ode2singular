# ode2singular
This is a symbolic solver for linear homogeneous ordinary differential equations of order 2 written for the free computer algebra system Maxima.
In order to use it put the file *ode2singular.mac* in one of the paths that is in your *file_search_maxima* variable and enter *load('ode2singular);* in Maxima.
The file *ode2singular.wxmx* to be used with wxMaxima contains some examples of equations that can be solved by ode2singular.
The file *singular_points.pdf* contains some explanations on the algorithm.

The function ode2singular tries to determine the singular points of the equation and use this information to solve it.
If it doesn't succeed, the user can propose a change of variable and ode2singular tries to solve the equation with the new variable.

**Examples of usage:**

1. In order to solve the equation
  
  *x^2 \* y''(x) + x \* y'(x) + y(x) = 0*
  
  enter in Maxima:
  
  *eq: x^2 \* 'diff(y,x,2) + x \* 'diff(y,x) + y = 0;*
  
  *ode2singular(eq, y, x);*

2. In order to solve Mathieu's equation with a change of variable replacing *x* by *cos(x)* enter:
  
  *eq: 'diff(y,x,2) + (a-2\*q\*cos(2\*x)) \* y = 0;*
  
  *phi: cos(x);*
  
  *phi_inv: acos(x);*
  
  *ode2singular_transform(eq, y, x, phi, phi_inv);*
