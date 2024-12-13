# Lua Recursive Table Traversal Bug

This repository demonstrates a potential issue with recursive table traversal in Lua.  Lua's `pairs` iterator does not guarantee a specific iteration order, which can lead to unexpected behavior in functions that modify the table while iterating.

The `bug.lua` file contains code that recursively traverses a nested table. If the table structure changes during traversal, the function's behavior will be unpredictable and the order of execution may vary between different Lua interpreters or even different runs of the same interpreter.

The `bugSolution.lua` file provides a solution that avoids this issue using a different approach.  See the solution for further details. 

## How to Reproduce

1. Clone this repository.
2. Run `bug.lua` using a Lua interpreter.
3. Observe the order of elements processed (you might need to print the values during iteration to see the order). You will observe that the order of operations may vary on different executions or with different versions of Lua.
4. Run `bugSolution.lua`. Note the improved consistency. 
