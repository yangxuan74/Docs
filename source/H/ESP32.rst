.. _h511:

ESP32
================

.. contents::

Hardware
--------

Platform :ref:`p511`: Espressif Systems is a privately held fabless semiconductor company. They provide wireless communications and Wi-Fi chips which are widely used in mobile devices and the Internet of Things applications.

.. list-table::

  * - **Microcontroller**
    - ESP32
  * - **Frequency**
    - 240MHz
  * - **Flash**
    - 4MB
  * - **RAM**
    - 320KB
  * - **Vendor**
    - `MakerAsia <http://iot-bits.com/nano32-esp32-development-board?utm_source=platformio.org&utm_medium=docs>`__


Configuration
-------------

.. code-block:: ini

  [env:nano32]
  platform = espressif32
  board = nano32

You can override default MakerAsia Nano32 settings per build environment using
``board_***`` option, where ``***`` is a JSON object path from
board manifest `nano32.json <https://github.com/platformio/platform-espressif32/blob/master/boards/nano32.json>`_. For example,
``board_build.mcu``, ``board_build.f_cpu``, etc.

.. code-block:: ini

  [env:nano32]
  platform = espressif32
  board = nano32

  ; change microcontroller
  board_build.mcu = esp32

  ; change MCU frequency
  board_build.f_cpu = 240000000L


Uploading
---------
MakerAsia Nano32 supports the following uploading protocols:

* ``espota``
* ``esptool``

Default protocol is ``esptool``

.. code-block:: ini

  [env:nano32]
  platform = espressif32
  board = nano32

  upload_protocol = esptool

Debugging
---------
:ref:`piodebug` currently does not support MakerAsia Nano32 board.

Frameworks
----------
.. list-table::
    :header-rows:  1

    * - Name
      - Description

    * - :ref:`framework_arduino`
      - Arduino Wiring-based Framework allows writing cross-platform software to control devices attached to a wide range of Arduino boards to create all kinds of creative coding, interactive objects, spaces or physical experiences

    * - :ref:`framework_espidf`
      - ESP-IDF is the official development framework for the ESP32 and ESP32-S Series SoCs.

    * - :ref:`framework_pumbaa`
      - Pumbaa is Python on top of Simba. The implementation is a port of MicroPython, designed for embedded devices with limited amount of RAM and code memory

    * - :ref:`framework_simba`
      - Simba is an RTOS and build framework with aims to make embedded programming easy and portable
