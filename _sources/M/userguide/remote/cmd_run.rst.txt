.. _cmd_remote_run:

pio remote run
==============

**Remote Firmware Updates**

.. contents::

Usage
-----

.. code-block:: bash

    pio remote run [OPTIONS]

    # process environments using specified PlatformIO Remote Agent
    pio remote --agent NAME run [OPTIONS]

Description
-----------


Options
-------

.. program:: pio remote run

.. option::
    -e, --environment

Process specified environments.

.. option::
    -t, --target

Process specified targets. See :option:`pio run --list-targets` documentation
for available targets.

.. option::
    --upload-port

If upload port is not specified, PlatformIO will try to detect it automatically.

.. option::
    -d, --project-dir

Specify the path to project directory. By default, ``--project-dir`` is equal
to current working directory (``CWD``).

.. option::
    -v, --verbose

Shows detailed information when processing environments.

.. option::
    --disable-auto-clean


.. option::
    -r, --force-remote

Example
-------

.. code::

    > pio remote run --environment uno --target upload

    Building project locally
    [Wed Oct 26 16:35:09 2016] Processing uno (platform: atmelavr, board: uno, framework: arduino)
    --------------------------------------------------------------------------------
    Verbose mode can be enabled via `-v, --verbose` option
    Collected 25 compatible libraries
    Looking for dependencies...
    Project does not have dependencies
    Compiling .pio/build/uno/src/main.o
    Archiving .pio/build/uno/libFrameworkArduinoVariant.a
    Indexing .pio/build/uno/libFrameworkArduinoVariant.a
    Compiling .pio/build/uno/FrameworkArduino/CDC.o
    Compiling .pio/build/uno/FrameworkArduino/HardwareSerial.o
    Compiling .pio/build/uno/FrameworkArduino/HardwareSerial0.o
    Compiling .pio/build/uno/FrameworkArduino/HardwareSerial1.o
    Compiling .pio/build/uno/FrameworkArduino/HardwareSerial2.o
    Compiling .pio/build/uno/FrameworkArduino/HardwareSerial3.o
    Compiling .pio/build/uno/FrameworkArduino/IPAddress.o
    Compiling .pio/build/uno/FrameworkArduino/PluggableUSB.o
    Compiling .pio/build/uno/FrameworkArduino/Print.o
    Compiling .pio/build/uno/FrameworkArduino/Stream.o
    Compiling .pio/build/uno/FrameworkArduino/Tone.o
    Compiling .pio/build/uno/FrameworkArduino/USBCore.o
    Compiling .pio/build/uno/FrameworkArduino/WInterrupts.o
    Compiling .pio/build/uno/FrameworkArduino/WMath.o
    Compiling .pio/build/uno/FrameworkArduino/WString.o
    Compiling .pio/build/uno/FrameworkArduino/_wiring_pulse.o
    Compiling .pio/build/uno/FrameworkArduino/abi.o
    Compiling .pio/build/uno/FrameworkArduino/hooks.o
    Compiling .pio/build/uno/FrameworkArduino/main.o
    Compiling .pio/build/uno/FrameworkArduino/new.o
    Compiling .pio/build/uno/FrameworkArduino/wiring.o
    Compiling .pio/build/uno/FrameworkArduino/wiring_analog.o
    Compiling .pio/build/uno/FrameworkArduino/wiring_digital.o
    Compiling .pio/build/uno/FrameworkArduino/wiring_pulse.o
    Compiling .pio/build/uno/FrameworkArduino/wiring_shift.o
    Archiving .pio/build/uno/libFrameworkArduino.a
    Indexing .pio/build/uno/libFrameworkArduino.a
    Linking .pio/build/uno/firmware.elf
    Checking program size
    Building .pio/build/uno/firmware.hex
    text       data     bss     dec     hex filename
    2574         48     168    2790     ae6 .pio/build/uno/firmware.elf
    ========================= [SUCCESS] Took 10.01 seconds =======================
    ================================== [SUMMARY] =================================
    Environment nodemcuv2   [SKIP]
    Environment uno_pic32   [SKIP]
    Environment teensy31    [SKIP]
    Environment uno         [SUCCESS]
    ========================= [SUCCESS] Took 10.01 seconds ========================
    Uploading firmware remotely
    [Wed Oct 26 19:35:20 2016] Processing uno (platform: atmelavr, board: uno, framework: arduino)
    ----------------------------------------------------------------------------------------------
    Verbose mode can be enabled via `-v, --verbose` option
    Looking for upload port...
    Auto-detected: /dev/cu.usbmodemFA1431
    Uploading .pio/build/uno/firmware.hex
    avrdude: AVR device initialized and ready to accept instructions
    Reading | ################################################## | 100% 0.00s
    avrdude: Device signature = 0x1e950f
    avrdude: reading input file ".pio/build/uno/firmware.hex"
    avrdude: writing flash (2622 bytes):
    Writing | ################################################## | 100% 0.43s
    avrdude: 2622 bytes of flash written
    avrdude: verifying flash memory against .pio/build/uno/firmware.hex:
    avrdude: load data flash data from input file .pio/build/uno/firmware.hex:
    avrdude: input file .pio/build/uno/firmware.hex contains 2622 bytes
    avrdude: reading on-chip flash data:
    Reading | ################################################## | 100% 0.34s
    avrdude: verifying ...
    avrdude: 2622 bytes of flash verified
    avrdude done.  Thank you.
    ========================= [SUCCESS] Took 3.04 seconds =======================
    ========================= [SUMMARY] =========================================
    Environment nodemcuv2   [SKIP]
    Environment uno_pic32   [SKIP]
    Environment teensy31    [SKIP]
    Environment uno         [SUCCESS]
    ========================= [SUCCESS] Took 3.04 seconds ========================
