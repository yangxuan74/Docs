
.. _ldf:

Library Dependency Finder (LDF)
===============================

Library Dependency Finder is a core part of PlatformIO Build System that
operates with the C/C++ source files and looks for ``#include ...``
directives to know what header directories to include for the compiler.


.. contents::

Configuration
-------------

Library Dependency Finder can be configured from :ref:`projectconf`:

.. toctree::
  :maxdepth: 2

  ../C/section_env_library

.. _ldf_storage:

Storage
-------


.. _ldf_mode:

Dependency Finder Mode
----------------------

A difference between ``chain/chain+`` and ``deep/deep+`` modes. For example,
there are 2 libraries:

* Library ``Foo`` with files:

  - ``Foo/foo.h``
  - ``Foo/foo.cpp``
  - ``Foo/extra.cpp``

* Library ``Bar`` with files:

  - ``Bar/bar.h``
  - ``Bar/bar.cpp``

:Case 1:

    * ``lib_ldf_mode = chain``
    * ``Foo/foo.h`` depends on the ``Bar`` library (contains ``#include <bar.h>``)
    * ``#include <foo.h>`` is located in one of the project source files

    Here the nested includes (``project file > foo.h > bar.h``) and LDF
    will find both libraries ``Foo`` and ``Bar``.

:Case 2:

    * ``lib_ldf_mode = chain``
    * ``Foo/extra.cpp`` depends on the ``Bar`` library (contains ``#include <bar.h>``)
    * ``#include <foo.h>`` is located in one of the project source files

    In this case, LDF will not find the ``Bar`` library because it doesn't know
    about the CPP file (``Foo/extra.cpp``).

:Case 3:

    * ``lib_ldf_mode = deep``
    * ``Foo/extra.cpp`` depends on ``Bar`` library (contains ``#include <bar.h>``)
    * ``#include <foo.h>`` is located in one of the project source files

    Firstly, LDF finds the ``Foo`` library, then it parses all sources
    from the ``Foo`` library and finds ``Foo/extra.cpp`` that depends
    on ``#include <bar.h>``.  Secondly, it will parse all sources from
    the ``Bar`` library. This operation continues until all
    dependencies will not be parsed.

.. _ldf_compat_mode:

Compatibility Mode
------------------

Compatibility mode allows one to control strictness of Library Dependency Finder.
If library contains one of manifest file (:ref:`library_json`,
``library.properties``, ``module.json``), then LDF check compatibility of this
library with real build environment. Available compatibility modes:

:``off``:
    Does not check for compatibility (is not recommended)


.. _ldf_c_cond_syntax:

C/C++ Preprocessor conditional syntax
-------------------------------------

In spite of the fact that Library Dependency Finder is written in pure Python,
it evaluates `C/C++ Preprocessor conditional syntax <https://gcc.gnu.org/onlinedocs/cpp/Conditional-Syntax.html#Conditional-Syntax>`_
(``#ifdef``, ``if``, ``defined``, ``else``, and ``elif``) without calling
``gcc -E``. For example,

``platformio.ini``

.. code-block:: ini

    [env:myenv]
    lib_ldf_mode = chain+
    build_flags = -D MY_PROJECT_VERSION=13

``mylib.h``

.. code-block:: c

    #ifdef MY_PROJECT_VERSION
    // include common file for the project
    #include "my_common.h"
    #endif

    #if MY_PROJECT_VERSION < 10
    // this include will be ignored because does not satisfy condition above
    #include "my_old.h"
    #endif
