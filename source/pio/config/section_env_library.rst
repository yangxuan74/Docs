.. _projectconf_section_env_library:

Library options
---------------


.. contents::
    :local:

.. _projectconf_lib_deps:

``lib_deps``
^^^^^^^^^^^^

Type: ``String`` | Multiple: ``Yes``

**Valid forms**

.. code-block:: ini

  ; one line definition (comma + space)
  [env:myenv]
  lib_deps = LIBRARY_1, LIBRARY_2, LIBRARY_N

  ; multi-line definition
  [env:myenv2]
  lib_deps =
    LIBRARY_1
    LIBRARY_2
    LIBRARY_N

The each line with ``LIBRARY_1... LIBRARY_N`` will be passed automatically to
:ref:`cmd_lib_install` command.

Please check :ref:`cmd_lib_install` for the valid declaration formats.

Example:

.. code-block:: ini

  [env:myenv]
  lib_deps =
    ; name-based (built-in library in framework)
    SPI

    ; owner-based declaration
    knolleary/PubSubClient

    ; SemVer specification
    bblanchon/ArduinoJson @ ~5.6,!=5.4

    ; external Git resource
    https://github.com/gioblu/PJON.git#v2.0

    ; custom name
    IRremoteESP8266=https://github.com/markszabo/IRremoteESP8266/archive/master.zip


.. _projectconf_lib_ignore:

``lib_ignore``
^^^^^^^^^^^^^^

Type: ``String`` | Multiple: ``Yes``

Specify libraries which should be ignored by Library Dependency Finder.

The correct value for this option is a library name (not folder name).
You will see these names in "Library Dependency Graph" when building a project
between ``<`` and ``>`` symbols.

**Example:**

``Build output``

.. code::

    ...
    Library Dependency Finder -> http://bit.ly/configure-pio-ldf
    LDF MODES: FINDER(chain+) COMPATIBILITY(soft)
    Collected 54 compatible libraries
    Scanning dependencies...
    Dependency Graph
    |-- <Hash> v1.0
    |-- <AsyncMqttClient> v0.8.2
    |   |-- <ESPAsyncTCP> v1.1.3
    |-- <ESP8266WiFi> v1.0
    |-- <ESP Async WebServer> v1.1.1
    |   |-- <ESPAsyncTCP> v1.1.3
    |   |-- <ESP8266WiFi> v1.0
    |   |-- <Hash> v1.0
    |   |-- <ArduinoJson> v5.13.1
    |-- <ArduinoJson> v5.13.1
    |-- <DNSServer> v1.1.0
    |   |-- <ESP8266WiFi> v1.0
    |-- <Ticker> v1.0
    ....

``platformio.ini``

.. code-block:: ini

    [env:myenv]
    ; Single line
    lib_ignore = AsyncMqttClient, DNSServer

    ; Multi-line
    lib_ignore =
      AsyncMqttClient
      ESP Async WebServer

.. _projectconf_lib_extra_dirs:

``lib_extra_dirs``
^^^^^^^^^^^^^^^^^^

Type: ``DirPath`` | Multiple: ``Yes``

This option can also be set by global environment variable
:envvar:`PLATFORMIO_LIB_EXTRA_DIRS`.

.. warning::
  This is a not direct path to a library with source code. It should be a path
  to storage that contains libraries grouped by folders. For example,
  ``D:\PlatformIO\extra\libraries`` but not ``D:\PlatformIO\extra\libraries\FooLibrary``.

Example:

.. code-block:: ini

    [env:myenv]
    lib_extra_dirs =
        /common/libraries
        /iot/libraries

.. _projectconf_lib_ldf_mode:

``lib_ldf_mode``
^^^^^^^^^^^^^^^^

Type: ``String`` | Multiple: ``No`` | Default: ``chain``

Example:

.. code-block:: ini

    [env:myenv]
    ; evaluate C/C++ Preprocessor conditional syntax
    lib_ldf_mode = chain+

.. _projectconf_lib_compat_mode:

``lib_compat_mode``
^^^^^^^^^^^^^^^^^^^

Type: ``String`` | Multiple: ``No`` | Default: ``soft``

By default, this value is set to ``lib_compat_mode = soft`` and means that LDF
will check only for framework compatibility.

Example:

.. code-block:: ini

    [env:myenv]
    ; Checks for the compatibility with frameworks and dev/platforms
    lib_compat_mode = strict

.. _projectconf_lib_archive:

``lib_archive``
^^^^^^^^^^^^^^^

Type: ``Bool (yes or no)`` | Multiple: ``No`` | Default: ``yes``

Create an archive (``*.a``, static library) from the object files and link it
into a firmware (program). This is default behavior of PlatformIO Build System
(``lib_archive = yes``).

Setting ``lib_archive = no`` will instruct PlatformIO Build System to link object
files directly (in-line). This could be useful if you need to override ``weak``
symbols defined in framework or other libraries.

Example:

.. code-block:: ini

    [env:myenv]
    lib_archive = no
