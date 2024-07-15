
2024-07-13 15:48

Status: #child 

Tags: [[programming-language]] [[go]]

# Go Fundamentals - Enums

- A way of defining a fixed list of values that are all related
- Go does not have a built in type, but it does provide tools such as iota to let you define your own using constants

```go
const (
	Sunday = 0
	Monday = 1
	Tuesday = 2
	Wednesday = 3
	Thursday = 4
	Friday = 5
	Saturday = 6
)
```

implementing with `iota`

```go
const (
  Sunday = iota
  Monday
  Tuesday
  Wednesday
  Thursday
  Friday
  Saturday
)
```

Now `iota` will assign numbers to the enums, 
Ordering is very important, we can skip values using `_` by iota



# References






