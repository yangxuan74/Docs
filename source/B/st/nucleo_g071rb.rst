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

.. _board_ststm32_nucleo_g071rb:

Nucleo G071RB
=============

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
    - `ST <https://www.st.com/en/evaluation-tools/nucleo-g071rb.html?utm_source=platformio.org&utm_medium=docs>`__


Configuration
-------------


.. code-block:: ini

  [env:nucleo_g071rb]
  platform = ststm32
  board = nucleo_g071rb

You can override default Nucleo G071RB settings per build environment using
``board_***`` option, where ``***`` is a JSON object path from
board manifest `nucleo_g071rb.json <https://github.com/platformio/platform-ststm32/blob/master/boards/nucleo_g071rb.json>`_. For example,
``board_build.mcu``, ``board_build.f_cpu``, etc.

.. code-block:: ini

  [env:nucleo_g071rb]
  platform = ststm32
  board = nucleo_g071rb

  ; change microcontroller
  board_build.mcu = stm32g071rbt6

  ; change MCU frequency
  board_build.f_cpu = 64000000L


Uploading
---------
Nucleo G071RB supports the following uploading protocols:

* ``blackmagic``
* ``cmsis-dap``
* ``jlink``
* ``mbed``
* ``stlink``

Default protocol is ``stlink``

.. code-block:: ini

  [env:nucleo_g071rb]
  platform = ststm32
  board = nucleo_g071rb

  upload_protocol = stlink

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

    * - :ref:`framework_stm32cube`
      - STM32Cube embedded software libraries, including: The HAL hardware abstraction layer, enabling portability between different STM32 devices via standardized API calls; The Low-Layer (LL) APIs, a light-weight, optimized, expert oriented set of APIs designed for both performance and runtime efficiency

    * - :ref:`framework_libopencm3`
      - The libOpenCM3 framework aims to create a free and open-source firmware library for various ARM Cortex-M0(+)/M3/M4 microcontrollers, including ST STM32, Ti Tiva and Stellaris, NXP LPC, Atmel SAM3, Energy Micro EFM32 and others
