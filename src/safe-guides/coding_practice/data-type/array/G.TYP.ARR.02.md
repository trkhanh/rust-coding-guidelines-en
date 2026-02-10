## G.TYP.ARR.02  使用数组索引时禁止越界访问

**【级别】** 要求

**【描述】**

越界访问在运行时会 Panic！

**【反例】**

```rust
// 不符合
let x = [1, 2, 3, 4];
x[9];
&x[2..9];
```

**【正例】**

```rust
// 符合
let x = [1, 2, 3, 4];
x[0];
x[3];
```

**【Lint Detection】**

| lint name                                                                                        | Clippy Detectable | Rustc Detectable | Lint Group  | Defaultlevel |
| ------------------------------------------------------------------------------------------------ | ------------- | ------------ | ----------- | --------- |
| [out_of_bounds_indexing](https://rust-lang.github.io/rust-clippy/master/#out_of_bounds_indexing) | yes           | no           | correctness | deny      |


