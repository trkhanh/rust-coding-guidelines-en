## G.TYP.VEC.01  禁止访问未初始化的数组

**【级别】** 建议

**【描述】**

访问未初始化数组的内存会导致未定义行为。

**【反例】**

 ```rust
 let mut vec: Vec<u8> = Vec::with_capacity(1000);
 unsafe { vec.set_len(1000); }
 // 不符合
 reader.read(&mut vec); // error: Undefined Behavior: using uninitialized data, but this operation requires initialized memory
 ```

**【正例】**

```rust
// 符合
let mut vec: Vec<u8> = vec![0; 1000];
reader.read(&mut vec);
```

**【Lint Detection】**

| lint name                                                    | Clippy Detectable | Rustc Detectable | Lint Group  | level |
| ------------------------------------------------------------ | ------------- | ------------ | ----------- | ----- |
| [uninit_vec](https://rust-lang.github.io/rust-clippy/master/#uninit_vec) | yes           | no           | correctness | deny  |
