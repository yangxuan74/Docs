
.. _projectconf:

配置文件
==================================

Each PlatformIO project has a configuration file named
``platformio.ini`` in the root directory for the project. This is a
`INI-style <http://en.wikipedia.org/wiki/INI_file>`_ file.

``platformio.ini`` has sections (each denoted by a ``[header]``) and
key / value pairs within the sections. Lines beginning with ``;``
are ignored and may be used to provide comments.


The other sections are optional to include. Here are the allowed
sections and their allowed contents:

.. toctree::
    :maxdepth: 2

    section_platformio
    section_env
    examples
