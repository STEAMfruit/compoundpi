.. _install:

===================
Server Installation
===================

The server component of Compound Pi can only be installed on the Raspberry Pi
architecture. On Raspbian, the following command can be used to install the
server package::

    $ sudo apt-get install compoundpi-server

.. warning::

    The Raspbian package will automatically install the :ref:`cpid` daemon in
    the boot sequence. This will make the camera inaccessible to other
    processes unless the daemon is manually stopped or prevented from starting.

On other platforms, the package can be installed from PyPI. First, ensure that
you have the ``pip`` command installed (this is in the ``python-pip`` package
on Debian and RedHat based distros). Use this to install compound pi,
specifying the ``server`` option to pull in all dependencies required by the
server component::

    $ sudo pip install "compoundpi[server]"

.. warning::

    The PyPI package does not include init-scripts (because it can't). You will
    need to write these for your platform manually if you wish the daemon to
    start automatically on boot-up.


===================
Client Installation
===================

The client component of Compound Pi can be installed on any machine with Python
available. On Ubuntu, the Waveform PPA can be used for simple installation::

    $ sudo add-apt-repository ppa:waveform/ppa
    $ sudo apt-get update
    $ sudo apt-get install compoundpi-client

On Raspbian (assuming you want to use a Raspberry Pi as a client), use the same
procedure as for Ubuntu (above) but omit the ``add-apt-repository`` step. Be
aware that the GUI client is untested under Raspbian.

On other platforms, the package can be installed from PyPI. First, ensure that
you have the ``pip`` command installed (this is in the ``python-pip`` package
on Debian and RedHat based distros). Use this to install compound pi,
specifying the ``client`` option to pull in all dependencies required by the
client component::

    $ sudo pip install "compoundpi[client]"

.. warning::

    Currently, the version of client and server must match exactly. The client
    will not work with a different version server (either older or newer).

