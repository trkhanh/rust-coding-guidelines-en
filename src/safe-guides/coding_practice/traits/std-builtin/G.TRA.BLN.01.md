## G.TRA.BLN.01   应该用具体类型的 `default()` 方法代替 `Default::default()` 调用

**【级别】** 建议

**【描述】**

为了增强可读性。

**【反例】**

```rust
#![warn(clippy::default_trait_access)]
// 不符合
let s: String = Default::default();
```

**【正例】**

```rust
#![warn(clippy::default_trait_access)]

// 符合
let s = String::default();
```

**【Lint Detection】**

| lint name                                                                                    | Clippy Detectable | Rustc Detectable | Lint Group | Defaultlevel |
| -------------------------------------------------------------------------------------------- | ------------- | ------------ | ---------- | --------- |
| [default_trait_access](https://rust-lang.github.io/rust-clippy/master/#default_trait_access) | yes           | no           | pedantic   | allow     |
