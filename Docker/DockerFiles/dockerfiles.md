+ Convert dockerfile to image:

`docker build --tag <nameofImage>:version . ` : here . means Dockerfile in current directory

+ Creating container from image:

`docker run --name <conatinername> -d imageName:version` here -d is detached mode

+ Deleting a container:

`docker rm -f conatinerName/Id`

+ Deleting an Image:

`docker rmi -f imagename`

+ Exposing container:

`docker run -d -p <hostPort>:<conatinerPort> --name <conatinername> -d imageName:version`

<img width="759" alt="image" src="https://user-images.githubusercontent.com/103237142/190279461-ecb38396-6ab7-4342-bdd0-3b776a4fc05b.png">

**Note: context means in current directory which is denoated as single dot ( . )**

--tag can be replaced with -t

docker while building looks for Dockerfile in current working directory, if the file name is something else we have to use -f flag

`docker build -t myubuntu:v1 -f dockerfile2 .`


Comments
---------------------

Comments in the dockerfile start with # and you can put anywhere those comments

`# from base image node`

FROM
---------------------
This is the first command in the Dockerfile. Without this, we can’t build an image. We can build the image just with this command. when we build just with FROM, we are actually taking the base image CMD whenever the image is instantiated.

FROM baseImage:tag

```
# from base image node
FROM node:8.11-slim
```

RUN
-----------------
RUN executes the instructions in a new layer on top of the existing image and commit those layers and the resulted layer will be used for the next instructions in the Dockerfile. consider this example we are doing npm install and ls -l with one RUN to avoid any additional layers.

They can be used to install utilities, application, extract files

It has two forms: shell form and exec form

Shell form: the command is run in shell 

`RUN <command>`

Exec form: runs binaries

`RUN ["executable","param1","param2"]`

![image](https://user-images.githubusercontent.com/103237142/190286705-3374aada-bc32-470b-8f33-8ff0b4363599.png)

Multiple run commands can be clubbed together using && 

![image](https://user-images.githubusercontent.com/103237142/190286727-4dbaa80a-fcf7-4f2c-8068-670097c713b0.png)

<img width="428" alt="image" src="https://user-images.githubusercontent.com/103237142/190286919-090a8c77-1c17-4b0d-87c1-ef4a15ba6df3.png">

<img width="429" alt="image" src="https://user-images.githubusercontent.com/103237142/190287481-d7d8a065-f3a4-4f55-9179-16efa23e63b7.png">

COPY
------------------
COPY is used to copy files or directories from source host filesystem to a destination in the container file system. consider this example where we are copying package.json from our system to container file system. we can verify that while building with the RUN command ls -l.

![image](https://user-images.githubusercontent.com/103237142/190288744-9927a2ea-91ef-4b4a-ae49-dbd4c1ea0408.png)

![image](https://user-images.githubusercontent.com/103237142/190288753-a57002f7-380e-4815-8231-40955be8ff64.png)

![image](https://user-images.githubusercontent.com/103237142/190288791-280d809f-648c-4ea6-a5a3-1478024b86d3.png)


