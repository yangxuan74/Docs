
.. _frameworks:

开发框架
============

.. contents::
    :local:


编程框架
-----------

.. toctree::
    :maxdepth: 1

    Arduino  <arduino>
    ESP-IDF  <espidf>
    cmsis
    libopencm3
    stm32cube

系统框架
-----------

.. toctree::
    :maxdepth: 1

    Zephyr <zephyr>
    freeRTOS <freertos>


图形框架
-----------
.. toctree::
    :maxdepth: 1

    TouchGFX <touchgfx>
    LittlevGL <littlevgl>

在单片机领域的GUI框架有：ucgui（STemWin/emwin）、TouchGFX、GuiLite、LittlevGL等。

emwin提供的更多是一些较底层的函数（如：画线、画圆），而且不能拖控件，做出来的界面更接近像素时代的产物。在emwin的开发中，要想显示图片，需要把图片转成bmp格式，再用BmpCvt转成数组，最后才用emwin的函数去调用这个数组，这是比较麻烦的。

TouchGFX都可以很好的解决这些问题，但是只能用于STM32的单片机上，TouchGFX还支持直接生成MDK/IAR工程。

.. note::
    GUI(Graphical User Interface) 图形用户界面。
