
2024-07-14 17:13

Status: #child 

Tags: [[programming-language]] [[go]]

# Go Fundamentals - Core Types

- Largest amount of storage in number in Gos core type is 64 bits
- Things that define the type
	- What kind of data it can store
	- What operations to do on it
	- What operations does to it
	- How much memory it use

### Boolean Type
- Can have only `true` or `false`
- The "zero value" of the boolean is `false`
- `==` or `>` results to `bool` value

### Number Type
- Integers & floating-point
- Default type and empty for all number is 0
- Negative numbers are stored in signed integers
- Types that can't store negative numbers is called unsigned integers
- How big and small a type can store is determined by how many bytes of internal storage they have
- `uint8 - uint64`
- `int8 - int64`
- `byte` - alias for `int8`
- `rune` - alias for `int32`

**Special integer type**
- `uint` - either 32 or 64 bits depending on where we compile, 32-bit system or 64-bit system
- `int or uint type of 64 bit system` is not the same as `int64`, and cannot be used together
- If did so, it will be problem when compiled in other `32 bit system`

- To choose a type for int, generally use `int` for most cases, switch to other type if using this is causing the problem, mostly due to memory usage
- So start with `int` if performance becomes a problem, switch `int8`

### Floating-point numbers

- Go uses two types of floats `float32` and `float64`, 
- `float64` allows to store more precision numbers
- Float numbers are stored by 2 parts, whole number and decimal, the storage of these 2 parts is done according to their length in each parts
- by default make the type `float64` unless need of memory efficiency

### Overflow and Wrap-around
- When initializing a number with a value that is too big for the type that we are using, we will get an *overflow error*
- When compiler does not catch this *overflow problem*, it does something called *wrap-around*, it goes from the highest possible value to the lowest possible value

**Big Numbers** are used when you needs numbers bigger or smaller than the actual core types are needed, they are imported from `math/big`

### byte
`byte` is an alias for `uint8`, with 8 bits of storage

### Text
- Go uses single *string* for texts
- Two type of string literals in go
	- Raw - in pair of back ticks
	- Interpreted -  in double quotes
- Encoded in UT-8 by default, but not limited to it


### Rune
`rune` is a type with storage of a single UTF-8 multi-byte character.
- alias for `int32`
- Go stores all strings as byte collection `[]byte` as it should allow flexibility for encoding (UTF-8 has different byte lengths)
- UTF-8 uses 1 to 4 bytes for encoding characters
 - The different encoding use a different number of bytes to encode a text
 - Legacy standard uses one byte to encode a single character
 - UTF-8 uses up to 4 bytes to encode a single character
 - To work with Unicode characters, it should be converted from a byte collection to a rune collection

When working with strings `strings` package has uses tools that we need

### nil value
`nil` is not a type but a special value in go, it represents *an empty value of no type*
Make sure to check if something is `nil` when working with pointers, maps and interfaces, if interacted with `nil` value the code will crash



# References






