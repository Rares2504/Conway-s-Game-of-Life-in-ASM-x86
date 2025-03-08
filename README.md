# README

## Project Overview

This repository contains three assembly source files written in x86 32-bit assembly language for the Computer Systems Architecture (ASC) Laboratory Assignment. Each file corresponds to a specific requirement (Cerinta) outlined in the assignment.

## Files Description

### 1. `141_Ungureanu_Rares_0.S`

- Implements **Cerinta 0x00**, which simulates Conway's Game of Life for a given number of iterations (`k`).
- The input consists of:
  - Matrix dimensions (`m` and `n`).
  - Number of live cells (`p`) and their positions.
  - Number of iterations (`k`).
- The output is the final state of the system after `k` evolutions, displayed as a matrix.
- The implementation reads input from `STDIN` and prints the final state to `STDOUT`.

### 2. `141_Ungureanu_Rares_1.S`

- Implements **Cerinta 0x01**, which extends the Game of Life simulation by introducing an encryption/decryption mechanism using the XOR operation.
- The input consists of:
  - Matrix dimensions (`m` and `n`).
  - Number of live cells (`p`) and their positions.
  - Number of iterations (`k`).
  - Operation mode (`o`): `0` for encryption, `1` for decryption.
  - Message (`m`): Either a plaintext string (for encryption) or a hexadecimal-encoded message (for decryption).
- The encryption key is generated from the final matrix state after `k` iterations.
- The message is XOR-ed with the key according to the specified operation mode.
- The result is displayed in hexadecimal format (for encryption) or plaintext (for decryption).

### 3. `141_Ungureanu_Rares_2.S`

- Implements **Cerinta 0x02**, which is a modified version of `Cerinta 0x00`.
- Instead of reading input from `STDIN`, it reads from a file named `in.txt`.
- Instead of printing the output to `STDOUT`, it writes the final matrix state to `out.txt`.
- Uses functions from C to handle file input and output.

## Environment Setup

- The code is written for **x86 32-bit assembly** and can be assembled and executed using **NASM** and **GCC**.
- To assemble and link:
  ```sh
  nasm -f elf32 filename.S -o filename.o
  gcc -m32 filename.o -o filename
  ```
- For `141_Ungureanu_Rares_2.S`, ensure `in.txt` exists before running the program.

## Usage

- Run the programs using the following command:
  ```sh
  ./filename < input.txt  # For 141_Ungureanu_Rares_0.S and 141_Ungureanu_Rares_1.S
  ./filename              # For 141_Ungureanu_Rares_2.S (reads from in.txt and writes to out.txt)
  ```

## Notes

- Ensure your system supports 32-bit binaries (may require `libc6-i386` on 64-bit Linux systems).
- Input validation is not included; ensure inputs follow the expected format.
- The XOR-based encryption is simple and does not provide strong security; it is mainly for educational purposes.

---

This README provides an overview of the project and its files. For more details, refer to the assignment description.

