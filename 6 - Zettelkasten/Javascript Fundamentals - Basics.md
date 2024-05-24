
2024-05-24 11:38

Status: #child

Tags: [[frontend]] [[programming-language]] [[backend]] [[3 - Tags/javascript|javascript]]

# JS

JS is single threaded & synchronous where only one command can be executed at a time, next line is executed after the line before execution is completed.

**Single Threaded** - One command at a time
**Synchronously Executed** - Every line is executed in the order it is written

There are two parts in execution, *Global Memory & Execution Context*

**Call Stack** - It is a stack in JS interpreter (eg: web browser) used to keep track of its place in a script that calls multiple function. When a function is called it is pushed to the call stack, when a function is called inside the function it is pushed on top of the stack. The call stack is LIFO stack.

**Functions**  are first class objects in JS, i.e. it can be passed as arguments to other functions and returned from other function as its values
**Higher Order Functions** are functions that takes other functions as its parameters or if it returns another function
**Callback Function** - The functions that are provided as argument to another HOF 







# References

- Call Stack - https://developer.mozilla.org/en-US/docs/Glossary/Call_stack
- FEM - Javascript: The Hard Parts, v2 - https://frontendmasters.com/courses/javascript-hard-parts-v2/

 







