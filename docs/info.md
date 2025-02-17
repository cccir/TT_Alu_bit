<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

Explain how your project works

Each clock cycles ALU performs one of the 8 possible operations and stores result in the 4-bit accumulator register.

## How to test

Explain how to use your project

accumulator [4 bit] = accumulator [4 bit] (operation) operand [4 bit]

  Supported operations:
  lda imm   ::  imm -> accumulator
  neg imm   ::  0x0F - imm -> accumulator
  shr       ::  accumulator / 2 -> accumulator
  sub imm   ::  accumulator - imm -> accumulator
  and imm   ::  accumulator & imm -> accumulator
  xor imm   ::  accumulator ^ imm -> accumulator
  or  imm   ::  accumulator | imm -> accumulator
  add imm   ::  accumulator + imm -> accumulator

  Matrix mapping of operation opcode to internal control signals
           muxA muxB muxC AtoX negX setC outC invC
  000 lda   -    -    1    0    0    -    0    -
  001 neg   -    -    1    0    1    -    0    -
  010 shr   -    -    1    1    0    -    0    -
  011 sub   1    1    0    0    1    1    1    1
  100 and   0    0    0    0    0    -    0    -
  101 xor   0    1    0    0    0    -    0    -
  110 or    1    0    0    0    0    -    0    -
  111 add   1    1    0    0    0    0    1    0

## External hardware

List external hardware used in your project (e.g. PMOD, LED display, etc), if any
