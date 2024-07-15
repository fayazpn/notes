
2024-07-13 18:15

Status: #child 

Tags: [[programming-language]] [[go]]

# Go Fundamentals - Loops

**For loops** - for collections

```go
for <initial statement>; <condition>; <post statement> {
	<statements>
}
```
- *initial statement* is checked before everything else, supports simple statements
- *condition* is checked before each loop and also supports simple statements
- *post statement* - is run after end of the each loop
- All these are optional

**For loops** - for conditions

- Another type of for loop where we read from a data source and there is more data to read

```go
for <condition> {
	<statements>
}
```
**For loops** - for un-ordered lists
- used for data structure like *maps*
```go
for <key>, <value> := range <map> {
	<statements>
}
```

- Looping over map
```go
for key, value := range config {
	fmt.Println(key, "=", value)
}
```

- Looping over map does not give guarantees like starting at 0, having no gaps
- can use _ to tell the compiler we don't want a certain variable


## Goto Statements

- Can be used in the cases where we need to goto a certain location in the function
- Can only be used inside the function scope, or there will be compilation error
- Used with caution as it can decrease the readability of the code
- `goto STOP` - where *STOP* is custom defined variable
- `STOP : ...`
# References






