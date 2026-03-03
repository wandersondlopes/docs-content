---
identifier: ABX00156
title: Arduino® Bughopper
type: maker
variant: 'Datasheet'
author: José Bagur
---

![](assets/featured.png)

# Description

<p style="text-align: justify;">The Arduino Bughopper is a compact USB-to-UART bridge board designed to bring straightforward remote debugging to the Arduino UNO Q via its JCTL connector. Built around the FTDI FT230XQ integrated circuit (IC), it provides a reliable, high-speed serial link between your development machine and the UNO Q, enabling advanced debugging and logging without occupying the board's main I/O pins. Its compact 38.5 × 11 mm footprint, USB-C connectivity, and multiple header options make it easy to integrate into any workspace, enclosure, or automated test setup.</p>

# Target Areas:

Embedded development, hardware testing, education

# CONTENTS

## Application Examples

<p style="text-align: justify;">The Arduino Bughopper, when connected to an Arduino UNO Q board, provides a dedicated debugging and serial communication channel for various development scenarios. Below are some application examples that demonstrate its practical value:</p>

- **Embedded development and debugging**: The Bughopper streamlines the firmware development workflow by providing a dedicated debug serial channel that does not interfere with the UNO Q's main I/O pins.
  - <p style="text-align: justify;"><strong>Remote debug over serial</strong>: Connect the Bughopper to the UNO Q's JCTL connector to establish a dedicated UART link for real-time debugging. Developers can monitor serial output, send debug commands, and inspect firmware behavior directly from their development machine via USB-C, all without occupying the UNO Q's primary serial port or I/O headers.</p>
  - <p style="text-align: justify;"><strong>Firmware flashing and continuous UART logging</strong>: Use the Bughopper as a persistent serial interface for firmware updates and continuous data logging during long-running tests. Its reliable FT230XQ-R USB-to-UART bridge ensures stable communication at data rates from 300 baud to 3 Mbaud, making it suitable for both routine flashing and high-throughput logging scenarios.</p>
  - <p style="text-align: justify;"><strong>Research and development (R&D) and testing</strong>: The Bughopper enables R&D teams and test engineers to integrate reliable debug access into their prototyping and validation workflows.</p>
  - <p style="text-align: justify;"><strong>Field diagnostics and automated test</strong>: Install the Bughopper into automated testing rigs to provide consistent, hands-free serial access to UNO Q boards. Its compact form factor and dual header options (2.54 mm female and 1.27 mm male) allow seamless integration into custom test fixtures, enabling field diagnostics and continuous integration pipelines for hardware/software validation.</p>
  - <p style="text-align: justify;"><strong>Education and training labs</strong>: The Bughopper offers a low-cost, student-friendly tool for teaching serial communication protocols and hardware debugging fundamentals.</p>
  - <p style="text-align: justify;"><strong>Teaching UART communication and debugging workflows</strong>: Institutions teaching embedded systems, IoT development, or hardware debugging can use the Bughopper with UNO Q boards to provide hands-on lab exercises. Students learn serial communication protocols, debugging techniques, and project troubleshooting using a modern USB-C interface with clear power status LEDs for quick visual feedback.</p>

## Features

### General Specifications Overview

<p style="text-align: justify;">The Arduino Bughopper is a compact USB-to-UART bridge board built around the FTDI FT230XQ IC. Designed exclusively for the Arduino UNO Q, it connects via the JCTL header to provide a dedicated debug and serial communication channel that does not interfere with the board's main I/O.
</p>

The main features of the board are highlighted in the table shown below.

