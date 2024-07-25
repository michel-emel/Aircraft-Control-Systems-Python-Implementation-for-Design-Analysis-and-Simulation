# Longitudinal Aircraft Control System

## Overview

This repository contains a Python notebook that models and analyzes the longitudinal control dynamics of an aircraft. The primary focus is on the system's response to various control inputs and fault conditions, and its availability, redundancy, and reachability. The notebook includes:

- Simulation of longitudinal aircraft dynamics
- Analysis of system controllability
- Fault tolerance and system availability studies
- Redundancy analysis
- Reachability analysis

## Contents

1. **[Model Definition](#model-definition)**
2. **[Parameters](#parameters)**
3. **[State Variables](#state-variables)**
4. **[Simulation and Results](#simulation-and-results)**
5. **[Fault Tolerance Analysis](#fault-tolerance-analysis)**
6. **[System Availability Analysis](#system-availability-analysis)**
7. **[Redundancy Analysis](#redundancy-analysis)**
8. **[Reachability Analysis](#reachability-analysis)**
9. **[Installation and Usage](#installation-and-usage)**
10. **[License](#license)**
11. **[Contributing](#contributing)**
12. **[Acknowledgements](#acknowledgements)**

## Model Definition

The `LongitudinalModel` class represents the longitudinal dynamics of an aircraft. It includes:

- **Aerodynamic forces and moments**: Drag, lift, and pitching moment.
- **Elevator effectiveness and thrust force**.
- **Linearized longitudinal model equations**.

### Key Constants and Parameters

- **g**: Acceleration due to gravity (9.81 m/s²)
- **m**: Aircraft mass (5000 kg)
- **I_yy**: Moment of inertia around the y-axis (1000 kg·m²)
- **bar_c**: Mean aerodynamic chord (5.0 m)
- **Aerodynamic Coefficients**:
  - **C_D0**: Drag coefficient at zero angle of attack (0.02)
  - **C_D_alpha**: Drag coefficient slope with angle of attack (0.2)
  - **C_D_q**: Drag coefficient slope with pitch rate (0.01)
  - **C_L0**: Lift coefficient at zero angle of attack (0.1)
  - **C_L_alpha**: Lift coefficient slope with angle of attack (0.1)
  - **C_L_q**: Lift coefficient slope with pitch rate (0.02)
  - **C_M0**: Pitching moment coefficient at zero angle of attack (0.05)
  - **C_M_alpha**: Pitching moment coefficient slope with angle of attack (-0.1)
  - **C_M_q**: Pitching moment coefficient slope with pitch rate (-0.02)
  - **C_Q_delta_e**: Elevator effectiveness coefficient (0.02)

## Parameters

The simulation parameters used are:

- **Initial State Variables**: 
  - `delta_u`: Forward velocity
  - `delta_theta`: Pitch angle
  - `delta_q`: Pitch rate
  - `delta_alpha`: Angle of attack

- **Fault Magnitude**: Represents the intensity of the fault introduced.

## State Variables

The following state variables are monitored during the simulation:

- **delta_u**: Forward velocity (m/s)
- **delta_theta**: Pitch angle (radians)
- **delta_q**: Pitch rate (radians/second)
- **delta_alpha**: Angle of attack (radians)

## Simulation and Results

Simulations are performed to observe the longitudinal dynamics of the aircraft. The state variables include forward velocity (`delta_u`), pitch angle (`delta_theta`), pitch rate (`delta_q`), and angle of attack (`delta_alpha`).

### Results

- **State Variables Over Time**: Plots of `delta_u`, `delta_theta`, `delta_q`, and `delta_alpha`.
- **3D Plots**: Variations of `delta_u` with respect to `delta_theta`, `delta_q`, and `delta_alpha`.

## Fault Tolerance Analysis

Fault tolerance is analyzed by introducing faults in the elevator and lift coefficient. The analysis compares the system's response under normal conditions with faulty conditions.

### Fault Analysis

- **Elevator Fault**: Faults in the elevator are introduced and compared.
- **Lift Coefficient Fault**: A fault is introduced by altering the lift coefficient.

## System Availability Analysis

The availability of the system is calculated based on the number of simulations where failures occur due to parameter exceedance. The simulation checks for failures under normal and fault conditions.

### Availability Calculation

- **Threshold**: Parameters exceeding this threshold are considered failures.
- **Simulation Results**: Availability percentage is reported based on the number of failures.

## Redundancy Analysis

The effect of introducing redundancy in the system is analyzed. Redundancy is added by running multiple simulations and combining their results to evaluate the system's reliability.

### Redundancy Calculation

- **Redundancy Factor**: The factor by which redundancy is introduced.
- **Redundancy Ratio**: Percentage of improved reliability with redundancy.

## Reachability Analysis

The reachability of a desired state from an initial state within a given time horizon is tested. The system's matrices and control inputs are used to determine if the desired state can be achieved.

### Reachability Test

- **System Matrices**: State transition matrix and input matrix.
- **Desired State**: Target state to be achieved.
- **Time Horizon**: Time within which the desired state should be reachable.

## Installation and Usage

To run the notebook, ensure you have the following Python libraries installed:

- `numpy`
- `scipy`
- `matplotlib`

## Contact

If you have any questions or feedback, feel free to reach out to me at:
- Email: lechiffremel@gmail.com
- GitHub: [michel-emel](https://github.com/michel-emel)
