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

.. _cmd_lib_install:

pio lib install
===============

.. contents::

Usage
-----

.. code-block:: bash

    pio lib [STORAGE_OPTIONS] install [OPTIONS] [LIBRARY...]

    # RECOMMENDED
    # install all project dependencies declared via "lib_deps"
    # (run it from a project root where is located "platformio.ini")
    pio lib install [OPTIONS]

    # install project dependent library
    # (run it from a project root where is located "platformio.ini")
    pio lib install [OPTIONS] [LIBRARY...]

    # install dependencies for the specific project environment
    # (run it from a project root where is located "platformio.ini")
    pio lib -e myenv install [OPTIONS] [LIBRARY...]
    pio lib -d /path/to/platformio/project -e myenv install [OPTIONS] [LIBRARY...]

    # install to global storage (NOT RECOMMENDED)
    pio lib --global install [OPTIONS] [LIBRARY...]
    pio lib -g install [OPTIONS] [LIBRARY...]

    # install to custom storage
    pio lib --storage-dir /path/to/dir install [OPTIONS] [LIBRARY...]
    pio lib -d /path/to/dir1 -d /path/to/dir2 install [OPTIONS] [LIBRARY...]

    # [LIBRARY...] forms
    pio lib [STORAGE_OPTIONS] install (with no args, install project dependencies from "lib_deps")
    pio lib [STORAGE_OPTIONS] install <ownername/name>
    pio lib [STORAGE_OPTIONS] install <ownername/name>@<version>
    pio lib [STORAGE_OPTIONS] install <ownername/name>@<version range>
    pio lib [STORAGE_OPTIONS] install <zip or tarball url>
    pio lib [STORAGE_OPTIONS] install file://<zip or tarball file>
    pio lib [STORAGE_OPTIONS] install file://<folder>
    pio lib [STORAGE_OPTIONS] install <repository>
    pio lib [STORAGE_OPTIONS] install <name>=<repository> (name it should have locally)
    pio lib [STORAGE_OPTIONS] install <repository#tag> ("tag" can be commit, branch or tag)

.. warning::

  * **VSCode**: "Menu: View > Command Palette... > PlatformIO: Rebuild C/C++
    Project Index"

Description
-----------

Install a library, and any libraries that it depends on using:

1. `PlatformIO Library Registry <https://platformio.org/lib>`_
2. Custom folder, repository or archive.

The ``version`` supports `Semantic Versioning <https://devhints.io/semver>`_ (
``<major>.<minor>.<patch>``) and can take any of the following forms:

* ``^1.2.3`` - any compatible version (new functionality in a backwards compatible manner and patches are allowed, 1.x.x). **RECOMMENDED**
* ``~1.2.3`` - any version with the same major and minor versions, and an
  equal or greater patch version
* ``>1.2.3`` - any version greater than ``1.2.3``. ``>=``, ``<``, and ``<=``
  are also possible
* ``>0.1.0,!=0.2.0,<0.3.0`` - any version greater than ``0.1.0``, not equal to
  ``0.2.0`` and less than ``0.3.0``
* ``1.2.3`` - an exact version number. Use only this exact version.

PlatformIO supports installing from local directory or archive.
YOu need to use ``file://`` prefix before local path.

* ``file:///local/path/to/the/platform/dir``
* ``file:///local/path/to/the/platform.zip``
* ``file:///local/path/to/the/platform.tar.gz``

Storage Options
---------------

See base options for :ref:`cmd_lib`.

Options
-------

.. program:: pio lib install

.. option::
    --save / --no-save

.. option::
    -s, --silent

Suppress progress reporting.

.. option::
    -f, --force

Reinstall library if it is already installed.

Version control
---------------

PlatformIO supports installing from Git, Mercurial and Subversion, and detects
the type of VCS using url prefixes: "git+", "hg+", or "svn+".

.. note::
    PlatformIO requires a working VCS command on your path: ``git``, ``hg``
    or ``svn``.

