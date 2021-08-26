.. _cmd_remote_test:

pio remote test
===============

.. contents::

Usage
-----

.. code-block:: bash

    pio remote test [OPTIONS]

    # run tests on specified PlatformIO Remote Agent
    pio remote --agent NAME test [OPTIONS]

Description
-----------

Options
-------

.. program:: pio remote test

.. option::
    -e, --environment

Process specified environments. More details :option:`pio run --environment`

.. option::
    -i, --ignore

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

For example, ``pio remote test --ignore "mytest*" -i "test[13]"``

.. option::
    --upload-port

A port that is intended for firmware uploading. To list available ports
please use :ref:`cmd_device_list` command.

If upload port is not specified, PlatformIO will try to detect it automatically.

.. option::
    --test-port

A Serial/UART port that PlatformIO uses as communication interface between
PlatformIO Unit Test Engine and target device. To list available ports
please use :ref:`cmd_device_list` command.

If test port is not specified, PlatformIO will try to detect it automatically.

.. option::
    -d, --project-dir

Specify the path to project directory. By default, ``--project-dir`` is equal
to current working directory (``CWD``).

.. option::
    -r, --force-remote

.. option::
    --without-building

Skip building stage.

.. option::
    --without-uploading

Skip uploading stage

.. option::
    -v, --verbose

