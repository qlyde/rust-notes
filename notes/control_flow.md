## Control Flow

### `if` Expressions

```rust
// if expressions
let number = 6;
if number % 4 == 0 {
    println!("number is divisible by 4");
} else if number % 3 == 0 {
    println!("number is divisible by 3");
} else if number % 2 == 0 {
    println!("number is divisible by 2");
} else {
    println!("number is not divisible by 4, 3, or 2");
}

// condition must be a bool
if number {} // compilation error

// if with let statements
// since if is an expression
let condition = true;
let number = if condition { 5 } else { 6 };

// types must match
let number = if condition { 5 } else { "six" }; // compilation error
```

### Loops

```rust
// loop: infinite loops
loop {
    println!("again!");
}

// break
let mut counter = 0;
let result = loop {
    counter += 1;
    if counter == 10 {
        break counter * 2; // return value
    }
};

// while: conditional loops
let mut number = 3;
while number != 0 {
    println!("{}!", number);
    number -= 1;
}

// for: looping through a collection
let a = [10, 20, 30, 40, 50];
for element in a.iter() {
    println!("{}", element);
}

// ranges (start..end) are bounded inclusively below and exclusively above
for number in (1..4).rev() { // reverse a range
    println!("{}!", number);
}
```
