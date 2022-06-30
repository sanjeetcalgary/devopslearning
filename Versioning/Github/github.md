# github
----------------
## SSH
You need to be authenticated on Github to do certain operations like pushing up code from local machine.
Your terminal will prompt every single time for github credentials.
To overcome this, we need to generate and configure SSH key. Once configured, you can connect to Github
without having to supply your credentials everytime

- Check whether you already have SSH keys `ls -al ~/.ssh`
  
  ![image](https://user-images.githubusercontent.com/103237142/176726435-aa67fd9e-5a52-40b5-92ef-74ab24461a7a.png)
  
- To generate new keys `ssh-keygen -t ed25519 -C "your_email@example.com"`
  When you're prompted to "Enter a file in which to save the key," press Entee. At the prompt, type a secure passphrase
  
  ![image](https://user-images.githubusercontent.com/103237142/176726606-907cadf0-788a-4b18-be59-fd3c49966c21.png)
  
- Ensure the ssh-agent is running, add your SSH private key to the ssh-agent

  ![image](https://user-images.githubusercontent.com/103237142/176726896-7a52fdbc-06fd-47d5-95ee-0f13ecf8050d.png)

- Run cat command and copy the key

  ![image](https://user-images.githubusercontent.com/103237142/176726990-1192cb3b-d766-4c30-bbb5-b83d136479a5.png)

- Go to settings and paste the SSH Key

  ![image](https://user-images.githubusercontent.com/103237142/176727176-a8d3a833-da23-421c-b831-a76be070526c.png)


## Clone
---------------------
Process of creating a local copy of an existing repository, we just need URL to clone
**NOTE**: Make sure you are not inside of a repo when you clone!

`git clone url` : Git will retrieve all the associated files of repo, git will initialise a new repository on your machine 
  giving u access to full git history of the cloned project
 
![image](https://user-images.githubusercontent.com/103237142/176727702-a3a49658-ea61-45d9-a9a1-8f31b8f550ff.png)


## Moving existing local repo to github
--------------------------
> Step-1: Create a new repo in github

> Step-2: Connect your local repo – remote

> Step-3: Push your changes to github

- Create a new repo in github

  ![image](https://user-images.githubusercontent.com/103237142/176729632-a8a18d9d-367e-4b70-aa15-f19aef62d392.png)

- Go to local working repo directory

  ![image](https://user-images.githubusercontent.com/103237142/176729769-baae1c72-88a3-4b32-bad7-f493237d661d.png)

- Connect using remote
  Remote: It is combination of a name and url, name can be anything but industry prefers ***"origin"***
  `git remote -v` : used to check current remote associated with local directory
  
  `git remote add name url` : used to establish remote connection between local directory and github repo
  
  ![image](https://user-images.githubusercontent.com/103237142/176730279-bb1cc66d-2095-45b6-b461-84e72d3b7114.png)

  ![image](https://user-images.githubusercontent.com/103237142/176730321-f9409b2d-30b4-4b24-a629-b694ee634a39.png)

- Push to github
  `git push origin githubBranch` : uswed to push the local repo to github repo, however due to naming we might get `refspec` issue

   ![image](https://user-images.githubusercontent.com/103237142/176731070-05c9cfc7-729b-4169-879b-449da2210b92.png)
  
   To solve this problem, `git show-ref`- this will show where HEAD is pointing to and use that
   ![image](https://user-images.githubusercontent.com/103237142/176731296-d00d9d71-21c6-4a80-bb64-1a0e454e8d12.png)

   git push origin HEAD:master => git push origin HEAD:main

  ![image](https://user-images.githubusercontent.com/103237142/176731511-5526fca1-4780-4c24-8bf1-1be32f3fdfbc.png)


## Cloning github repo to local 
---------------------
> Step-1: Use existing repo from github

> Step-2: Clone it to local

> Step-3: Do some work locally

> Step-4: Push your changes to github

- Clone repo

  ![image](https://user-images.githubusercontent.com/103237142/176732362-4ea90f42-9ba5-4ffa-9909-54e6fb240dbe.png)


- Perform task locally

  ![image](https://user-images.githubusercontent.com/103237142/176732493-1bdbef66-7bd5-424e-adbf-bd157b0cc5d0.png)

- Commit and Push to github

  ![image](https://user-images.githubusercontent.com/103237142/176732609-45044753-512e-478a-828a-8ecc6ba07036.png)

  ![image](https://user-images.githubusercontent.com/103237142/176732639-2677130a-0a5a-4a26-91f3-05279fa8415f.png)


## Fetch and Pull
------------------
| Fetch | Pull |
| ------ | ----------- |
| Get changes from remote branch  | Get changes from remote branch |
| Doesnot merge or overwrite local repo | Automatically apply changes or overwrite the local repo |

![image](https://user-images.githubusercontent.com/103237142/176744570-0ad3a927-73bc-4d96-9fea-1b7098aedf8a.png)

- There can be three scenarios
  + Changes in local repo but remote repo has no change
  + Changes in remote repo but local repo remains same
  + Change in both remote and local


> Changes in local repo but remote repo has no change

  ![image](https://user-images.githubusercontent.com/103237142/176745465-2fc1dc74-b545-4575-a34b-6e9e0642bf7f.png)

  ![image](https://user-images.githubusercontent.com/103237142/176745548-02a7f792-f1cb-428e-8810-7113e7e8b886.png)

  Now let's do some changes in local and push
  
  ![image](https://user-images.githubusercontent.com/103237142/176746053-679d087f-24d3-4870-a531-5891d5498889.png)

  ![image](https://user-images.githubusercontent.com/103237142/176746121-d9ea2292-a2ea-4aef-b0ac-896867888b6a.png)

> Changes in remote repo but local repo remains same

  ![image](https://user-images.githubusercontent.com/103237142/176746395-77747789-8ffc-4548-94db-b38746a9f7f9.png)

  Now we have two options to get updates from github repo: `fetch` and `pull`
  It is always adviced to use fetch, just to make sure your work is not overwritten
  
  `git fetch remoteName branchName` : this will fetch the remote branch
  
  ![image](https://user-images.githubusercontent.com/103237142/176746872-4efca77f-b499-4722-82a7-836b19f07f09.png)

  Now, you can checkout the new changes before merging in detached mode
  
  ![image](https://user-images.githubusercontent.com/103237142/176747499-f24c6e37-3c7c-4d4d-b2c2-aec6af101132.png)

  ![image](https://user-images.githubusercontent.com/103237142/176747554-3cb8ce8e-1911-410b-9e6a-3fbb8da6d875.png)

  Now you can decide to merge
  ![image](https://user-images.githubusercontent.com/103237142/176747822-449483dd-59ee-44e8-a0a0-e6094f2f8c46.png)

  ![image](https://user-images.githubusercontent.com/103237142/176747945-e1cb76f8-f0bb-42df-bfcf-79a6c9422bf4.png)

  ![image](https://user-images.githubusercontent.com/103237142/176748010-e2ec867c-c015-4d57-9fa8-d161603f8aee.png)

  `git pull remoteName branchName` : this will fetch and merge, if resolve if any conflict
   
   ![image](https://user-images.githubusercontent.com/103237142/176748336-2315a628-da92-44cc-a423-d495c00f7453.png)

   ![image](https://user-images.githubusercontent.com/103237142/176748410-de046a6b-953f-4bc4-8b8d-098cb714b964.png)

> Change in both remote and local - resolve conflict if any

  Added a new file in local repo
  ![image](https://user-images.githubusercontent.com/103237142/176748767-106e770e-4480-4ef3-88f8-ff5ec45f77a0.png)

  Updated a file by adding content in local
  ![image](https://user-images.githubusercontent.com/103237142/176748889-efe6fd40-194d-4132-8386-2a112ac4de8f.png)

  Updated a file in local by removing some content
  ![image](https://user-images.githubusercontent.com/103237142/176749032-aee39e98-f699-4476-bc89-e351b59d588d.png)

  ![image](https://user-images.githubusercontent.com/103237142/176749103-805d192b-3aae-4e7b-b35f-16b7e1fbf9ee.png)

  Commit the changes in local repo
  ![image](https://user-images.githubusercontent.com/103237142/176749214-b03bb182-7c4d-4967-9938-89b9bd7e1758.png)

  At the same time, somebody updated food.txt in remote
  ![image](https://user-images.githubusercontent.com/103237142/176749579-d17df9c5-f080-4a61-8c1f-e14cf44501af.png)

  Removed contents from another file in remote
  ![image](https://user-images.githubusercontent.com/103237142/176749729-a08ba3b4-b9bc-44ac-ad80-bdbacddee9bd.png)

  Added a new file in remote
  ![image](https://user-images.githubusercontent.com/103237142/176749877-13bf1bdd-1f38-41c5-8c25-0f9524869b73.png)

  Now, first we fetch the remote and decide what to merge and resolve conflicts
  ![image](https://user-images.githubusercontent.com/103237142/176750048-d6593c47-e570-4e4c-8418-90ca0a7a730a.png)

  ![image](https://user-images.githubusercontent.com/103237142/176750214-82cf6ce7-136f-4e91-a7fe-e1f4c70c73d3.png)

  ![image](https://user-images.githubusercontent.com/103237142/176750263-c3cf5994-3000-4d2f-9369-bce27cb27995.png)

  Resolve the conflicts
  ![image](https://user-images.githubusercontent.com/103237142/176750404-8c628baf-3790-4169-8762-678d27f8f126.png)

  ![image](https://user-images.githubusercontent.com/103237142/176750473-c00743db-e124-491f-9ab0-49ec859c4d3d.png)

  ![image](https://user-images.githubusercontent.com/103237142/176750800-02169fec-e859-4841-bd09-f58f400ce6ee.png)

  Now push to remote
  ![image](https://user-images.githubusercontent.com/103237142/176750920-e05ca408-995e-40dc-9fdc-16cdcc411e9c.png)

  ![image](https://user-images.githubusercontent.com/103237142/176750990-6099a3ec-4c09-4421-904e-83542e16e1aa.png)



  
  
  
