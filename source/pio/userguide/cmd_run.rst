.. _cmd_run:

pio run
=======

.. contents::

Usage
-----

.. code-block:: bash

    pio run [OPTIONS]


Description
-----------

Options
-------

.. program:: pio run

.. option::
    -e, --environment

Process specified environments. Multiple environments are allowed.

.. option::
    -t, --target

Process specified targets. Multiple targets are allowed.

You can configure default targets per project environment using
:ref:`projectconf_targets` option in :ref:`projectconf`.

.. option::
    --list-targets

.. versionadded:: 5.0

List available project targets. It's also possible to list targets per project
environment using :option:`pio run --environment` option.

There are also built-in system targets:

* Device

    + ``monitor`` automatically start :ref:`cmd_device_monitor` after successful
      build operation. You can configure monitor using
      :ref:`projectconf_section_env_monitor`.

* System

    + ``envdump`` dump current build environment

.. option::
    --upload-port

Custom upload port of embedded board. To print all available ports use
:ref:`cmd_device_list` command.

If upload port is not specified, PlatformIO will try to detect it automatically.

.. option::
    -d, --project-dir

Specify the path to project directory. By default, ``--project-dir`` is equal
to current working directory (``CWD``).

.. option::
    -c, --project-conf

Process project with a custom :ref:`projectconf`.

.. option::
    -j, --jobs

Control a number of parallel build jobs. Default is a number of CPUs in a system.

.. option::
    -s, --silent

Suppress progress reporting

.. option::
    -v, --verbose

Shows detailed information when processing environments.


.. option::
    --disable-auto-clean


Examples
--------

1. Process `Wiring Blink Example <https://github.com/platformio/platformio-examples/tree/develop/wiring-blink>`_

.. code::

    > pio run

    [Wed Sep  7 15:48:58 2016] Processing uno (platform: atmelavr, board: uno, framework: arduino)
    -----------------------------------------------------------------------------------------------
    Verbose mode can be enabled via `-v, --verbose` option
    Collected 36 compatible libraries
    Looking for dependencies...
    Project does not have dependencies
    Compiling .pio/build/uno/src/main.o
    Archiving .pio/build/uno/libFrameworkArduinoVariant.a
    Indexing .pio/build/uno/libFrameworkArduinoVariant.a
    Compiling .pio/build/uno/FrameworkArduino/CDC.o
    ...
    Compiling .pio/build/uno/FrameworkArduino/wiring_shift.o
    Archiving .pio/build/uno/libFrameworkArduino.a
    Indexing .pio/build/uno/libFrameworkArduino.a
    Linking .pio/build/uno/firmware.elf
    Building .pio/build/uno/firmware.hex
    Calculating size .pio/build/uno/firmware.elf
    AVR Memory Usage
    ----------------
    Device: atmega328p

    Program:    1034 bytes (3.2% Full)
    (.text + .data + .bootloader)

    Data:          9 bytes (0.4% Full)
    (.data + .bss + .noinit)


    =========================== [SUCCESS] Took 2.47 seconds ===========================

    [Wed Sep  7 15:49:01 2016] Processing nodemcu (platform: espressif8266, board: nodemcu, framework: arduino)
    -----------------------------------------------------------------------------------------------
    Verbose mode can be enabled via `-v, --verbose` option
    Collected 34 compatible libraries
    Looking for dependencies...
    Project does not have dependencies
    Compiling .pio/build/nodemcu/src/main.o
    Archiving .pio/build/nodemcu/libFrameworkArduinoVariant.a
    Indexing .pio/build/nodemcu/libFrameworkArduinoVariant.a
    Compiling .pio/build/nodemcu/FrameworkArduino/Esp.o
    Compiling .pio/build/nodemcu/FrameworkArduino/FS.o
    Compiling .pio/build/nodemcu/FrameworkArduino/HardwareSerial.o
    ...
    Archiving .pio/build/nodemcu/libFrameworkArduino.a
    Indexing .pio/build/nodemcu/libFrameworkArduino.a
    Linking .pio/build/nodemcu/firmware.elf
    Calculating size .pio/build/nodemcu/firmware.elf
    text       data     bss     dec     hex filename
    221240      888   29400  251528   3d688 .pio/build/nodemcu/firmware.elf
    Building .pio/build/nodemcu/firmware.bin
    =========================== [SUCCESS] Took 6.43 seconds ===========================

    [Wed Sep  7 15:49:07 2016] Processing teensy31 (platform: teensy, board: teensy31, framework: arduino)
    -----------------------------------------------------------------------------------------------
    Verbose mode can be enabled via `-v, --verbose` option
    Collected 96 compatible libraries
    Looking for dependencies...
    Project does not have dependencies
    Compiling .pio/build/teensy31/src/main.o
    Compiling .pio/build/teensy31/FrameworkArduino/AudioStream.o
    Compiling .pio/build/teensy31/FrameworkArduino/DMAChannel.o
    ...
    Compiling .pio/build/teensy31/FrameworkArduino/yield.o
    Archiving .pio/build/teensy31/libFrameworkArduino.a
    Indexing .pio/build/teensy31/libFrameworkArduino.a
    Linking .pio/build/teensy31/firmware.elf
    Calculating size .pio/build/teensy31/firmware.elf
    text       data     bss     dec     hex filename
    11288       168    2288   13744    35b0 .pio/build/teensy31/firmware.elf
    Building .pio/build/teensy31/firmware.hex
    =========================== [SUCCESS] Took 5.36 seconds ===========================

    [Wed Sep  7 15:49:12 2016] Processing lpmsp430g2553 (platform: timsp430, build_flags: -D LED_BUILTIN=RED_LED, board: lpmsp430g2553, framework: arduino)
    -----------------------------------------------------------------------------------------------
    Verbose mode can be enabled via `-v, --verbose` option
    Collected 29 compatible libraries
    Looking for dependencies...
    Project does not have dependencies
    Compiling .pio/build/lpmsp430g2553/src/main.o
    Compiling .pio/build/lpmsp430g2553/FrameworkAnergia/HardwareSerial.o
    Compiling .pio/build/lpmsp430g2553/FrameworkAnergia/IPAddress.o
    ...
    Compiling .pio/build/lpmsp430g2553/FrameworkAnergia/wiring_digital.o
    Compiling .pio/build/lpmsp430g2553/FrameworkAnergia/wiring_pulse.o
    Compiling .pio/build/lpmsp430g2553/FrameworkAnergia/wiring_shift.o
    Archiving .pio/build/lpmsp430g2553/libFrameworkAnergia.a
    Indexing .pio/build/lpmsp430g2553/libFrameworkAnergia.a
    Linking .pio/build/lpmsp430g2553/firmware.elf
    Calculating size .pio/build/lpmsp430g2553/firmware.elf
    text       data     bss     dec     hex filename
    820           0      20     840     348 .pio/build/lpmsp430g2553/firmware.elf
    Building .pio/build/lpmsp430g2553/firmware.hex
    =========================== [SUCCESS] Took 2.34 seconds ===========================

