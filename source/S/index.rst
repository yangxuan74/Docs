.. _solution:

技术方案
===========

.. contents::
    :local:

trezor
------------

.. image:: ./images/trezor.png
    :target: https://github.com/trezor


mcuboot
------------

MCUboot is a secure bootloader for 32-bit MCUs. The goal of MCUboot is to
define a common infrastructure for the bootloader, system flash layout on
microcontroller systems, and to provide a secure bootloader that enables
simple software upgrades.

MCUboot is operating system and hardware independent and relies on
hardware porting layers from the operating. Currently, mcuboot works
with both the Apache Mynewt and Zephyr operating systems, but more
ports are planned in the future. RIOT is currently supported as a boot
target with a complete port planned.

.. code-block:: bash

    boot/bootutil: The core of the bootloader itself.
    boot/boot_serial: Support for serial upgrade within the bootloader itself.
    boot/zephyr: Port of the bootloader to Zephyr
    boot/mynewt: Mynewt bootloader app
    boot/mbed: Port of the bootloader to Mbed-OS
    boot/nuttx: Bootloader application and port of MCUboot interfaces for NuttX.
    boot/espressif: Bootloader application and MCUboot port for Espressif SoCs.
    imgtool: A tool to securely sign firmware images for booting by MCUboot.
    sim: A bootloader simulator for testing and regression
