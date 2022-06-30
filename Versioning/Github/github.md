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


  
