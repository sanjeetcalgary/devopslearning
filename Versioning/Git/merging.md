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




