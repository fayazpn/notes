

2024-07-02 00:09

Status: #child 

Tags: [[rust]] [[programming-language]] 

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






