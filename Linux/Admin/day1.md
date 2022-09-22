File System Structure
-----------------------------------

All Linux systems have a directory structure that starts at the root directory. The root
directory is represented by a forward slash, like this: **/**. Everything that exists on your Linux
system can be found below this root directory.

<img width="436" alt="image" src="https://user-images.githubusercontent.com/103237142/191854539-12a20f99-f0a4-4fb1-b826-faf5fcca6954.png">

<img width="576" alt="image" src="https://user-images.githubusercontent.com/103237142/191854275-49fc04cd-efd2-4df0-93a3-8b8d8929ba1a.png">

| Directory Name | Description|
|----------------|------------|
| /bin | Consists of executables, binaries to execute commands cat, bash, touch, sh, sudo etc.|
| /sbin | binaries to configure the operating system like disk, partition, upgrades, networking etc.|
| /lib | system binaries, contains kernel modules and those shared library images needed to boot the system and run the commands in the root filesystem|
| /opt | store optional software|
| /boot | contains all files needed to boot the computer |
| /etc | All of the machine-specific configuration files should be located here | 
| /home | store personal or project data here, ame in the format /home/$USERNAME|
|  /root | default location for personal data and profile of the root user | 
| /srv | data that is served by your system |
| /media | serves as a mount point for removable media devices such as CDROM's, digital cameras, and various usb-attached devices|
| /mnt | used for temporary mount points |
| /tmp | store temporary data when needed |
| /dev | consists of device files |
| /proc | Process information |
| /usr | contain shareable, read only data |
| /var | Files that are unpredictable in size, such as log, cache and spool files |



