# Building Large Projects

## Overview
As a codebase grows, organizing files and automating the build process becomes essential. Tools like Make and CMake manage dependencies, compile options, and installation steps.

## Detailed Explanation
- **Makefiles**: Use rules describing how to build targets from source files. Dependencies ensure only changed files are recompiled.
- **CMake**: A cross-platform build system generator that produces Makefiles or project files for various IDEs. Its configuration language (`CMakeLists.txt`) describes the project structure.
- **Directory Layout**: Common practice separates source (`src/`), headers (`include/`), build scripts, and tests.
- **Production Code**: Organize modules logically and use version control (like Git) for collaboration.

## Code Examples
Simple Makefile:
```makefile
CC=gcc
CFLAGS=-Wall

app: main.o util.o
$(CC) $(CFLAGS) $^ -o $@

main.o: main.c util.h
$(CC) $(CFLAGS) -c main.c

util.o: util.c util.h
$(CC) $(CFLAGS) -c util.c
```
Run `make` to build the program.

CMake example (CMakeLists.txt):
```cmake
cmake_minimum_required(VERSION 3.5)
project(myapp C)
add_executable(myapp main.c util.c)
```

## Common Pitfalls & Warnings
1. **Hardcoding compiler paths** makes the build non-portable.
2. **Ignoring dependencies** can lead to stale object files when headers change.

## Best Practices
- Keep build scripts under version control and document how to build the project.
- Use out-of-source builds with CMake to keep build artifacts separate from source files.

## Mini Exercise
Set up a small project with a Makefile that builds two source files into one executable. Modify one file and rerun `make` to see that only the changed file is recompiled.
