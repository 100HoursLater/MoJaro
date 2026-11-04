# MoJaro Math Library

-----

## Rules

-----

### Special Floats
- `math->float4` : 4 bit float
- `math->float256` : 256 bit float
  
-----

### Special Integers
- `math->integer4` : 4 bit integer (explicit bit-width goes from 128 to 8 bit, no more)
- `math->integer256` : 256 bit integer

-----

### Functions
- `math->log(x);` : this returns the natural logarithm of x (lets say x is an integer)
- `math->log10(x);` : this returns the base 10 logarithm of x (lets say x is an integer)
- `math->pow(x,y);` : this Returns the value of x to the power of y
- `math->scalbln(x, y)` : Returns x*Ry (R is usually 2)
- `math->sin(x);` : Returns the sine of x (x is in radians)
- `math->sqrt(x);` : 	Returns the square root of x
- `math->cos(x);` : Returns the cosine of x (x is in radians)
- `math->ceil(x);`
- `math->floor(x);`
- `math->abs(x);` : absolute value
- `math->clamp(x,min,max);`

------

### Pre-Defined variables: 
- `math->EPSILON` : this is a float64 
- `math->PI` : this is a float64 equal to 3.14159 etc
- `math->E` : this is Euler number essential for natural logs
- `math->TAU` : this is 2 * PI
- `math->NaN` : this is Not a Number
- `math->INF` : this is INFINITY
------
