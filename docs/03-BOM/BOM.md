
---
title: Bill of Materials
---

## Overview

This Bill of Materials (BOM) identifies the electrical, mechanical, and electromechanical components required for my subsystem of the automated garment-folding device.

The subsystem uses a Microchip PIC18F57Q43 Curiosity Nano microcontroller to control a SKYSHALO 12 V linear actuator through a FAN8011N H-bridge motor driver. The actuator moves a folding panel attached to the main platform through hinges.

The design also incorporates 3D-printed structural components, voltage regulation, circuit protection, user input, status indication, and connectors for communication with other subsystems.

The BOM reflects the current prototype design. Component prices and final purchasing information will be updated as parts are selected and acquired.

## Bill of Materials

| Component | Qty | Manufacturer / Part Number | Unit Cost | Schematic Reference |
|---|---:|---|---|---|
| PIC18F57Q43 Curiosity Nano development board | 1 | Microchip / PIC18F57Q43 Curiosity Nano | TBD | U5 |
| H-Bridge motor driver | 1 | Fairchild Semiconductor / FAN8011N | TBD | U4 |
| 12 V linear actuator, 6-inch stroke | 1 | SKYSHALO / Model TBD | TBD | J8 (external actuator) |
| 3D-printing filament (PLA or PETG) | 1 spool (1 kg) | Manufacturer TBD | TBD | Mechanical assembly |
| Folding panel hinges | 2 (estimated) | Manufacturer TBD | TBD | Mechanical assembly |
| 5 V linear voltage regulator | 1 | L7805 / Manufacturer TBD | TBD | U2 |
| DC barrel jack | 1 | Manufacturer TBD | TBD | J6 |
| Fuse | 1 | Rating and manufacturer TBD | TBD | F2 |
| Momentary pushbutton | 1 | Manufacturer TBD | TBD | SW1 |
| Status LED | 1 | Manufacturer TBD | TBD | D6 |
| 330 ohm resistor | 1 | Manufacturer TBD | TBD | R12 |
| 10 kohm resistor | 1 | Manufacturer TBD | TBD | R13 |
| 0.1 uF capacitor | 2 | Manufacturer TBD | TBD | C1, C7 |
| 0.33 uF capacitor | 1 | Manufacturer TBD | TBD | C6 |
| 8-pin connector | 1 | Manufacturer TBD | TBD | J1 |
| 4-pin connector | 1 | Manufacturer TBD | TBD | J7 |
| 2-pin actuator connector | 1 | Manufacturer TBD | TBD | J8 |

## Component Selection and Design Decisions

### Microcontroller

The Microchip PIC18F57Q43 Curiosity Nano serves as the central controller for the subsystem. It provides digital input and output connections for actuator control, pushbutton operation, status indication, and communication with other team subsystems.

The microcontroller was selected because it is compatible with the team's embedded development platform and provides the necessary interfaces for coordinating the folding sequence.

### Motor Driver and Linear Actuator

The SKYSHALO 12 V linear actuator was selected to provide the linear motion needed to move the folding panel. The selected design uses a 6-inch stroke actuator to extend and retract the folding mechanism.

The FAN8011N H-bridge is included in the schematic to provide bidirectional motor control. The microcontroller sends digital control signals to the H-bridge, which changes the polarity of the motor output to control the direction of actuator movement.

The compatibility of the motor driver's current rating with the actuator's operating and stall current must be verified before hardware implementation.

### Mechanical Components

The mechanical assembly incorporates 3D-printing filament and folding panel hinges.

PLA or PETG filament will be used to manufacture custom actuator mounting brackets, supports, and other structural components. These parts can be designed to match the dimensions of the prototype and modified during testing.

Two hinges are currently estimated for the folding panel. The hinges will connect the moving panel to the stationary platform, allowing the panel to rotate as the linear actuator extends and retracts.

These mechanical components were included because they support a compact, customizable, and affordable prototype.

### Power Regulation and Protection

The subsystem includes an L7805 voltage regulator to provide a regulated 5 V supply for appropriate low-voltage electronics.

The linear actuator requires a 12 V supply. The power distribution system must accommodate the different voltage and current requirements of the motor and control circuitry.

A fuse is included to provide protection against excessive current. Its final rating will be determined after the actuator's electrical requirements are verified.

### User Input and Status Indicator

A momentary pushbutton provides a digital input to the microcontroller, allowing the user to interact with the subsystem.

A status LED provides visual feedback during operation. A 330 ohm resistor limits LED current, while the 10 kohm resistor and 0.1 uF capacitor support the pushbutton input circuit.

### Connectors and Integration

The schematic includes an eight-pin connector, a four-pin connector, and a two-pin actuator connector.

These connectors provide interfaces for communication, power distribution, and electrical connections between the subsystem and the other components of the automated garment-folding device.

## Relationship to Product Requirements

The selected components support the automated garment-folding device by providing controlled folding-panel movement, simple user interaction, and integration with the team's other subsystems.

The linear actuator and hinges create the mechanical movement needed to fold garments. The microcontroller and motor driver coordinate the movement, while the 3D-printed components provide customizable mounting and structural support.

The design emphasizes affordability, ease of assembly, compact construction, and the ability to modify components during prototype development.

## Cost Summary

The total subsystem cost will be calculated after final vendor selections and unit prices have been confirmed.

| Cost Category | Estimated Cost |
|---|---|
| Microcontroller and motor driver | TBD |
| Linear actuator | TBD |
| Mechanical components (filament and hinges) | TBD |
| Power supply and regulation | TBD |
| Electronic components and connectors | TBD |
| **Total Estimated Subsystem Cost** | **TBD** |

## Resources

- [Microchip PIC18F57Q43 Product Information](https://www.microchip.com/en-us/product/PIC18F57Q43)
- [FAN8011N Datasheet Search](https://www.google.com/search?q=FAN8011N+datasheet)
- [L7805 Datasheet Search](https://www.google.com/search?q=L7805+datasheet)
- [SKYSHALO Linear Actuator - Home Depot](https://www.homedepot.com/p/334440429)

## Notes

This BOM represents the current subsystem design. Component quantities, exact manufacturer part numbers, purchasing links, and costs will be finalized during procurement and prototype assembly.

Mechanical components such as the filament and hinges are included in the BOM but do not appear as electrical components in the KiCad schematic.
