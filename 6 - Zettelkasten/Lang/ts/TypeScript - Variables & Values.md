
2024-09-03 20:53

Status: #child 

Tags: [[typescript]]

# TypeScript - Variables & Values

- **Literal Type** - is the type that is taken from the primitive value which is in a `const` declaration `const number = 79`
	- When declared by `let` or `var` compiler knows that there is a possibility of value getting changed
- `let x = 10 as 79` - this is type casting, where we know the type of the variable more than the compiler
- When variable is declared but not assigned a value, then it is given the value `any` - implicit `any`
- `let endTime: Date` - this is called **Type Annotation**
- `let date3 = 'thing' as any as Date` - Here we are casting up to any then down to the `Date` type, we will get the methods of the `Date` type here which will break in run time
	- Used in situations where I am creating a test case
- **Function Return** -  type a functions return type to make the function like a 'contract' to the outside world, also if we do not type the return type we will get the error in the place that we are using it rather than the place of implementation, When we are trying to use the returned value of the function we will get the error that is called 'duck typing'

# References
https://frontendmasters.com/courses/typescript-v4/functions-return-types/





