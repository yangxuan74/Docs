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

.. _cmd_package_publish:

pio package publish
===================

.. versionadded:: 5.0

.. contents::

Usage
-----

.. code-block:: bash

    pio package publish [<source directory, tar.gz or zip>] [OPTIONS]


Description
-----------

Options
~~~~~~~

.. program:: pio package publish

.. option::
    --owner

.. option::
    --released-at

Custom release date and time in the next format (UTC): 2014-06-13 17:08:52

.. option::
    --private

.. note::
    The permission to set custom release dates and times is only available to Super Admins.

Restrict access to a package (will not be available publicly). The default is to publish
a package publicly.

.. option::
  --no-notify

Do not notify by email when package is processed. The default behavior is to notify.

.. option::
  --non-interactive

Do not show interactive prompt.

