# 1.2 Basic Conventions of the Coding Specification

## Content Organization of the Coding Specification

**The programming specification is by no means written to increase the burden on developers; its purpose is to help developers write high-quality Rust code.**

To achieve this goal, the specification clauses are divided into two categories: **Principles** and **Guidelines**.

* **Principles** serve as broad directions for guidance during programming or refer to general categories of situations. A small number of principles cover cases detectable by the Rust compiler, included because compiler diagnostic messages can sometimes be confusing; these principles help developers avoid such scenarios.
* **Guidelines** are more specific than principles and include positive and negative examples for further clarification. Some guidelines also specify exceptions. Most guidelines can be detected via lints.

#### Relationship Between Guidelines, rustfmt, and Clippy

The specification is primarily divided into two parts: **Code Style** and **Programming Practices**.

**Code Style**

This section covers naming, formatting, and comments:

* **Naming:** Primarily checked via Clippy lints. For naming rules not provided by Clippy, custom lints are required.
* **Formatting:** Automatically handled by `rustfmt`. The specification categorizes most `rustfmt` configuration items to help developers create their own configurations. A configuration template is also provided.
* **Comments:** Includes regular and documentation comments. These are regulated through a combination of `rustfmt` and Clippy.

**Programming Practices**

The content of programming practices is categorized by Rust language features. Each feature summarizes daily best practices into specific principles and guidelines. While most rules are recommendations, those marked as requirements are generally related to safety.

Most guidelines in this section rely on Clippy lints for detection. However, it does not map all 500+ Clippy lints one-to-one; "trick-based" lints are excluded.

**Guidelines prioritize readability, maintainability, safety, and performance in general scenarios, covering less than 1/5 of all Clippy lints.** Some guidelines missing from Clippy require custom lints.

The focus of the programming practices section is on **Unsafe Rust**, where principles outweigh guidelines and Clippy lints are less effective. This section contains more mandatory rules to help developers avoid common pitfalls.

---

## Content Conventions

Clauses are identified by the prefix in their heading:

* **P** identifies a **Principle**. Format: `P.Element.Number`.
* **G** identifies a **Guideline**. Format: `G.Element.Number`.
* When sub-directories exist, the format is `P.Element.SubElement.Number` or `G.Element.SubElement.Number`.

Numbers start from `01` and increment. `Element` is a three-letter English abbreviation for the key element of the domain (corresponding to the second-level directory). (Terminology reference: [SEI CERT C Coding Standard](https://wiki.sei.cmu.edu/confluence/display/c/SEI+CERT+C+Coding+Standard))

| Element | Explanation | Element | Explanation |
| --- | --- | --- | --- |
| **NAM** | Naming | **CMT** | Comment |
| **FMT** | Format | **TYP** | Data Type |
| **CNS** | Const | **VAR** | Variables |
| **EXP** | Expression | **CTF** | Control Flow |
| **REF** | Reference | **PTR** | Pointer |
| **STR** | String | **INT** | Integer |
| **MOD** | Module | **CAR** | Cargo |
| **MEM** | Memory | **FUD** | Function Design |
| **MAC** | Macro | **STV** | Static Variables |
| **GEN** | Generic | **TRA** | Trait |
| **ASY** | Async | **UNS** | Unsafe Rust |
| **SAS** | Safety Abstraction | **FFI** | Foreign Function Interface |
| **LAY** | Memory Layout | **ERR** | Error Handling |
| **CLT** | Collection | **MTH** | Multi-threading |
| **EMB** | Embedded Rust | **FIO** | Input/Output |
| **SEC** | Security | **SPT** | Smart Pointer |
| **UNT** | Unit Type | **BOL** | Bool |
| **CHR** | Char | **FLT** | Float |
| **SLC** | Slice | **TUP** | Tuple |
| **ARR** | Array | **VEC** | Vector |
| **SCT** | Struct | **ENM** | Enum |
| **UNI** | Union | **BLN** | Built-in (Standard Library) |
| **OBJ** | Trait Object | **LFT** | Lifetime |
| **BOX** | `Box<T>` type | **DRP** | Drop (Destructor) |
| **DCL** | Declarative Macro | **PRO** | Procedural Macro |
| **LCK** | Lock Synchronization | **LKF** | Lock-Free |
| **CGN** | Code Generation | **OTH** | Others |

---

## Open Source License for Referenced Code

All external code referenced in this specification complies with the **MIT/Apache/Mozilla** public licenses.

## Special Thanks

This guide refers to the *Huawei C Programming Guide V 1.0*. Special thanks to the **Huawei Open Source Capability Center** for their assistance with the programming guide specification!

---

**Would you like me to translate a specific guideline, such as one from the Unsafe (UNS) or Security (SEC) sections?**