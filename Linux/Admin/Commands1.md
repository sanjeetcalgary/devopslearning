File System
----------------------------

**Redirect**

![image](https://user-images.githubusercontent.com/103237142/192408331-008ef16e-e856-45f7-9268-130fbc24b3ea.png)

+ **>** (1- STDOUT)

<img width="385" alt="image" src="https://user-images.githubusercontent.com/103237142/192408653-b26e46bf-9003-4718-9de9-3af9b384a5da.png">

+ **>>** (append)

<img width="391" alt="image" src="https://user-images.githubusercontent.com/103237142/192408958-7582c462-97e3-4998-9203-bd1a592cc557.png">

+ **2>** ( error redirect)

<img width="475" alt="image" src="https://user-images.githubusercontent.com/103237142/192409127-c8557ab4-0849-40a9-8b64-a2d469f40bbc.png">

+ **2>>** (with append)

<img width="532" alt="image" src="https://user-images.githubusercontent.com/103237142/192409255-1a921fed-14ad-4e6e-96ec-6fa6b268f964.png">

+ **&>** ( all in same file)

<img width="475" alt="image" src="https://user-images.githubusercontent.com/103237142/192409881-2238c641-f48b-41c8-8417-8aa21594592f.png">

**Cut**

cutting out the sections from each line of files and writing the result to standard output

`cut <option> <file>`

`cut -d 'delimiter' -f<fieldnumber> filename`

<img width="341" alt="image" src="https://user-images.githubusercontent.com/103237142/192410541-43eca565-1d58-40d8-870b-44edb976d2c5.png">

`cut -b pos,pos,... filename `

<img width="324" alt="image" src="https://user-images.githubusercontent.com/103237142/192410728-30cf2170-9989-4f67-a28a-31706a7e2c9a.png">

`cut -b <block interval> filename`

<img width="325" alt="image" src="https://user-images.githubusercontent.com/103237142/192410808-f447428d-584b-4f3f-b74f-6eecff1bf1e4.png">

**Tee**

tee command reads the standard input and writes it to both the standard output and one or more files

-	a : It basically do not overwrite the file but append to the given file.

<img width="661" alt="image" src="https://user-images.githubusercontent.com/103237142/192550819-56633228-05c9-4c0c-aac0-05355226e0b4.png">

<img width="349" alt="image" src="https://user-images.githubusercontent.com/103237142/192551000-57ce6cf2-4208-4bf1-805b-b12734c94776.png">

**Grep**

Search for anything

| option flag| Decsription|
|------------|------------|
| - | list the matching |
| -v | list all not matching |
| -c | count of matching |
| -n | matching line number |
| -i | case insensitive search |

<img width="533" alt="image" src="https://user-images.githubusercontent.com/103237142/192552645-c54eacf0-d3e2-47cd-853e-e4d33c1c4fd1.png">

**Sort**

| option flag| Decsription|
|------------|------------|
| -r | reverse |
| -n | sort numerically |
| -f | case insensitive sorting |

<img width="398" alt="image" src="https://user-images.githubusercontent.com/103237142/192553455-70eef08f-c91e-4f01-ac06-279b9de69130.png">

<img width="395" alt="image" src="https://user-images.githubusercontent.com/103237142/192553632-6fc2cb69-0a95-481e-90e4-a05489d7d8a9.png">

**Cmp**

compare two files, gives the first mismatch

<img width="469" alt="image" src="https://user-images.githubusercontent.com/103237142/192554089-eeac0bf3-cb28-4a8a-a272-8001ae21a7da.png">

**diff**

Compares files line by line and outputs the difference between them.

the line with **<** is for first file and the line with **>** is for second file

to make both files same, 

![image](https://user-images.githubusercontent.com/103237142/192554757-8af3f6ed-18bd-4998-a17f-fb71162e179b.png)

<img width="410" alt="image" src="https://user-images.githubusercontent.com/103237142/192555037-62a0e4a3-9699-493b-97ca-01c42ef4933c.png">

**Tar**

tar is used to archive and extract files and directories (Note: not compress only archive) Can be compressed using gzip

`tar [options] [archive-file] [file or directory to be archived]`

| option flag| Decsription|
|------------|------------|
| -c | Creates Archive |
| -x | Extract the archive |
| -f | creates archive with given filename |
| -t | displays or lists files in archived file |
| -z | zip, tells tar command that creates tar file using gzip |
| -v | display verbose |

Compress & archive : `tar cvzf myfirst.tar.gz ./Admin`

<img width="449" alt="image" src="https://user-images.githubusercontent.com/103237142/192557244-1d3252f0-9388-43fa-9e7d-aa94ef3421ce.png">

Exclude some files in tar: ` tar --exclude='*.log' --exclude='script.sh' -cvzf mysecond.tar.gz ../Admin`

<img width="604" alt="image" src="https://user-images.githubusercontent.com/103237142/192558492-c9402a15-7576-4b2b-9bb7-d27d19950454.png">

Extract: ` tar xvzf mysecond.tar.gz`

<img width="621" alt="image" src="https://user-images.githubusercontent.com/103237142/192559289-2b164954-47e2-4b8f-b3bd-97edc330443e.png">

to a specific location: `tar xvzf mysecond.tar.gz -C ~/day2/`

<img width="418" alt="image" src="https://user-images.githubusercontent.com/103237142/192559931-ee856715-e388-4f97-8978-f5620137f3c7.png">

```
File size:

$ du --sh <path>

```
<img width="445" alt="image" src="https://user-images.githubusercontent.com/103237142/192560750-5ecc1dc8-3b33-4eae-9e23-69dd03645b56.png">

**Gzip**

Compress and Decompress files

| option flag| Decsription|
|------------|------------|
| -r | compress recursive |
| -d | decompress |

<img width="644" alt="image" src="https://user-images.githubusercontent.com/103237142/192562432-5e7798c1-409b-4502-899d-b9d2ff78d163.png">

<img width="619" alt="image" src="https://user-images.githubusercontent.com/103237142/192562670-96f4e472-5ba0-44b6-920d-9439298a4f43.png">

<img width="496" alt="image" src="https://user-images.githubusercontent.com/103237142/192562876-ea3a958e-d48f-40ec-b6ca-3accb0a0e757.png">

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


















