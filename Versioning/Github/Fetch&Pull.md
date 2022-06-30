# Fetch and Pull
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


