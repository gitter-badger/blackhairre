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

Go to https://raw.githubusercontent.com/amicolode/blackhairre/master/builds/blackhairre-latest.img to download the image.

If your computer has a slot for SD cards, insert the card. If not, insert the card into an SD card reader, then connect the reader to your computer.

Open your file manager and find out the letter the drive you inserted is. Remember it.

Go to http://sourceforge.net/projects/win32diskimager/ and download win32diskimager (Ignore this step if you have win32diskimager installed already)

Run the executable file you just downloaded. Follow the steps to install win32diskimager. (And ignore this step if you have win32diskimager installed already)





