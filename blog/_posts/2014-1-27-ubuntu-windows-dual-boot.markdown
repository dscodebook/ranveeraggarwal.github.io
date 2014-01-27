---
layout: blog
title: "Dual Booting Windows with Ubuntu on UEFI firmware"
---

Dual booting Windows and Ubuntu has always been a painful task. With the advent of UEFI (Unified Extensible Firmware Interface) this pain has now reached the next level. So what do we do? Using VM isn't an option thanks to performance issues.

After numerous experimenting on my poor laptop (I guess I used to screw it up almost once a month) I finally found a foolproof (almost!) completely working method.

Here are the steps (Assuming you have Windows running on UEFI):

* Create a partition. This is the most trivial step. Can be done by right clicking on `My Computer` and then going for `Manage > Disk Management` and then `shrinking a volume`. You can either leave it at that or give that volume a new label. Doesn't affect the installation.
* Go to the `BIOS` menu. This can generally be accessed from the start screen by pressing an assigned key. For my laptop (Dell Inspiron 7520) it was <kbd>F2</kbd>.
* Disable `Secure Boot`. This can be found under `Boot` or in some cases `Security` category. Just hit <kbd>Enter</kbd> when you get the `Secure Boot` option and then hit disable.
<<<<<<< HEAD
* Now you will need a UEFI-compatible bootable media. For this, you will need a software known as [Win32 Disk Imager](http://sourceforge.net/projects/win32diskimager/). Just write your ISO onto your Pen Drive (or any other bootable media device) and that's it! You have created a UEFI-compatible media.
