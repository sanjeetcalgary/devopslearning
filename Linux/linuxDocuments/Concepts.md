# Types of Users

![image](https://user-images.githubusercontent.com/103237142/176241017-55e91246-4f2d-40fa-9806-aa1e322eaaf8.png)

## Users & groups
----------------
- User and groups are used to access control
- User is associated to a group
- Every user has UID (Unique user id)
- User id and UID are stored in /etc/passwd
- User password is stored in /etc/shadow

## File Types
---------------
| Symbol | Type | Description |
| ------ | ----------- | ---------- |
| ~   | Regular file | Normal file text, executable files |
| d | directory |   |
| l    | link | Shortcut that points to file location  |
| s    | socket | Shortcut that points to file location  |
| p    | pipe | Process communicate without network  |

## File Permission
------------------
To check permission, use `$ ls -l path`

![image](https://user-images.githubusercontent.com/103237142/176242277-25a41295-1b6b-4dce-94fe-9379e1e360cf.png)

| Symbol | Description |
| ------ | ----------- |
| r   | Permission to read |
| w | Permission to write |
| x    | Permission to execute |
| -    | No permission |

![image](https://user-images.githubusercontent.com/103237142/176243203-87b1bec3-4083-46de-98b7-f85f36ed5805.png)

| Field | Description |
| ------ | ----------- |
| 1 byte   | File type (-, d, l) |
| 3 byte | Owner’s permission |
| 3 byte    | Group’s permission |
| 3 byte    | Other user permission |
| 1 byte | Number of links or directories inside that directory |
| 1 byte    | User who owns that file |
| 1 byte    | Group that belongs to |

![image](https://user-images.githubusercontent.com/103237142/176243603-8abb8d55-3c54-4ea5-be68-980c1f3ae21e.png)
![image](https://user-images.githubusercontent.com/103237142/176243615-7cb4db94-0d7c-408c-aa3c-9f0053a7ae37.png)

### Change Permission
- Only root can change file’s owner
- Only root or owner can change file’s group
- `chown` is used to change ownership
```
$ chown [-R] user_name file/directory
```
- `chgrp` is used to change group
```
$ chgrp [-R] group_name file/directory
```
- Changing file/directory permission `chmod`
```
$ chmod [-option]  mode file/directory
    + options include:
      - -R : recursive
      - -v : verbose
      - -reference : reference of other file's for mode
     + mode include:
      - u =user, g= group, o=other, a=all
      - + = grant, - = remove, = =set      
```
chmod ugo+r file = grant read access to all for a file

```
chmod u=rw,og=r new_file.txt
Using the “=” operator means we wipe out any existing permissions and then set the ones specified.
```
## Input Output Redirects
-------------------
> - Standard Input (stdin)- file description number -0
    * used to get file contents of a file 
        + `<` is used as input redirect
        
> - Standard output (stdout) - file description number -1
    * used to redirect console output
        + Redirect to a file / overwritten `>`
        + Use the same file or append  `>>`
    
> - Standard error (stderr) - file description number -2
    * used to redirect errors
        + Using file descriptor i.e. 2 e.g. `telnet localhost 2> errorfile`




