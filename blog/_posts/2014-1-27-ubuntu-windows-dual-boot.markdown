---
layout: post
title:  "Dual Booting Windows with Ubuntu"
date:   2014-1-27 15:04:20 +0530
categories: tutorials
type: blog
---
Dual booting Windows and Ubuntu has always been a painful task. With the advent of **Secure Boot** this pain has now reached the next level. So what do we do? Using VM isn't an option thanks to performance issues.

<img src="http://3.bp.blogspot.com/-1pOdeS95c3g/UxgVZBcufTI/AAAAAAAAA-I/tFV6eplRFYE/s1600/Windows_8.1_Adds+Unity-Style_Search_Feature.png" class="img-responsive">

After numerous experimenting on my poor laptop (I guess I used to screw it up almost once a month) I finally found a foolproof (almost!) working method.

Here are the steps (Assuming you have Windows running on UEFI firmware):

* Create a partition. This is the most trivial step. Can be done by right clicking on My Computer and then going for *Manage > Disk Management* and then shrinking a volume. You can either leave it at that or give that volume a new label. Doesn't affect the installation.
* Go to the *BIOS menu*. This can generally be accessed from the start screen by pressing an assigned key. For my laptop (Dell Inspiron 7520) it was <kbd>F2</kbd>.
* Disable **Secure Boot**. This can be found under *Boot* or in some cases *Security* category. Just hit <kbd>Enter</kbd> when you get the Secure Boot option and then hit disable.
* Now you will need a UEFI-compatible bootable media. For this, you will need a software known as [Win32 Disk Imager](http://sourceforge.net/projects/win32diskimager/). Just write your ISO onto your Pen Drive (or any other bootable media device) and that's it! You have created a UEFI-compatible media.
* Next, boot from the Pen Drive you created.
* After that install normally. Use the partition that you created in step one (**Ext4** file system and mount point **/**).
* Now you have installed Ubuntu, the only thing remains is to fix the boot. Upon restart, you will see all options on the GRUB menu, but the Windows options won't work. For that you need to do something.
* To fix your boot, you will need to install **boot-repair**. To do this, fire up a terminal and type:


        sudo add-apt-repository ppa:yannubuntu/boot-repair && sudo apt-get update

    and press <kbd>Enter</kbd>. And then type:

        sudo apt-get install -y boot-repair && (boot-repair &)

    and press <kbd>Enter</kbd>.

* And then do a **Recommended Repair**.

<img src="http://pix.toile-libre.org/upload/original/1335260967.png" class="img-responsive"/>

And that's it! Check out your system by restarting and trying to boot into all your OSs (Windows would most probably be labelled as *Windows UEFI Boot Loader*).

This method works in most cases. In case it doesn't, mail me at ranveer[at]cse.iitb.ac.in
