
2024-07-02 00:10

Status: #child 

Tags: [[programming-language]] [[rust]]


## Functions

Functions are logical code blocks that can be used at different points in our code. We can structure code into sub-programs that perform specific tasks.

```rust
fn function_name(parameter_list) -> return_type 
{ // code 
}
```

- fn: Defines the function.
- function_name: The name of the function.
- parameter_list: Parameters for the function enclosed within parentheses. Multiple parameters are separated by a comma.
- -> return_type: Defines the return type of the function.
- {..}: The function body enclosed within braces.

```rust
fn subtract(x: i32, y: i32) -> i32 
{ 
	return x - y; 
} 

// Call the function 
let difference = subtract(10, 5); 
println!("The difference is {}", difference);
```

### Implementations

**impl** keyword is used for methods related to *struct* or *enum*. It is like defining set of behaviours for a particular type.

```rust
struct StructName { 
	// fields 
} 
impl StructName { 
	// methods 
}
```

```rust
struct Circle {     
	radius: f64, 
}

impl Circle {     
	fn area(&self) -> f64 {         
		3.14 * (self.radius * self.radius)     
	}     
	
	fn perimeter(&self) -> f64 {         
		2.0 * 3.14 * self.radius     
		} 
} 
let circle = Circle { radius: 10.0 }; 
println!("The area of the circle is {}", circle.area()); 
println!("The perimeter of the circle is {}", circle.perimeter());
```

The &self keyword refers to the instance of Rectangle, similar to this in other languages.

### Traits

Traits are useful when defining shared behaviour across multiple types.

```rust
trait Shape {
    fn area(&self) -> f64;
    fn circumference(&self) -> f64;
}

struct Circle {
    radius: f64,
}

struct Square {
    side: f64,
}

impl Shape for Circle {
    fn area(&self) -> f64 {
        std::f64::consts::PI * self.radius * self.radius
    }

    fn circumference(&self) -> f64 {
        2.0 * std::f64::consts::PI * self.radius
    }
}

impl Shape for Square {
    fn area(&self) -> f64 {
        self.side * self.side
    }

    fn circumference(&self) -> f64 {
        4.0 * self.side
    }
}

fn main() {
    let circle = Circle { radius: 5.0 };
    let square = Square { side: 3.0 };

    println!("Circle Area: {}", circle.area());
    println!("Circle Circumference: {}", circle.circumference());

    println!("Square Area: {}", square.area());
    println!("Square Circumference: {}", square.circumference());
}

```

**Why use traits?**
- **Polymorphism** - Enables different types to be treated the same way if they have same trait. This is useful for writing generic functions or struct that can operate on any type that implements specific trait.
- **Code reusability**  - Multiple types can implement the same trait, adhering to a common interface.
- **Type Safety** - Traits ensure that only types that implement a specific behavior can be used in certain contexts
```rust 
// Application of shape trait defined above
fn print_shape_info<T: Shape>(shape: &T) { 
	println!("Area: {}", shape.area()); 
	println!("Circumference: {}", shape.circumference()); 
} 

fn main() { 
	let circle = Circle { radius: 5.0 }; 
	let square = Square { side: 3.0 }; 
	print_shape_info(&circle); 
	print_shape_info(&square); 
}
```
The function `print_shape_info` can accept any type `T` that implements the `Shape` trait.


**Traits vs Implements**

- **Defining Methods Directly in `impl`**: Useful for associating methods with a specific type. All instances of the type can use these methods.
- **Traits**: Define shared behavior that multiple types can implement. Traits allow for polymorphism, code reuse, and type safety.

# References






