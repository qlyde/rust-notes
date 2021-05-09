## Functions

```rust
// defining functions
// functions can be called before they are defined
fn main() {
    foo();
}

fn foo() {
    println!("hello, world");
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
    5 // last evaluated expression is returned
}

// return keyword
fn three() -> i32 {
    return 3;
}
```
