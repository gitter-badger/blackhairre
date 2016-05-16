Blackhairre
=====

#About
Simple Operating System for ARM devices. Based off Raspbian and Debian.

#Installation
##On Linux
Run `wget https://raw.githubusercontent.com/amicolode/blackhairre/master/builds/blackhairre-latest.img`

Run `df -h` to see what devices are currently mounted.

If your computer has a slot for SD cards, insert the card. If not, insert the card into an SD card reader, then connect the reader to your computer.

Run `df -h` again. The new device that has appeared is your SD card. The left column gives the device name of your SD card; it will be listed as something like `/dev/mmcblk0p1` or `/dev/sdd1`. The last part (`p1` or `1` respectively) is the partition number but you want to write to the whole SD card, not just one partition. You therefore need to remove that part from the name, getting, for example, `/dev/mmcblk0` or `/dev/sdd` as the device name for the whole SD card. Note that the SD card can show up more than once in the output of df; it will do this if you have previously written a Raspberry Pi image to this SD card, because the Raspberry Pi SD images have more than one partition.

Now that you've noted what the device name is, you need to unmount it so that files can't be read or written to the SD card while you are copying over the SD image.

Run umount `/dev/sdd1`, replacing `sdd1` with whatever your SD card's device name is (including the partition number).

If your SD card shows up more than once in the output of df due to having multiple partitions on the SD card, you should unmount all of these partitions.

Run `dd bs=4M if=blackhairre-latest.img of=/dev/sdd`. Replace `sdd` with the name of the whole SD card.

##On Windows

Download the image from https://raw.githubusercontent.com/amicolode/blackhairre/master/builds/blackhairre-latest.img

Insert the SD card into your SD card reader and check what drive letter it was assigned. You can easily see the drive letter (for example G:) by looking in the left column of Windows Explorer. You can use the SD Card slot (if you have one) or a cheap Adapter in a USB slot.

Download the Win32DiskImager utility (it is also a zip file). You can run this from a USB drive.

Extract the executable from the zip file and run the Win32DiskImager utility; you may need to run the utility as Administrator! 

Right-click on the file, and select 'Run as Administrator'

Select the blackhairre image file.
Select the drive letter of the SD card in the device box. Be careful to select the correct drive; if you get the wrong one you can destroy your data on the computer's hard disk! If you are using an SD Card slot in your computer (if you have one) and can't see the drive in the Win32DiskImager window, try using a cheap Adapter in a USB slot.

Click Write and wait for the write to complete.

Exit the imager and eject the SD card.

Plug the SD card into the raspberry pi.

##What we used
NOOBS by the Raspberry Pi Foundation at https://www.raspberrypi.org/downloads/noobs/ for the core OS.

XFCE at http://www.xfce.org for the desktop environment

The RPi Easy Setup Guide at http://elinux.org/RPi_Easy_SD_Card_Setup (which is shared under the Creative Commons Attribution-ShareAlike 3.0 Unported license at http://creativecommons.org/licenses/by-sa/3.0/)


