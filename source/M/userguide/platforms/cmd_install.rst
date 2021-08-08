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

.. _cmd_platform_install:

pio platform install
====================

.. contents::

Usage
-----

.. code-block:: bash

    pio platform install [OPTIONS] [PLATFORM...]

    # [PLATFORM...] forms
    pio platform install <name>
    pio platform install <name>@<version>
    pio platform install <name>@<version range>
    pio platform install <ownername>@<version>
    pio platform install <ownername>@<version range>
    pio platform install <zip or tarball url>
    pio platform install file://<zip or tarball file>
    pio platform install file://<folder>
    pio platform install <repository>
    pio platform install <name=repository> (name it should have locally)
    pio platform install <repository#tag> ("tag" can be commit, branch or tag)

Options
-------

.. program:: pio platform install

.. option::
    --with-package

Install specified package (or alias)


.. option::
    --without-package

Do not install specified package (or alias)

.. option::
    --skip-default

Skip default packages

.. option::
    --with-all-packages

Install all declared packages in ``platform.json``

.. option::
    -f, --force

Reinstall/redownload development platform and its packages if they exist


Description
-----------


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

Also, PlatformIO supports installing from local directory or archive. Need to
use ``file://`` prefix before local path. Also, directory or archive should
contain ``platform.json`` manifest.

* ``file:///local/path/to/the/platform/dir``
* ``file:///local/path/to/the/platform.zip``
* ``file:///local/path/to/the/platform.tar.gz``

Version control
---------------

PlatformIO supports installing from Git, Mercurial and Subversion, and detects
the type of VCS using url prefixes: "git+", "hg+", or "svn+".

.. note::
    PlatformIO requires a working VCS command on your path: ``git``, ``hg``
    or ``svn``.

Git
^^^

The supported schemes are: ``git``, ``git+https`` and ``git+ssh``. Here are
the supported forms:

* https://github.com/platformio/platform-NAME.git
* git+git://git.server.org/my-platform
* git+https://git.server.org/my-platform
* git+ssh://git.server.org/my-platform
* git+ssh://user@git.server.org/my-platform
* [user@]host.xz:path/to/repo.git

Passing branch names, a commit hash or a tag name is possible like so:

* https://github.com/platformio/platform-name.git#master
* git+git://git.server.org/my-platform#master
* git+https://git.server.org/my-platform#v1.0
* git+ssh://git.server.org/my-platform#7846d8ad52f983f2f2887bdc0f073fe9755a806d

Mercurial
^^^^^^^^^

The supported schemes are: ``hg+http``, ``hg+https`` and ``hg+ssh``. Here are
the supported forms:

* hg+hg://hg.server.org/my-platform
* hg+https://hg.server.org/my-platform
* hg+ssh://hg.server.org/my-platform

Passing branch names, a commit hash or a tag name is possible like so:

* hg+hg://hg.server.org/my-platform#master
* hg+https://hg.server.org/my-platform#v1.0
* hg+ssh://hg.server.org/my-platform#4cfe2fa00668

Subversion
^^^^^^^^^^

The supported schemes are: ``svn``, ``svn+svn``, ``svn+http``, ``svn+https``
and ``svn+ssh``. Here are the supported forms:

* svn+svn://svn.server.org/my-platform
* svn+https://svn.server.org/my-platform
* svn+ssh://svn.server.org/my-platform

You can also give specific revisions to an SVN URL, like so:

* svn+svn://svn.server.org/my-platform#13
