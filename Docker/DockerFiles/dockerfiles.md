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

<img width="486" alt="image" src="https://user-images.githubusercontent.com/103237142/190534680-8501acb2-6155-4fc6-9897-9b3028843c92.png">

<img width="406" alt="image" src="https://user-images.githubusercontent.com/103237142/190534717-9ff7263b-6169-464c-bd88-40ce71583666.png">

<img width="732" alt="image" src="https://user-images.githubusercontent.com/103237142/190534774-5b77a175-c191-4d66-ba82-29ce904d0e1c.png">

<img width="946" alt="image" src="https://user-images.githubusercontent.com/103237142/190534797-3f07d999-9fc5-45f8-bad6-a53a8f10bf2a.png">

**Note:** Used code is @ Docker/Concept/mycode.zip

ADD
-------------------------
ADD is used to add files or directories and remote files from URL from source host filesystem to a destination in the container file system

- This command also copies one or more files/directories from the docker host into image
- It can also extract TAR files from the docker host into docker image and download files from a URL and copy them into the docker image
- It eliminates the need for untar and download utilities like wget and curl

![image](https://user-images.githubusercontent.com/103237142/190536440-e7c5507f-301a-4c6f-8554-61a4cf58d050.png)

![image](https://user-images.githubusercontent.com/103237142/190536452-a39d8b52-a7c0-48e2-ac07-e07501007a3f.png)

_Task:_

Download the code from github as zip >> try to run without unzip

<img width="528" alt="image" src="https://user-images.githubusercontent.com/103237142/190539309-20cef732-de4f-4973-bef4-91d2fbfbfed9.png">

Now change the dockerfile

<img width="630" alt="image" src="https://user-images.githubusercontent.com/103237142/190539349-43e1c07d-4c9a-4eb1-a86c-176354536784.png">

```
FROM ubuntu
RUN apt-get update && apt-get install -y curl apache2 unzip
# Add works similar to copy but it can download from internet and paste
# like we can download the code or artifacts hosted on github
# lets say our code is at https://github.com/mdn/beginner-html-site-styled
# from here lets take the zip url i.e. right click on ZIp and copy link address: https://github.com/mdn/beginner-html-site-styled/archive/refs/heads/gh-pages.zip
# to customize the path we can give any name like mypage with extemntion
ADD https://github.com/mdn/beginner-html-site-styled/archive/refs/heads/gh-pages.zip /var/www/html/mypage.zip
# since the code is zip, so unzip and copy in directory- download unzip and move the code to source directory
# here * means all files
# summary: download from github as zip >> unzip it >> move to source folder
RUN cd /var/www/html/ && unzip mypage.zip && mv /var/www/html/beginner-html-site-styled-gh-pages/* /var/www/html
# provide the permission to execute
RUN chmod +x /var/www/html
# now start the httpd service
CMD apachectl -DFOREGROUND

```
<img width="718" alt="image" src="https://user-images.githubusercontent.com/103237142/190540869-9d255c96-4ec2-4d3e-ad6d-eed91f99a852.png">

ENV:
----------------
ENV sets the environment variables for the subsequent instructions in the build stage. Consider the below example where we define the environment variable workdirectory and we used that later with $. There are two forms: single and multiple values

<img width="274" alt="image" src="https://user-images.githubusercontent.com/103237142/190541118-f3cac806-304e-4d1e-a75a-ef16a102185b.png">

- To supply environment variables to the image; aka runtime variables
- ARG is compile time variable, ENV is runtime variable
- ENV values can be overridden when starting a container using -e flag or –env

![image](https://user-images.githubusercontent.com/103237142/190541270-2be10ece-24f2-4017-a5dd-a1f039cb9967.png)

![image](https://user-images.githubusercontent.com/103237142/190541288-1cd36ac4-46d7-40f7-aa78-1277a55fe8c4.png)

![image](https://user-images.githubusercontent.com/103237142/190541301-39aede6e-c20e-4969-96fa-34a969543bc6.png)

**Task:**

```
FROM ubuntu
RUN apt-get update && apt-get install -y curl apache2 unzip
# environment variable
# ENV VAR_NAME VAR_VALUE and it is referenced using $VAR_NAME
ENV HTML beginner-html-site-styled
ADD https://github.com/mdn/$HTML/archive/refs/heads/gh-pages.zip /var/www/html/mypage.zip
# since the code is zip, so unzip and copy in directory- download unzip and move the code to source directory
# here * means all files
# summary: download from github as zip >> unzip it >> move to source folder
RUN cd /var/www/html/ && unzip mypage.zip && mv /var/www/html/$HTML-gh-pages/* /var/www/html
RUN echo $HTML > /var/www/html/env.html
# provide the permission to execute
RUN chmod +x /var/www/html
# now start the httpd service
CMD apachectl -DFOREGROUND

```

<img width="835" alt="image" src="https://user-images.githubusercontent.com/103237142/190544659-78de1892-2228-45dd-8d62-9dba947cfc46.png">

<img width="807" alt="image" src="https://user-images.githubusercontent.com/103237142/190544699-64471cd4-0ab1-46ff-b37a-94b54051ab7a.png">



