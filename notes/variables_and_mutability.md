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
