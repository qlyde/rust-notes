## Ownership

```rust
// each value in Rust has an owner
// when the owner goes out of scope, the value will be dropped
{
    let s = "hello";
}
// scope is over, s no longer valid

let x = 5;
let y = x;
// x and y pushed onto the stack
// x still valid

// String is made up of ...
// stack: pointer to heap data, length, capacity
// heap: contents of string
let s1 = String::from("hello");
let s2 = s1; // called a move
// only stack data is copied
// s1 and s2 point to same heap data
// s1 no longer valid

// double free error when s1 and s2 go out of scope
// so s1 is no longer considered valid after move
println!("{}, world!", s1); // compilation error: value borrowed after move

// clone
let s1 = String::from("hello");
let s2 = s1.clone(); // deep copy of heap data (expensive)
// s1 still valid

// if a type implements the Copy trait, an older variable is still usable after assignment
// cannot implement Copy trait if Drop trait is implemented
```

### Ownership and Functions

```rust
// passing a variable to a function will move or copy, like assignment
fn main() {
    let s = String::from("hello");
    takes_ownership(s); // s is moved into function
    // s no longer valid

    let x = 5;
    makes_copy(x); // x is moved into function but i32 is Copy
    // x is still valid
}

fn takes_ownership(some_string: String) { // some_string comes into scope
    println!("{}", some_string);
} // some_string goes out of scope

fn makes_copy(some_integer: i32) { // some_integer comes into scope
    println!("{}", some_integer);
} // some_integer goes out of scope
```

```rust
// returning values transfers ownership
fn main() {
    let s1 = gives_ownership(); // give_ownership moves return value into s1
    let s2 = String::from("hello"); // s2 comes into scope
    let s3 = takes_and_gives_back(s2); // s2 moved into takes_and_gives_back which moves return value into s3
}

fn gives_ownership() -> String {
    let some_string = String::from("hello");
    some_string // moves return value into calling function
}

fn takes_and_gives_back(a_string: String) -> String {
    a_string // moves return value into calling function
}
```
