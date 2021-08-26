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

.. _cmd_package_pack:

pio package pack
================

.. versionadded:: 5.0

.. contents::

Usage
-----

.. code-block:: bash

    pio package pack [<source directory, tar.gz or zip>] [OPTIONS]

Description
-----------


:Tool:
  A ``package.json`` is a manifest file of a tool package. It is intended for toolchains,
  flashers, debugging servers, simulators, and other tools.

See a `manifest validation scheme <https://github.com/platformio/platformio-core/blob/develop/platformio/package/manifest/schema.py>`_.

Options
~~~~~~~

.. program:: pio package pack

.. option::
    -o, --output

Specify a destination path (folder or a full path to file) where to store a tarball.
The default is to create a tarball in the current working directory.
