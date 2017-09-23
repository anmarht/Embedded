# Embedded

Everything you need to know to start developing barebones or an embedded Linux and flash it to a board, whether that's a Beaglebone, Raspberry PI, your old TP-Link, Linksys, Asus router, BananaPI...etc.

## Operating system to use
Linux or Mac. I'm using an Ubuntu VM on my Windows.

## Tools to buy

JTAG for the target archtecture, USB to Serial.
====
For JTAG, i haven't come across needing it so far.

For a working USB-to-serial that works, you can buy this [KEDSUM® CP2102](https://www.amazon.com/gp/product/B009T2ZR6W/ref=oh_aui_detailpage_o00_s00?ie=UTF8&psc=1).

## Tools to Download

Mobaxterm (Windows only), Putty, or any software that can access Serial port.

I prefer Mobaxterm when needing to work with Windows. [Download it](http://mobaxterm.mobatek.net/download.html).

On Ubuntu:

```
sudo apt-get install gtkterm
```
then run it using sudo as it needs administrative privileges.

```
sudo gtkterm
```

Download Qemu (this is to create virtual devices)

```
sudo apt-get install qemu
```


*NOTE: With TP-Link routers, once you open the serial session, reboot the router, and keep typing "tpl" and enter, until you get a command prompt.*

## Using the tools with routers

Disassemble the router.

### Serial (RS-232)

On the board, look for 4 points of contant that are aligned in a straight line, and sometimes a border is drawn around them.

d c b a
o o o o

usually:

d sends data
c received data
b GND (Ground)


Connect your: (colors might be different, be smart and try to find what goes where if this doesn't work)

| USB to Serial | Router board |
| ------------- | ------------ |
| Rx (White)    | d            |
| Tx (Green)    | c            |
| Rx (Black)    | b            |

Once you turn on the router, it should start writing to RS232. So you should see output immediately.

## Processor/Microcontroller Architectures

### MIPS

MIPS is a reduced instruction set computer (RISC) instruction set architecture (ISA)[1]:A-1[2]:19 developed by MIPS Technologies (formerly MIPS Computer Systems). [(From Wikipedia)](https://en.wikipedia.org/wiki/MIPS_architecture)

Designer: MIPS Technologies, [Imagination Technologies](https://www.imgtec.com/)


#### Routers using it
TP-Link router ArcherC2 uses MIPS. Mine is ArcherC2 AC750.

MIPS SDK is at: https://community.imgtec.com/developers/mips/tools/codescape-mips-sdk/download-codescape-mips-sdk-essentials/

This SDK builds Barebones MIPS apps as well as Linux.

@@ i should create a folder MIPSEXample to put the code


## Famous BootLoaders
They run first, then they load the linux.

###	U-BOOT (DAS U-BOOT) [https://www.denx.de/wiki/U-Boot](https://www.denx.de/wiki/U-Boot)
•	The "Universal Bootloader" ("Das U-Boot") is a monitor program.
•	Free Software: full source code under GPL
•	hosted on SourceForge: http://sourceforge.net/projects/u-boot
•	production quality: used as default boot loader by several board vendors
•	portable and easy to port and to debug
•	many supported architectures: PPC, ARM, MIPS, x86, m68k, NIOS, Microblaze
•	more than 216 boards supported by public source tree
•	many, many features

My TP-Link ArcherC2 uses U-Boot.

### BAREBOX [www.barebox.org](http://www.barebox.org/)  (Swiss Army Knife for bare metal)
Started as a fork from U-Boot in 2007, then renamed to Barebox in 2009.
Barebox is an open source, primary boot loader used in embedded devices. It is available for a number of different computer architectures, including ARM, Blackfin, MIPS, Nios and x86.


### BUSYBOX [https://busybox.net/](https://busybox.net/) (The Swiss Army Knife of Embedded Linux)

Link: https://busybox.net/about.html

BusyBox combines tiny versions of many common UNIX utilities into a single small executable. It provides replacements for most of the utilities you usually find in GNU fileutils, shellutils, etc. The utilities in BusyBox generally have fewer options than their full-featured GNU cousins; however, the options that are included provide the expected functionality and behave very much like their GNU counterparts. BusyBox provides a fairly complete environment for any small or embedded system.

BusyBox has been written with size-optimization and limited resources in mind. It is also extremely modular so you can easily include or exclude commands (or features) at compile time. This makes it easy to customize your embedded systems. To create a working system, just add some device nodes in /dev, a few configuration files in /etc, and a Linux kernel.

## Embedded Kits

###	YOCTO PROJECT [https://www.yoctoproject.org](https://www.yoctoproject.org)

The Yocto Project is an open source collaboration project that provides templates, tools and methods to help you create custom Linux-based systems for embedded products regardless of the hardware architecture. It was founded in 2010 as a collaboration among many hardware manufacturers, open-source operating systems vendors, and electronics companies to bring some order to the chaos of embedded Linux development.

###	ELDK [https://www.denx.de/wiki/DULG/ELDK](https://www.denx.de/wiki/DULG/ELDK)

**ELDK** is based on YOCTO project.

Download: https://www.denx.de/wiki/view/DULG/ELDKAvailability


