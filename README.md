<div align="center">

# 🕷️ **SPIDER Language (SP)**  
### *The Better Way to Hack.*

<img src="https://dummyimage.com/800x200/000/fff&text=SPIDER+LANGUAGE" width="100%">

**Lightweight. Fast. Security-Focused. Built for Red Teaming.**

![Stars](https://img.shields.io/github/stars/your/repo?style=for-the-badge&color=black)
![Issues](https://img.shields.io/github/issues/your/repo?style=for-the-badge&color=white)
![License](https://img.shields.io/badge/license-MIT-black?style=for-the-badge)

**Discord:** https://discord.gg/yourserver

</div>

---

# 🧩 What is SPIDER?

**SPIDER (SP)** is a **security-oriented programming language** written in **Rust** with a **C backend compiler**.

It was designed specifically for:

- Red teaming  
- Penetration testing  
- Embedded scripting  
- Rapid exploit prototyping  
- Automation  
- Network tooling  

SPIDER includes **100+ built-in security functions**, supports **interpreted or compiled execution**, and features an extremely flexible syntax inspired by **Rust, C, and custom DSL design**.

---

# ✨ Features

### 🔹 **Full Toolchain Included**
- **Lexer** (`lexer.rs`) – Tokenizes advanced SP syntax  
- **Parser** (`parser.rs`) – Builds a rich AST with support for structs, enums, lambdas, pattern matching, loops, etc.  
- **Interpreter** (`interpreter.rs`) – Executes SP code dynamically  
- **Native Compiler** (`compiler.rs`) – Converts AST → C → compiled executable via gcc/clang  
- **CLI Runtime** (`main.rs`) – The `sp` command (run, compile, check, terminal)

---

# 🛠️ Built-In Security & Networking Keywords

From the lexer:

- `scan`
- `exploit`
- `payload`
- `socket`
- `thread`
- `process`
- `memory`
- `inject`
- `hook`
- `packet`
- `encrypt`
- `decrypt`
- `hash`
- `shell`
- `spawn`

SPIDER is **natively aware** of offensive-security workflows.

---

# 📦 File Extension

SPIDER programs use:

```
.spdi
```

---

# 🚀 Terminal Usage

```
sp terminal
```

SPIDER has a custom interactive REPL with:

- ASCII art banner  
- Root mode flag (`--r`)  
- Colored output  
- All SPIDER commands accessible directly  

---

# 🔧 CLI Commands

```
sp run <file.spdi> [-d]
sp compile <file.spdi>
sp check <file.spdi>
sp terminal [--r]
```

### Modes:
- `run` → interpret  
- `compile` → generate native C binary  
- `check` → syntax analysis only  
- `terminal` → interactive shell  

---

# 🧠 Syntax Examples

### Variables
```spider
let x = 10;
mut y = 20;
```

### Functions
```spider
func add(a: int, b: int) -> int {
    return a + b;
}
```

### Structs
```spider
struct User {
    name: str,
    age: int
}

let u = User {
    name: "kcdev",
    age: 17
};
```

### Arrays & Maps
```spider
let arr = [1, 2, 3];
let m = { "ip": "127.0.0.1", "port": 8080 };
```

### Networking example
```spider
let body = https_get("https://example.com");
print(body);
```

### Try/Catch
```spider
try {
    risky();
} catch err {
    print("Error: " + err);
}
```

### Lambdas
```spider
let f = (x) => x * 2;
```

---

# ⚙️ Compilation Pipeline

SPIDER uses a **multi-stage build**:

1. Lexer → tokens  
2. Parser → AST  
3. AST → generated C source (`program.c`)  
4. gcc/clang → native binary (`program.exe` or `program`)  
5. Temporary C file auto-removed  

Snippet from compiler backend showing C type mapping:  
*(From compiler.rs)*  
```
int → int64_t
uint → uint64_t
float → double
bool → bool
str → char*
ptr → void*
```

---

# 📚 Interpreter Features

The interpreter supports:

- Struct/object field access  
- Function calls + method calls  
- Arrays & maps  
- Binary/unary ops  
- Ternary expressions  
- Pattern-matching  
- Looping: `for`, `while`, `loop`, `do while`  
- `break` / `continue`  
- try/catch  
- Built-in filesystem & HTTP utilities (`https_get`, `https_post`, `write_file`, `list_dir`, etc.)  

---

# 🧵 Example Program

```spider
func hello(name: str) -> void {
    print("Hello, " + name);
}

hello("World");
```

---

# 🔨 Build SPIDER From Source

```
git clone https://github.com/your/repo
cd spider
cargo build --release
```

Run SPIDER:

```
./target/release/sp terminal
```

---

# ⭐ Contributing

PRs are welcome!  
SPIDER is actively evolving toward **v3.1** with more security tooling and speedups.

---

# 📜 License

MIT License  
Free for personal and commercial use.

---

<div align="center">
  
### 🕷️ **SPIDER — The Better Way to Hack.**

</div>
