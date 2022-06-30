# Merging
--------------
There are three types of merging:
- Fast forward merge: there was no additional commit on master
- Git merge and merge commit
- Resolving merge conflicts

To merge, we have to move to receiving branch and then merge the needed branch over there

![image](https://user-images.githubusercontent.com/103237142/176709245-c5153819-99b5-401a-a5e5-431af806015c.png)

When there is no conflict, its called merge commit

![image](https://user-images.githubusercontent.com/103237142/176709439-8554775a-783f-404e-b6ea-b6665a82b249.png)

![image](https://user-images.githubusercontent.com/103237142/176709518-a2083a80-dd2e-4407-8eb1-b255d7e4423b.png)

When there is conflict, we get message as

![image](https://user-images.githubusercontent.com/103237142/176709646-8d11bb0f-81b1-41bc-8666-91d7b5517c72.png)

## Resolving conflict
Whenever you encounter merge conflicts, follow the steps to resolve them:

  ![image](https://user-images.githubusercontent.com/103237142/176710492-2955fa66-01ed-455f-9fa6-2580092f4f27.png)

+ Open the files with merge conflict
  
  ![image](https://user-images.githubusercontent.com/103237142/176710565-dc082a3c-549c-4ab0-bc34-3c085082b7a6.png)

+ Edit the files to remove conflicts. Decide which branch's content you want to keep. or keep both contents
+ Remove the conflict markers in the document

  ![image](https://user-images.githubusercontent.com/103237142/176710633-04b8ab9b-c989-4f73-8b9f-7d9a3307b8a0.png)

+ Add your changes and then make commit
  
  ![image](https://user-images.githubusercontent.com/103237142/176710721-92b91392-46f8-4d5c-8490-f095abc6a302.png)
  
  ![image](https://user-images.githubusercontent.com/103237142/176710776-ffc523a6-29f1-4bb9-8c01-97d4837d4cd3.png)

## Stashing
----------------------------
- Often, when you’ve been working on part of your project, things are in a messy state and you want to switch branches for a bit to 
  work on something else. The problem is, you don’t want to do a commit of half-done work just so you can get back to this point later. 
  The answer to this issue is the git stash command.
  
- Stashing takes the dirty state of your working directory — that is, your modified tracked files and staged changes — and saves it on 
  a stack of unfinished changes that you can reapply at any time (even on a different branch).
  
- When there is no conflict, git allows to bring the work along to new branch (switching) but when there is conflict , git will not allow 
  you to switch branch. In that case if you are not ready to commit, we stash it
  
- Stash pop is used to remove the most recently stashed changes in your stash and re-apply them to your working copy

  ![image](https://user-images.githubusercontent.com/103237142/176712310-df2e5032-9387-455a-91ba-5f0f087a69ec.png)

  ![image](https://user-images.githubusercontent.com/103237142/176712339-8d529fd6-af3f-41a5-bc2a-e0bbd65d5fb1.png)

- To remove/delete stash, we use stash drop stash_id
  
  ![image](https://user-images.githubusercontent.com/103237142/176712490-278b2c42-c299-4dd7-a29a-943f5ded5f72.png)

## Undoing changes (Time travel)
--------------
- Detached mode: Suppose we want to check how the repo looked after some specific commit, or you want to retrieve something from that commit
  + Using `git log` find the commit id where you want to go and copy first 4-5 characters
    
    ![image](https://user-images.githubusercontent.com/103237142/176718120-485005b9-82a8-423b-bd44-e2b12260670c.png)
    
    ![image](https://user-images.githubusercontent.com/103237142/176718714-092f8f4f-4dbf-4113-ab88-8f78fd02509c.png)

  + Using `git checkout commitId` go in detached head mode to check out
  
    ![image](https://user-images.githubusercontent.com/103237142/176718883-3cc50c99-e912-4841-babe-2a44f40392b7.png)
    
    Now, we can check the files
    
    ![image](https://user-images.githubusercontent.com/103237142/176718983-3cba6f2c-b5b9-4ef0-a6a1-4cce06abadb2.png)

   + You can check the work, to come out of detached mode, switch branch
   
    ![image](https://user-images.githubusercontent.com/103237142/176719186-31e00827-ef56-4e11-a83f-97d422a1c9f6.png)

    ![image](https://user-images.githubusercontent.com/103237142/176719282-b3d8e603-ecff-4d82-aa16-4c5073a68220.png)

- Restore: Suppose you made some changes to a file and added to staging, but you realised you have made some mistake and you 
           dont want to commit the changes, use restore to roll back from staging
  
    ![image](https://user-images.githubusercontent.com/103237142/176719985-5aec0cd1-47a3-47e0-8836-d63bc6e5b39f.png)

- Reset: You can reset repo to a specific commit time
  
    ![image](https://user-images.githubusercontent.com/103237142/176720431-4136d5f7-530f-492a-9aa4-0b735646e683.png)

    ![image](https://user-images.githubusercontent.com/103237142/176720504-10ff32e6-d4be-45cd-9ac7-8f9f2476fb90.png)

    Now , we want repo to reset to second commit
    Get the commit ID and reset
    
    ![image](https://user-images.githubusercontent.com/103237142/176720779-b2c5dc45-befa-48e0-9fba-f8102e42d4f7.png)

    ![image](https://user-images.githubusercontent.com/103237142/176720829-0362e73a-7534-440d-ad72-a9a95cf99651.png)

