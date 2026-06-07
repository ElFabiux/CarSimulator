# CarSimulator

Digital logic simulation of a vehicle transmission and dashboard instrumentation system built with LogicCircuit. The project models how user inputs such as power, gear selection, acceleration, braking, and Shiftronic controls affect vehicle state, speed, RPM, and visual dashboard outputs.

## Overview

CarSimulator is an educational digital architecture project focused on simulating basic vehicle behavior using logic circuits instead of traditional programming code.

The system represents a simplified car control model where the user can turn the vehicle on, select a transmission mode, accelerate, brake, and observe changes in the current gear, tachometer, and speedometer.

The complete simulation is contained in a single LogicCircuit project file and is organized through a hierarchy of reusable digital components, including logic gates, flip-flops, registers, adders, multiplexing logic, BCD decoding, LED matrices, and 7-segment displays.

## Key Features

* Vehicle transmission simulation using digital logic
* Finite State Machine for gear selection
* Gear states: Park, Reverse, Neutral, Drive, and Sport
* Shiftronic-style manual shifting with `+` and `-` controls
* Safety logic to prevent invalid gear transitions
* Accelerator and brake input controls
* Speed and RPM state tracking
* 4-bit adder/subtractor logic for arithmetic operations
* Registers for storing simulation state
* Gear output through a 7-segment display
* Tachometer visualization using LED matrix output
* Speedometer visualization using LED matrix output
* Global power control for enabling/disabling the system
* Modular hierarchical circuit design

## Tech Stack

* LogicCircuit
* Digital Logic
* Finite State Machine
* Flip-Flops
* Registers
* Adders
* Counters
* BCD Decoder
* LED Matrix
* 7-Segment Displays
* XML Circuit Project

## Architecture

The project follows a hierarchical circuit architecture. The top-level circuit integrates user controls, transmission logic, arithmetic units, registers, and dashboard displays.

### Main Circuit

The `Main` circuit works as the entry point of the simulation. It connects the visible user controls with the internal logic modules and dashboard outputs.

It includes buttons for power, gear selection, Shiftronic shifting, acceleration, and braking. It also hosts the visual outputs for the current gear, tachometer, and speedometer.

### Transmission Control

The transmission logic is implemented as a Finite State Machine. It manages the current gear state and supports both direct gear selection and sequential manual shifting.

Supported states include:

* **P:** Park
* **R:** Reverse
* **N:** Neutral
* **D:** Drive
* **S:** Sport

A dedicated gear limit circuit prevents the system from shifting beyond the valid gear range when using the `+` and `-` controls.

### Arithmetic Logic

The simulator uses adder/subtractor logic to calculate changes in speed and RPM based on accelerator and brake inputs.

Acceleration increases the stored values, while braking decreases them. These values are stored in registers and then sent to the dashboard display system.

### Memory and State

Registers and flip-flops are used to preserve the current simulation state across clock cycles. This allows the simulator to keep track of values such as selected gear, speed, and RPM while the system is running.

### Display System

The dashboard output is represented using digital displays:

* **7-Segment Display:** Shows the current transmission gear.
* **Tacometer LED Matrix:** Displays the RPM level.
* **Speedometer LED Matrix:** Displays the current speed level.

The display system converts internal binary values into visual output that can be interpreted by the user during the simulation.

## User Controls

The simulation includes the following controls:

* **E:** Power on/off
* **P:** Park
* **R:** Reverse
* **N:** Neutral
* **D:** Drive
* **S:** Sport
* **+:** Shift up using Shiftronic mode
* **-:** Shift down using Shiftronic mode
* **Acelerador:** Increase speed and RPM
* **Freno:** Decrease speed and RPM

## Getting Started

### Requirements

* LogicCircuit software
* `CarSimulator.CircuitProject` file

### Running the Simulation

1. Open LogicCircuit.
2. Load the `CarSimulator.CircuitProject` file.
3. Open the `Main` circuit.
4. Turn on the simulator using the `E` button.
5. Select a gear using one of the transmission buttons.
6. Use the accelerator and brake controls to change the vehicle state.
7. Observe the current gear, tachometer, and speedometer outputs.

## Project Purpose

This project was created to practice digital logic design by modeling a simplified vehicle control system.

It demonstrates understanding of finite state machines, sequential logic, combinational logic, arithmetic circuits, register-based memory, control signals, digital displays, and modular circuit architecture.

CarSimulator highlights how real-world system behavior can be represented using hardware-style logic components.
