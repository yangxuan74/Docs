.. |PIODebug| replace:: **PlatformIO Debugging Solution**

.. _piodebug:

Debugging
=========

.. contents:: 目录索引
    :local:
    :depth: 1

|PIODebug| offers a unique debugging experience for productive embedded
development. Using our multi-board and multi-architecture programming
experience, we simplified the debugging process in the same way. A zero
debugging configuration with support for the most popular debugging probes
and compatibility between IDEs and OS.

Developers can finally forget about complex UI windows which they need to
pre-configure before a simple “Hello World!” debugging session. No need to
know any aspects about the debugging server or how to configure it. PIO
Unified Debugger does this complex work automatically having a rich
configuration database per each board and debugging probe.

Just select a board, connect debugging probe (if a board does not have
onboard debugging interface), specify it in PlatformIO project configuration
file “platformio.ini”, and a project is ready for 1-Click debugging.


* "1-click" solution, zero configuration
* Support over 300+ embedded boards (see below)
* Multiple architectures and development platforms
* Windows, MacOS, Linux

.. hint::

  - Local, Global, and Static Variable Explorer
  - Conditional Breakpoints
  - Expressions and Watchpoints
  - Generic Registers
  - Peripheral Registers
  - Memory Viewer
  - Disassembly
  - Multi-thread support
  - A hot restart of an active debugging session

Configuration
-------------

|PIODebug| can be configured using :ref:`projectconf`:

.. toctree::
  :maxdepth: 2

  section_env_debug

.. _debugging_tools:

Tools & Debug Probes
--------------------

You can switch between debugging tools using :ref:`projectconf_debug_tool`
option.

.. warning::
  You will need to install debug tool drivers depending on your operating
  system. Please check "Drivers" section for debugging tool below.


.. _debugging_platforms:

Platforms
---------
.. list-table::
    :header-rows:  1

    * - Name
      - Description

    * - :ref:`p215`
      - The STM32 family of 32-bit Flash MCUs based on the ARM Cortex-M processor is designed to offer new degrees of freedom to MCU users. It offers a 32-bit product range that combines very high performance, real-time capabilities, digital signal processing, and low-power, low-voltage operation, while maintaining full integration and ease of development.

Frameworks
----------
.. list-table::
    :header-rows:  1

    * - Name
      - Description

    * - :ref:`framework_arduino`
      - Arduino Wiring-based Framework allows writing cross-platform software to control devices attached to a wide range of Arduino boards to create all kinds of creative coding, interactive objects, spaces or physical experiences

    * - :ref:`framework_cmsis`
      - The ARM Cortex Microcontroller Software Interface Standard (CMSIS) is a vendor-independent hardware abstraction layer for the Cortex-M processor series and specifies debugger interfaces. The CMSIS enables consistent and simple software interfaces to the processor for interface peripherals, real-time operating systems, and middleware. It simplifies software re-use, reducing the learning curve for new microcontroller developers and cutting the time-to-market for devices

    * - :ref:`framework_espidf`
      - ESP-IDF is the official development framework for the ESP32 and ESP32-S Series SoCs.

    * - :ref:`framework_stm32cube`
      - STM32Cube embedded software libraries, including: The HAL hardware abstraction layer, enabling portability between different STM32 devices via standardized API calls; The Low-Layer (LL) APIs, a light-weight, optimized, expert oriented set of APIs designed for both performance and runtime efficiency

    * - :ref:`framework_simba`
      - Simba is an RTOS and build framework with aims to make embedded programming easy and portable

    * - :ref:`framework_zephyr`
      - The Zephyr Project is a scalable real-time operating system (RTOS) supporting multiple hardware architectures, optimized for resource constrained devices, and built with safety and security in mind

    * - :ref:`framework_libopencm3`
      - The libOpenCM3 framework aims to create a free and open-source firmware library for various ARM Cortex-M0(+)/M3/M4 microcontrollers, including ST STM32, Ti Tiva and Stellaris, NXP LPC, Atmel SAM3, Energy Micro EFM32 and others

Boards
------

.. note::
    For more detailed ``board`` information please scroll tables below by horizontal.


