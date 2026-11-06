# MoJaro

## Global/Orphaned Code

-------------
**Global/Orphaned Code** just means you code is loose inside a class and not inside of a function or struct or Enum, 
Said code is fine, but from a code organisation strategy, it is not good practice, for a one liner, sure it's fine, but for a large code it isn't.

-------------

### What about C-Style code?

Sure it is possible in MoJaro to ignore all my warnings and do everything inside of flat global structs, but you still need that class and anyways, the normal syntax is just:

- # Head Class
- ## Functions(s) 
- ### Structs, or
- #### Enum's
----------------
