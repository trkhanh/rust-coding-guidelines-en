## G.CMT.01 Add "Erros" Section to documentation for public functoin returning `Result`

**【Level】** Advisory

**【Description】**

For public (pub) fuction that return a `Result` type, it is recommended ot include and `# Errors` section in the documentation. This section should explain the specific scenarios in which the funciton returns an error an what types of errors can be expected, assiting users in proper error handling.

Note: This rule can be detected by Cargo Clippy, but it does not trigger a waring by default.

**【Negative Example】**

```rust
#![warn(clippy::missing_errors_doc)]

use std::io;
// Non-compliant：Clippy will issue a warning:
//  "warning: docs for function returning `Result` missing `# Errors` section"
pub fn read(filename: String) -> io::Result<String> {
    unimplemented!();
}
```

**【Positive Example】**

```rust
#![warn(clippy::missing_errors_doc)]

use std::io;
// Compliant：Added a standardized Errors documentation section

/// # Errors
///
/// Will return `Err` if `filename` does not exist or the user does not have
/// permission to read it.
pub fn read(filename: String) -> io::Result<String> {
    unimplemented!();
}
```

**【Lint Detection】**

| lint name                                                                                          | Clippy Detectable | Rustc Detectable | Lint Group | Default level |
| -------------------------------------------------------------------------------------------------- | ------------- | ------------ | ---------- | ---------- |
| [missing_errors_doc](https://rust-lang.github.io/rust-clippy/master/index.html#missing_errors_doc) | yes           | no           | Style      | allow      |