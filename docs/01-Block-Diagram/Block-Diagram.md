
---
title: Individual Block Diagram
---

## Overview

This block diagram illustrates the electrical architecture and control connections of my subsystem for the automated garment-folding device. The subsystem is responsible for controlling a linear actuator that moves one of the folding panels during the folding sequence.

The design incorporates a Microchip PIC18F57Q43 Curiosity Nano microcontroller, a Fairchild Semiconductor FAN8011N H-bridge motor driver, a SKYSHALO linear actuator, a pushbutton, a status LED, a power regulation system, and connectors for communication with other team subsystems.

## Block Diagram

![Ruben Esquer Individual Block Diagram](individual-block-diagram.png.drawio.png)

**Figure 1:** Individual subsystem block diagram showing the microcontroller, actuator control, power distribution, user input, and subsystem connections.

## Design Decisions and System Architecture

The subsystem was organized around the PIC18F57Q43 Curiosity Nano because it provides digital input and output capabilities for controlling the actuator and interfacing with other components.

The FAN8011N H-bridge was selected to provide bidirectional motor control. The microcontroller sends digital control signals to the motor driver, which is intended to extend and retract the SKYSHALO linear actuator.

The power system separates the 12 V supply required by the actuator from the regulated 5 V supply used by the low-voltage electronics. A voltage regulator provides the lower-voltage supply, while a shared ground provides a common electrical reference.

A pushbutton provides a digital input, and a status LED provides visual feedback. Two subsystem connectors allow electrical connections with other parts of the team's garment-folding device.

## Microcontroller Connections

The block diagram identifies the following GPIO signals:

| GPIO | Function | Signal Type |
|------|----------|-------------|
| RD1 | Status LED | Digital Output |
| RA7 | Pushbutton | Digital Input |
| RF0 | H-Bridge Extend Control | Digital Output |
| RF1 | H-Bridge Retract Control | Digital Output |
| RA1 | Subsystem Connector 1 | Digital I/O |
| RA2 | Subsystem Connector 2 | Digital I/O |

The connections shown represent the planned subsystem interfaces and will be verified during hardware integration and testing.

## Relationship to Product Requirements

The subsystem supports the automated garment-folding device by providing controlled movement of a folding panel. Bidirectional actuator operation allows the panel to move through the folding sequence and return toward its original position.

The pushbutton provides a simple user interface, while the status LED allows the user to observe system activity. The connectors support integration with the other team members' subsystems.

The separation of motor power and logic power supports the different electrical requirements of the actuator and microcontroller.

## Resources

The editable source file and exported diagram are maintained in the project repository.
