# Huffman Encoding in C

A C implementation of **Huffman coding**, a classic algorithm for lossless data compression.
It gives shorter binary codes to characters that appear often and longer codes to rare ones, so the same text takes fewer bits to store.

This was a course project for the C programming class of my AI & Cybersecurity program at ITS Academy Olivetti (Bologna, Italy).

## What the program does

You type a text (at least 80 characters, with at least 8 different characters), and the program goes through four steps:

1. **Frequency analysis**: counts how many times each character appears.
2. **Huffman tree and codes**: builds the Huffman tree and prints the binary code for each character.
3. **Compression**: encodes the whole text as a string of bits.
4. **Decompression and check**: decodes the bits back to text and checks that it matches the original.

Example: a 106-character sentence needs 848 bits in plain 8-bit ASCII. With Huffman coding it needs **430 bits, about 49% less**, and the decoded text is identical to the original.

## How it works

- A **min-heap** (priority queue), written from scratch, keeps the characters sorted by frequency.
- The two least frequent nodes are merged again and again until a single **binary tree** is left.
- Going left in the tree adds a `0` to the code and going right adds a `1`, so each character gets a unique code.
- All memory is allocated dynamically and freed at the end of the program.

## Project structure

| File | Content |
|------|---------|
| `huffman.h` | Data structures (tree node, min-heap) and function declarations |
| `huffman.c` | Heap, tree building, code generation, encoding and decoding |
| `main.c` | Input checks and the four steps above |
| `Makefile` | Build instructions |

## Build and run

You need `gcc` and `make`.

```bash
make
./prog        # on Windows: prog.exe
```

The program output is in Italian.

## Skills used

C programming · pointers and dynamic memory management · data structures (binary trees, heaps) · recursion · modular code with header files and a Makefile
