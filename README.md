basic information
=================
This repository contains my configuration for a ts7260 root filesystem.
It's my goal to build a openwrt image with this configuration file which
should work with the kernel based on the linux 2.6 kernel from ynezz

installation
============
Basicly, these are the steps I took:

1. `svn co svn://svn.openwrt.org/openwrt/trunk/ openwrt` which was the command 
   I found on https://dev.openwrt.org/wiki/GetSource. I used the trunk version 
   because the current 10.03.1 has no ep93xx support.

1. Create an env directory and initiate the git repository.  This can also be
   done by running `scripts/env list`

1. Clone this repository into your env directory.

Running make should create the same image as I am. :-)

compiling kernel
================
As far as I know I just checked out the tree from ynezz and build it by
creating the configuration file on the normal way: 
`make ARCH=arm ts72xx_defconfig`.  I had to enable the console to see
something on `/dev/ttyAM0`.  `CONFIG_SERIAL_8250` and 
`CONFIG_SERIAL_8250_CONSOLE` are enabled in my config.  Building the modules
was done by simply run `make INSTALL_MOD_PATH=$(pwd)/../modules modules_install`
which installed the modules in the ../modules directory.  I manually added the
modules to my image.

links
=====
* The [ynezz repository](https://github.com/ynezz/linux-2.6) which gave me 
  the idea of building my own kernel
* I've found [a mirror of openwrt on hithub](https://github.com/mirrors/openwrt)
  It will probably be usefull for further development.
