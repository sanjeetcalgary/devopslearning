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

> Step-3: o	Push your changes to github


