## G.TYP.BOL.03 不应将数字类型转换为布尔值

**【级别】** 要求

**【描述】**

这可能会让布尔值在内存中的表示无效。

**【反例】**

```rust
let x = 1_u8;
unsafe {
    // 不符合
    let _: bool = std::mem::transmute(x); // where x: u8
}

```

**【Lint Detection】**

| lint name                                                                                      | Clippy Detectable | Rustc Detectable | Lint Group | Defaultlevel |
| ---------------------------------------------------------------------------------------------- | ------------- | ------------ | ---------- | --------- |
| [transmute_int_to_bool](https://rust-lang.github.io/rust-clippy/master/#transmute_int_to_bool) | yes           | no           | complexity | warn      |


