# gcd_accelator
finding greatest common divisor of two positive number using subtraction based euclidean algorithm


## Overview

This project implements a hardware accelerator for computing the Greatest Common Divisor (GCD) of two numbers using subtraction based Euclidean algorithm. The design follows a datapath and control-path architecture, where the datapath performs arithmetic operations and the controller manages the sequence of operations through a finite state machine (FSM).

The accelerator repeatedly performs subtraction and comparison operations until the GCD is obtained, demonstrating the principles of hardware-software co-design and algorithm acceleration.

## Features

- GCD computation using the Euclidean algorithm
- Separate Datapath and Control Path implementation
- Finite State Machine (FSM) based controller
- Register-based operand storage which is PIPO registers
- Comparator and subtractor-based architecture

## Architecture

The GCD Accelerator consists of:

- Datapath
  - Operand Registers (PIPO's)
  - Comparator
  - Subtractor
  - Multiplexers

- Control Path
  - FSM Controller
  - Load Control Signals
  - Register Enable Signals
  - Done Signal Generation

The controller continuously monitors the datapath status and generates control signals until the GCD result is computed.

## Algorithm

1. Load operands A and B.
2. Compare A and B.
3. If A > B, compute A = A - B.
4. If B > A, compute B = B - A.
5. Repeat until A = B.
6. Output A (or B) as the GCD.

## Verification

The design was verified using a Verilog testbench in QuestaSim.

### Test Cases

- GCD(24,16) = 8
- GCD(48,18) = 6
- GCD(15,10) = 5
