Create 2 partitions

partition 1, "LIVE", format: fat32, no flag,   size: all that is left from partition_2, content: x.iso

partition 2, "ESP",  format: fat32, flag: esp, size: 500 MB, content: folders /grub, /EFI

.. /grub/grub.cfg points to the grub.cfg in partition 1

.. no need to touch partition 2.


---


partition 1: 

It is important that the order of files stays as they were added the first time.
reason: the physical storage on the pen drive.

(!) Such will brake the stick: have the stick ready (.iso files on it, and the grub.cfg), 
and now: adding or removing an .iso and changing the grub.cfg file to reflect the changes.

Rather: to remove the grub.cfg (storing it somewhere), to add another .iso,
change the grub.cfg and paste the changed grub.cfg onto the pen drive.

.. rather not to delete already added .iso files, in that case: take all .iso out, zero-out the partition,
paste all .iso back, then paste back the grub.cfg


---


partition 1, content:


x.iso, y.iso ..

\HBCD		// Hirens.BootCD.15.2.zip, all its contents into \HBCD

\memdisk 	// for FD12LITE; from: download Syslinux

grub.exe	// for HBCD; from: /HBCD/dos/dos.gz; unzip to .img, mount the .img and find grub.exe

menu.lst	// for HBCD; from: /HBCD/menu.lst, copy (not cut)


grub.cfg	// (!) to delete this file, do changes, and re-paste this file after changes had been done


---


