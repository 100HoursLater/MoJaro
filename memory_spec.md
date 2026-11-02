# MoJaro Memory Rules:

## Rules:
-----

### Rule 1 : Special Imports 
 - `import "memory" from 'std';` : this import allows you do memory more in-depth like memory fence `memory->memory_fence(/*memory address here*/);`

-----

### Rule 2 : Threads (IMPORTANT)
- Interfaces represent the whole program in memory 
- Classes represent each thread (must be serialized in order to communicate with each other) 

-----

### Rule 3 : alloc and falloc (IMPORTANT) 
- `alloc` : allocation, each thread has its own arena, alloc bumps the point and supports multiple different arguments inside of it's `sizeof` (comma seperated chaining)
- `falloc` : free-allocation, falloc is like a targeted missile strike, it only deletes the reference from memory and pointers to exactly what you put in its `sizeof` arguments-
and it also supports different arguments inside of its `sizeof` (comma separated chaining)

-----

### Rule 4 : Causal Access Pointers behave like dot-notation in JS, Java and C#
- it **is** the access operator, but its memory rules is simple: 
   <ol type="A">
   <li>what you don't reference, you don't pay for</li>
   <li>underneath the autocompletion and English reference name(s), it is a memory address</li>
   </ol>

-----

