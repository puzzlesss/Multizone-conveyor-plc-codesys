# Multizone Conveyor & Tank Level Industrial Automation System
**Built using CODESYS | Ladder Logic | Structured Text | PID Control | HMI**

---

## Project Overview
A fully simulated industrial automation system designed and programmed in CODESYS, replicating real-world manufacturing control challenges. The project consists of two integrated subsystems:

1. **Multizone Conveyor Control System** — a 3-zone conveyor with state machine logic, fault handling, and zone coordination
2. **PID Tank Level Control System** — automated fill/drain control with real-time setpoint tracking and HMI monitoring

---

## System 1 — Multizone Conveyor Control

### How It Works
- 3 independent conveyor zones (Z1, Z2, Z3) controlled via PLC
- Each zone has a dedicated motor command and feedback signal
- State machine manages zone transitions: IDLE → RUNNING → FAULT → RESET
- Emergency stop (E-Stop) halts all zones instantly and safely

### Key Features
- Start/Stop/Reset/E-Stop push button logic
- Run permissive interlocking — zone only starts if system is safe
- Motor feedback monitoring — detects start failures and raises faults
- Fault code system (SYS_FaultCode) for diagnostics
- 10+ simulated operating and fault scenarios validated

### PLC Tags (GVL_IO)
| Tag | Type | Description |
|-----|------|-------------|
| DI_StartPB | BOOL | Start push button |
| DI_StopPB | BOOL | Stop push button |
| DI_EStopOK | BOOL | E-Stop safety signal |
| DO_Z1_MotorCmd | BOOL | Zone 1 motor output |
| SYS_FaultActive | BOOL | System fault flag |
| SYS_FaultCode | UINT | Fault identification code |

---

## System 2 — PID Tank Level Control

### How It Works
- Level sensors (DI_LevelLow, DI_LevelHigh) feed into PLC
- PID controller maintains tank level at setpoint
- Fill valve (DO_FillValve) and drain valve (DO_DrainValve) actuated automatically
- HMI displays real-time level, valve states, and system status

### Key Features
- PID tuning for stable setpoint tracking
- Automatic switchover between fill and drain modes
- Real-time HMI monitoring of all process variables
- Manual override capability

---

## Technologies Used
- **Platform:** CODESYS Control Win V3 x64
- **Languages:** Ladder Logic (LD), Structured Text (ST), Function Block Diagram (FBD)
- **Control:** PID Control, State Machine Design
- **Interface:** HMI Development (CODESYS Visualization)
- **Architecture:** Modular PLC design with reusable Function Blocks

---

## Project Structure
├── PLC_PRG          # Main program — conveyor + tank logic
├── GVL_IO           # Global variable list — all I/O tags
├── FB_ZoneConveyor  # Function block — zone control logic
├── Task Configuration # IEC task setup
└── HMI Visualization  # Operator interface panels

---

## Screenshots

### Ladder Logic — Conveyor Control
![Ladder Logic](images/ladder_logic.png)

### Variable List — GVL_IO
![Variables](images/gvl_io.png)

---

## What I Learned
- Designing modular, scalable PLC architecture from scratch
- Implementing real-world fault handling and safety interlocks
- Tuning PID controllers for stable process control
- Building operator-friendly HMI interfaces
- Structuring industrial automation projects professionally

---

## Author
**Surya DV**
Clemson University | M.S. Electrical & Computer Engineering | Class of 2026
📧 suryadv8@gmail.com
🔗 linkedin.com/in/suryadv25
