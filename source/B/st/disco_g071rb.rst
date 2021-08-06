.. _board_ststm32_disco_g071rb:

STM32G071RB
================

.. contents::

Hardware
--------

.. list-table::

  * - **Microcontroller**
    - STM32G071RBT6
  * - **Frequency**
    - 64MHz
  * - **Flash**
    - 128KB
  * - **RAM**
    - 36KB
  * - **Vendor**
    - `ST <https://www.st.com/en/evaluation-tools/stm32g071b-disco.html?utm_source=platformio.org&utm_medium=docs>`__


Configuration
-------------

.. code-block:: ini

  [env:disco_g071rb]
  platform = ststm32
  board = disco_g071rb

You can override default ST STM32G071B Discovery settings per build environment using
``board_***`` option, where ``***`` is a JSON object path from
board manifest `disco_g071rb.json <https://github.com/platformio/platform-ststm32/blob/master/boards/disco_g071rb.json>`_. For example,
``board_build.mcu``, ``board_build.f_cpu``, etc.

.. code-block:: ini

  [env:disco_g071rb]
  platform = ststm32
  board = disco_g071rb

  ; change microcontroller
  board_build.mcu = stm32g071rbt6

  ; change MCU frequency
  board_build.f_cpu = 64000000L


Uploading
---------
ST STM32G071B Discovery supports the following uploading protocols:

* ``blackmagic``
* ``cmsis-dap``
* ``jlink``
* ``mbed``
* ``stlink``

Default protocol is ``stlink``

.. code-block:: ini

  [env:disco_g071rb]
  platform = ststm32
  board = disco_g071rb

  upload_protocol = stlink


Frameworks
----------
.. list-table::
    :header-rows:  1

    * - Name
      - Description

    * - :ref:`framework_cmsis`
      - The ARM Cortex Microcontroller Software Interface Standard (CMSIS) is a vendor-independent hardware abstraction layer for the Cortex-M processor series and specifies debugger interfaces. The CMSIS enables consistent and simple software interfaces to the processor for interface peripherals, real-time operating systems, and middleware. It simplifies software re-use, reducing the learning curve for new microcontroller developers and cutting the time-to-market for devices

    * - :ref:`framework_stm32cube`
      - STM32Cube embedded software libraries, including: The HAL hardware abstraction layer, enabling portability between different STM32 devices via standardized API calls; The Low-Layer (LL) APIs, a light-weight, optimized, expert oriented set of APIs designed for both performance and runtime efficiency

    * - :ref:`framework_libopencm3`
      - The libOpenCM3 framework aims to create a free and open-source firmware library for various ARM Cortex-M0(+)/M3/M4 microcontrollers, including ST STM32, Ti Tiva and Stellaris, NXP LPC, Atmel SAM3, Energy Micro EFM32 and others
