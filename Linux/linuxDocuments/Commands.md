## Commands
------------------------------
`ls` - lists files and directories
```
$ ls
```
![image](https://user-images.githubusercontent.com/103237142/176059143-163f2a61-bacd-49a1-a5c5-b3b753d705eb.png)

> `ls -l` - shows file or directory, size, modified date and time, file or folder name and owner of the file, and its permission.
> ```
> $ ls -l
> ```
> ![image](https://user-images.githubusercontent.com/103237142/176059673-f8f42709-e3ef-412c-a4c5-4670c0d94dfc.png)

> `ls -a` - List all files including hidden files
> ```
> $ ls -a
> ```
> ![image](https://user-images.githubusercontent.com/103237142/176059770-b3afc58f-d7c6-4a90-a535-4c0c56b7b7a9.png)

> `ls -r` - display files and directories in reverse order
> ```
> $ ls -r
> ```
> ![image](https://user-images.githubusercontent.com/103237142/176060377-08bf8a74-119d-4e33-9385-72da9dd655ca.png)

> `ls -R` - Display files and directories artifacts recursively
> ```
> $ ls -R
> ```
> ![image](https://user-images.githubusercontent.com/103237142/176060421-64da1039-4c30-4a5d-9591-db3d8ffbf485.png)

> `ls -ltr` - show the latest modification file or directory date as last.
> ```
> $ ls -ltr
> ```
> ![image](https://user-images.githubusercontent.com/103237142/176060505-4a0b05be-16e2-400b-838e-57524c9a7456.png)

> `ls -l /var` - list files under directory /var
> ```
> $ ls -l /var
> ```
> ![image](https://user-images.githubusercontent.com/103237142/176060578-a008250b-0fd0-4ab4-87a9-7608e3832019.png)

### CD Commands
| Option | Description |
| ------ | ----------- |
| cd /usr/local   | Change from current directory to /usr/local |
| cd - | Switch back to previous directory where you working earlier |
| cd ..    | Change Current directory to parent directory. |
| cd ../ ../ | Move two directory up from where you are now |
| cd ~    | Move to users home directory from anywhere |

### DIR Commands
| Option | Description |
| ------ | ----------- |
| dir   | list directories |
| dir -a | List all files in a directory including hidden |

### TOUCH Commands- create, change and modify timestamps of a file
| Option | Description |
| ------ | ----------- |
| touch filename1 file2 file3 …   | Creates empty files |
| touch -c filename | Will create file if it doesnot exist else will not |

### Copy/Move Commands
| Option | Description |
| ------ | ----------- |
| cp <source> <destination>   | Copy from source to destination |
| cp -r source dest | Copy recursively |
| mv <source> <destination>   | move from source to destination |
| mv -I source dest | Throw warning for overwriting |

### Cat Commands
| Option | Description |
| ------ | ----------- |
| cat /etc/passwd   | display the contents of a file |
| cat file1 file2  | display multiple file contents |
| cat >file   | create a file with cat command, provide input and press Ctrl + D |
| cat file | more | display content more |
| cat file | less | display content less |
| cat -n file | display line numbers of file |
 
![image](https://user-images.githubusercontent.com/103237142/176214859-3fc8ef7d-932b-479e-aa33-58100642b95a.png)

![image](https://user-images.githubusercontent.com/103237142/176215043-e4a9fbf5-fb7f-4306-b5de-bfdc69bee3bf.png)

![image](https://user-images.githubusercontent.com/103237142/176215248-731ec5ca-46cd-4578-9fb2-2126e26e67b0.png)

![image](https://user-images.githubusercontent.com/103237142/176215536-841bd086-20cb-4dbb-ba75-5201b7d283f1.png)

---------------------------------------
### Find command
> - `$ find . -name filename.txt` : Find all the files whose name is filename.txt in a current working directory.
     
 ![image](https://user-images.githubusercontent.com/103237142/176219854-e99fecb0-b62b-4d05-b45a-278c137c3cfb.png)

> - `$ find /home -name filename.txt` : Find all the files under /home directory with the name filename.txt
 
 ![image](https://user-images.githubusercontent.com/103237142/176220331-c83f68e6-90c1-4379-af31-2db8db9dc7f0.png)

> - `$ find /home -iname file.txt` : Find file ignoring cases

 ![image](https://user-images.githubusercontent.com/103237142/176221204-8b3766db-884b-426b-a4ac-ecf6efec9a5e.png)

> - `$ find / -type d -name directoryName` : Find all directories whose name is directoryName in / directory.

> - `$ find / -perm /u=r` : Find all directories whose name is directoryName in / directory.
 
> - `$find / -perm /a=x` : Find all Executable files.
 
> - `$ find . -type f -name "tecmint.txt" -exec rm -f {} \` : To find a single file called tecmint.txt and remove it.
 
> - `$ find . -type f -name "*.txt" -exec rm -f {} \` : To find and remove multiple files such as .txt, then use
---------------------------------------- 

 ### Grep command : used for searching strings based on pattern in a file
 If grep command unavailable then install it
  * `$ apt-get install grep` : in Ubuntu
  * `$ yum install grep` : in Centos
 
 > - `$ grep 'serachstring' filename` : Search any line that contains the word in filename
  
 ![image](https://user-images.githubusercontent.com/103237142/176231378-d6d41d75-bc2e-48fb-890a-649bd4236817.png)

 > - `$ grep -i 'serachstring' filename` : Perform a case-insensitive search for the word
 
 ![image](https://user-images.githubusercontent.com/103237142/176231871-26781c4b-2389-4209-8174-122a8289d1c4.png)

 > - `$ grep -R 'httpd' .` : Look for all files in the current directory and in all of its subdirectories in Linux for the word ‘httpd’
 
 > - `$ grep -c 'nixcraft' frontpage.md' .` : Search and display the total number of times that the string ‘nixcraft’ appears in a file named frontpage.md
 
 ![image](https://user-images.githubusercontent.com/103237142/176233946-a171b6bc-b18b-42b2-a5a8-5df58dfb780c.png)

 > - `$ grep -v 'string' file' .` : Search and display file contents except for the search string
 
 ![image](https://user-images.githubusercontent.com/103237142/176234443-2d50d4e5-be7d-4dcc-8ed0-84d86f38e77d.png)

  > - `$ egrep -i 'string|string' file' .` : used to search two words in a file
 
 ![image](https://user-images.githubusercontent.com/103237142/176234796-63610ff5-4a6b-43f6-a4b2-5dc83bb9fc80.png)

-------------------------------------
 ### WC commands
The wc (word count) command in Unix/Linux operating systems is used to find out number of newline count, word count, byte 
and characters count in a files specified by the file arguments

`wc -l` : Prints the number of lines in a file.

`wc -w` : prints the number of words in a file.

`wc -m`: prints the count of characters from a file.
 
`wc -L` : prints only the length of the longest line in a file.

![image](https://user-images.githubusercontent.com/103237142/176451909-60aecec2-c320-40b3-9f32-2f27ff7c5825.png)

------------------------------------
### Tee command
Used to print the output on console and redirect it to a file at the same time

```
df -h | tee diskusage.txt 
 -a (--append) - Do not overwrite the files instead append to the given files.
```
![image](https://user-images.githubusercontent.com/103237142/176459253-b299530a-ad63-485f-abbc-269ce8490df9.png)

![image](https://user-images.githubusercontent.com/103237142/176459383-2772043e-e8b4-452a-bd3b-c30c747decc4.png)

![image](https://user-images.githubusercontent.com/103237142/176459712-78423d0c-bf71-4b89-b6db-8dca696aee4c.png)

![image](https://user-images.githubusercontent.com/103237142/176459795-577c3cfb-ad1c-4361-b499-f5ff5d056d58.png)

-----------------------------------
### Cut command
The cut command is used to extract the specific portion of text in a file

```
Extract by character
cut -c1 diskusage.txt : get first character of every line of file 
cut -c1,2,5 diskusage.txt : get the first, second and fifth character from every line of file
```
![image](https://user-images.githubusercontent.com/103237142/176461062-58e37763-f15b-4326-b9e9-a6d1ebf08db3.png)

![image](https://user-images.githubusercontent.com/103237142/176461337-cedc88f0-6c47-4010-96f7-53651e4f3429.png)

```
Extract by range
cut -c1-5 diskusage.txt : get the range of characters from 1-5
cut -c1-5,10-16 diskusage.txt : get the range of characters from 1-5 and 10-16
```
![image](https://user-images.githubusercontent.com/103237142/176462832-9bff6420-7e3c-4d4a-9ad5-d4a5960d29c9.png)

![image](https://user-images.githubusercontent.com/103237142/176463037-16827fa3-810b-42ea-82e4-5e6e1e3ee2c8.png)


 
 
 
