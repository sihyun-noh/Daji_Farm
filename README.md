
# Structured C Coding Test — Math Problems

This project demonstrates a **structured C style** with **modular problem units** and a **problem registry** for easy extensibility.

## Features
- Each problem lives in its own module (`src/problems/*.c`) and exposes a `Problem` struct.
- A central registry (`src/problems/registry.c`) collects available problems.
- `main` shows a menu to run a **single problem** or **run all** (in sequence).
- Utilities (`src/utils.c`) provide reusable math helpers.

## Build
```bash
make
```
Binary will be at `bin/c_math_problems`.

## Run
```bash
./bin/c_math_problems
```
Follow the on-screen menu and prompts.

## Add a New Problem
1. Create `src/problems/<your_problem>.c` implementing a `Problem` instance:
   ```c
   #include "problem.h"
   static int run_your_problem(void) { /* ... */ return 0; }
   Problem PROBLEM_YOUR_PROBLEM = { .name = "Your Problem", .run = run_your_problem };
   ```
2. Add it to the registry array in `src/problems/registry.c`.
3. Rebuild with `make`.

## Implemented Problems
1. Prime check
2. GCD & LCM
3. Fibonacci (iterative)
4. Sum of multiples (3 or 5 up to N)
5. Palindrome check (unsigned long long)
6. Combinations nCr (64-bit multiplicative; small n recommended)

> Note: The nCr implementation uses a 64-bit multiplicative method with reduction to reduce overflow risk, but very large n may still overflow `unsigned long long`.
