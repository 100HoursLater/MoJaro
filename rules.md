# rules of MoJaro

## Operators
-----
### Assignment
Assignment goes right to left in all cases 
- `int x = 10;` integer x has 10 
- ` int o = fn fuction() {// do something}>.return;` integer o now has the return value of function **fuction**

------

### Comparison
Comparison goes right to left in all cases and has an implicit boolean
```
int x = 10; 
if (x == 10) {} // this return true and the block continues 

int y = 1;

if (y == 2) {} // this returns false and escapes the whole if block (if not if else or just else is present)
```

-----
### Addition
Addition operator (+) has one main purpose and one side purpose: 
- **Main:** *Adding two values together*
- **Side:** *chaining in property structs*

Main: 
```
int i = 10;
int p = 10;

i + p // = 20
```
Side:
```
// name property struct 
struct O* Property((Prop_Name)+(MyClass)=>{
  (void)->/*Some value and operation*/;
});
```



------

### Subtraction 
Subtraction operator (-) has one purpose and that is to take a one number away from another
```
int i = 10; 
int p = 5; 

i - p // = 5
```

-----

### multiply 
Multiplication operator (*) has one purpose and that is to multiply two values together
```
int i = 10;
int p = 3; 

i * p // (10+10+10) = 30 
```

-----

### division 
Division operator (/) has one purpose and that is to divide a value using another value 
```
int i = 3; 
int p = 2;

i / p // = 6 
```

-----
### More than 
More than operator (>) has one purpose that is to ask whether a value is more than another value
```
int i = 10; 
int p = 15; 

if (p > i) {} // true
```

------

### Less than 
Less than operator (<) has one purpose that is to ask whether a value is less than another value 
```
int i = 10; 
int p = 15; 
if (i < p) {} // true
```

-----

### More than equals
More than equals operator (>=) has one purpose that is to ask whether a value is more than or equal to another value
```
int i = 10; 
int p = 15; 

if (p >= i) {} // true
```

------

### Less than equals
Less than operator (<=) has one purpose that is to ask whether a value is less than or equal to another value 
```
int i = 10; 
int p = 15; 
if (i <= p) {} // true
```

-----

### Boolean AND 
Logical/Boolean AND (&&) has one purpose, that is to ask whether two values are false or true 

```
bool i = true;
bool p = true;

if (i && p) {} // true
```
-----

### Bitwise AND
Bitwise AND (&) has one purpose, and that is two ask if two values are 1 or 0 
```
int i = 0; 
int p = 0; 

if (i & p) {} // false/0
```
------

### Boolean OR 
Logical/Boolean OR (||) has one purpose, and that is to ask whether at least one of the two values is true 
```
bool i = true;
bool p = false;
if (i || p) {} // true
```
------

### Bitwise OR 
Bitwise OR (|) has one purpose, to ask whether at least one of two values is 1 
```
int i = 1; 
int p = 0;

if (i | p) {} // true 
```

-----

### Modulo 
Modulo Operator (%) has one purpose, has the same sign as the dividend
```
-10 % 3 = -1
```

-----

### Causal/Access Pointer
 Access Pointer (->) has one purpose and it's the same as dot-notation 

 ```
 fn MyFuction(int i = 0, int u = 0) {
  return self->i;
  return self->u;
 };

fn MyOtherFunction() {
 MyFunction->i; 
 MyFunction->u;
}
```
-----

### Negate 
Negate operator (!) has one purpose and that is to negate a Boolean value 

``` 
int p = 10; 
int i = 15;

if !(i > p) {} // normally this would be true, but here it's asking if it's NOT that so = false
```

-----

### increment 

Increment operator (++) adds 1 to a value 

```
for(int i = 0; i < 10; i++) {} // as this loop runs, i gets 1 added to it per iteration
```

outside of a for loop:

```
int x = 5; 

int a = x++; // x becomes 6 and a gets a 6
int b = ++x; // b gets 6 and x becomes 7
```

-----

### decrement 

Decrement operator (--) subtracts 1 from a value 

```
for(int i = 0; i < 10; i--) {} // as this loop runs, i gets 1 gets subtracted to it per iteration
```

outside of a for loop:

```
int x = 5; 

int a = x++; // x becomes 4 and a gets a 5
int b = ++x; // b gets 4 and x becomes 4
```

-----

### self 

Self keyword (self) has one purpose and that is self always points to the immediate construct you are currently inside.

``` 
fn myFuction(int x = 10) {
 self->x; // self is the function (myFuction)
  fn MyFunction(int u = 10) {
   self->u; // self is the function (MyFunction)
   return self->u; // MyFunction
  }
  return self->x; // myFuction
}
```
------
