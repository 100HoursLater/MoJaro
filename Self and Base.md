# MoJaro 
## self and Base

--------

### self
- self refers to the immediate construct your inside of

### base
- base refers to the base construct you are currently inside of.

-------

### Inheritance

#### base
```
class MyClass extends MyBaseClass {
 base->x; // points to MyBaseClass
 int y = 10;

 fn MyFunction() {
  base->y; // points to MyClass
 };
};
```

#### self
```
class MyClass extends MyBaseClass {
 int y = 10;
 fn MyFunction(int x = 10) {
   self->x; // refers to MyFunction
 };
self->y; // refers to MyClass
};
```
