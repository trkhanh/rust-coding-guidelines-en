# 3.11 Traits
Trait refers to trait. In rust, a trais is not a concreate type, but rather an abstract interface. However, through `impt Trait` and `dyn Trait`, traits can also be used as types

## Key Terminology Note:
- Concrete Type: A type with a known size and structure (like i32 or String).

- Abstract Interface: A way to define behavior that different types can share.

- impl Trait: Used for Static Dispatch (resolved at compile time).

- dyn Trait: Used for Dynamic Dispatch (resolved at runtime using a vtable).