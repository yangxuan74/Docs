
.. _cmd_debug:

pio debug
=========

Helper command for :ref:`piodebug`.

.. contents::

Usage
-----

.. code-block:: bash

    pio debug [OPTIONS]

    # A binary shortcut for "pio debug --interface=gdb" command
    piodebuggdb [GDB OPTIONS]


Description
-----------

Prepare PlatformIO project for debugging or launch debug server.


Options
-------

.. program:: pio debug

.. option::
    -e, --environment

Debug specified environments.

.. option::
    -d, --project-dir
