
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
      - Description
      - wifi
      - ble
      - usb
      - can
      - eth
    * - :ref:`p511`
      - YES
      - YES
      - YES
      - YES
      - YES
      - YES
    * - :ref:`esp32`
      - YES
      - YES
      - YES
      - YES
      - YES
      - YES


开发工具
---------

* `platform-espressif32 <https://github.com/platformio/platform-espressif32/tree/master/examples?utm_source=platformio.org&utm_medium=docs>`_


.. include:: espidf_4.3.rst
.. include:: espidf_4.0.rst
