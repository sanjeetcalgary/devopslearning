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

**Cp**

used to copy files or group of files or directory. cp [OPTION] Source Destination

+ Two file names: If the command contains two file names, then it copy the contents of 1st file to the 2nd file. If the 2nd file doesn’t exist, then first it creates one and content is copied to it. But if it existed then it is simply overwritten without any warning. 

` cp Src_file Dest_file `

+ One or more arguments : If the command has one or more arguments, specifying file names and following those arguments, an argument specifying directory name then this command copies each source file to the destination directory with the same name, created if not existed but if already existed then it will be overwritten

`cp Src_file1 Src_file2 Src_file3 Dest_directory`

+ Two directory names : If the command contains two directory names, cp copies all files of the source directory to the destination directory, creating any files or directories needed. This mode of operation requires an additional option, typically R, to indicate the recursive copying of directories

`cp -R Src_directory Dest_directory`

`-p option will preserve file permission and timestamp`

<img width="676" alt="image" src="https://user-images.githubusercontent.com/103237142/192603170-79dfbb59-6697-4f92-a705-3eff78e95143.png">

<img width="504" alt="image" src="https://user-images.githubusercontent.com/103237142/192603805-4f900320-5e91-4edd-b8d8-a3808cb83c5c.png">

<img width="540" alt="image" src="https://user-images.githubusercontent.com/103237142/192604048-ebebaa5d-dc09-4abc-abf5-93586cba9198.png">

<img width="372" alt="image" src="https://user-images.githubusercontent.com/103237142/192604281-2263f174-759b-4a9d-b817-f06c4324c370.png">

**Find & Exec**

used to find files and directories and perform subsequent operations on them. It supports searching by file, folder, name, creation date, modification date, owner and permissions. By using the ‘-exec’ other UNIX commands can be executed on files or folders found. 

+ Find a file with specific name [ use ` -name`]

` $ find <location> -name <filename>` : using -iname we can make case insensitive

<img width="335" alt="image" src="https://user-images.githubusercontent.com/103237142/192623316-6034d3b0-c9aa-48c0-b1be-50463e6f46e1.png">

+ Find a file with specific name [ use ` -name`]

` find . -type d -name <dirName>`

<img width="571" alt="image" src="https://user-images.githubusercontent.com/103237142/192623947-8971f4dd-290c-4845-9a86-9c3f5e205671.png">

+ Find files with specific permission or without specific permission (using ! )

` find . -type f -perm 0777`

`find / -type f ! -perm 777`

<img width="369" alt="image" src="https://user-images.githubusercontent.com/103237142/192624446-d0be1985-61df-47b6-9266-35e5419abda9.png">

<img width="371" alt="image" src="https://user-images.githubusercontent.com/103237142/192624748-ab009f99-d32a-4e57-af88-7e812158728d.png">

<img width="448" alt="image" src="https://user-images.githubusercontent.com/103237142/192625313-67d5f015-762a-4ccf-8973-771954294d69.png">

```
find . -type f -name "*.log" -exec cat {} \; >> newfile.txt
```

Note: put name in double quotes

**mv**

mv stands for move. mv is used to move one or more files or directories from one place to another in a file system like UNIX. It has two distinct functions: 

(i) It renames a file or folder. 

(ii) It moves a group of files to a different directory.

<img width="592" alt="image" src="https://user-images.githubusercontent.com/103237142/192875528-5ad08be3-34d8-47a3-b15b-09343b41a7d6.png">

**rm**

rm stands for remove here. rm command is used to remove objects such as files, directories, symbolic links and so on from the file system like UNIX.

<img width="345" alt="image" src="https://user-images.githubusercontent.com/103237142/192876201-d67c0661-b722-4dd2-ad3b-4893e291de71.png">

