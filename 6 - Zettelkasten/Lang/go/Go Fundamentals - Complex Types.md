
2024-07-15 17:57

Status: #child 

Tags: [[programming-language]] [[go]]

# Go Fundamentals - Complex Types

**Collection Type** - Arrays, slices and maps
- They are strongly typed and easy to loop over, but they each have unique qualities

### Arrays
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
- Using *len* in a loop is okay as it tracks the length of each array internally, so it does not count items when we call *len*, same with other collections

### Slices
- Arrays are rigid when it comes to size
- Slices are like arrays with sorted numeric indexed collection without size limitations
- *append function* - accepts the slice and value to add and return a new slice
- It is not a true type like array, default used slices for collections
- append function in slice can take `...` notation to accept more than one item to append
- Can create slice from slice using `[:]` notation
- **Slice internals**
	- Collections are not value type like string, value types can be copied and compared, Slices work more like pointers, they are not exactly pointers
	- There is a *hidden array* that stores the value and when making changes to slice it changes the underlying array
	- There are 3 hidden properties
		- length
		- a pointer to the hidden array
		- starting point in the hidden array
	- size of the hidden array and size of the slice are not always the same
	- size of the slice can be found using `len`
	- size of the hidden array is the capacity of slice `cap`
	- if the hidden array is not full, the value is added to the hidden array and *length* property is updated
	- if hidden array is full, Go creates a larger array, copies all the contents to the new array and adds the new value, updates the slice from pointing old to new, updates length and its starting point*
	- starting point only matter if the slice is subset of the values from an array or slice, else it will be first element in the hidden array
	- we can control the size of the *hidden array* when you define a slice. 
	  `make(<sliceType>, <length>, <capacity>)` where capacity is optional
#### Behavior of slices
- Slice cannot be one another except for the nil value
- Slice does not store values in them directly
- What it stores is the pointer to the array, starting point in the array, capacity of the slice, length of the slice
- The pointer to the hidden can be shared by more than 1 slice
- normal assigning of variable and `[:]`does not create a new slice, they point to the same hidden array
- `append(s1, 4)` - creates a new slice in the hidden array, they are not linked anymore, this was due to during append there was no space in the hidden array, hidden array got replaced in the first slice
- `make([]int, 5, 10)` then `append(s1,6)` does not create a new hidden array if there is extra capacity in the defined slice, in this case there is a link in the `s2` as the hidden array is the same
- same setup as above, if you append elements than there is space, the hidden array in the first slice gets replaced by new bigger one
- `copy` - copy copies to new hidden array, but the destination array should be of exact size
- `append([]int{}, s1...}` - does same as the `copy` function except that we don't have to worry about the size of the second slice, this is used in the real-world code
	- Slightly more memory efficient solution is to avoid the dummy memory allocation in the `append` function `append(s1[:0:0], s1...)` - by creating a 0 capacity range copy

### Map 
- Not similar as to arrays and slices
- In arrays and slices, the *key* is a placeholder where it just filled with numbers,
- Here it is actual `<key>:<value>` pair where we should define both
- There is no size limitations like arrays and slices
- *key* can be any value that can be directly compared to each other such as `int`, `string` but not `slices`
- *value* can be any value such as `pointers`
- Should not use map as an ordered list, as it is not guaranteed to give in arranged manner
- syntax : `map[<key_type]<value_type>{key: value..}`
- `make` function can be used to create map
- Maps are like slices in a way that they are not values nor pointers, challenging part is that it does not have a set length
- Before setting the value we must make sure that it is initialized
- so we should not try to define the map with `var`
- When reading from Map, if there exists no key, it will return zero value for that key, if we need to handle it another way, we can use the format `<value>, <exists_value> := <map>[<key>]`, the `exists_value` returns a boolean value which we can use to handle the cases
- use *range* to the loop the array as the map does not guarantee the ordering every time




# References






