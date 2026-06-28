slstatus - suckless status
==========================
n9mi's personal slstatus build

Features
--------
- Battery percentage/state/time left
- Cat (read file)
- CPU usage
- CPU frequency
- Custom shell commands
- Date and time
- Disk status (free storage, percentage, total storage and used storage)
- Available entropy
- Username/GID/UID
- Hostname
- IP address (IPv4 and IPv6), interface status
- Kernel version
- Keyboard indicators
- Keymap
- Load average
- Network speeds (RX and TX)
- Number of files in a directory (hint: Maildir)
- Memory status (free memory, percentage, total memory and used memory)
- Swap status (free swap, percentage, total swap and used swap)
- Temperature
- Uptime
- Volume percentage
- WiFi signal percentage and ESSID


Requirements
------------
Currently slstatus works on FreeBSD, Linux and OpenBSD.
In order to build slstatus you need the Xlib header files.

- For volume percentage on Linux the kernel module `snd-mixer-oss` must be
  loaded.
- For volume percentage on FreeBSD, `sndio` must be installed.


Installation
------------
For fresh install Debian/others users, please install
```
sudo apt update
sudo apt install -y \
    network-manager \
    pulseaudio-utils \
    brightnessctl \
    gawk \
    coreutils
```

Edit config.mk to match your local setup (slstatus is installed into the
/usr/local namespace by default).

Afterwards enter the following command to build and install slstatus (if
necessary as root):

```
make clean install
```

For LightDM users, add this on `.xsessionrc`
```sh
#!/bin/sh
slstatus &
```

Running slstatus
----------------
See the man page for details.


Configuration
-------------
slstatus can be customized by creating a custom config.h and (re)compiling the
source code. This keeps it fast, secure and simple.
