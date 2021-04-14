# CYSBSYSKIT-DEV-01 BSP

## Overview

The CYSBSYSKIT-DEV-01 Rapid IoT Connect Developer Kit allows for evaluation of the CYSBSYS-RP01 Rapid IoT Connect module on a standard Feather form factor. The CYSBSYS-RP01 Rapid IoT Connect module is a turnkey module that enables secure, scalable, and reliable compute and connect.

![](docs/html/board.png)

To use code from the BSP, simply include a reference to `cybsp.h`.

## Features

### Kit Features:

* CYSBSYS-RP01 module
* Support of up to 2MB Flash and 1MB SRAM
* 512-Mbit external Quad SPI NOR Flash that provides a fast, expandable memory for data and code
* KitProg3 on-board SWD programmer/debugger, USB-UART, and USB-I2C bridge functionality
* A user LED, a user button, and a reset button
* Battery connector, charging IC, and charging indicator LED
* One KitProg3 mode button, one KitProg3 status LED, and one KitProg3 power LED
* OPTIGA™ Trust M advanced security controller for secure data storage
* Thermistor for sensing the ambient temperature
* 16KB of Emulated EEPROM
* Feather compatible pin header
* Dedicated SDHC to interface with WICED wireless devices.
* Delivers dual-cores, with a 150-MHz Arm Cortex-M4 as the primary application processor and a 100-MHz Arm Cortex-M0+ as the secondary processor for low-power operations.
* Supports Full-Speed USB, a Quad-SPI interface, 13 serial communication blocks, 7 programmable analog blocks, and 56 programmable digital blocks.

### Kit Contents:

* CYSBSYSKIT-DEV-01 Rapid IoT Connect Developer Edition Kit
* Adafruit 128 x 32 OLED Screen FeatherWing (Adafruit product ID: 2900)

## BSP Configuration

The BSP has a few hooks that allow its behavior to be configured. Some of these items are enabled by default while others must be explicitly enabled. Items enabled by default are specified in the CYSBSYSKIT-DEV-01.mk file. The items that are enabled can be changed by creating a custom BSP or by editing the application makefile.

Components:
* Device specific category reference (e.g.: CAT1) - This component, enabled by default, pulls in any device specific code for this board.
* BSP_DESIGN_MODUS - This component, enabled by default, causes the Configurator generated code for this specific BSP to be included. This should not be used at the same time as the CUSTOM_DESIGN_MODUS component.
* CUSTOM_DESIGN_MODUS - This component, disabled by default, causes the Configurator generated code from the application to be included. This assumes that the application provides configurator generated code. This should not be used at the same time as the BSP_DESIGN_MODUS component.

Defines:
* CYBSP_WIFI_CAPABLE - This define, disabled by default, causes the BSP to initialize the interface to an onboard wireless chip if it has one.
* CY_USING_HAL - This define, enabled by default, specifies that the HAL is intended to be used by the application. This will cause the BSP to include the applicable header file and to initialize the system level drivers.

### Clock Configuration

| Clock    | Source    | Output Frequency |
|----------|-----------|------------------|
| FLL      | IMO       | 100.0 MHz        |
| PLL      | IMO       | 48.0 MHz         |
| CLK_HF0  | CLK_PATH0 | 100 MHz          |
| CLK_HF2  | CLK_PATH0 | 100 MHz          |

### Power Configuration

* System Active Power Mode: LP
* System Idle Power Mode: Deep Sleep
* VDDA Voltage: 3300 mV
* VDDD Voltage: 1800 mV

See the [BSP Setttings][settings] for additional board specific configuration settings.

## API Reference Manual

The CYSBSYSKIT-DEV-01 Board Support Package provides a set of APIs to configure, initialize and use the board resources.

See the [BSP API Reference Manual][api] for the complete list of the provided interfaces.

## More information
* [CYSBSYSKIT-DEV-01 BSP API Reference Manual][api]
* [CYSBSYSKIT-DEV-01 Documentation](http://www.cypress.com/CYSBSYSKIT-DEV-01)
* [Cypress Semiconductor, an Infineon Technologies Company](http://www.cypress.com)
* [Cypress Semiconductor GitHub](https://github.com/cypresssemiconductorco)
* [ModusToolbox](https://www.cypress.com/products/modustoolbox-software-environment)

[api]: https://cypresssemiconductorco.github.io/TARGET_CYSBSYSKIT-DEV-01/html/modules.html
[settings]: https://cypresssemiconductorco.github.io/TARGET_CYSBSYSKIT-DEV-01/html/md_bsp_settings.html

---
© Cypress Semiconductor Corporation, 2019-2021.