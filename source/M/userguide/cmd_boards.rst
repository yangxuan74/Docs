
.. _cmd_boards:

板级支持
==========

.. contents::

Usage
-----

.. code-block:: bash

    pio boards [OPTIONS] [FILTER]

Description
-----------

List pre-configured Embedded Boards

Options
~~~~~~~

.. program:: pio boards

.. option::
    --installed

List boards only from the installed platforms

.. option::
    --json-output

Return the output in `JSON <http://en.wikipedia.org/wiki/JSON>`_ format

Examples
--------

1. Show all available pre-configured embedded boards

.. code-block:: bash

    > pio boards

    Platform: atmelavr
    ---------------------------------------------------------------------------
    ID                    MCU           Frequency  Flash   RAM    Name
    ---------------------------------------------------------------------------
    btatmega168           atmega168     16MHz     14K    1K    Arduino BT ATmega168
    btatmega328           atmega328p    16MHz     28K    2K    Arduino BT ATmega328
    diecimilaatmega168    atmega168     16MHz     14K    1K    Arduino Duemilanove or Diecimila ATmega168
    diecimilaatmega328    atmega328p    16MHz     30K    2K    Arduino Duemilanove or Diecimila ATmega328
    esplora               atmega32u4    16MHz     28K    2K    Arduino Esplora
    ethernet              atmega328p    16MHz     31K    2K    Arduino Ethernet
    ...

2. Filter Arduino-based boards

.. code-block:: bash

    > pio boards arduino

    Platform: atmelavr
    ---------------------------------------------------------------------------
    ID                    MCU           Frequency  Flash   RAM    Name
    ---------------------------------------------------------------------------
    btatmega168           atmega168     16MHz     14K    1K    Arduino BT ATmega168
    btatmega328           atmega328p    16MHz     28K    2K    Arduino BT ATmega328
    diecimilaatmega168    atmega168     16MHz     14K    1K    Arduino Duemilanove or Diecimila ATmega168
    diecimilaatmega328    atmega328p    16MHz     30K    2K    Arduino Duemilanove or Diecimila ATmega328
    esplora               atmega32u4    16MHz     28K    2K    Arduino Esplora
    ethernet              atmega328p    16MHz     31K    2K    Arduino Ethernet
    ...


3. Filter mbed-enabled boards

.. code-block:: bash

    > pio boards mbed

    Platform: ststm32
    ---------------------------------------------------------------------------
    ID                    MCU            Frequency  Flash   RAM    Name
    ---------------------------------------------------------------------------
    disco_f401vc          stm32f401vct6  84MHz     256K   64K   32F401CDISCOVERY
    nucleo_f030r8         stm32f030r8t6  48MHz     64K    8K    ST Nucleo F030R8
    ...
