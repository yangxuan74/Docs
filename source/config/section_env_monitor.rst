.. _projectconf_section_env_monitor:

Monitor options
---------------

.. contents::
    :local:

.. _projectconf_monitor_port:

``monitor_port``
^^^^^^^^^^^^^^^^

Type: ``String`` | Multiple: ``No``

Port, a number or a device name, or valid `URL Handlers <https://pyserial.readthedocs.io/en/latest/url_handlers.html#urls>`__.
See :option:`pio device monitor --port`. To print all available serial ports please use :ref:`cmd_device_list` command.

Please note that you can use Unix shell-style wildcards:

.. list-table::
    :header-rows:  1

    * - Pattern
      - Meaning

    * - ``*``
      - matches everything

    * - ``?``
      - matches any single character

    * - ``[seq]``
      - matches any character in seq

    * - ``[!seq]``
      - matches any character not in seq

Example:

.. code-block:: ini

    [env:custom_monitor_port]
    ...
    ; Unix
    monitor_port = /dev/ttyUSB1

    ; Windows, COM1 or COM3
    monitor_port = COM[13]

    ; Socket
    monitor_port = socket://localhost:4444

.. _projectconf_monitor_speed:

``monitor_speed``
^^^^^^^^^^^^^^^^^

Type: ``Number`` | Multiple: ``No`` | Default: ``9600``

A monitor speed (`baud rate <http://en.wikipedia.org/wiki/Baud>`_).
See :option:`pio device monitor --baud`.

Example:

.. code-block:: ini

    [env:custom_monitor_speedrate]
    ...
    monitor_speed = 115200

.. _projectconf_monitor_filters:

``monitor_filters``
^^^^^^^^^^^^^^^^^^^

Type: ``String`` | Multiple: ``Yes``

Apply filters and text transformation for device output. See available filters at
:ref:`cmd_device_monitor_filters`.

Example:

.. code-block:: ini

    [env:log_output_to_file_with_timestamp]
    ...
    platform = ...
    monitor_filters = log2file, time, default

.. _projectconf_monitor_rts:

``monitor_rts``
^^^^^^^^^^^^^^^

Type: ``Number (0 or 1)`` | Multiple: ``No``

A monitor initial ``RTS`` line state. See :option:`pio device monitor --rts`.

.. _projectconf_monitor_dtr:

``monitor_dtr``
^^^^^^^^^^^^^^^

Type: ``Number (0 or 1)`` | Multiple: ``No``

A monitor initial ``DTR`` line state. See :option:`pio device monitor --dtr`.

.. _projectconf_monitor_flags:

``monitor_flags``
^^^^^^^^^^^^^^^^^

Type: ``String`` | Multiple: ``Yes``

Example:

.. code-block:: ini

    [env:extra_monitor_flags]
    platform = ...
    board = ...
    monitor_flags=
        --parity
        N
        --encoding
        hexlify