```
Search in Vim:

To search in Vim you must be in normal mode

To search forward, press / and to search backward press ?, type the search pattern and press Enter to run the search:

Press n to search for the next occurrence or uppercase N to search in the opposite direction.

The basic steps to perform a search in Vim are as follows:

i. Press /.
ii. Type the search pattern.
iii. Press Enter to perform the search.
iv. Press n to find the next occurrence or N to find the previous occurrence.

To search for a whole word, start the search by pressing / or ?, type \< to mark the beginning of a word, enter the search pattern, 
type \> to mark the end of a word, and hit Enter to perform the search.

For example, to search for “gnu” you would use /\<gnu\>:

```

**ls**

command lists files and directories within the file system

-l : with description
-a : hidden files
-s or --sort=size
-t or --sort=time

-r : output in reverse order

<img width="438" alt="image" src="https://user-images.githubusercontent.com/103237142/192881200-d376b9a8-b05e-46fe-83c6-1dfbc3c116a5.png">

<img width="436" alt="image" src="https://user-images.githubusercontent.com/103237142/192881242-f4e90650-24e6-41a3-a3f6-20505877826a.png">

<img width="373" alt="image" src="https://user-images.githubusercontent.com/103237142/192881561-902b4264-6c78-4ca8-9b5d-b61f4055bd14.png">

<img width="360" alt="image" src="https://user-images.githubusercontent.com/103237142/192881611-46ce259c-05e9-4eb0-ab96-b4f584671b7c.png">

<img width="363" alt="image" src="https://user-images.githubusercontent.com/103237142/192881651-4de1e540-c699-4ad0-8019-14ff31cdd8d2.png">

**file timestamp**

•	Access timestamp (atime): which indicates the last time a file was accessed. `$ ls -lu [filename]`
•	Modified timestamp (mtime): which is the last time a file’s contents were modified. `$ ls -l [filename]`
•	Change timestamp (ctime): which refers to the last time some metadata related to the file was changed `$ ls -lc [filename]`

<img width="354" alt="image" src="https://user-images.githubusercontent.com/103237142/192882120-98ea9ae2-26f4-482d-b192-3214a61a61a2.png">

<img width="366" alt="image" src="https://user-images.githubusercontent.com/103237142/192882259-b7763f02-c345-429c-9e60-808624731578.png">

**cat**

It reads data from the file and gives their content as output. It helps us to create, view, concatenate files

+ To view contents of a file preceding with line numbers. Command: `$cat -n filename`
+ Create a file `$ cat > filename`
+ append the contents of one file to the end of another file `$cat file1 >> file2`
+ display content in reverse order using tac command.  `$tac filename`
+ file has a lot of content and can’t fit in the terminal.  `$cat "filename" | more`

<img width="674" alt="image" src="https://user-images.githubusercontent.com/103237142/192883248-5cce1f60-cc31-438e-a160-9af60ef5adff.png">

<img width="677" alt="image" src="https://user-images.githubusercontent.com/103237142/192883546-5dc8b204-ad88-4e23-9e02-16e81fc59104.png">

<img width="682" alt="image" src="https://user-images.githubusercontent.com/103237142/192883694-3d88db47-d968-41ee-bfec-ccb676c9a921.png">

**wc**

wc stands for word count. As the name implies, it is mainly used for counting purpose.

-w : number of words present in a file
-m : count of characters from a file.

<img width="267" alt="image" src="https://user-images.githubusercontent.com/103237142/192884015-b1a14d73-6cf7-4b4c-9a79-ac755f4f03dc.png">

**Links**

Creating links is a kind of shortcuts to access a file. Links allow more than one file name to refer to the same file, elsewhere. 

1.	Soft Link or Symbolic links: Symbolic links are not updated (they merely contain a string which is the path name of its target)

`$ ln  -s [original filename] [link name] `

<img width="472" alt="image" src="https://user-images.githubusercontent.com/103237142/192887203-eb4b0c03-f736-48b8-b14e-2cc1dd7e5cb8.png">


