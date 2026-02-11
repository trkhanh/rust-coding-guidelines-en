# 3.19 Unsafe Rust

Unsafe Rust is a superset of Safe Rust, meaning that Safe Rust's safety checks also exist within Unsafe Rust. However, the following five things in Unsafe Rust are beyond the reach of Safe Rust's checks:

1. Dereferencing raw pointers
2. Calling `unsafe` functions (C functions, compiler intrinsics, or raw allocators)
3. Implementing `unsafe` traits
4. Mutable static variables
5. Accessing fields of a `union`

When using Unsafe Rust, certain conventions must be followed to avoid the occurrence of undefined behavior.

For specialized terminology regarding Unsafe Rust, you can check the [Unsafe 代码术语指南](./unsafe_rust/glossary.md) .

**The semantics of Unsafe Rust: This is where the compiler cannot guarantee safety; the programmer must ensure safety.** [Unsafe 代码术语指南](./unsafe_rust/glossary.md)