..  Copyright (c) 2014-present PlatformIO <contact@platformio.org>
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
       http://www.apache.org/licenses/LICENSE-2.0
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

.. _cmd_platform_search:

pio platform search
===================

.. contents::

Usage
-----

.. code-block:: bash

    pio platform search QUERY [OPTIONS]

Description
-----------

Search for development :ref:`platforms`

Options
~~~~~~~

.. program:: pio platform search

.. option::
    --json-output

Return the output in `JSON <http://en.wikipedia.org/wiki/JSON>`_ format


Examples
--------

1. Print all available development platforms

.. code::

    > pio platform search

    atmelavr ~ Atmel AVR
    ====================
    Atmel AVR 8- and 32-bit MCUs deliver a unique combination of performance, power efficiency and design flexibility. Optimized to speed time to market-and easily adapt to new ones-they are based on the industrys most code-efficient architecture for C and assembly programming.

    Home: https://platformio.org/platforms/atmelavr
    Packages: toolchain-atmelavr, framework-arduinoavr, framework-simba, tool-avrdude, tool-micronucleus

    atmelsam ~ Atmel SAM
    ====================
    Atmel | SMART offers Flash- based ARM products based on the ARM Cortex-M0+, Cortex-M3 and Cortex-M4 architectures, ranging from 8KB to 2MB of Flash including a rich peripheral and feature mix.

    Home: https://platformio.org/platforms/atmelsam
    Packages: toolchain-gccarmnoneeabi, framework-arduinosam, framework-simba, tool-openocd, framework-mbed, tool-avrdude, tool-bossac

    espressif32 ~ Espressif 32
    ==========================
    Espressif Systems is a privately held fabless semiconductor company. They provide wireless communications and Wi-Fi chips which are widely used in mobile devices and the Internet of Things applications.

    Home: https://platformio.org/platforms/espressif32
    Packages: toolchain-xtensa32, framework-simba, framework-arduinoespressif32, framework-pumbaa, framework-espidf, tool-esptoolpy

    espressif8266 ~ Espressif 8266
    ==============================
    Espressif Systems is a privately held fabless semiconductor company. They provide wireless communications and Wi-Fi chips which are widely used in mobile devices and the Internet of Things applications.

    Home: https://platformio.org/platforms/espressif8266
    Packages: toolchain-xtensa, framework-simba, tool-esptool, tool-mkspiffs, tool-espotapy, framework-arduinoespressif8266, sdk-esp8266

    freescalekinetis ~ Freescale Kinetis
    ====================================
    Freescale Kinetis Microcontrollers is family of multiple hardware- and software-compatible ARM Cortex-M0+, Cortex-M4 and Cortex-M7-based MCU series. Kinetis MCUs offer exceptional low-power performance, scalability and feature integration.
    ...

2. Search for TI development platforms

.. code::

    > pio platform search texas

    timsp430 ~ TI MSP430
    ====================
    MSP430 microcontrollers (MCUs) from Texas Instruments (TI) are 16-bit, RISC-based, mixed-signal processors designed for ultra-low power. These MCUs offer the lowest power consumption and the perfect mix of integrated peripherals for thousands of applications.

    Home: https://platformio.org/platforms/timsp430
    Packages: toolchain-timsp430, tool-mspdebug, framework-energiamsp430, framework-arduinomsp430

    titiva ~ TI TIVA
    ================
    Texas Instruments TM4C12x MCUs offer the industrys most popular ARM Cortex-M4 core with scalable memory and package options, unparalleled connectivity peripherals, advanced application functions, industry-leading analog integration, and extensive software solutions.

    Home: https://platformio.org/platforms/titiva
    Packages: ldscripts, framework-libopencm3, toolchain-gccarmnoneeabi, tool-lm4flash, framework-energiativa

.. code::

    > pio platform search framework-mbed

    atmelsam ~ Atmel SAM
    ====================
    Atmel | SMART offers Flash- based ARM products based on the ARM Cortex-M0+, Cortex-M3 and Cortex-M4 architectures, ranging from 8KB to 2MB of Flash including a rich peripheral and feature mix.

    Home: https://platformio.org/platforms/atmelsam
    Packages: toolchain-gccarmnoneeabi, framework-arduinosam, framework-simba, tool-openocd, framework-mbed, ldscripts, tool-bossac

    freescalekinetis ~ Freescale Kinetis
    ====================================
    Freescale Kinetis Microcontrollers is family of multiple hardware- and software-compatible ARM Cortex-M0+, Cortex-M4 and Cortex-M7-based MCU series. Kinetis MCUs offer exceptional low-power performance, scalability and feature integration.

    Home: https://platformio.org/platforms/freescalekinetis
    Packages: framework-mbed, toolchain-gccarmnoneeabi

    nordicnrf51 ~ Nordic nRF51
    ==========================
    The Nordic nRF51 Series is a family of highly flexible, multi-protocol, system-on-chip (SoC) devices for ultra-low power wireless applications. nRF51 Series devices support a range of protocol stacks including Bluetooth Smart (previously called Bluetooth low energy), ANT and proprietary 2.4GHz protocols such as Gazell.

    Home: https://platformio.org/platforms/nordicnrf51
    Packages: framework-mbed, tool-rfdloader, toolchain-gccarmnoneeabi, framework-arduinonordicnrf51

    nxplpc ~ NXP LPC
    ================
    The NXP LPC is a family of 32-bit microcontroller integrated circuits by NXP Semiconductors. The LPC chips are grouped into related series that are based around the same 32-bit ARM processor core, such as the Cortex-M4F, Cortex-M3, Cortex-M0+, or Cortex-M0. Internally, each microcontroller consists of the processor core, static RAM memory, flash memory, debugging interface, and various peripherals.

    Home: https://platformio.org/platforms/nxplpc
    Packages: framework-mbed, toolchain-gccarmnoneeabi

    siliconlabsefm32 ~ Silicon Labs EFM32
    =====================================
    Silicon Labs EFM32 Gecko 32-bit microcontroller (MCU) family includes devices that offer flash memory configurations up to 256 kB, 32 kB of RAM and CPU speeds up to 48 MHz. Based on the powerful ARM Cortex-M core, the Gecko family features innovative low energy techniques, short wake-up time from energy saving modes and a wide selection of peripherals, making it ideal for battery operated applications and other systems requiring high performance and low-energy consumption.

    Home: https://platformio.org/platforms/siliconlabsefm32
    Packages: framework-mbed, toolchain-gccarmnoneeabi

    ststm32 ~ ST STM32
    ==================
    The STM32 family of 32-bit Flash MCUs based on the ARM Cortex-M processor is designed to offer new degrees of freedom to MCU users. It offers a 32-bit product range that combines very high performance, real-time capabilities, digital signal processing, and low-power, low-voltage operation, while maintaining full integration and ease of development.

    Home: https://platformio.org/platforms/ststm32
    Packages: framework-libopencm3, toolchain-gccarmnoneeabi, tool-stlink, framework-spl, framework-cmsis, framework-mbed, ldscripts

    teensy ~ Teensy
    ===============
    Teensy is a complete USB-based microcontroller development system, in a very small footprint, capable of implementing many types of projects. All programming is done via the USB port. No special programmer is needed, only a standard USB cable and a PC or Macintosh with a USB port.

    Home: https://platformio.org/platforms/teensy
    Packages: framework-arduinoteensy, tool-teensy, toolchain-gccarmnoneeabi, framework-mbed, toolchain-atmelavr, ldscripts
    ...
