# Embedded

Everything you need to know to start developing barebones or an embedded Linux and flash it to a board, whether that's a Beaglebone, Raspberry PI, your old TP-Link, Linksys, Asus router, BananaPI...etc.

## Boards

### MIPS

MIPS is a reduced instruction set computer (RISC) instruction set architecture (ISA)[1]:A-1[2]:19 developed by MIPS Technologies (formerly MIPS Computer Systems).

Designer: MIPS Technologies, Imagination Technologies https://www.imgtec.com/

Link to Wikipedia: https://en.wikipedia.org/wiki/MIPS_architecture

TP-Link router ArcherC2 uses MIPS.
MIPS SDK is at: https://community.imgtec.com/developers/mips/tools/codescape-mips-sdk/download-codescape-mips-sdk-essentials/
This SDK builds Barebones MIPS apps as well as Linux apps. 


## Useful Software

###	YOCTO PROJECT
Link: https://www.yoctoproject.org

###	ELDK
Link: https://www.denx.de/wiki/DULG/ELDK
DENX is based on YOCTO project.

###	U-BOOT (DAS U-BOOT)
•	The "Universal Bootloader" ("Das U-Boot") is a monitor program.
•	Free Software: full source code under GPL
•	hosted on SourceForge: http://sourceforge.net/projects/u-boot
•	production quality: used as default boot loader by several board vendors
•	portable and easy to port and to debug
•	many supported architectures: PPC, ARM, MIPS, x86, m68k, NIOS, Microblaze
•	more than 216 boards supported by public source tree
•	many, many features

### BAREBOX
Started as a fork from U-Boot in 2007, then renamed to Barebox in 2009.
Barebox is an open source, primary boot loader used in embedded devices. It is available for a number of different computer architectures, including ARM, Blackfin, MIPS, Nios and x86.


### BUSYBOX (THE SWISS ARMY KNIFE OF EMBEDDED LINUX)
Link: https://busybox.net/about.html
BusyBox combines tiny versions of many common UNIX utilities into a single small executable. It provides replacements for most of the utilities you usually find in GNU fileutils, shellutils, etc. The utilities in BusyBox generally have fewer options than their full-featured GNU cousins; however, the options that are included provide the expected functionality and behave very much like their GNU counterparts. BusyBox provides a fairly complete environment for any small or embedded system.
BusyBox has been written with size-optimization and limited resources in mind. It is also extremely modular so you can easily include or exclude commands (or features) at compile time. This makes it easy to customize your embedded systems. To create a working system, just add some device nodes in /dev, a few configuration files in /etc, and a Linux kernel.






