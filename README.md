<div align="center">

# SPIDER Language (SP)  
### The Better Way to Hack

<img src="https://dummyimage.com/800x200/000/fff&text=SPIDER+LANGUAGE" width="100%">

![Stars](https://img.shields.io/github/stars/kernelcore-dev/SPIDER?style=for-the-badge&color=black)
![Issues](https://img.shields.io/github/issues/kernelcore-dev/SPIDER?style=for-the-badge&color=white)
![License](https://img.shields.io/badge/license-MIT-black?style=for-the-badge)

**Repository:**  
https://github.com/kernelcore-dev/SPIDER  

**Linux Runtime:**  
https://github.com/kernelcore-dev/SPIDER/blob/main/sp  

**Windows Runtime:**  
https://github.com/kernelcore-dev/SPIDER/blob/main/sp.exe  

</div>

---

# Overview

SPIDER (SP) is a security-focused programming language designed for red teaming, exploit development, penetration testing, and fast automation tasks.  
It is written in Rust and compiles to C before generating a native executable.

SPIDER includes:

- A complete lexer, parser, interpreter, and compiler
- A custom interactive terminal
- Over 100 security-related built-in functions
- A red-team–oriented syntax and keyword set

SPIDER programs use the `.spdi` extension.

---

# Features

### Full Toolchain
- **lexer.rs** — Tokenizes SPIDER source code  
- **parser.rs** — Produces a structured AST  
- **interpreter.rs** — Executes SPIDER programs dynamically  
- **compiler.rs** — Converts AST → C → native machine code  
- **main.rs** — Provides the CLI and terminal environment  

### Security-Oriented Keywords
SPIDER includes specialized keywords for offensive tooling:

`scan`, `exploit`, `payload`, `socket`, `thread`, `process`, `memory`,  
`inject`, `hook`, `packet`, `encrypt`, `decrypt`, `hash`, `shell`, `spawn`

### Language Capabilities
- Variables, functions, structs, enums, type aliases  
- Pattern matching, lambda expressions, ternary expressions  
- Arrays, maps, struct literals  
- File I/O, HTTP/HTTPS utilities, directory operations  
- Error handling via `try` / `catch`  
- While loops, for loops, ranges, infinite loops  

---

# Runtime Binaries

### Linux (tested)
`sp` — ELF binary  
Runs on most x86_64 Linux systems.  
macOS **is not guaranteed** to work via the Linux binary and may require manual build.

### Windows
`sp.exe` — Native Windows PE executable  

### From Source
You may also build SPIDER manually using Rust and Cargo (see below).

---

# CLI Usage

SPIDER provides a command-line runtime with several modes:

```
sp terminal [--r]       Start interactive terminal (--r enables root mode)
sp run <file.spdi> [-d] Execute a SPIDER script (optional debug output)
sp compile <file.spdi>  Compile to a native executable
sp check <file.spdi>    Syntax check without execution
```

---

# Getting Started

### Build From Source

```
git clone https://github.com/kernelcore-dev/SPIDER
cd SPIDER
cargo build --release
```

Resulting binary will be located in:

```
target/release/sp
```

---

# Syntax Examples

### Variables
```spider
let a = 10;
mut b = 20;
```

### Functions
```spider
func add(x: int, y: int) -> int {
    return x + y;
}
```

### Structs
```spider
struct User {
    name: str,
    age: int
}

let u = User {
    name: "kernel",
    age: 17
};
```

### Maps and Arrays
```spider
let arr = [1, 2, 3];
let config = { "mode": "test", "level": 5 };
```

### Networking
```spider
let body = https_get("https://example.com");
print(body);
```

### Error Handling
```spider
try {
    risky();
} catch e {
    print("Error: " + e);
}
```

### Lambdas
```spider
let f = (x) => x * 3;
```

---

# Compilation Pipeline

SPIDER uses a multi-stage compilation flow:

1. Source → tokens (lexer)  
2. Tokens → AST (parser)  
3. AST → generated C code  
4. C → native executable via gcc/clang  
5. Temporary `.c` file is removed  

Internal C type mapping includes:

```
int   -> int64_t
uint  -> uint64_t
float -> double
bool  -> bool
str   -> char*
ptr   -> void*
```

---

# Interpreter Capabilities

The interpreter supports:

- Structs, maps, arrays  
- Field/method access  
- Binary and unary operations  
- Ternary operators  
- Pattern matching  
- Loops with break/continue  
- `for` loops over ranges and arrays  
- Built-in filesystem functions  
- HTTP/HTTPS GET and POST  
- JSON handling  

---

# Example Program

```spider
func greet(name: str) -> void {
    print("Hello, " + name);
}

greet("World");
```

---

# Contributing

Contributions are welcome.  
SPIDER is under active development and expanding toward future versions with improved performance, additional security functions, and enhanced syntax.

---

# License

MIT License  
Free for both personal and commercial use.

---

<div align="center">
SPIDER Language — The Better Way to Hack
</div>
