basic information
=================
This repository contains my configuration for a ts7260 root filesystem.
It's my goal to build a openwrt image with this configuration file which
should work with the kernel based on the linux 2.6 kernel from ynezz

installation
============
Basicly, these are the steps I took:
1. svn co svn://svn.openwrt.org/openwrt/trunk/ which was the command I found
   on https://dev.openwrt.org/wiki/GetSource. I used the trunk version because
   the current 10.03.1 has no ep93xx support.
1. Create an env directory and initiate the git repository.  This can also be
   done by running `scripts/env list`
1. Clone this repository into your env directory.
Running make should create the same image as I am. :-)

links
=====
* The ynezz repository which gave me the idea of building my own kernel:
  https://github.com/ynezz/linux-2.6
* I've found a mirror of openwrt on hithub: https://github.com/mirrors/openwrt
  It will probably be usefull for further development.