| **Feature**                   | **Description**                                                                                                                                  |
|-------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| USB-to-UART Bridge            | FTDI FT230XQ-R, USB 2.0 Full Speed, data rates from 300 baud to 3 Mbaud                                                                        |
| USB Connector                 | USB-C (CX60B-16P) for modern, reversible connections                                                                                             |
| Level Translator              | SN74AVC2T245RSWR bidirectional voltage-level translator for safe UART communication between +3.3 VDC and VTARGET domains                        |
| ESD Protection                | ESD321DYAR (×3) and STN1010SB301 for robust electrostatic discharge protection on USB and signal lines                                           |
| Header Connectors             | Female 2.54 mm 2×5 header for direct cable attachment; male 1.27 mm 2×5 header (FTSH-105-01-L-DH-C-TR) for compact ribbon cable setups          |
| CBUS Open-Drain Outputs       | 4× configurable CBUS outputs via 2N7002PS,115 MOSFETs                                                                                           |
| Onboard LEDs                  | Green (+3V3 power), Red (VTARGET status), 2× Yellow (TXD and RXD activity)                                                                      |
| Power Supply                  | +5 VDC via USB-C; +3.3 VDC generated by the FT230XQ-R internal LDO regulator                                                                    |
| Target Board Compatibility    | Arduino UNO Q (via JCTL connector)                                                                                                               |
| Dimensions                    | 38.5 mm × 11 mm                                                                                                                                 |
| Weight                        | TBD                                                                                                                                              |

<div style="page-break-after: always;"></div>

### Accessories

- TBD

### Related Products

- Arduino UNO Q (SKU: TBD)

<div style="page-break-after: always;"></div>

## Ratings

### Recommended Operating Conditions

<p style="text-align: justify;">The table below provides a comprehensive guideline for the optimal use of the Bughopper, outlining typical operating conditions and design limits. The operating conditions of the Bughopper are largely based on the specifications of the FTDI FT230XQ USB-to-UART bridge and the board's level translator (SN74AVC2T245RSWR).</p>

<div style="text-align:center;">

|           **Parameter**           |     **Symbol**     | **Min** | **Typ** | **Max** | **Unit** |
|:---------------------------------:|:------------------:|:-------:|:-------:|:-------:|:--------:|
| USB Supply Voltage (VBUS)         | V<sub>USB</sub>    |   4.0   |   5.0   |   5.25  |     V    |
| FT230XQ-R Supply Voltage (VCC)    | V<sub>CC</sub>     |   3.3   |   5.0   |   5.5   |     V    |
| Internal LDO Output Voltage       | V<sub>3V3OUT</sub> |    -    |   3.3   |    -    |     V    |
| VTARGET Voltage<sup>1</sup>       | V<sub>TARGET</sub> |   TBD   |   TBD   |   TBD   |     V    |
| Operating Temperature             | T<sub>OP</sub>     |   -40   |    -    |    85   |    °C    |
| Operating Current (Active)        | I<sub>OP</sub>     |    -    |    8    |    -    |    mA    |
| USB Suspend Current               | I<sub>SUSP</sub>   |    -    |   125   |    -    |    µA    |

</div>

<p style="text-align: justify;">
<sup>1</sup> VTARGET is the voltage level supplied by the connected Arduino UNO Q board through the JCTL connector. This voltage is used as the reference for the level translator's B-side (target side) and the VTARGET status LED.
</p>

<div style="background-color: #FFFFE0; border-left: 6px solid #FFD700; margin: 20px 0; padding: 15px;">
<p style="text-align: justify;"><strong>Driver Tip:</strong> The Bughopper uses the FTDI FT230XQ-R, which is supported by FTDI's royalty-free <strong>Virtual Com Port (VCP)</strong> and <strong>Direct (D2XX)</strong> drivers. These drivers are available for Windows, macOS, and Linux, and enable the board to appear as a standard serial COM port on your development machine.</p>
</div>

<div style="background-color: #FFCCCC; border-left: 6px solid #FF0000; margin: 20px 0; padding: 15px;">
<p style="text-align: justify;"><strong>Safety Note:</strong> The Bughopper is powered exclusively through its USB-C connector. Do not attempt to supply external power through the header connector pins. Ensure that the JCTL connector is properly aligned before connecting the board to the Arduino UNO Q to prevent damage to both boards.</p>
</div>

<div style="page-break-after: always;"></div>

## Functional Overview

