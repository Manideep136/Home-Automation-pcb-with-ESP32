# Home-Automation-pcb-with-ESP32

A custom PCB-based home automation system designed around the ESP32 microcontroller. The project is designed to control high-current AC loads using relay switching while providing a compact and organized PCB for the control electronics.

## Project Overview

This project focuses on designing a dedicated home automation PCB using an **ESP32** as the main controller.

The PCB is designed to interface with a high-current relay for controlling electrical loads. The design was created using **KiCad**, including the schematic, PCB layout, custom footprint, and 3D model integration.

The main goal of this project is to develop a practical and customizable hardware platform for ESP32-based home automation applications.

## Features

- ESP32-based control system
- High-current relay switching
- Designed for loads up to **30A** (relay/load rating dependent)
- Custom PCB designed in KiCad
- Screw terminal connections for external wiring
- Dedicated relay footprint
- Compact PCB layout
- Custom relay footprint and 3D model
- Designed with PCB routing and clearance considerations
- Suitable as a base platform for IoT and home automation projects

## Hardware

### Main Components

| Component | Description |
|---|---|
| ESP32 | Main microcontroller |
| 30A Relay | High-current load switching |
| Power Supply | Provides required DC power |
| Screw Terminals | Load and power connections |
| PCB | Custom KiCad-designed board |

### Relay

The PCB uses a **PR13-5V-450-1C 5V relay** footprint.

The relay footprint was integrated into KiCad using a custom `.kicad_mod` footprint.

> **Important:** The actual safe switching current depends on the relay's datasheet, PCB design, connector rating, wire size, enclosure, and the type of load. Do not assume that every 30A load is safe simply because the relay is labeled 30A.

## PCB Design

The PCB was designed using **KiCad 10**.
KiCad Files
Schematic

The schematic contains the electrical connections between the ESP32, relay, power connections, and other components.

Home automation with ESP32.kicad_sch
PCB

The PCB layout contains the physical board design, component placement, copper tracks, board outline, and routing.

Home automation with ESP32.kicad_pcb
Project

The main KiCad project file is:

Home automation with ESP32.kicad_pro
Custom Footprint

A custom footprint was added for the relay:

PR13-5V-450-1C.pretty/
└── RELAY_PR13-5V-450-1C.kicad_mod

A STEP model is also included for 3D visualization:

PR13-5V-450-1C.step
Working Principle

The basic operating concept is:

          ESP32
            │
            │ Control Signal
            ▼
       Relay Driver
            │
            ▼
       5V Relay Coil
            │
            ▼
     Relay Contacts
            │
            ▼
       AC Load

The ESP32 provides the control signal to operate the relay. The relay electrically switches the connected load.

Additional sensors and IoT functionality can be integrated into the ESP32 firmware depending on the application.

PCB Design Considerations

Because the PCB is intended for high-current switching, special attention should be given to:

PCB trace width
Copper thickness
Clearance between high-voltage and low-voltage sections
Creepage distance
Connector current rating
Relay contact rating
Wire gauge
Fuse/protection
Thermal considerations
Enclosure and insulation

The PCB should be reviewed against the applicable electrical safety requirements before being connected to mains power.
