- Make polymorphic functions
- < operator dont coerce to number if two strings are compared which holds number it does alpha numeric comparison
- validator functions using JS


 function isValidName(name) {
	if(typeof name === 'string' && name.trim().length >= 3) {
		return
	}
return false
- }

function hoursAttended(attended, length) {

	if(typeof attened === 'string' && attended.trim() != "") {
		attended = Number(attended)
	}
	
	if(typeof length === 'string' && length.trim() != "") {
		length = Number(length)
	}
	if(typeof attened === "number" && typeof length === "number" && attened >=0 && length >= 0 && Number.isInteger(attented) && Number.isInteger(length) && attened <= length) {
		return true
	}
	
	 return false
}

- Equality checking
	- == vs ===
		- both checks the type
		- identical when types match
		- ==
			- == allows coercion if types are different
			- === disallows coercion if types are the same
			- null == undefined as per spec
			- == prefers to numeric comparsion of both op
			- in == if u compare non primitive then it invokes ToPrimitive algorithm
			- var w = 42
			- var v = [42]
				- if(v == w)
					- v -> toPrimitive(v) -> "42"
					- 42 = "42"
					- 42 == toNumber("42")
			- corner cases
				- var work = []
				- if(work)  %%True This is ok, This is implicit%%
				- if(work == true) %%False Not ok %%
				- if(work == false) %% True %%
				- Avoid
					- when == with 0/''/' '
					- == with non primitives
					- == true or == false instead toBoolean or ===
				- When to use
					- use it always when you know the types
		- ====
			- dont use if you know the types
				- if different types its always false
				- if true, its not worth the use
				- when types are different
					- one == is equal two or more ===
			- use it when you dont know the types
			- protect using ===