<p style="text-align: justify;">
The core of the Bughopper is the FT230XQ-R USB-to-UART bridge from FTDI. The board receives +5 VDC power from the USB-C connector and generates +3.3 VDC through the FT230XQ-R's internal LDO regulator. UART signals (TXD and RXD) are routed through a SN74AVC2T245RSWR bidirectional level translator, which ensures safe voltage-level translation between the +3.3 VDC domain of the FT230XQ-R and the VTARGET domain of the connected Arduino UNO Q board. Four onboard LEDs provide visual status: a green LED for the +3.3 VDC power rail, a red LED for the VTARGET rail, and two yellow LEDs for TXD and RXD activity.
</p>

### Pinout

The Bughopper connectors pinout is shown in the figure below.

![](assets/Bughopper_Pinout.png)

<div style="page-break-after: always;"></div>

### Block Diagram

An overview of the high-level architecture of the Bughopper is illustrated in the figure below.

![](assets/Bughopper_Block_Diagram.png)

The Bughopper's architecture can be summarized in the following functional blocks:

- **USB-C Connector (CX60B-16P)**: Provides the physical USB interface to the host development machine. Includes ESD protection (ESD321DYAR) on the data lines and a TVS diode (STN1010SB301) on VBUS.
- **FTDI FT230XQ-R**: The central IC of the board. It handles the entire USB protocol, converts USB data to UART signals (TXD, RXD), generates +3.3 VDC via its internal LDO, and provides four configurable CBUS outputs.
- **Level Translator (SN74AVC2T245RSWR)**: Performs bidirectional voltage-level translation between the FT230XQ-R's +3.3 VDC UART signals and the VTARGET domain of the connected UNO Q, ensuring safe communication across different voltage levels.
- **CBUS Open-Drain MOSFETs (2N7002PS,115 ×4)**: Convert the FT230XQ-R's CBUS outputs to open-drain signals, allowing flexible interfacing with external circuits through the board's header connectors.
- **Status LEDs**: Four LEDs provide at-a-glance status: green (DL1, +3V3 power), red (DL3, VTARGET), and two yellow (DL2 for TXD, DL4 for RXD activity).
- **ESD Protection**: ESD321DYAR devices on USB data lines and the VTARGET line, plus a STN1010SB301 on VBUS, protect the board against electrostatic discharge events.

<div style="page-break-after: always;"></div>

### Power Supply

<div style="text-align:justify;">

The Bughopper is powered through its USB-C connector:

- **USB-C connector (+5 VDC)**: The primary and only power input. When connected to a USB host (development machine), the board receives +5 VDC through VBUS. This voltage powers the FT230XQ-R's VCC pin directly.
- **Internal +3.3 VDC LDO (FT230XQ-R 3V3OUT)**: The FT230XQ-R generates +3.3 VDC from the +5 VDC USB supply using its integrated LDO regulator. This regulated output powers the FT230XQ-R's I/O (VCCIO pin) and the level translator's A-side (VCCA).
- **VTARGET**: This is not a power input to the Bughopper. Instead, it is the voltage reference supplied by the connected Arduino UNO Q through the JCTL connector. VTARGET is used as the reference for the level translator's B-side (VCCB) and as the supply for the VTARGET status LED.

</div>

<div style="background-color: #FFFFE0; border-left: 6px solid #FFD700; margin: 20px 0; padding: 15px;">
<strong>Power Tip:</strong> The Bughopper draws approximately 8 mA during active operation and approximately 125 µA during USB suspend, making it suitable for always-connected debug setups with minimal power overhead.
</div>

<div style="background-color: #FFCCCC; border-left: 6px solid #FF0000; margin: 20px 0; padding: 15px;">
<strong>Safety Note:</strong> Do not attempt to power the Bughopper through any pin other than the USB-C connector. The header connector pins are designed for signal communication and voltage reference (VTARGET) only, not for supplying power to the board.
</div>

<div style="page-break-after: always;"></div>

## Device Operation

<div style="text-align:justify;">

