## References and Borrowing

```rust
fn main() {
    let s1 = String::from("hello");

    // `calculate_length` borrows a reference to s1
    // &s1 is a reference to s1 that does not own s1
    let len = calculate_length(&s1);

    // can still use s1 after borrowing
    println!("The length of '{}' is {}.", s1, len);
}

fn calculate_length(s: &String) -> usize {
    s.len()
}
```
