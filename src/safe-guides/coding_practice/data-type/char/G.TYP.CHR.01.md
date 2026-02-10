## G.TYP.CHR.01  不应将字符字面量强制转换为 `u8`

**【级别】** 建议

**【描述】**

应该使用字节字面量，而不应使用字符字面量强转为 `u8`。

**【反例】**

```rust
// 不符合
'x' as u8
```

**【正例】**

```rust
// 符合
b'x'
```

**【Lint Detection】**

| lint name                                                                        | Clippy Detectable | Rustc Detectable | Lint Group | Defaultlevel |
| -------------------------------------------------------------------------------- | ------------- | ------------ | ---------- | --------- |
| [char_lit_as_u8](https://rust-lang.github.io/rust-clippy/master/#char_lit_as_u8) | yes           | no           | complexity | warn      |