### Getting Started - IDE

To use the Bughopper with the Arduino UNO Q, install the Arduino Desktop IDE **[1]**. Connect the Bughopper to your development machine using a USB-C cable. Once connected, the board will appear as a standard serial COM port thanks to FTDI's Virtual Com Port (VCP) drivers. Then, connect the Bughopper to the UNO Q's JCTL connector using the appropriate header cable.

### Getting Started - Arduino Web Editor

All Arduino devices work out of the box on the Arduino Cloud Editor **[2]** by installing a simple plugin. The Arduino Cloud Editor is hosted online. Therefore, it will always be up-to-date with all the latest features and support for all boards and devices. Follow **[3]** to start coding on the browser and upload your sketches onto your device.

### Getting Started - Arduino Cloud

All Arduino IoT-enabled products are supported on Arduino Cloud, which allows you to log, graph, and analyze sensor data, trigger events, and automate your home or business. Take a look at the official documentation to know more.

### FTDI Drivers

The Bughopper uses the FTDI FT230XQ-R, which requires FTDI's VCP (Virtual Com Port) or D2XX drivers to be installed on your development machine. These drivers are available for Windows, macOS, and Linux from the FTDI website **[4]**. Most modern operating systems include built-in FTDI driver support.

### Sample Sketches

Sample sketches demonstrating the use of the Bughopper with the Arduino UNO Q can be found either in the "Examples" menu in the Arduino IDE or in the "Bughopper Documentation" section of Arduino documentation **[5]**.

### Online Resources

Now that you have gone through the basics of what you can do with the device, you can explore the endless possibilities it provides by checking exciting projects on Arduino Project Hub **[6]**, the Arduino Library Reference **[7]**, and the online store **[8]** where you will be able to complement your Bughopper board with additional extensions, sensors, and actuators.

</div>

<div style="page-break-after: always;"></div>

## Mechanical Information

<p style="text-align: justify;">
The Bughopper is a compact, single-sided 38.5 mm × 11 mm board with a USB-C connector on one end, a female 2.54 mm 2×5 header on the opposite end, and a male 1.27 mm 2×5 header adjacent to it. The board's narrow form factor is designed for easy integration into workspaces, enclosures, and automated test fixtures.
</p>

### Board Dimensions

The Bughopper board outline is shown in the figure below; all the dimensions are in mm.

![](assets/Bughopper_Outline.png)

<div style="page-break-after: always;"></div>

### Board Connectors

<p style="text-align: justify;">
The Bughopper features three connectors: a USB-C connector (CX60B-16P) on one end for host communication and power, a female 2.54 mm 2×5 header for direct cable attachment, and a male 1.27 mm 2×5 header (FTSH-105-01-L-DH-C-TR) for compact ribbon cable connections. The placement of these connectors is shown in the figure below; all the dimensions are in mm.
</p>

![](assets/Bughopper_Connectors.png)

<div style="page-break-after: always;"></div>

### Board Peripherals and Actuators

<p style="text-align: justify;">
The Bughopper has four onboard LEDs that provide visual status feedback. A green LED (DL1, HSMG-C190) indicates the +3V3 power rail status, a red LED (DL3, XHY-STB0603SR) indicates the VTARGET rail status, and two yellow LEDs (DL2 and DL4, KPT-1608YC) indicate TXD and RXD serial activity, respectively. The placement of these components is shown in the figure below; all the dimensions are in mm.
</p>

![](assets/Bughopper_PeripheralsActuators.png)

<div style="page-break-after: always;"></div>

## Product Compliance

### Product Compliance Summary

| **Product Compliance** |
|:----------------------:|
|  CE (European Union)   |
|          RoHS          |
|         REACH          |
|          WEEE          |

### Declaration of Conformity CE DoC (EU)

<p style="text-align: justify;">
We declare under our sole responsibility that the products above are in conformity with the essential requirements of the following EU Directives and therefore qualify for free movement within markets comprising the European Union (EU) and European Economic Area (EEA).
</p>

