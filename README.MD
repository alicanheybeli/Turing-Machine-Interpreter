# Turing Machine Interpreter

A Brainfuck interpreter written in C with basic optimizations.

## Optimizations

- **Run-length encoding** — consecutive identical instructions (`+`, `-`, `<`, `>`) are folded into a single instruction with a count value, reducing the instruction count significantly
- **Zero cell optimization** — `[-]` is replaced with a single zero instruction instead of looping
- **Pre-computed bracket jumps** — `[` and `]` jump targets are resolved once at load time, eliminating bracket scanning at runtime

## Usage

```
./interpreter <program.bf>
```

## Build

```
gcc main.c -o interpreter
```

## Current state

Functional. Interprets standard Brainfuck programs correctly with the optimizations above. No JIT compilation or further optimization passes.
