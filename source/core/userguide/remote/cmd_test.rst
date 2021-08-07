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

.. _cmd_remote_test:

pio remote test
===============

Helper command for remote :ref:`unit_testing`.

.. contents::

Usage
-----

.. code-block:: bash

    pio remote test [OPTIONS]

    # run tests on specified PlatformIO Remote Agent
    pio remote --agent NAME test [OPTIONS]

Description
-----------

Run remotely tests from PlatformIO based project. More details about PlatformIO
:ref:`unit_testing`.

This command allows you to apply the tests for the environments specified
in :ref:`projectconf`.

Options
-------

.. program:: pio remote test

.. option::
    -e, --environment

Process specified environments. More details :option:`pio run --environment`

.. option::
    -i, --ignore

Ignore tests where the name matches specified patterns. More than one
pattern is allowed. If you need to ignore some tests for the specific
environment, please take a look at :ref:`projectconf_test_ignore` option from
:ref:`projectconf`.

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

By default, :ref:`pioremote` processes project on a host machine and deploy
final testing firmware (program) to remote device (embedded board).

If you need to process project on remote machine, please use
:option:`pio remote test --force-remote` option. In this case,
:ref:`pioremote` will automatically synchronize your project with remote machine,
install required toolchains, frameworks, SDKs, etc., and process project.


.. option::
    --without-building

Skip building stage.

.. option::
    --without-uploading

Skip uploading stage

.. option::
    -v, --verbose

Shows detailed information when processing environments.

This option can also be set globally using :ref:`setting_force_verbose` setting
or by environment variable :envvar:`PLATFORMIO_SETTING_FORCE_VERBOSE`.

Examples
--------

For the examples please follow to :ref:`unit_testing` page.
