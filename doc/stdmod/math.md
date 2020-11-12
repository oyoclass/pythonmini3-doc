## math — Mathematical functions
<!-- doc for this module is completed -->

This module contains some mathematical operations (subset of Python's standard *math* module), to use it, make sure use ```import math``` first to import it.

### Constants

* ```math.e``` : The mathematical constant e = 2.718281..., to available precision
* ```math.pi``` : The mathematical constant π = 3.141592..., to available precision.

### Functions

* ```math.acos(x)``` : Return the arc cosine of x, in radians.
* ```math.acosh(x)``` : Return the inverse hyperbolic cosine of x.
* ```math.asin(x)``` : Return the arc sine of x, in radians.
* ```math.asinh(x)``` : Return the inverse hyperbolic sine of x.
* ```math.atan(x)``` : Return the arc tangent of x, in radians.
* ```math.atan2(y, x)``` : Return atan(y / x), in radians. The result is between -pi and pi.
* ```math.atanh(x)``` : Return the inverse hyperbolic tangent of x.
* ```math.ceil(x)``` : Return the ceiling of x as a float, the smallest integer value greater than or equal to x.
* ```math.copysign(x, y)```: Return x with the sign of y. On a platform that supports signed zeros, copysign(1.0, -0.0) returns -1.0.
* ```math.cos(x)``` : Return the cosine of x radians.
* ```math.cosh(x)``` : Return the hyperbolic cosine of x.
* ```math.degrees(x)``` : Convert angle x from radians to degrees.
* ```math.exp(x)``` : Return e**x.
* ```math.fabs(x)``` : Return the absolute value of x.
* ```math.factorial(x)``` : Return x factorial.
* ```math.floor(x)``` : Return the floor of x as a float, the largest integer value less than or equal to x.
* ```math.hypot(x, y)``` : Return the Euclidean norm, sqrt(x*x + y*y). This is the length of the vector from the origin to point (x, y).
* ```math.log(x[,base])``` : With one argument, return the natural logarithm of x (to base e). With two arguments, return the logarithm of x to the given base, calculated as log(x)/log(base).
* ```math.log10(x)``` : Return the base-10 logarithm of x. This is usually more accurate than log(x, 10).
* ```math.pow(x, y)``` : Return x raised to the power y.
* ```math.radians``` : Convert angle x from degrees to radians.
* ```math.sin(x)``` : Return the sine of x radians.
* ```math.sinh(x)``` : Return the hyperbolic sine of x.
* ```math.sqrt(x)``` : Return the square root of x.
* ```math.tan(x)``` : Return the tangent of x radians.
* ```math.tanh(x)``` : Return the hyperbolic tangent of x.
* ```math.trunc(x)``` : Return the Real value x truncated to an Integral (usually a long integer).


### Example

```python
import math

print math.pi
# 3.14159265359

print math.sqrt(4)
# 2.0

print math.sin(math.pi/6)
# 0.5

print math.degrees(math.pi/6)
# 30.0
```

### Reference

* [Python Math Module, python.org](https://docs.python.org/2/library/math.html)
