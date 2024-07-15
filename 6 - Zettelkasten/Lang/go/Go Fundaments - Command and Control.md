
2024-07-13 17:04

Status: #child 

Tags: [[programming-language]] [[go]]

# Go Fundaments - Command and Control

**If Statements** -
```go
if <boolean expression> {
	<code block>
} else if <boolean expression> {
	<code block>
} else {
	<code block>
}
```


**Initial if statements**

- A common use case where we call a function and not care about what it returns , such as api end points, have a problem of the return value not going anywhere as it is still in the scope
- To stop these unwanted variables from hanging around we can use the scope rules to get rid of them, by using the *initial if statements*
```go
if <initial statement>; <boolean expression> {
	<code block>
}
```
- Go only allows simple statements in the initial statement section
	- `i := 0`
	- `i = (j * 10) == 40`
	- `i++`
- We cannot define a variable using `var` in the statement section

**Switch Statements**
- Has *initial statement* and *expression*, which are optional
- Expression is much more than the one in *initial if statements*
```go
switch <expression> {..}
switch <initial statement>; {..}
switch {..}
```

When a case matches, only its statements are run
To get the fall through like other languages, we need to add `fallthrough` at the end of every case, which will move on to the next case
These type of switch statement is called *expression switch* statement

Each case can check for multiple values
```go
case time.Monday, time.Tuesday, time.Wednesday, time.Thursday,
time.Friday:

   fmt.Println("Born on a weekday")
```




# References






