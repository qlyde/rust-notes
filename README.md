# rust-notes

## Table of Contents

1. [Data Types](#data-types)
2. [Variables and Mutability](#variables-and-mutability)

## Data Types

```rust
// integers
let x: i8 = ... // signed 8-bit integer
let x: u8 = ... // unsigned 8-bit integer
let x: i16 = ... // signed 16-bit integer
let x: u16 = ... // unsigned 16-bit integer
let x: i32 = ... // signed 32-bit integer
let x: u32 = ... // unsigned 32-bit integer
let x: i64 = ... // signed 64-bit integer
let x: u64 = ... // unsigned 64-bit integer
let x: i128 = ... // signed 128-bit integer
let x: u128 = ... // unsigned 128-bit integer
let x: isize = ... // signed 64- or 32-bit integer depending on architecture
let x: usize = ... // unsigned 64- or 32-bit integer depending on architecture

// integer literals

```

## Variables and Mutability

```rust
// variables are immutable by default
let foo = 5;

// mutable variables
let mut bar = 5;

// constants must be type annotated
const MAX_POINTS: u32 = 100_000;

// variable shadowing
// variable type can be changed
let spaces = "   ";
let spaces = spaces.len();
```
