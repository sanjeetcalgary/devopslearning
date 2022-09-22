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


File Types
------------------------

| Symbol | Name | Description|
|--------|------|------------|
| **-** | regular file | different files such us text files, images, binary files, shared libraries, etc. You can create a regular file with the touch command |
| **d** | directory | folder, Directory can be created with the mkdir command |
| **c** | character device file | Character and block device files allow users and programs to communicate with hardware peripheral devices. |
| **b** | block device file | Block devices are similar to character devices. They mostly govern hardware as hard drives, memory, etc. |
| **s** | local socket file | sockets are used for communication between processes. Generally, they are used by services such as X windows, syslog and etc. |
| **p** | named pipe | allow communication between two local processes. They can be created by the mknod command and removed with the rm command. |
| **I** | symbolic link | an administrator can assign a file or directory multiple identities. Symbolic link can be though of as a pointer to an original file.|

```
Check the system variables, user variables, env variables defined: $ set | less

check only env variables: $ env | less
```

<img width="317" alt="image" src="https://user-images.githubusercontent.com/103237142/191865219-0e4d7ec5-f40c-4788-a28b-51eecf90b932.png">

To make environmental variable ` $ export var=value`

<img width="741" alt="image" src="https://user-images.githubusercontent.com/103237142/191865187-2b86fe85-29d4-4f29-8d68-441a5953b961.png">

$PATH: it has binaries for executables so if we keep any script in the bin directories mentioned here, we can run it from anywhere with just name 

<img width="456" alt="image" src="https://user-images.githubusercontent.com/103237142/191866050-01b3ba65-aee3-4487-aa8e-c3ebcb9d2ff7.png">


