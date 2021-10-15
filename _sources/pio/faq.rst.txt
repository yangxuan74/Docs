
.. _faq:

FAQ
===================

.. contents::
    :local:

.. _faq_install_python:

Install Python
--------------------------

`Python <https://www.python.org/downloads/>`_ is installed by default on the all popular OS except Windows.

Please navigate to official website and `Download the latest Python <https://www.python.org/downloads/>`_
and install it. Please **READ NOTES BELOW**.

:macOS:
  Please read the "Important Information" displayed during installation for information
  about SSL/TLS certificate validation and the running the **"Install Certificates.command"**.

  If you do not install SSL/TLS certificates, PlatformIO will not be able to download
  dependent packages, libraries, and toolchains.

:Windows:
  Please select ``Add Python to Path`` (see below), otherwise, ``python`` command will
  not be available.

.. _faq_convert_ino_to_cpp:

Convert Arduino to C++
----------------------------

Some IDE doesn't support Arduino files (``*.ino`` and ``.pde``) because
they are not valid C/C++ based source files:

1. Missing includes such as ``#include <Arduino.h>``
2. Function declarations are omitted.

In this case, code completion and code linting do not work properly or
are disabled. To avoid this issue you can manually convert your INO files to CPP.

For example, we have the next ``Demo.ino`` file:

.. code-block:: cpp

    void setup () {
        someFunction(13);
    }

    void loop() {
        delay(1000);
    }

    void someFunction(int num) {
    }

Let's convert it to  ``Demo.cpp``:

1. Add ``#include <Arduino.h>`` at the top of the source file
2. Declare each custom function (excluding built-in, such as ``setup`` and ``loop``)
   before it will be called.

The final ``Demo.cpp``:

.. code-block:: cpp

    #include <Arduino.h>

    void someFunction(int num);

    void setup () {
        someFunction(13);
    }

    void loop() {
        delay(1000);
    }

    void someFunction(int num) {
    }

Finish.

Program Memory Usage
--------------------

PlatformIO calculates firmware/program memory usage based on the next segments:

:``.text``:

    The code segment, also known as a text segment or simply as
    text, is where a portion of an object file or the corresponding section of
    the program's virtual address space that contains executable instructions
    is stored and is generally read-only and fixed size.

:``.data``:

    The .data segment contains any global or static variables which have a
    pre-defined value and can be modified. The values for these variables are
    initially stored within the read-only memory (typically within ``.text``)
    and are copied into the ``.data`` segment during the start-up routine of
    the program. Example,

    .. code-block:: cpp

         int val = 3;
         char string[] = "Hello World";

:``.bss``:

     Uninitialized data is usually adjacent to the data segment. The BSS
     segment contains all global variables and static variables that are
     initialized to zero or do not have explicit initialization in the source code.
     For instance, a variable defined as ``static int i;`` would be contained
     in the BSS segment.

The rough calculation could be done as:

* PROGRAM (Flash) = ``.text`` + ``.data``
* DATA (RAM) = ``.bss`` + ``.data``

If you need to print **all memory sections and addresses**, please use
:option:`pio run --verbose` command.

Recommended for reading:

* https://en.wikipedia.org/wiki/Data_segment
* `text, data and bss: Code and Data Size Explained <https://mcuoneclipse.com/2013/04/14/text-data-and-bss-code-and-data-size-explained/?utm_source=platformio&utm_medium=docs>`_

.. _faq_advanced_serial_monitor_ui:

Advanced Serial Monitor with UI
-------------------------------

PlatformIO Core provides CLI version (:ref:`cmd_device_monitor`) of Serial Monitor.
If you need advanced instrument with a rich UI, we recommend free and multi-platform
`CoolTerm <https://freeware.the-meiers.org/?utm_source=platformio&utm_medium=docs>`_
serial port terminal application.

.. warning::
  Please note that you need to **manually disconnect (close serial port connection)** in
  CoolTerm **before doing uploading** in PlatformIO. PlatformIO can not disconnect/connect
  to a target device automatically when CoolTerm is used.

.. _faq_troubleshooting:

Troubleshooting
---------------

Installation
~~~~~~~~~~~~


'platformio' is not recognized as an internal or external command
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

If you modify system environment variable ``PATH`` in your Bash/Fish/ZSH
profile, please do not override global ``PATH``. This line
``export PATH="/my/custom/path"`` is incorrect. Use ``export PATH="/my/custom/path":$PATH``
instead.

.. _faq_udev_rules:

99-platformio-udev.rules
''''''''''''''''''''''''

Linux users have to install `udev <https://en.wikipedia.org/wiki/Udev>`_ rules
for PlatformIO supported boards/devices. The
latest version of rules may be found at https://raw.githubusercontent.com/platformio/platformio-core/master/scripts/99-platformio-udev.rules

.. note::
  Please check that your board's PID and VID  are listed in the rules.
  You can list connected devices and their PID/VID using :ref:`cmd_device_list`
  command.

This file must be placed at ``/etc/udev/rules.d/99-platformio-udev.rules``
(preferred location) or ``/lib/udev/rules.d/99-platformio-udev.rules``
(required on some broken systems).

Please open system Terminal and type

.. code-block:: bash

    # Recommended
    curl -fsSL https://raw.githubusercontent.com/platformio/platformio-core/master/scripts/99-platformio-udev.rules | sudo tee /etc/udev/rules.d/99-platformio-udev.rules

    # OR, manually download and copy this file to destination folder
    sudo cp 99-platformio-udev.rules /etc/udev/rules.d/99-platformio-udev.rules


Restart "udev" management tool:

.. code-block:: bash

    sudo service udev restart

    # or

    sudo udevadm control --reload-rules
    sudo udevadm trigger


Ubuntu/Debian users may need to add own “username” to the “dialout” group if
they are not “root”, doing this issuing

.. code-block:: bash

    sudo usermod -a -G dialout $USER
    sudo usermod -a -G plugdev $USER

Similarly, Arch users may need to add their user to the “uucp” group

.. code-block:: bash

    sudo usermod -a -G uucp $USER
    sudo usermod -a -G lock $USER

.. note::
  You will need to log out and log back in again (or reboot) for the user
  group changes to take effect.

After this file is installed, physically unplug and reconnect your board.

ImportError: cannot import name _remove_dead_weakref
''''''''''''''''''''''''''''''''''''''''''''''''''''

Windows users can experience this issue when multiple Python interpreters are
installed in a system and conflict each other. The easy way to fix this
problem is uninstalling all Python interpreters using Windows Programs Manager
and installing them manually again.

1. "Windows > Start Menu > Settings > System > Apps & Features", select
   Python interpreters and uninstall them.
2. Install the latest Python interpreter, see :ref:`faq_install_python` guide
3. Remove ``C:\Users\YourUserName\.platformio`` and ``C:\.platformio`` folders
   if exist (do not forget to replace "YourUserName" with the real user name)


.. note::
    You can add ``platformio`` and ``pio`` commands to your system environment.

