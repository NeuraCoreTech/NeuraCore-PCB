# FPGA Dev Board - Xilinx XC7Z020

Custom Zynq-7000 FPGA + ARM SoC development board based on the Xilinx XC7Z020-1CLG484I.

This repository contains the PCB design files, schematics, BOM, and hardware documentation for the board.

---

## Overview

This board is designed as a general-purpose Zynq development platform featuring:

- Xilinx XC7Z020 SoC
- DDR3L memory subsystem
- Gigabit Ethernet
- USB programming and UART interface
- USB OTG support
- QSPI boot flash
- Multi-rail power architecture
- FPGA PL expansion banks

The design targets embedded Linux, FPGA acceleration, digital design experimentation, and hardware/software co-design workflows.

---

## Hardware Features

### Processing System
- Xilinx XC7Z020-1CLG484I
- Dual-core ARM Cortex-A9
- FPGA programmable logic fabric

### Memory
- DDR3L memory interface
- Fly-by routed DDR topology
- Dedicated VTT termination rail

### Power Architecture
Power rails:
- 5V Input
- 3.3V
- 1.8V
- 1.35V
- 1.0V
- 0.675V DDR termination

Power sequencing implemented using:
- TPS56628 buck converters
- Dedicated PG sequencing
- Protection and filtering stages

### Connectivity
- Gigabit Ethernet (RTL8211F PHY)
- USB-C programming interface
- USB OTG via USB3320 ULPI PHY
- FT2232H for JTAG + UART

### Boot & Programming
- QSPI flash boot support
- Boot mode DIP switches
- Digilent HS3 compatible JTAG header

### FPGA I/O
- PL banks exposed for expansion
- HDMI-capable bank preparation
- Mixed-voltage IO support

---

## Repository Structure

```text
.
├── schematic/
├── pcb/
├── bom/
├── manufacturing/
├── images/
└── README.md
```

---

## Design Files

| File | Description |
|------|-------------|
| Schematic PDF | Complete board schematic |
| BOM | Bill of materials |
| PCB Layout | Board routing and placement |
| Gerbers | Manufacturing outputs |

---

## Key Components

| Component | Part |
|-----------|------|
| SoC | XC7Z020-1CLG484I |
| DDR3L | MT41K256M16TW |
| Ethernet PHY | RTL8211F-CG |
| USB PHY | USB3320 |
| USB/JTAG Interface | FT2232HL |
| QSPI Flash | W25Q512JVEIQ |

---

## Development Status

Current revision:
- v0.07

Status:
- Hardware prototype
- Under validation/testing

Known improvements and future revisions are documented within the schematic notes.

---

## Toolchain

Designed using:
- EasyEDA

Firmware/software targets:
- Vivado
- Vitis
- PetaLinux

---

## Bring-Up Checklist

- [ ] Verify all power rails
- [ ] Validate power sequencing
- [ ] DDR memory calibration
- [ ] QSPI boot validation
- [ ] JTAG connectivity test
- [ ] Ethernet PHY validation
- [ ] USB OTG validation

---

## Manufacturing Notes

Before fabrication:
- Verify impedance-controlled traces
- Review DDR length matching
- Validate power plane integrity
- Confirm connector footprints
- Review DFM constraints

---

## Contributors

NeuraCoreTech Hardware Team



---
## Acknowledgements

This part of project (PCB) is heavily based on the open-source Zynq-7000 FPGA development board work by rehsd.

Original reference project:
https://github.com/rehsd/FPGA

Additional documentation and development notes:
https://www.rehsdonline.com/

The hardware architecture, schematic structure, and several subsystem implementations were adapted from the original project and modified for NeuraCoreTech requirements.

We thank rehsd for openly publishing the design resources and documentation.
