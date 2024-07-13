
2024-07-13 11:13

Status: #child 

Tags: [[programming-language]] [[go]]

# Go Fundamentals - Value versus pointer

- With values like `int, bool, string`, go makes a copy of the value and that copy is used inside the function (Call by value)
- When doing call by value, the change in value inside the function does not affect the original value itself
- CBV results in fewer bugs, as Go uses simple memory management system called *Stack*
- Downside of Call by value is, in real-world there can be lots of functions, and nested functions, which can lead to high memory usage in this case

**Pointer**

It is not a value itself, but address of the value that we want, when passing this to a function, we pass the address of the value in the memory to the function, So no new copy is created when (Passing by Value)

- When creating a pointer value, go cannot manage it using the *Stack* anymore. Because *Stack* uses simple scope logic to know when it can reclaim the memory, which is not the same for the pointer
- We can GET the value from the pointer
- Go puts the value on the *heap*, this allow the value to exist until no part of app has pointer to it anymore, then Go reclaims these values through *garbage collection process*, which happens periodically in the background.
- Sometimes the values put in the heap is not just because there is a pointer to it, its not clear, working out weather a value is to be put on the heap is called *escape analysis*
- We do not have control over what is put in the *Stack* or *Heap*
- Though it gives memory advantage, if not used properly, it can increase the cpu usage, as it takes extra CPU cycles, for garbage collector to release the heap
- The pointer address with no value will be `nil`

**Init a pointer**
- `<name> * <type>` -  initial value will be nil
- Can use build in `new` function for this, which will get some memory for a type and return a pointer to the address `<name> := new (<type>)`
- Get pointer from an existing variable by using `&` notation `<var1> := &<var2>`

**Getting a pointer**
- Need to do `nil` checks before *de-referring* the variables, it is to avoid the de-referencing errors
- dereference is done by adding `*` in the front
- 3

#### Function design with pointers

- A function should be designed to accept the pointers
- Any change made to the value of the pointer inside the function will apply to the value if its referenced anywhere else
- If a function accepts a pointer it should have arguments with `*`

#### Pointer value swap




 

# References






