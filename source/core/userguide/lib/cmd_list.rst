..  Copyright (c) 2014-present PlatformIO <contact@platformio.org>
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
       http://www.apache.org/licenses/LICENSE-2.0
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

.. _cmd_lib_list:

pio lib list
============

.. contents::

Usage
-----

.. code-block:: bash

    pio lib [STORAGE_OPTIONS] list [OPTIONS]

    # list project dependent libraries
    # (run it from a project root where is located "platformio.ini")
    pio lib list [OPTIONS]

    # list libraries from global storage
    pio lib --global list [OPTIONS]
    pio lib -g list [OPTIONS]

    # list libraries from custom storage
    pio lib --storage-dir /path/to/dir list [OPTIONS]
    pio lib -d /path/to/dir list [OPTIONS]

Description
-----------

List installed libraries

Storage Options
---------------

See base options for :ref:`cmd_lib`.

Options
-------

.. program:: pio lib list

.. option::
    --json-output

Return the output in `JSON <http://en.wikipedia.org/wiki/JSON>`_ format

Examples
--------

.. code::

    > pio lib -g list

    Library Storage: /storage/dir/...

    Adafruit Unified Sensor
    =======================
    #ID: 31
    Required for all Adafruit Unified Sensor based libraries.

    Version: 1.0.2
    Keywords: sensors
    Compatible frameworks: arduino
    Compatible platforms: atmelavr, atmelsam, espressif8266, intel_arc32, microchippic32, nordicnrf51, teensy, timsp430
    Authors: Adafruit

    ArduinoJson
    ===========
    #ID: 64
    An elegant and efficient JSON library for embedded systems

    Version: 5.8.0
    Keywords: web, json, http, rest
    Compatible frameworks: arduino
    Compatible platforms: atmelavr, atmelsam, espressif8266, intel_arc32, microchippic32, nordicnrf51, teensy, timsp430
    Authors: Benoit Blanchon

