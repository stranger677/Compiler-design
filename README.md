
# EasyC: A User-Centric C Compiler with Custom Syntax

![Compiler Design](https://img.shields.io/badge/Subject-Compiler_Design-blue) 
![C Language](https://img.shields.io/badge/Language-C-yellowgreen)

A custom C compiler that replaces traditional syntax with intuitive keywords to make C programming more accessible for beginners.

## Features

- Converts beginner-friendly syntax to standard C code
- Supports custom keywords like:
  - `wholeNum` → `int`
  - `when` → `if` 
  - `display` → `printf`
- Full compilation pipeline:
  - Lexical analysis (Flex)
  - Syntax parsing (Bison)
  - Semantic analysis
  - Code generation

## Installation

### Prerequisites
- Flex 2.6+
- Bison 3.7+
- GCC compiler

### Build Instructions
```bash
# Generate lexer and parser
flex calc.l
bison -d calc.y

# Compile the compiler
gcc lex.yy.c calc.tab.c -o easyc

# Run the compiler
./easyc < input.easyc
```

## Usage

1. Write code in EasyC syntax (example: `input.easyc`):
```c
wholeNum main() {
    wholeNum x = 5;
    when (x > 3) {
        display("Hello World!\n");
    }
    sendBack 0;
}
```

2. Compile to standard C:
```bash
./easyc < input.easyc > output.c
```

3. Compile the generated C code:
```bash
gcc output.c -o program
./program
```

## Keyword Mapping

| EasyC | Standard C |
|-------|------------|
| `wholeNum` | `int` |
| `when` | `if` |
| `keepGoing` | `while` |
| `display` | `printf` |
| `sendBack` | `return` |

## Project Structure

```
easyc-compiler/
├── src/
│   ├── lexer.l       # Flex lexer rules
│   ├── parser.y      # Bison grammar rules
│   └── main.c        # Driver code
├── samples/          # Example EasyC programs
├── Makefile          # Build automation
└── README.md
```

## Contributors


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

The markdown formatting will automatically render nicely on GitHub. Let me know if you'd like to add any additional sections!
