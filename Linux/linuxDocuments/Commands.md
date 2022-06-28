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

