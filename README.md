# ode2singular
This is a symbolic solver for linear homogeneous ordinary differential equations of order 2 written for the free computer algebra system Maxima.
In order to use it put the file *ode2singular.mac* in one of the paths that is in your *file_search_maxima* variable and enter *load('ode2singular);* in Maxima.
The file *ode2singular.wxmx* to be used with wxMaxima contains some examples of equations that can be solved by the program.
The file *singular_points.pdf* contains some explanations on the algorithm and on the explicit formulas used in the program.

The program tries to determine the singular points of the equation and use this information to solve it.
If it doesn't succeed the user can propose a change of variable and the program tries to solve the equation with the new variable.

**Examples of usage:**

1. In order to solve the equation
  
  *y''(x) + y'(x)/x + y(x)/x^2 = 0*
  
  enter in Maxima:
  
  *p1: 1/x;*
  
  *p0: 1/x^2;*
  
  *ode2singular(p1, p0, y, x);*

2. In order to solve Mathieu's equation with a change of variable replacing *x* by *cos(x)* enter:
  
  *p1: 0;*
  
  *p0: a-2\*q\*cos(2\*x);*
  
  *phi: cos(x);*
  
  *phi_inv: acos(x);*
  
  *ode2singular_transform(p1, p0, y, x, phi, phi_inv);*
