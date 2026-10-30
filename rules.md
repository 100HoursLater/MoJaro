# rules of MoJaro

## Operators
-----
### Assignment
Assignment goes right to left in all cases 
`int x = 10;` integer x has 10 
` int o = fn fuction() {// do something}>.return;` integer o now has the return value of function **fuction**

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
Addition operator has one main purpose and one side purpose: 
**Main:** *Adding two values together*
**Side:** *chaining in property structs*

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

