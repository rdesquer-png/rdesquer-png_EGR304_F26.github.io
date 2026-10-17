
---
title: Component Selection
---

# Component Selection

## Automated Garment Folding Device

This report compares major components for an automated garment-folding device controlled by the PIC18F57Q43 microcontroller. Components are evaluated based on affordability, performance, reliability, and compatibility with the overall design.

## 1. Linear Actuator

The linear actuator is responsible for pushing the folding panel to fold clothing. The desired stroke length is between 4 and 8 inches, with a preferred operating voltage of 12V DC and a target cost of $30 or less per actuator.

### Option 1: VEVOR 12V High-Speed Linear Actuator

- **Model:** OK648-1000N
- **Price:** $36.90
- **Voltage:** 12V DC
- **Stroke:** 6 inches
- **Speed:** 0.55 inches/second
- **Rated force:** 1000 N
- **Product:** [VEVOR Linear Actuator](https://www.vevor.com/linear-actuators-c_11633/vevor-linear-actuator-12v-6inch-0-55-s-high-speed-220lbs-1000n-ip54-protection-p_010576478447)

![VEVOR Actuator](images/vevor-actuator.jpg)

| Pros | Cons |
|---|---|
| Faster movement than the slower 6-inch option | Exceeds the $30 budget |
| Meets the preferred 6-inch stroke | Requires an external motor driver |
| High force capacity | More force than may be needed |
| IP54 protection | Higher power demand |

### Option 2: SKYSHALO 12V Linear Actuator

- **Model:** JQXXXZXQ6INCFHA2PV9-0110
- **Price:** $22.22
- **Voltage:** 12V DC
- **Stroke:** 6 inches
- **Speed:** 0.19 inches/second
- **Rated force:** 1500 N
- **Product:** [SKYSHALO Linear Actuator](https://www.homedepot.com/p/334440429)

![SKYSHALO Actuator](images/skyshalo-actuator.jpg)

| Pros | Cons |
|---|---|
| Within the $30 budget | Slower extension speed |
| Meets the preferred 6-inch stroke | May increase folding cycle time |
| High load capacity | Requires an external motor driver |
| Includes mounting hardware | Technical documentation must be verified |

### Option 3: KFFKFF 12V High-Speed Linear Actuator

- **Price:** $28.99
- **Voltage:** 12V DC
- **Stroke:** 4 inches
- **Speed:** 0.6 inches/second
- **Rated force:** 1000 N
- **Product:** [KFFKFF Linear Actuator](https://www.walmart.com/ip/18122624399)

![KFFKFF Actuator](images/kffkff-actuator.jpg)

| Pros | Cons |
|---|---|
| Within the $30 budget | Shorter stroke than other options |
| Fastest advertised movement | May require different mounting geometry |
| Suitable for compact folding mechanisms | Requires an external motor driver |
| Operates at 12V DC | Technical documentation must be verified |

### Final Component Selection

**Choice: Option 3 - KFFKFF 12V High-Speed Linear Actuator (Provisional)**

**Rationale:**

The KFFKFF linear actuator is the preferred candidate because it provides a good balance between affordability and operating speed. At approximately $28.99, it meets the project's target budget of $30 per actuator. Its advertised speed of 0.6 inches per second is faster than the other two candidates, potentially reducing the time required to fold clothing.

Although its 4-inch stroke is shorter than the other options, it may provide sufficient travel when connected to a properly designed folding-panel linkage. The final selection will depend on verifying the required mechanical movement, electrical current, and manufacturer specifications.

If a longer stroke is necessary, the SKYSHALO 6-inch actuator is the preferred budget alternative.


## 2. Photoresistor

The photoresistor will detect changes in light caused by clothing covering the folding surface. The sensor will be connected to the PIC18F57Q43 analog input through a voltage divider.

### Option 1: Smraza Photoresistor

- **Brand:** Smraza
- **Cost to team:** $0.00 (provided)
- **Type:** Light-dependent resistor (LDR)
- **Part number:** To be confirmed
- **Purpose:** Detect changes in light

| Pros | Cons |
|---|---|
| Already available at no cost | Exact specifications need verification |
| Simple interface using a voltage divider | Requires calibration |
| No additional shipping or purchasing | Sensitive to changes in ambient lighting |

**Product image:** Add photo of our Smraza sensor.

### Option 2: Adafruit CdS Photoresistor

- **Part number:** 161
- **Price:** $0.95
- **Type:** CdS light-dependent resistor
- **Product:** [Adafruit Photoresistor](https://www.adafruit.com/product/161)

| Pros | Cons |
|---|---|
| Low purchase cost | Additional purchase required |
| Documentation and tutorials available | Sensitive to ambient lighting |
| Easy to interface with the PIC ADC | Requires a voltage divider |
| Compact size | Not suitable for precise light measurements |

### Option 3: SparkFun Mini Photocell

- **Part number:** SEN-09088
- **Price:** $1.75
- **Light resistance:** Approximately 1 kOhm
- **Dark resistance:** Approximately 10 kOhm
- **Maximum power:** 100 mW
- **Product:** [SparkFun Mini Photocell](https://www.sparkfun.com/mini-photocell.html)

| Pros | Cons |
|---|---|
| Small size for installation | More expensive than Adafruit option |
| Datasheet and hookup guide available | Requires additional purchase |
| Compatible with analog sensing circuits | Requires calibration for reliable detection |
| Simple through-hole connections | Affected by surrounding lighting conditions |

### Final Photoresistor Selection

**Choice: Option 1 - Smraza Photoresistor (Provisional)**

**Rationale:**

The Smraza photoresistor is the preferred option because it is already available to our team at no additional cost. This reduces project expenses and allows immediate testing. A photoresistor can detect changes in light when clothing covers the sensing area, providing a simple input for the folding system.

The sensor can be connected to the PIC18F57Q43 using a voltage divider and analog-to-digital conversion. Before finalizing the selection, the team will verify the sensor's specifications and test its reliability under different lighting conditions.


## 3. Motor Driver (H-Bridge)

The motor driver will control the extension and retraction of the linear actuator in our automated garment-folding device. The PIC18F57Q43 microcontroller will send control signals to the motor driver, which will control the direction of the actuator's DC motor.

The motor driver must support bidirectional operation and handle the electrical current required by the selected actuator.

### Option 1: FAN8011N H-Bridge

- **Manufacturer:** Fairchild Semiconductor
- **Model:** FAN8011N
- **Cost to team:** $0.00 (provided in class)
- **Type:** Motor driver integrated circuit
- **Operating voltage:** Must be verified using the datasheet
- **Output current:** Must be verified
- **Product information:** [FAN8011N Datasheet Search](https://www.google.com/search?q=FAN8011N+datasheet)

| Pros | Cons |
|---|---|
| Already available at no additional cost | Output current must be verified |
| No additional purchasing required | May require external circuitry |
| Designed for motor-control applications | Compatibility with our actuator is not yet confirmed |
| Can be incorporated into our custom PCB | Requires careful circuit design and testing |

### Option 2: L298N Motor Driver Module

- **Model:** L298N
- **Estimated price:** $4-$10
- **Motor supply voltage:** Up to 46V (IC rating)
- **Output current:** Up to 2A per channel (IC rating)
- **Type:** Dual H-bridge motor driver
- **Product information:** [L298N Datasheet](https://www.st.com/resource/en/datasheet/l298.pdf)

| Pros | Cons |
|---|---|
| Affordable and widely available | Significant voltage drop during operation |
| Supports forward and reverse motor control | Less efficient than newer motor drivers |
| Compatible with microcontroller control signals | Current capability may be insufficient |
| Commonly used in educational projects | May require heatsinking under load |

### Option 3: Pololu VNH5019 Motor Driver

- **Manufacturer:** Pololu
- **Model:** VNH5019 Motor Driver Carrier
- **Approximate price:** $20
- **Operating voltage:** 5.5V to 24V
- **Continuous current capability:** Approximately 12A under suitable cooling conditions
- **Type:** High-current H-bridge motor driver
- **Product:** [Pololu VNH5019](https://www.pololu.com/product/1451)

| Pros | Cons |
|---|---|
| Designed for higher-current DC motors | More expensive than the other options |
| Supports bidirectional motor control | Additional purchase required |
| Includes current-sensing capability | Larger board than a single IC |
| Includes protection features | Must still be checked against motor stall current |

### Final Motor Driver Selection

**Choice: Option 1 - FAN8011N H-Bridge (Provisional)**

**Rationale:**

The FAN8011N is our initial preferred motor-driver candidate because it was provided in class at no additional cost. Using an available component would reduce our project expenses and allow us to integrate the motor-control circuit into our existing hardware design.

However, the FAN8011N must be evaluated against the selected linear actuator's voltage and current requirements before the selection can be finalized.

The L298N offers an inexpensive alternative, but its limited current capability and electrical losses may reduce performance.

The Pololu VNH5019 provides a higher-current alternative with additional protection and monitoring features, making it a stronger choice if our actuator requires more current than the class-provided driver can safely deliver.

The final motor-driver selection will be based on verified electrical compatibility, reliability, and overall cost.


## 4. Power Supply and Power Input

The automated garment-folding device requires electrical power for its linear actuator, motor driver, microcontroller, and sensors.

Three power-delivery approaches are considered: a wall-connected power supply, two 9V batteries connected in series, and an external DC supply connected through a barrel jack.

### Option 1: Wall-Connected AC/DC Power Supply

- **Example model:** MEAN WELL GST60A12-P1J
- **Input:** Household AC electricity
- **Output:** 12V DC
- **Maximum output current:** 5A
- **Rated power:** 60W
- **Price:** Verify current vendor price
- **Product:** [MEAN WELL GST60A12-P1J](https://www.digikey.com/en/products/detail/mean-well-usa-inc/GST60A12-P1J/7703712)

| Pros | Cons |
|---|---|
| Provides continuous power from a wall outlet | Requires access to an electrical outlet |
| Regulated 12V output | Not portable |
| Enclosed power adapter | Output current must meet actuator requirements |
| Suitable for household operation | Additional regulation needed for low-voltage electronics |

### Option 2: Two 9V Batteries Connected in Series

- **Example:** Two Energizer MAX 9V alkaline batteries
- **Battery voltage:** 9V each
- **Combined nominal voltage:** 18V DC
- **Configuration:** Series connection
- **Price:** Cost of two batteries and battery connectors
- **Datasheet:** [Energizer 9V Battery](https://data.energizer.com/pdfs/max-eu-9v.pdf)

| Pros | Cons |
|---|---|
| Portable power source | 18V is too high for a 12V actuator without regulation |
| Does not require a wall outlet | Poor choice for high-current motor loads |
| Simple battery connections | Batteries require replacement |
| Useful for low-power experiments | Limited runtime and voltage stability |

### Option 3: External DC Supply Through a Barrel Jack

- **Connector:** Three-pin DC barrel jack
- **Cost to team:** $0.00 (provided in class)
- **Input voltage:** Depends on connected external supply
- **Proposed supply:** Regulated 12V DC adapter
- **Connector information:** [Pololu DC Barrel Jack](https://www.pololu.com/product/1139/)

| Pros | Cons |
|---|---|
| Barrel jack already available to the team | Jack does not generate power |
| Allows easy connection and disconnection | Requires a compatible external supply |
| Convenient for PCB integration | Plug dimensions and polarity must match |
| Can support external power during testing | Current rating must be verified |

### Final Power Supply Selection

**Choice: Option 1 - Wall-Connected 12V AC/DC Supply**

**Rationale:**

The wall-connected 12V DC power supply is the preferred option because the automated garment-folding device is intended primarily for household use.

A regulated wall adapter provides continuous power without requiring battery replacement. It also avoids the limitations of two 9V batteries, which produce approximately 18V in series and are poorly suited to high-current motor applications.

The existing barrel jack may be used as the physical connection between the wall adapter and the device, provided the connector dimensions, polarity, and current ratings are compatible.

The final supply rating will be selected after calculating the total current requirements and including a 25% safety margin.


## 5. Voltage Regulator

The voltage regulator converts the 12V DC power supply into a regulated 5V output for the low-voltage components of our automated garment-folding device.

Three voltage regulators are compared based on cost, efficiency, output current, heat generation, and ease of integration.

### Option 1: STMicroelectronics L7805ABV

- **Manufacturer:** STMicroelectronics
- **Model:** L7805ABV
- **Cost to team:** $0.00 (provided in class)
- **Type:** Linear voltage regulator
- **Output voltage:** 5V DC
- **Rated output current:** Up to 1.5A with adequate cooling
- **Package:** TO-220
- **Datasheet:** [STMicroelectronics L78 Series](https://www.st.com/resource/en/datasheet/l78.pdf)

| Pros | Cons |
|---|---|
| Already available at no additional cost | Generates heat when stepping 12V down to 5V |
| Provides a fixed 5V output | Less efficient than switching regulators |
| Simple three-pin design | May require a heatsink |
| Easy to integrate into a custom PCB | Current capacity depends on thermal conditions |
| No output adjustment required | Not ideal for high-current applications |

### Option 2: LM2596 Adjustable Buck Converter

- **Manufacturer:** Texas Instruments (regulator IC)
- **Model:** LM2596-based adjustable module
- **Type:** Switching step-down regulator
- **Input voltage:** Typically 4.5V to 40V for the IC
- **Output voltage:** Adjustable
- **Rated IC output current:** Up to 3A
- **Price:** Verify selected module price
- **Product:** [Texas Instruments LM2596](https://www.ti.com/product/LM2596)

| Pros | Cons |
|---|---|
| Higher efficiency than a linear regulator | Requires output voltage adjustment |
| Produces less heat during voltage conversion | More complex circuitry |
| Can provide relatively high output current | Switching may introduce electrical noise |
| Suitable for 12V-to-5V conversion | Module quality varies by manufacturer |

### Option 3: Pololu D24V22F5

- **Manufacturer:** Pololu
- **Model:** D24V22F5
- **Type:** Fixed-output switching regulator
- **Input voltage:** 5.3V to 36V, subject to dropout requirements
- **Output voltage:** 5V DC
- **Typical maximum output current:** Approximately 2.5A, depending on operating conditions
- **Approximate price:** $18.95
- **Product:** [Pololu D24V22F5](https://www.pololu.com/product/2858)

| Pros | Cons |
|---|---|
| High efficiency | More expensive than our existing regulator |
| Fixed 5V output | Requires an additional purchase |
| Compact size | Current capacity depends on operating conditions |
| Includes electrical protection features | More complex internal design |
| Produces less heat than a linear regulator | Switching can introduce electrical noise |

### Final Voltage Regulator Selection

**Choice: Option 1 - STMicroelectronics L7805ABV (Provisional)**

**Rationale:**

The STMicroelectronics L7805ABV is our preferred voltage regulator because it was provided in class at no additional cost. Using this component reduces the overall project budget and allows us to integrate the regulator directly into our custom circuit.

The L7805ABV provides a fixed 5V output suitable for compatible low-voltage electronic components. Its simple three-pin design also makes it easier to incorporate into our schematic and PCB.

Although the LM2596 and Pololu D24V22F5 offer higher efficiency, the L7805ABV may be sufficient for our design if the total 5V current requirement is relatively low.

The main disadvantage is heat generation when converting 12V to 5V. For example, at a load current of 0.2A:

Power dissipated = (12V - 5V) x 0.2A = 1.4W

This heat may require a heatsink or other thermal management.

Before finalizing the selection, the team will verify the total current requirement, thermal performance, and correct power connection for the PIC18F57Q43 development board.


## 6. Operational Amplifier (Op-Amp)

The operational amplifier may be used to condition analog signals from sensors in our automated garment-folding device. It can buffer, amplify, or filter sensor signals before they are measured by the PIC18F57Q43 microcontroller.

Three quad operational amplifiers are compared based on cost, operating voltage, power consumption, signal performance, and ease of integration.

### Option 1: Microchip MCP6004

- **Manufacturer:** Microchip Technology
- **Model:** MCP6004
- **Cost to team:** $0.00 (provided in class)
- **Type:** Quad operational amplifier
- **Number of amplifiers:** 4
- **Operating voltage:** 1.8V to 6.0V
- **Gain-bandwidth product:** 1 MHz
- **Input/output:** Rail-to-rail
- **Typical supply current:** 100 microamps per amplifier
- **Product:** [Microchip MCP6004](https://www.microchip.com/en-us/product/mcp6004)

| Pros | Cons |
|---|---|
| Already available at no additional cost | Cannot operate directly from the 12V supply |
| Compatible with a regulated 5V supply | Requires proper signal-conditioning circuitry |
| Rail-to-rail input and output | Limited 1 MHz bandwidth |
| Low power consumption | Four amplifiers may be unnecessary |
| Four amplifiers in one IC | Additional wiring and PCB space required |

### Option 2: Texas Instruments LM324

- **Manufacturer:** Texas Instruments
- **Model:** LM324
- **Type:** Quad operational amplifier
- **Number of amplifiers:** 4
- **Operating voltage:** 3V to 30V
- **Gain-bandwidth product:** 1.2 MHz
- **Typical supply current:** 175 microamps per amplifier
- **Price:** Verify current supplier price
- **Product:** [Texas Instruments LM324](https://www.ti.com/product/LM324)

| Pros | Cons |
|---|---|
| Wide operating voltage range | Output does not swing fully to the positive supply |
| Four amplifiers in one IC | Less suitable for full-range 5V ADC signals |
| Common and well-documented | Additional purchase required |
| Suitable for basic analog signal processing | Higher input bias current than CMOS alternatives |

### Option 3: Texas Instruments TLV2374

- **Manufacturer:** Texas Instruments
- **Model:** TLV2374
- **Type:** Quad operational amplifier
- **Number of amplifiers:** 4
- **Operating voltage:** 2.7V to 16V
- **Gain-bandwidth product:** 3 MHz
- **Input/output:** Rail-to-rail
- **Typical supply current:** 550 microamps per amplifier
- **Price:** Verify current supplier price
- **Product:** [Texas Instruments TLV2374](https://www.ti.com/product/TLV2374)

| Pros | Cons |
|---|---|
| Higher bandwidth than MCP6004 | Additional purchase required |
| Rail-to-rail input and output | Higher typical supply current |
| Compatible with a 5V supply | Higher performance may be unnecessary |
| Four amplifiers in one IC | Requires external circuit components |

### Final Operational Amplifier Selection

**Choice: Option 1 - Microchip MCP6004 (Provisional)**

**Rationale:**

The Microchip MCP6004 is our preferred operational amplifier because it was provided in class at no additional cost. Its low power consumption and compatibility with a regulated 5V supply make it suitable for our embedded system.

The MCP6004 provides four independent operational amplifiers, allowing multiple analog signals to be conditioned if necessary. Its rail-to-rail input and output capability is useful for interfacing with the microcontroller's analog-to-digital converter.

Although the TLV2374 offers greater bandwidth and the LM324 supports a wider supply voltage range, the MCP6004 provides sufficient performance for many low-frequency sensor applications without requiring an additional purchase.

The final circuit will be evaluated to determine whether amplification or buffering is necessary. If the photoresistor can be read reliably using a simple voltage divider, the operational amplifier may not be required for that sensor.
