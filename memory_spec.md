# MoJaro Memory Rules:

## Rules:
-----

### Rule 1 : Special Imports 
 - `import "memory" from 'std';` : this import allows you do memory more in-depth like memory fence `memory->memory_fence(/*memory address here*/);`

-----

### Rule 2 : Threads (IMPORTANT)
- the file itself represent the whole program in memory 
- Classes represent each thread (must be serialized in order to communicate with each other) 

-----

### Rule 3 : alloc and falloc (IMPORTANT) 
- `alloc` : allocation, each thread has its own arena, alloc bumps the point and supports multiple different arguments inside of it's `sizeof` (comma seperated chaining)
- `falloc` : free-allocation, falloc is like a targeted missile strike, it only deletes the reference from memory and pointers to exactly what you put in its `sizeof` arguments
and it also supports different arguments inside of its `sizeof` (comma separated chaining)

-----

### Rule 4 : Causal Access Pointers behave like dot-notation in JS, Java and C#
- it **is** the access operator, but its memory rules is simple: 
   <ol type="a">
   <li>what you don't reference, you don't pay for</li>
   <li>underneath the autocompletion and English reference name(s), it is a memory address</li>
   </ol>

-----

### Rule 5 : Semicolon 
- Semicolon (;) is the statement terminator and also represents where a block ends.

----- 

### Rule 6 : Return 
- `return 0;` : exits with success and clears the whole program from memory
- `return -1;` : exits with failure and clears whole program from memory

-----

### Rule 7 : STD is modularised

<ol type="a">
<li>each component of the std-lib is modular, as such if you import say `io`, it will only compile `io` alongside your program, alongside Rule 4.1(WYDR,YDPF)</li>
</ol>

----- 

### Rule 8 : Memory Sharing and Micro Inheritence
- suffix `*` (`Left* right`) is memory sharing, both `Left` and `right` occupy the same memory space
- it also allows for Micro Inheritance, where `Left` shares it things with `right`
----- 



