
2024-06-26 18:13

Status: #adult

Tags:  [[programming-language]]  [[3 - Tags/javascript|javascript]]

# Closures

In JS function does not retain memory, but we can make them retain memory using a method called function closures
When *function B* is returned from inside the *function A*, the surrounding scope of everything used by *function B* is also returned with it. These values are still accessible if we run *function A* but not directly accessible, so we can say these values are *cached*

This cached values are stored in ‘backpack’ of the returned function in a hidden property called *[ [ scope ] ]* or backpack, which is not accessible to us except through the function only.


```js
function test() {
	let count = 0;

	function increment () {
		return count ++
	}

	return increment
}

const tester = test()

```

In this snippet, *tester* name space will hold the actual returned function *increment* which can be invoked anytime.

When *tester()* is invoked, execution context of *increment* is first checked of *count*, once it is not found, then it first checks if *count* is present in the backpack, before checking the outer execution context.

The *count* variable here is always cached in the backpack.

-  C.O.V.E - Close over variable environment
- P.L.S.R.D - Persistant Lexically/Static scoped data

Multiple closure instances have independent separate backpack.

 Use Cases
- limit function - Function that would remember the high score
- memoization - Can memoize an expensive operation so that it does not have to calculated later on
- iterators/generators - iterators such as forEach will remember the current index, function generators are functions that can remember which line and which value when stopped executing and can resume the execution later
- module pattern - Using this pattern, the code can be modularized so we can use same name-space and avoid global polluting of variables
- async js - closures are used in async js


# References
FEM - Javascript: The Hard Parts, v2 - https://frontendmasters.com/courses/javascript-hard-parts-v2/
FCC - https://www.freecodecamp.org/news/javascript-lexical-scope-tutorial/





