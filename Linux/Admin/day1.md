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

<img width="516" alt="image" src="https://user-images.githubusercontent.com/103237142/192057947-90970cb4-e4f5-42ee-aac6-39038551575c.png">

<img width="473" alt="image" src="https://user-images.githubusercontent.com/103237142/192058028-dc0e0fbc-717e-4a8c-8bcc-0e32a3740f7b.png">

<img width="415" alt="image" src="https://user-images.githubusercontent.com/103237142/192058521-ba81a289-9369-42b8-80d0-1ef23c730e7e.png">

```
#!/bin/bash
cat /etc/ubuntu-release
uptime
date
umeek
```

<img width="398" alt="image" src="https://user-images.githubusercontent.com/103237142/192059061-1e737ef3-eb0a-4d28-93f5-09516a28a667.png">

<img width="437" alt="image" src="https://user-images.githubusercontent.com/103237142/192059249-8d530b9c-3f48-47bc-90bc-6a64d3420d26.png">

Permissions
---------------------------

<img width="681" alt="image" src="https://user-images.githubusercontent.com/103237142/192059659-29341bdb-73c0-4c90-9bf9-1f0386eb9a7b.png">

<img width="655" alt="image" src="https://user-images.githubusercontent.com/103237142/192059882-211d84b6-b96d-454a-b3d2-a235e0611af0.png">

<img width="649" alt="image" src="https://user-images.githubusercontent.com/103237142/192060080-5cb560ef-c26e-49a2-ba01-e688afaa0672.png">

```
Check user's group: $ id <user>
```
<img width="320" alt="image" src="https://user-images.githubusercontent.com/103237142/192061560-d1a51adc-9923-42e9-b5aa-d4c3b64cf66f.png">

<img width="495" alt="image" src="https://user-images.githubusercontent.com/103237142/192066309-9b049813-5a59-4660-a4f0-a5733cf4d3be.png">

<img width="699" alt="image" src="https://user-images.githubusercontent.com/103237142/192066463-43da0599-6a60-4326-b655-a3b42327129e.png">

Chmod & Chown
-----------------------
**Chmod**: Change file permission

**Chown**: Change file ownership

**What is SUID and how to set it in Linux?**

SUID (Set owner User ID up on execution) is a special type of file permissions given to a file. Normally in Linux/Unix when a program runs, it inherits access permissions from the logged in user. SUID is defined as giving temporary permissions to a user to run a program/file with the permissions of the file owner rather that the user who runs it. In simple words users will get file ownerâ€™s permissions as well as owner UID and GID when executing a file/program/command.

<img width="367" alt="image" src="https://user-images.githubusercontent.com/103237142/192075648-5a66cfdb-5d1b-4e4d-87ff-736b59d5547f.png">

User Management
----------------------------
+ Adding a user: `$ useradd <uname>`
+ Check the user added `$ cat /etc/passwd | grep -i <uname>`

<img width="409" alt="image" src="https://user-images.githubusercontent.com/103237142/192125163-dbc6e381-18d8-4cfb-98e2-cfbb40a14b7a.png">

There are 7 enteries sperated with **:**

| User Name|:|Password|:|UserID|:|GroupID|:|Comments|:|Home directory|:|Shell|
|----------|-|--------|-|------|-|-------|-|--------|-|--------------|-|-----|

using options, we can decide these values, namely

|flag | meaning|
|-----|--------|
| -u | UserID |
| -g | Group |
| -c | Comments|
| -d | home directory | 
| -s | Shell|

<img width="669" alt="image" src="https://user-images.githubusercontent.com/103237142/192125511-2aaf4d32-91a9-4fcb-bcde-8287f5900d42.png">

`$ id <UserName>` : This command will show user detail like UID, Group

<img width="336" alt="image" src="https://user-images.githubusercontent.com/103237142/192125555-aa0324aa-1338-4e45-b2b9-9d0d069ed602.png">

+ To create a group : `$ groupadd <groupName>`
+ To check groups: `$ cat /etc/group`

Changing the password as root user or logged in user ` $ passwd <Uname>`




