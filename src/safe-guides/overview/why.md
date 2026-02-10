# 1.1 Why We Need Rust Coding Guidelines

## Foreword

When first learning Rust, I was amazed by the advanced nature of its tooling. Tools like `rustfmt` automatically format code, and `clippy` helps standardize unidiomatic patterns. They are truly excellent tools. At the time, I believed Rust had no need for formal coding guidelines like other languages.


However, as I delved deeper into Rust, I discovered many shortcomings in these tools; their coverage is not comprehensive. For instance, improper configuration or use of `rustfmt` can lead to code errors, and it cannot recognize the semantics of various names in Rust code. `clippy` suffers from false positives or irrational lints, and it fails to cover areas like Unsafe Rust. If developers—especially beginners—depend on these tools as a "black box" without understanding the reasoning behind the lints, they will struggle to improve development efficiency when high code quality is required.

Therefore, `rustfmt` and `clippy` are not panaceas. We still need a comprehensive and universal coding specification that encompasses these tools. By providing standardized principles and rules, we can help Rust teams understand the fundamental framework for writing idiomatic code, enabling rapid adoption and strengthening collaboration and trust between teams.

## Limitations of Rustfmt and Clippy

### Limitations of Rustfmt

While `rustfmt` boosts productivity by eliminating manual formatting, it cannot replace a coding specification for defining Rust's overall coding style.

Its primary deficiencies include:

1. **Semantic Blindness:** Rust is a language that emphasizes semantics. Naming variables, types, and functions requires careful semantic consideration, especially regarding ownership. `rustfmt` cannot judge naming semantics. While `clippy` addresses some of this, its coverage remains fragmentary for developers.
2. **Configuration Risks:** Improper use or configuration can lead to issues. Since `rustfmt` modifies code without compiling it, features like "format on save" or incorrect settings can result in corrupted or erroneous code modifications.
3. **Fragmented Settings:** Most developers do not understand the implications of every scattered configuration option.
4. **Documentation Gaps:** `rustfmt` does not cover standards for code comments and documentation.

To address these, a universal specification is needed to provide a holistic view of naming, formatting, and comments. This specification organizes `rustfmt` rules into logical categories to help teams establish their own styles rather than just mechanically extracting tool settings.

### Limitations of Clippy

As the primary linter in the Rust ecosystem, `clippy` provides essential static checks and explains how to fix issues. However, it is not a substitute for coding guidelines due to several flaws:

1. **Unsafe Rust Gaps:** `clippy` lacks many lint checks for Unsafe Rust. Since Unsafe Rust is a critical component, a dedicated specification is required to help developers write safe "unsafe" code.
2. **Information Overload:** With over 500 lints (and growing), it is impossible for developers to learn them all individually. A specification helps categorize and organize these lints.
3. **Controversial Recommendations:** The grading of lints (allow/warning/deny) is often debated. Some "allow" lints may be problematic in specific contexts, while some "warning" lints may be perfectly reasonable. This inconsistency led to projects like [noisy-clippy](https://github.com/dtolnay/noisy-clippy) to analyze how many recommendations fail to fit real-world scenarios.

## The Role of Coding Guidelines

The Rust Coding Guidelines serve the following purposes:

1. **Quality Improvement:** Adhering to Rust's language features to enhance readability, maintainability, robustness, and portability.
2. **Safety in Unsafe Rust:** Standardizing the writing of Unsafe Rust to improve security.
3. **Efficiency:** Providing systematic, easy-to-apply, and easy-to-check clauses to help developers work faster.
4. **Proactive Development:** Giving developers a global vision so they follow good practices *during* development, rather than fixing warnings line-by-line after the fact.
5. **Knowledge Gap Coverage:** While not a textbook, the specification covers areas where knowledge gaps might lead to program errors, ensuring quality across teams with varying skill levels.

---