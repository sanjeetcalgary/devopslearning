# git
------------------
## Init & Status

`git status` : gives information on the current status of a git repository and its contents

![image](https://user-images.githubusercontent.com/103237142/176695783-c240d4df-4d5b-4b88-b851-6773cc8743a9.png)

`git init` : used to create a new repository. This is done once per project, the directory where this command is run becomes home of local repository

![image](https://user-images.githubusercontent.com/103237142/176695988-de400e1f-989b-447e-99d1-da0aa37021a0.png)

**Note**: 
```
Do not init a repo inside of a repo, so always use git status to verify you are not inside a repo before calling git init
```

## .git
--------------------------
It is the hidden folder which is generated when git is initialised, it consists of important config files of repositoty

![image](https://user-images.githubusercontent.com/103237142/176700124-7f102bc0-f73c-4930-ae99-d5616eaaa44c.png)

## Workflow
-------------------

![image](https://user-images.githubusercontent.com/103237142/176700515-285d3ddd-92ab-4a54-98ab-991a50846669.png)

Working Directory: Local directory where you are working
Staging area: It is the placeholder for files before it is committed
Repository: It is the .git folder, so when we commit the changes are pushed to .git

1. When some changes are made, git notice changes but its not tracking them

   ![image](https://user-images.githubusercontent.com/103237142/176701403-5767206f-b8f7-4ee2-8274-5b55d6b91fcd.png)

2. Move the changes from local to staging

   ![image](https://user-images.githubusercontent.com/103237142/176701585-b9bbea17-4388-4f6d-857e-c9f1cc1664f8.png)

   ![image](https://user-images.githubusercontent.com/103237142/176701624-84a782e8-c59d-492e-bdb0-9e471928ac8c.png)

3. Commit- Git commit which moves files from staging to .git, while doing so, we have to provide a commit message to summarize 
           and snapshot in the commit
   
   ![image](https://user-images.githubusercontent.com/103237142/176702026-8f1a0f69-2d9d-49dd-9ba7-2b2c755f3932.png)

   ` $ git commit -m "message"` : If you don’t give message, an editor will open and ask to enter message before continuing
   
   ![image](https://user-images.githubusercontent.com/103237142/176702207-64695f5d-be1d-48b1-bb5a-eb2f0d5c85ae.png)

   ![image](https://user-images.githubusercontent.com/103237142/176702241-8133c5c6-71af-4c01-8c64-2e26c4893fac.png)

4. Now git starts tracking the committed files
  
   ![image](https://user-images.githubusercontent.com/103237142/176702343-a90ac58b-4a9c-4dbc-8bca-30e50991e09f.png)

   We can see here in .git folder, file and COMMIT_EDITMSG directory is created
  
5. When a committed file is modified ( which is being tracked by git)

   ![image](https://user-images.githubusercontent.com/103237142/176702560-48f9f964-74b7-41b1-9a3f-7c3169d07d83.png)

   Now add and commit


## log
------------------
`$ git log` : It retrieves the log for commits for the selected repository

![image](https://user-images.githubusercontent.com/103237142/176703227-8caa509c-20ca-46fa-814e-7c94591404de.png)

## Amending Commit
--------------
- Process of redoing last commit, if any mistake is made `(Note: this is applicable only for the last commit)` 
  it’s a way to make any changes in last commit
- amend command will redo the previous commit

  ![image](https://user-images.githubusercontent.com/103237142/176704302-ec30a89a-4e17-484e-91c6-8186b8856842.png)
  
  ![image](https://user-images.githubusercontent.com/103237142/176704548-69475fc4-787b-47c6-903a-a33e853d77d0.png)


## gitignore
------------------
We can tell Git which files or directories to ignore in a given repository using .gitignore file. This is used for files which 
you never want to commit like secret key files, API keys, Credentials, Operating system files, log files, dependencies and packages.

- Create a file called .gitignore in the root of a repository. Inside the file, we can write patterns to tell git which files and 
  directories to exclude from tracking/ commit
- Foldername/ will ignore entire directory
- `*.log` will any file with .log extension

![image](https://user-images.githubusercontent.com/103237142/176705207-cc8dd6c4-fd29-44b5-b4d9-35e11968b487.png)

![image](https://user-images.githubusercontent.com/103237142/176705228-c96638df-168c-4690-b0aa-e964d62bc360.png)

![image](https://user-images.githubusercontent.com/103237142/176705267-324899c8-d987-408f-81e0-58eb2eeb919b.png)




