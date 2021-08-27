
.. _espidf:

ESP-IDF
============================

.. contents::
    :local:
    :depth: 1

框架简介
---------

`ESP-IDF <https://docs.espressif.com/projects/esp-idf/zh_CN/latest/esp32/index.html>`_ 是乐鑫官方的物联网开发框架，适用于乐鑫 ESP32、ESP32-S 和 ESP32-C 系列 SoC。
基于 C/C++ 语言提供了一个自给自足的 SDK，方便用户在这些平台上开发通用应用程序。
ESP-IDF 目前已服务支持数以亿计的物联网设备，并已开发构建了多种物联网产品，例如照明、消费电子大小家电、支付终端、工控等各类物联网设备。


平台特性
---------
.. list-table::
    :header-rows:  1

    * - Name
      - Core
      - RAM
      - WiFi
      - BLE
      - USB
      - TWAI
      - Ethernet
    * - `ESP32 <https://docs.soc.xin/ESP32>`_
      - 600 DMIPS
      - 520 KB
      - 802.11 b/g/n
      - v4.2
      - NO
      - YES
      - 10/100M
    * - `ESP32-S2 <https://docs.soc.xin/ESP32-S2>`_
      - 360 DMIPS
      - 320 KB
      - 802.11 b/g/n
      - NO
      - USB OTG
      - NO
      - NO
    * - `ESP32-S3 <https://docs.soc.xin/ESP32-S3>`_
      - 720 DMIPS
      - 512 KB
      - 802.11 b/g/n
      - v5.0
      - USB OTG
      - YES
      - NO
    * - `ESP32-C3 <https://docs.soc.xin/ESP32-C3>`_
      - 200 DMIPS
      - 400 KB
      - 802.11 b/g/n
      - v5.0
      - NO
      - YES
      - NO
    * - `ESP32-C6 <https://docs.soc.xin/ESP32-C6>`_
      - 200 DMIPS
      - 400 KB
      - 802.11 b/g/n
      - v5.2
      - NO
      - YES
      - NO



开发平台
---------

* `platform-espressif32 <https://github.com/platformio/platform-espressif32/tree/master/examples?utm_source=platformio.org&utm_medium=docs>`_

资源列表
~~~~~~~~~~~~

.. list-table::
    :header-rows:  1

    * - platform
      - xtensa32
      - xtensa32s2
      - esp32ulp
      - esp32s2ulp
      - riscv-esp
      - espidf
      - arduino
    * - 3.3.1
      - 5.2.0
      - 8.4.0
      - 2.28.51
      - 2.28.51
      - 8.4.0
      - 1.0.6
      - 4.3.0


.. include:: espidf_4.3.rst
.. include:: espidf_4.0.rst
