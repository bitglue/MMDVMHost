# Debian package for MMDVMHost

Debian packages for MMDVMHost are maintained by Phil Frost, W8II. They are
tested on a Raspberry Pi 3 and Raspbian Stretch.

To install, start with a
[fresh Raspbian Stretch install](https://www.raspberrypi.org/downloads/raspbian/),
then run:

    curl -s https://raw.githubusercontent.com/bitglue/MMDVMHost/master/debian/quickstart | sudo bash

Then edit `/etc/MMDVM.ini` to suit, then reboot.

Note that `MMDVM.ini` should disable file logging, that is it should include:

    [Log]
    FileLevel=0

To check the status of the service:

    sudo systemctl status mmdvmhost

To watch the logs in real-time:

    sudo journalctl -u mmdvmhost.service -f

To restart (necessary after modifying MMDVM.ini):

    sudo systemctl restart mmdvmhost
