# 🐧 Pelang — Penguin Language

**Pelang** is a small, friendly programming language with a compiler written in **Python**.
The goal is a clean, readable language that is easy to learn and a compiler codebase that is easy to understand and hack on.

> ⚠️ **Status:** Early development. The syntax and features below are planned and may change.

---

## ✨ Goals

- **Simple syntax**: readable, minimal punctuation, easy for beginners.
- **Educational compiler**: every stage (lexing, parsing, analysis, code generation) is clear and well documented.
- **Written in pure Python**: no heavy dependencies needed to get started.
- **Helpful errors**: clear error messages with line and column information.

## 🐧 A Taste of Pelang (planned syntax)

```pelang
# hello.pe
fn greet(name: str) -> str {
    return "Hello, " + name + "!"
}

let penguins = 3

if penguins > 0 {
    print(greet("Pelang"))
}

for i in 0..penguins {
    print("🐧 #" + str(i))
}
```

## 🏗️ Compiler Architecture

```
source (.pe)
    │
    ▼
┌──────────┐   ┌──────────┐   ┌────────────┐   ┌──────────────┐
│  Lexer   │──▶│  Parser  │──▶│  Semantic  │──▶│   Code Gen   │──▶ output
│ (tokens) │   │  (AST)   │   │  Analysis  │   │ (target TBD) │
└──────────┘   └──────────┘   └────────────┘   └──────────────┘
```

| Stage             | Responsibility                                          |
|-------------------|---------------------------------------------------------|
| Lexer             | Turns source text into a stream of tokens               |
| Parser            | Builds an Abstract Syntax Tree (AST) from tokens        |
| Semantic Analysis | Scope resolution, type checking, error reporting        |
| Code Generation   | Emits the target output (bytecode / Python / C / LLVM)  |

## 📁 Project Structure (planned)

```
pelang/
├── pelang/
│   ├── __init__.py
│   ├── __main__.py      # CLI entry point
│   ├── lexer.py         # Tokenizer
│   ├── tokens.py        # Token types
│   ├── parser.py        # Parser -> AST
│   ├── ast.py           # AST node definitions
│   ├── analyzer.py      # Semantic analysis / type checker
│   ├── codegen.py       # Code generator
│   └── errors.py        # Error types and reporting
├── examples/            # Example .pe programs
├── tests/               # Unit tests
├── pyproject.toml
└── README.md
```

## 🚀 Getting Started

### Requirements

- Python **3.10+**

### Installation

```bash
git clone <your-repo-url> pelang
cd pelang
python -m venv .venv
source .venv/bin/activate
pip install -e .
```

### Usage (planned)

```bash
# Compile and run a Pelang program
pelang run examples/hello.pe

# Compile only
pelang build examples/hello.pe -o hello

# Show tokens / AST for debugging
pelang tokens examples/hello.pe
pelang ast examples/hello.pe
```

### Running Tests

```bash
python -m pytest
```

## 🗺️ Roadmap

- [ ] Lexer: numbers, strings, identifiers, keywords, operators, comments
- [ ] Parser: expressions, statements, functions, control flow
- [ ] AST pretty-printer
- [ ] Semantic analysis: scopes and variable resolution
- [ ] Type checking: `int`, `float`, `str`, `bool`
- [ ] Code generation (first target TBD)
- [ ] CLI (`pelang run`, `pelang build`)
- [ ] Standard library basics (`print`, `len`, `input`)
- [ ] REPL
- [ ] Language specification document

## 🤝 Contributing

Contributions, ideas, and feedback are welcome! Feel free to open an issue or a pull request.

## 📄 License

TBD. Add a license (e.g. MIT) before the first release.
