
2024-07-12 15:44

Status: #child 

Tags: [[programming-language]] [[go]]

# Go Fundamentals - Variables

- variables in go is defined with `:=`
- string should be enclosed in double quotes
- A variable holds data temporarily, it needs 4 things
	- a statement of declaring the variable
	- name of the variable
	- type of data that it can hold
	- initial value for it
- Some of these above mentioned are optional
- If type is mentioned, but no initial value is given, then GO uses the zero value for the type we opted
- If we give initial value but not a type, Go has a ruleset onto how to infer the types

example `var foo string = "bar"`
`var` - declaration of the variable definition
`foo` - name of the variable
`string` -  the type of the variable
`bar` -  the initial value

if a variable is defined outside any function, then that is *package level variable defenition*

**Declaring multiple variable at once with var** - 
- This method is common when declaring package level variable, variables not need to be of the same type, they all can have their own initial values
- Not a norm, used when defining package-level variables, in there we will use the full notation

**Situation where we should type interface**

There are times where we need to use all parts of the declaration, as go won't be able to guess the correct type.

`var seed = 1234455454234`
`rand.NewSource(seed)` - > thows error as seed cannot be a an `int` but an `int64`

`var seed int64 = 123123123123123`


**Declaring the variable inside the function** - If the variable declaration is inside the function, we can use the short hand expression of `:-`

**Short hand declaration for multiple variables** - `Debug, LogLevel, startUpTime := false, "info", time.Now()`

**Using var to declare multiple variables on the same line** - `var start, middle, end float32` , `var name, left, right, top, bottom = "one", 1, 1.5, 2, 2.5`
- When using this, if defining the type, all var should be single type
- When assigning values, the type will be taken from the literal value

**Go allows to use UTF-8 chars** 


**Changing multiple values at once** - `query, limit, offest := "bat", 10, 0`
`query, limit, offest = "ball", 23, 3`


# References






