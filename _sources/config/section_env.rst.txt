.. _projectconf_section_env:

Section ``[env]``
=================

.. contents::
    :local:

Each project may have multiple *configuration environments* defining
the available project tasks for building, programming, debugging, unit
testing, device monitoring, library dependencies, etc. The
configuration environments are declared using ``[env]`` sections in
:ref:`projectconf`.

The allowed options are listed under `Options`_.

Common ``[env]``
----------------

An optional configuration environment with common options that will be
shared between all ``[env:NAME]`` environments in the platform.ini
file. It is very useful if the configuration file has a lot of
environments ``[env:NAME]`` and they share common settings.


Options
-------

.. toctree::
    :maxdepth: 2

    section_env_platform
    section_env_build
    section_env_library
    section_env_upload
    section_env_monitor
    section_env_check
    section_env_test
    section_env_debug
    debugging