2.	Hard Links: hard links always refer to the source, even if moved or removed.

`$ ln  [original filename] [link name] `

<img width="415" alt="image" src="https://user-images.githubusercontent.com/103237142/192887999-657c7f48-0b27-4caa-8f3a-daaa8223b534.png">

When you change content, link files will auto-update

<img width="432" alt="image" src="https://user-images.githubusercontent.com/103237142/192888194-64cbc856-7651-40eb-a3d3-ca188b50d767.png">

When we move sourcefile, softlink fails but hardlink works

<img width="439" alt="image" src="https://user-images.githubusercontent.com/103237142/192888433-e685c26d-d7cb-47b2-bf30-46f7cdc348c0.png">

When we delete source file, softlink fails but hardlink works

<img width="613" alt="image" src="https://user-images.githubusercontent.com/103237142/192888657-f8e27d73-1b20-4aab-ad00-480574670f22.png">


Read file Content
------------------------
+ By opening the file: vi / vim / nano
+ Without opening: cat, more, less
+ With condition: more, tail, grep, awk, sed

**AWK**

1. AWK Operations: 

(a) Scans a file line by line 

(b) Splits each input line into fields 

(c) Compares input line/fields to pattern 

(d) Performs action(s) on matched lines 

2. Useful For: 

(a) Transform data files 

(b) Produce formatted reports 

3. Programming Constructs: 

(a) Format output lines 

(b) Arithmetic and string operations

(c) Conditionals and loops 

```
$ awk options program file

$ awk [options] ‘[selection _criteria] {action }' input-file

Options:
  -F fs     To specify a file separator.
  -f file     To specify a file that contains awk script
  -v var=value     To declare a variable.

$0: Represents the entire line of text.
$1: Represents the first field.
$2: Represents the second field.
$7: Represents the seventh field.
$45: Represents the 45th field.
$NF: Stands for “number of fields,” and represents the last field.
$NR: It will print line or record number
```

To define an awk script, use braces surrounded by single quotation marks


date | awk '{print $2,$3,$6}'

+ OFS: (output field separator) variable to put a separator between the output `date | awk 'OFS="/" {print$2,$3,$6}'`

  enclose the command in single quotes ('), not curly braces ({}): `date | awk 'OFS="-" {print$2,$3,$6}'`

+ BEGIN rule is executed once before any text processing starts. In fact, it’s executed before awk even reads any text. An END rule is executed after all processing has completed. You can have multiple BEGIN and END rules, and they’ll execute in order.
+ BEGIN rule has its own set of actions enclosed within its own set of curly braces ({}).

`who | awk 'BEGIN {print "Active Sessions"} {print $1,$4}'`

+ Field Seperator :  use that file and the -F (separator string) option to tell awk to use the colon (:) as the separator. 

`awk -F: '{print $1,$6}' /etc/passwd`

 Self
 -----------
 
 $ git --version | awk -F ' ' '{print $3}'
 
 <img width="426" alt="image" src="https://user-images.githubusercontent.com/103237142/193377551-7d62a569-b8da-4819-a3b8-26d8bb6a79b2.png">

<img width="636" alt="image" src="https://user-images.githubusercontent.com/103237142/193377921-2f6d217e-e2a5-4b1e-a020-1fd06247f2c3.png">

task: i have a file like

```
name  company jl  project client  city
sanjeet Infosys 5 BoFa  Mortgage  Calgary
Rakesh  Amerifirst  6 Automation  Client  Charlette
Balaji  TCS Churchill 7 SPOC  BA  Chennai
```

I want to retrieve only the city for each

<img width="365" alt="image" src="https://user-images.githubusercontent.com/103237142/193378516-6146784d-0b98-45c1-ad94-879ef9ddfbf7.png">

<img width="521" alt="image" src="https://user-images.githubusercontent.com/103237142/193378571-442c8664-4eec-455d-a8a1-59593e231030.png">




