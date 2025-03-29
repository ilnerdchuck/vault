---
id: 1742049341-dlx-assembly-cheat-sheet
aliases:
  - DLX Assembly Cheat Sheet
tags: []
title: DLX Assembly Cheat Sheet
---
# Instruction Set Overview

## Data Transfers

| Instruction | Description |
|-------------|-------------|
| LB, LBU, SB | Load byte, load byte unsigned, store byte |
| LH, LHU, SH | Load halfword, load halfword unsigned, store halfword |
| LW, SW      | Load word, store word (to/from integer registers) |
| LF, LD, SF, SD | Load SP float, load DP float, store SP float, store DP float (SP - single precision, DP - double precision) |
| MOV12S, MOVS2I | Move from/to GPR to/from a special register |
| MOVF, MOVD  | Copy one floating-point register or a DP pair to another register or pair |
| MOVFP2I, MOV12FP | Move 32 bits from/to FP register to/from integer registers |

## Arithmetic / Logical

| Instruction | Description |
|-------------|-------------|
| ADD, ADDI, ADDU, ADDUI | Add, add immediate (all immediates are 16-bits); signed and unsigned |
| SUB, SUBI, SUBU, SUBUI | Subtract, subtract immediate; signed and unsigned |
| MULT, MULTU, DIV, DIVU | Multiply and divide, signed and unsigned; operands must be floating-point registers; all operations take and yield 32-bit values |
| AND, ANDI   | And, and immediate |
| OR, ORI, XOP, XOPI | Or, or immediate, exclusive or, exclusive or immediate |
| LHI         | Load high immediate - loads upper half of register with immediate |
| SLL, SRL, SRA, SLLI, SRLI, SRAI | Shifts: both immediate(S_1) and variable form(S_2); shifts are shift left logical, right logical, right arithmetic |
| S_1, S_2    | Set conditional: "_" may be LT, GT, LE, GE, EQ, NE |

## Control

| Instruction | Description |
|-------------|-------------|
| BEQZ, BNEZ  | Branch GPR equal/not equal to zero; 16-bit offset from PC |
| BFPT, BFPF  | Test comparison bit in the FP status register and branch; 16-bit offset from PC |
| J, JR       | Jumps: 26-bit offset from PC(J) or target in register(JR) |
| JAL, JALR   | Jump and link: save PC+4 to R31, target is PC-relative(JAL) at a register(JALR) |
| TRAP        | Transfer to operating system at a vectored address |
| RFE         | Return to user code from an exception; restore user code |

## Floating Point

| Instruction | Description |
|-------------|-------------|
| ADDD, ADDF  | Add DP, SP numbers |
| SUBD, SUBF  | Subtract DP, SP numbers |
| MULTD, MULTF | Multiply DP, SP floating point |
| DIVD, DIVF  | Divide DP, SP floating point |
| CVTP2D, CVTP2I, CVTD2F, CVTD2I, CVTI2F, CVTI2D | Convert instructions: CVTx2y converts from type x to type y, where x and y are one of I(Integer), D(Double precision), or F(Single precision). Both operands are in the FP registers. |
| _D, _F      | DP and SP compares: "_" may be LT, GT, LE, GE, EQ, NE; set comparison bit in FP status register. |


