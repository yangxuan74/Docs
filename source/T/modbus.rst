.. _modbus:

modbus
==============

* 关键词：``STM32`` ``FreeRTOS`` ``Modbus``
* 资源库：`GitHub <https://github.com/OS-Q/T21>`_

.. contents::
    :local:

.. note::
    意法半导体ST是全球最大的半导体公司之一，是MCU领域的王者，STM32 HAL库具有很好的迁移适配能力。

FreeRTOS
--------------
任务分配
~~~~~~~~~~~~~~

Modbus
-------------------
.. warning::
    目前的串口DMA和TCP无法同时使用，需要更新。

工程示例
-------------------

.. code-block:: ini

    Examples
    ├── STM32F103 --> USB-CDC Master/Slave
    ├── STM32F429 --> NUCLEO-F429ZI Modbus TCP/RTU (DMA) master/slave
    LIB --> Library Folder
        ├── Inc
        │    └── Modbus.h
        └── Src
            ├── Modbus.c
            └── UARTCallback.c


.. hint::
    :ref:`t21` 适配STM32平台
