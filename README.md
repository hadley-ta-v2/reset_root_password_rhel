# reset_root_password_rhel

#Reboot the System:
#### Restart your RHEL 9 VM.
#Access GRUB Menu:
#### During the boot process, press e to edit the GRUB menu.
#Edit Kernel Parameters:
#### Find the line that starts with linux and go to the end of this line.
#### Add rd.break at the end of the line.
#### Press Ctrl + x to boot with these parameters.
#Remount the Filesystem:
#### You will be dropped into an emergency shell.
#Remount the root filesystem as read-write:
#### mount -o remount,rw /sysroot

#Change Root Directory:
#### Switch to the root filesystem:
#### chroot /sysroot

#Reset the Root Password:
#### Use the passwd command to change the root password:
#### passwd

#Relabel Filesystem for SELinux:
#### Create a file to ensure SELinux relabels the filesystem on the next boot:
#### touch /.autorelabel

#Exit and Reboot:


#### After the system reboots, you should be able to log in with the new root.
