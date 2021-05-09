# rust-notes

## Table of Contents

1. [Data Types](#data-types)
2. [Variables and Mutability](#variables-and-mutability)
3. [Functions](#functions)

## Data Types

### Scalar Types

```rust
// integers
let x = 0; // i32 is default
let x: i8 = 0; // signed 8-bit integer
let x: u8 = 0; // unsigned 8-bit integer
let x: i16 = 0; // signed 16-bit integer
let x: u16 = 0; // unsigned 16-bit integer
let x: i32 = 0; // signed 32-bit integer
let x: u32 = 0; // unsigned 32-bit integer
let x: i64 = 0; // signed 64-bit integer
let x: u64 = 0; // unsigned 64-bit integer
let x: i128 = 0; // signed 128-bit integer
let x: u128 = 0; // unsigned 128-bit integer
let x: isize = 0; // signed 64- or 32-bit integer depending on architecture
let x: usize = 0; // unsigned 64- or 32-bit integer depending on architecture

// integer literals
let y = 98_222; // decimal 98222
let y = 0xff; // hex 255
let y = 0o77; // octal 63
let y = 0b1111_0000; // binary 240
let y = b'A'; // byte 65 (u8 only)

// type suffixes
let z = 57u8;

// floating-points
let f = 0.0; // f64 is default
let f: f32 = 0.0; // f32 single-precision
let f: f64 = 0.0; // f64 double-precision

// booleans
let t = true;
let f: bool = false;

// characters
let c = 'z'; // single quotes
let c: char = 'ℤ'; // four byte UTF-8
```

### Compound Types

```rust
// tuples
// fixed length
let tup: (i32, f64, u8) = (500, 6.4, 1);
let (x, y, z) = tup; // destructuring tuple
let five_hundred = tup.0; // accessing tuple element

// arrays
// fixed length, same type
let a = [1, 2, 3, 4, 5];
let a: [i32; 5] = [1, 2, 3, 4, 5]; // declaring type and size
let a = [3; 5]; // [3, 3, 3, 3, 3]
let first = a[0]; // accessing array element
```

## Variables and Mutability

```rust
// variables are immutable by default
let foo = 5;
foo = 6; // compilation error

// mutable variables
let mut bar = 5;

// constants must be type annotated
// cannot be assigned to function calls
const MAX_POINTS: u32 = 100_000;

// variable shadowing
// variable type can be changed
let spaces = "   ";
let spaces = spaces.len();
```

## Functions

```rust
// defining functions
// functions can be called before they are defined
fn main() {
    foo();
}

fn foo() {
    println!("hello world");
}

// function parameters
// all parameters must be type annotated
fn bar(x: i32, y: i32) {}

// statements: instructions that don't return a value
// expressions: evaluate to a resulting value
let x = (let y = 6); // compilation error
let y = {
    let x = 3;
    x + 1 // no semicolon, semicolon turns an expression into a statement
}; // {} is an expression

// function return values
// return type declared with ->
fn five() -> i32 {
    5
}

// return keyword
fn three() -> i32 {
    return 3;
}
```