### Declaration of Conformity to EU RoHS & REACH 211 01/19/2021

<p style="text-align: justify;">
Arduino boards are in compliance with RoHS 2 Directive 2011/65/EU of the European Parliament and RoHS 3 Directive 2015/863/EU of the Council of 4 June 2015 on the restriction of the use of certain hazardous substances in electrical and electronic equipment.
</p>

| **Substance**                          | **Maximum Limit (ppm)** |
|----------------------------------------|-------------------------|
| Lead (Pb)                              | 1000                    |
| Cadmium (Cd)                           | 100                     |
| Mercury (Hg)                           | 1000                    |
| Hexavalent Chromium (Cr6+)             | 1000                    |
| Poly Brominated Biphenyls (PBB)        | 1000                    |
| Poly Brominated Diphenyl ethers (PBDE) | 1000                    |
| Bis(2-Ethylhexyl) phthalate (DEHP)     | 1000                    |
| Benzyl butyl phthalate (BBP)           | 1000                    |
| Dibutyl phthalate (DBP)               | 1000                    |
| Diisobutyl phthalate (DIBP)            | 1000                    |

<div style="page-break-after: always;"></div>

Exemptions: No exemptions are claimed.

<p style="text-align: justify;">
Arduino Boards are fully compliant with the related requirements of European Union Regulation (EC) 1907 /2006 concerning the Registration, Evaluation, Authorization and Restriction of Chemicals (REACH). We declare none of the SVHCs (https://echa.europa.eu/web/guest/candidate-list-table), the Candidate List of Substances of Very High Concern for authorization currently released by ECHA, is present in all products (and also package) in quantities totaling in a concentration equal or above 0.1%. To the best of our knowledge, we also declare that our products do not contain any of the substances listed on the "Authorization List" (Annex XIV of the REACH regulations) and Substances of Very High Concern (SVHC) in any significant amounts as specified by the Annex XVII of Candidate list published by ECHA (European Chemical Agency) 1907 /2006/EC.
</p>

### Conflict Minerals Declaration

<p style="text-align: justify;">
As a global supplier of electronic and electrical components, Arduino is aware of our obligations concerning laws and regulations regarding Conflict Minerals, specifically the Dodd-Frank Wall Street Reform and Consumer Protection Act, Section 1502. Arduino does not directly source or process conflict minerals such as Tin, Tantalum, Tungsten, or Gold. Conflict minerals are contained in our products in the form of solder, or as a component in metal alloys. As part of our reasonable due diligence, Arduino has contacted component suppliers within our supply chain to verify their continued compliance with the regulations. Based on the information received thus far we declare that our products contain Conflict Minerals sourced from conflict-free areas.
</p>

## Company Information

| **Company Information** | **Details**                                |
|-------------------------|--------------------------------------------|
| **Company Name**        | Arduino S.r.l.                             |
| **Company Address**     | Via Andrea Appiani, 25-20900 Monza (Italy) |

## Reference Documentation

| **No.** | **Reference**                   | **Link**                                           |
|:-------:|---------------------------------|----------------------------------------------------|
|    1    | Arduino IDE (Desktop)           | https://www.arduino.cc/en/Main/Software            |
|    2    | Arduino IDE (Cloud)             | https://create.arduino.cc/editor                   |
|    3    | Arduino Cloud - Getting Started | https://docs.arduino.cc/arduino-cloud/guides/overview/ |
|    4    | FTDI VCP Drivers                | https://ftdichip.com/drivers/vcp-drivers/          |
|    5    | Bughopper Documentation         | TBD                                                |
|    6    | Project Hub                     | https://create.arduino.cc/projecthub               |
|    7    | Library Reference               | https://www.arduino.cc/reference/en/               |
|    8    | Online Store                    | https://store.arduino.cc/                          |

## Document Revision History

|  **Date**  | **Revision** |       **Changes**       |
|:----------:|:------------:|:-----------------------:|
| TBD        |      1       |     First release       |