.. _part:

技术组件
===========

.. _openblt:

OpenBLT
-----------------

``MCU`` ``bootloader`` ``GPLv3``

`OpenBLT Repo <https://github.com/feaser/openblt>`_ |
`OpenBLT Home <https://www.feaser.com/openblt>`_

OpenBLT is an open source bootloader for STM32, XMC, HCS12 and other microcontroller targets.

OpenBLT enables you and your customers to update the firmware on your microcontroller based product. A major benefit of OpenBLT being open source is that you can customize and tweak the bootloader to your specific needs.

.. image:: ./images/openblt.jpg
    :target: https://github.com/feaser/openblt

.. note::
    该方案可以通过STM32CubeMX 查找 OpenBootloader打开示例工程

.. _mcuboot:

mcuboot
------------

``MCU`` ``bootloader``

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

.. note::
    该方案已被STM32 CubeMX支持，集成在相关示例中

.. _solution:

技术方案
===========

.. contents::
    :local:

.. _trezor:

trezor
------------

``MCU`` ``STM32`` ``Bitcoin``

.. image:: ./images/trezor.png
    :target: https://github.com/trezor


.. _rufus:

Rufus
------------

`Rufus GitHub <https://github.com/pbatard/rufus>`_ |
`Rufus Website <http://rufus.ie/zh/>`_

可以帮助格式化和创建可引导USB闪存盘的工具

* 需要把一些可引导的ISO格式的镜像（Windows，Linux，UEFI等）创建成USB安装盘的时候
* 需要使用一个还没有安装操作系统的设备的时候
* 需要从DOS系统刷写BIOS或者其他固件的时候
* 需要运行一个非常底层的工具的时候
