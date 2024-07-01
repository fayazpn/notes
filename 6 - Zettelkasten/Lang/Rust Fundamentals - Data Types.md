
2024-07-01 18:03

Status: #child 

Tags: [[programming-language]] [[rust]] 
## Data Types

- **unsigned** - Can store range from 0 - 2^n-1,  u8 stores number from 0 to 2^8-1 i.e 0-255, *u8*
- **signed** - Each signed variant can store numbers from -(2^(n – 1)) to 2^(n – 1) – 1 inclusive, where n is the number of bits that variant uses. So an i8 can store numbers from -(2^7) to 2^7 – 1, which equals -128 to 127. *i8*
- **float** - Rust’s floating-point types are f32 and f64, which are 32 bits and 64 bits in size, respectively. The default type is f64 because on modern CPUs, it’s roughly the same speed as f32 but is capable of more precision. All floating-point types are signed. *f8*
- **character** - let character: char = 'a';
- **boolean** - let boolean: bool = true;
- **tuple** - used for grouping different data types, let tuple: (i32, f64, bool) = (...)
- {:?} - used for debugging
- **arrays** - used for grouping same data types
	- `let array: [i32, 5 ] = [1,1,1,1,1]`
- **string** - used for grouping characters
	- `let string: &str = "Hello World"`
- **vector** - is used for grouping different data types and it is dynamic
	- `let mut vector: Vec<i32> = vec![1,3,4]`
	- `vector.push(5)`
- **hashmap** - hash-map is used for grouping 2 different data-types as key-value pairs
	- `let mut hash_map: HashMap<&str, char> = std::collections::HashMap::new()`
	- `hash_map.insert(k: "this", v: 'c')`
	-  `hash_map.insert(k: "that", v: 'd')`
	- `println!("Hash Map => {:?}", hash_map)`
	- When you invoke `std::collections::HashMap::new`, you create a new HashMap object that has no key-value pairs initially. You can then use methods such as insert, get, and remove to add, retrieve, or remove elements from the HashMap.

### Arrays vs Vectors

|                                                                                                                          |                                                                                                                          |
| ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| **Arrays**                                                                                                               | **Vectors**                                                                                                              |
| Arrays in Rust have a fixed size determined at compile time.                                                             | Vectors, represented by the Vec<T> type, are dynamic arrays that can grow or shrink at runtime.                          |
| Elements in an array have the same type, and the length is part of the array’s type signature.                           | Vectors can store elements of different types, as they utilise Rust’s generic type system.                               |
| Arrays are allocated on the stack, making them more memory efficient and generally faster to access compared to vectors. | Vectors are allocated on the heap, allowing them to have a flexible size.                                                |
| The mut keyword can be used to declare a mutable array, allowing modifications to its elements.                          | The mut keyword can be used with vectors to declare mutable vectors and modify their elements.                           |
| However, arrays cannot be dynamically resized once created. Their size is static and cannot be changed during runtime.   | Vectors provide additional methods and functionality not available with arrays, such as push, pop, and dynamic resizing. |

**Struct** - short for *structure*, Structs are similar to classes in other programming languages and are a fundamental building block for defining complex data structures and organizing data in Rust programs.
*example of simple struct to represent a 2D point*
``` struct Point {  x: f64,  y: f64,  } ```

**Enums** - Enums are used to represent data that can have different forms while still maintaining a clear type definition. It is a type, we need to instantiate it before using it. *Enums* requires to have special debug formatter.
```rust
enum Color {
	red,
	green, 
	blue
}

fn main() {
	let color: Color = Color::blue
}
```


### Mutability in Rust

**Mutability** is a concept where the value can be changed after it is created, **Immutability** is where the values cannot be changed after it is created.
By default all the data value in rust is immutable, to create type safety. Rusts borrow checker enforces these rules at compile time to ensure memory safety.

Mutability can be achieved through following:
	 **Variables** : Standard variable created is immutable by default unless we add keyword *mut* in front
		`let mut x = 5`
	**References** : Rust has two types of references, known as borrowing: mutable references and immutable references. Borrowing resolves conflicting access and avoids data races.
	**Immutable Reference** : Created with *T*& and allows read-only access to data. Multiple immutable references can exist simultaneously but cannot coexist with mutable references. 
	
```rust
let x = 10; let y = &x; // Immutable borrow of x
```

**Mutable Reference** : **Mutable reference**: Created with &mut T and allows read-write access to the data. We get temporary access to modify the variable, it borrows the reference of the data without taking the ownership of it. It is more stricter than **Immutable** borrows.
- Once value is mutably borrowed, no other borrow of that values are allowed.
- Allows modification
- Only one mutable borrow allowed in a particular scope
- Also cannot use the borrowed value in the same scope again
```rust
let mut x = 10; // x needs to be mutable to allow mutable borrowing 
{ 
	let y = &mut x; // Mutable borrow of 
	x *y += 5; // Modify the value through the mutable reference 
} // y goes out of scope here, and the mutable borrow ends
```

**Immutable Reference** - Allows reading data without modifying it , cannot change the value in this reference. 
- You can have multiple immutable borrows of the same data at the same time.
- While one or more immutable borrows are active, no mutable borrows are allowed.

### Loops

**loop** - Infinite loop that keeps executing the enclosed until a condition is met. We use this when we are unsure about number of iterations or for infinite loop.
```rust 
let mut counter: i32 = 0;
loop {
	println!("Looping...");
	counter += 1;
	if counter >= 5 {
		break;
	}
}
```

**while** - Evaluates a condition before executing the loop body, if condition is true, the loop body is executed. If the condition is false from the beginning, the body would never execute.

```rust
let mut i: i32 = 0;
while i < 10 {
	println("Looping")
	i += 1;
}
```

**for** - The loop executes for each element in the collection and implicitly handles the termination condition. It is used for iterating in collection or a range, arrays, vectors or iterators. 
```rust
for i: i32 in 0..10 {
	println!("looping")
}
```

### Match

It is like switch statement in other languages but with additional features.
It allows us to compare a value against series of patterns, where upon matching that piece of code is run. Pattern matching is exhaustive on Rust, we must cover all the cases or code won't compile.

**Match with range patterns**
```rust
let number = 5; 
match number {  
	1..=5 => println!("one through five"),  
	_ => println!("something else"), 
}
```

The _ pattern is used for handling all remaining values. If _ wasn’t present and the match expression doesn’t handle all possible values, then the code would not compile.

# References






