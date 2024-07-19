
2024-07-15 17:57

Status: #child 

Tags: [[programming-language]] [[go]]

# Go Fundamentals - Complex Types

**Collection Type** - Arrays, slices and maps
- They are strongly typed and easy to loop over, but they each have unique qualities

#### Arrays
- `[<size>]<type>` - 
	- `[10] int` - initializes array of size 10
	- `[] int` - If the size is not mentioned it would be a slice
		- It is more flexible
- **Array Initialization** - `[<size>]<type>{<value1>,..}` 
	- `[5]string{1}` - init first value as 1
	- `[...]string{9,9,9,9,9}` - initialize with data
	- length is set at runtime and is not changeable at runtime
- **Array Initialization using keys** - Can set values in any position and leave others the default value
	- `arr2 := [...]int{9:0}` - set value 0 to the index 9

**Looping over array**
- **For** loop has three possible parts
	- Logic that can run before loop
	- Logic that runs on each iteration
	- Logic that runs at each end of loop iteration
- Using *len* in a loop is okay as it tracks the length of each array internally, so it does not count items when we call len, same with other collections

### Slices
- Arrays are rigid when it comes to size
- Slices are like arrays with sorted numeric indexed collection without size limitations
- *append function* - accepts the slice and value to add and return a new slice
- It is not a true type like array, default used slices for collections



# References






