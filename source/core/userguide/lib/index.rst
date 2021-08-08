.. _cmd_lib:

Library Manager CLI
===================

Usage
-----

.. code-block:: bash

    # To print all available commands and options use
    pio lib --help
    pio lib COMMAND --help

Options
-------

.. program:: pio lib

.. option::
    -d, --storage-dir

.. option::
    -g, --global

.. option::
    -e, --environment

Manage libraries for the specific project build environments declared in
:ref:`projectconf`. Works for ``--storage-dir`` which is valid PlatformIO
project.


Commands
--------

.. toctree::
    :maxdepth: 2

    cmd_builtin
    cmd_install
    cmd_list
    cmd_register
    cmd_search
    cmd_show
    cmd_stats
    cmd_uninstall
    cmd_update
