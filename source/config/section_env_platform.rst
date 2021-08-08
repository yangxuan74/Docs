
.. _projectconf_section_env_platform:

Platform options
----------------

.. contents::
    :local:

.. _projectconf_env_platform:

``platform``
^^^^^^^^^^^^

Type: ``String`` | Multiple: ``No``

:ref:`platforms` name.

PlatformIO allows one to use specific version of platform using
`Semantic Versioning <https://devhints.io/semver>`_ (X.Y.Z=MAJOR.MINOR.PATCH) or VCS
(Git, Mercurial and Subversion).

Version specifications can take any of the following forms:

* ``1.2.3``: an exact version number. Use only this exact version
* ``^1.2.3``: any compatible version (exact version for ``1.x.x`` versions)
* ``~1.2.3``: any version with the same major and minor versions, and an
  equal or greater patch version
* ``>1.2.3``: any version greater than ``1.2.3``. ``>=``, ``<``, and ``<=``
  are also possible
* ``>0.1.0,!=0.2.0,<0.3.0``: any version greater than ``0.1.0``, not equal to
  ``0.2.0`` and less than ``0.3.0``

Examples:

.. code-block:: ini

    [env:the_latest_version]
    platform = atmelavr

    [env:exact_version]
    platform = atmelavr@1.2.3

    [env:specific_major_version]
    platform = atmelavr@^1.2.3

    [env:specific_major_and_minor_version]
    platform = atmelavr@~1.2.3

    [env:development_verion_by_git]
    platform = https://github.com/platformio/platform-ststm32.git

    [env:custom_git_branch]
    platform = https://github.com/platformio/platform-espressif8266.git#feature/stage

    [env:specific_git_commit]
    platform = https://github.com/platformio/platform-espressif8266.git#921855a9c530082efddb5d48b44c3f4be0e2dfa2

.. _projectconf_env_platform_packages:

``platform_packages``
^^^^^^^^^^^^^^^^^^^^^

Type: ``String`` | Multiple: ``Yes``

Examples:

.. code-block:: ini

    [env:override_default_toolchain]
    platform = atmelavr
    platform_packages =
      ; use GCC AVR 5.0+
      toolchain-gccarmnoneeabi@>1.50000.0

    [env:override_framework]
    platform = espressif8266
    platform_packages =
      ; use upstream Git version
      framework-arduinoespressif8266 @ https://github.com/esp8266/Arduino.git

    [env:external_package]
    platform = ststm32
    platform_packages =
      ; latest openOCD from PlatformIO Package Registry
      tool-openocd

      ; source code of ST-Link
      tool-stlink-source @ https://github.com/texane/stlink.git

.. _projectconf_env_framework:

``framework``
^^^^^^^^^^^^^

Type: ``String`` | Multiple: ``Yes``

:ref:`frameworks` name.


.. _projectconf_env_board:

``board``
^^^^^^^^^

Type: ``String (ID)`` | Multiple: ``No``

*PlatformIO* has pre-configured settings for the most popular boards:

- build configuration
- upload configuration
- debugging configuration
- connectivity information, etc.

``board_build.mcu``
^^^^^^^^^^^^^^^^^^^

Type: ``String`` | Multiple: ``No``

.. _projectconf_board_build.f_cpu:

``board_build.f_cpu``
^^^^^^^^^^^^^^^^^^^^^

Type: ``Number`` | Multiple: ``No``

The option ``board_build.f_cpu`` is used to define MCU frequency (Hertz, Clock). A
format of this option is ``C-like long integer`` value with ``L`` suffix. The
1 Hertz is equal to ``1L``, then 16 MHz (Mega Hertz) is equal to ``16000000L``.

.. _projectconf_board_build.ldscript:

``board_build.ldscript``
^^^^^^^^^^^^^^^^^^^^^^^^

Type: ``String`` | Multiple: ``No``

Path to the linker script to be used instead of the one defined by a framework. This
is useful for specifying a modified linker script, for example, when an application
requires a special memory section for a bootloader.

.. _projectconf_board_more_options:

More options
^^^^^^^^^^^^

You can override any board option declared in manifest file using the next
format ``board_{OBJECT.PATH}``, where ``{OBJECT.PATH}`` is an object path in
JSON manifest. Please navigate to "boards" folder of `PlatfomIO development platforms <https://github.com/topics/platformio-platform>`_
and open JSON file to list all available options.

For example, `Manifest: Espressif ESP32 Dev Module <https://github.com/platformio/platform-espressif32/blob/develop/boards/esp32dev.json>`_:

.. code-block:: ini

    [env:custom_board_options]
    ; Custom CPU Frequency
    board_build.f_cpu = 160000000L

    ; Custom FLASH Frequency
    board_build.f_flash = 80000000L

    ; Custom FLASH Mode
    board_build.flash_mode = qio

    ; Custom linker script
    board_build.ldscript = /path/to/ldscript.ld

    ; Custom maximum program size
    board_upload.maximum_size = 1310720
