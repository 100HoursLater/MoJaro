# MoJaro 
## Importance Of Ordering (IOO) 

-------------

### MoJaro is Sequential 

Code execution is **top-down sequential** (TDS), so your order matters. 

As a little example:

```
int A = 1; 
int B = 2; 
alloc(sizeof(A,B));
```
This is ordered correctly; it creates A and then B and then allocates them into memory, however if we shift the order a bit:

```
alloc(sizeof(A,B));
int A = 1;
int B = 2;
```
Nope not valid, MJC will hit the alloc call and throw a null reference error. 

the rule of IOO, is global, your order matters everywhere.

-------------
