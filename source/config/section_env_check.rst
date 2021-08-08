.. _projectconf_section_env_check:

Check options
-------------

.. contents::
    :local:

.. _projectconf_check_tool:

``check_tool``
^^^^^^^^^^^^^^

Type: ``String`` | Multiple: ``Yes`` | Default: ``cppcheck``

A name of the check tool used for analysis. This option is useful when you
want to check source code with two or more tools.

**Example**

.. code-block:: ini

    [env:myenv]
    platform = ...
    board = ...
    check_tool = cppcheck, clangtidy


.. _projectconf_check_patterns:

``check_patterns``
^^^^^^^^^^^^^^^^^^

Type: ``String (Pattern)`` | Multiple: ``Yes``


Another option for filtering source files is :option:`pio check --pattern` command.

**Example**

.. code-block:: ini

    [env:custom_check_patterns]
    platform = ...
    board = ...
    check_tool = clangtidy
    check_patterns =
      app/sources
      tests/hardware/*.c


.. _projectconf_check_flags:

``check_flags``
^^^^^^^^^^^^^^^

Type: ``String`` | Multiple: ``Yes``

Additional flags to be passed to the tool command line. This option is useful
when you want to adjust the check process to fit your project requirements.
By default, the flags are passed to all tools specified in :ref:`projectconf_check_tool`
section. To set individual flags, define tool name at the beginning of the line.

Another option for adding flags is :option:`pio check --flags` command.

**Example**

.. code-block:: ini

    [env:extra_check_flags]
    platform = ...
    board = ...
    check_tool = cppcheck, clangtidy
    check_flags =
      --common-flag
      cppcheck: --enable=performance --inline-suppr
      clangtidy: -fix-errors -format-style=mozilla


.. _projectconf_check_severity:

``check_severity``
^^^^^^^^^^^^^^^^^^

Type: ``String`` | Multiple: ``Yes`` | Default: ``low, medium, high``


Another option for filtering source files is :option:`pio check --severity` command.

**Example**

.. code-block:: ini

    [env:detect_only_medium_or_high_defects]
    platform = ...
    board = ...
    check_severity = medium, high
