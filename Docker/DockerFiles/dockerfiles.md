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

WORKDIR:
---------------------
WORKDIR sets the working directory for all the consecutive commands. we can have multiple WORKDIR commands and will be appended with a relative path. Consider the following example where we have two WORKDIR commands leads to /usr/node/app

```
# from base image node
FROM node:8.11-slim

WORKDIR /usr/node
WORKDIR app

RUN pwd

# command executable and version
ENTRYPOINT ["node"]
```

Used to set default working directory for the container. Similar to cd in the container If the directory specified doesn’t exist, it will be created and cd to it

![image](https://user-images.githubusercontent.com/103237142/190837453-7b25a794-d6ee-470c-9452-b371241c57ef.png)

```
FROM ubuntu
RUN apt-get update && apt-get install -y curl apache2 unzip
ENV HTML beginner-html-site-styled
# Workdir=> will CD to this location
WORKDIR /var/www/html/
#ADD https://github.com/mdn/$HTML/archive/refs/heads/gh-pages.zip /var/www/html/mypage.zip
# even this line can be modified
ADD https://github.com/mdn/$HTML/archive/refs/heads/gh-pages.zip ./mypage.zip
# RUN cd /var/www/html/ && unzip mypage.zip && mv /var/www/html/$HTML-gh-pages/* /var/www/html
# RUN echo $HTML > /var/www/html/env.html
# the above line can be rewritten in WORKDIR terms, . means current directory
RUN unzip mypage.zip && mv $HTML-gh-pages/* . && echo $HTML > ./env.html
# provide the permission to execute
RUN chmod +x /var/www/html
# now start the httpd service
CMD apachectl -DFOREGROUND

```

<img width="457" alt="image" src="https://user-images.githubusercontent.com/103237142/190838032-e903789a-85f1-47fa-825b-c667cebfa964.png">

<img width="771" alt="image" src="https://user-images.githubusercontent.com/103237142/190838038-77688267-c0c1-4283-b92e-ab197f747f51.png">

<img width="724" alt="image" src="https://user-images.githubusercontent.com/103237142/190838049-e658cf76-168e-4603-a108-794156f57da9.png">

LABELS
-------------------------
LABEL is used to add some metadata to the image. if we use the same label as the base image and the most recent label value is applied.

Defines name and email of image creator; mention author’s name i.e. it adds metadata to image. It is a key-value pair, to include spaces within label values use quotesand backslash (\) for multiplines It is deprecated , now its called as LABEL

![image](https://user-images.githubusercontent.com/103237142/190838091-fe54d617-ffd7-438f-a484-e58274f6c36b.png)

```

# from base image node
FROM node:8.11-slim
LABEL "about"="This file is just am example to demonstarte the LABEL"
ENV workdirectory /usr/node
WORKDIR $workdirectory
WORKDIR app
COPY package.json .
RUN ls -ll
# command executable and version
ENTRYPOINT ["node"]
```

Note:

```
Going inside of a running container:

$ docker exec -it (interactive) <nameofContainer> bash

Changing ownership:
chown <newuser>:<applicaion> directory -R
```

```
FROM ubuntu
RUN apt-get update && apt-get install -y curl apache2 unzip
LABEL obj=checking_for_ownership
ENV HTML beginner-html-site-styled
WORKDIR /var/www/html/
ADD https://github.com/mdn/$HTML/archive/refs/heads/gh-pages.zip ./mypage.zip
RUN unzip mypage.zip && mv $HTML-gh-pages/* . && echo $HTML > ./env.html
# Add user & Change the file ownership- chown user:group directory -R
RUN useradd apiserver && chown apiserver:apiserver /var/www/html -R
# Switch to the added user
USER apiserver
# remove file we dont need
RUN rm -rf mypage.zip $HTML-gh-pages/
#RUN chmod +x /var/www/html
USER root
CMD apachectl -DFOREGROUND
```

<img width="726" alt="image" src="https://user-images.githubusercontent.com/103237142/191137673-94c917b5-3817-42ce-b64a-2c87802248e7.png">

ARGS
-----------------------
ARG is used to pass some arguments to consecutive instructions and this is only command other than a comment can be used before FROM. We can see ARG usage in the below file and also we can pass that with the build command.

To supply arguments while building image; aka build-time variables; If docker file expects ARG variables but none is provided docker will throw error, to avoid that always give default values ARG values can be inspected after image built by using docker history of that image

It’s value is passed in build command as 

![image](https://user-images.githubusercontent.com/103237142/191140878-0e63dbfe-3175-4809-870e-51189a9a17ba.png)

![image](https://user-images.githubusercontent.com/103237142/191140889-10f24da2-d95d-4d69-b86f-dfc320010312.png)

![image](https://user-images.githubusercontent.com/103237142/191140901-a44dae1c-70e3-41bc-82b0-724b27fccb1e.png)

```
# from base image node
ARG NODE_VERSION=8.11-slim
FROM node:$NODE_VERSION
LABEL "about"="This file is just am example to demonstarte the LABEL"
ENV workdirectory /usr/node
WORKDIR $workdirectory
WORKDIR app
COPY package.json .
RUN ls -ll &&\
    npm install
ADD index.js .
RUN ls -l
# command executable and version
ENTRYPOINT ["node"]
```

```
# basically ARGS can be used to pass dynamic values to docker file
# syntax: ARG <var>=<defaultvalue>-- this is the value used when value is not passed
# its value is referenced as $varName
FROM ubuntu
ARG user=apiserver
RUN apt-get update && apt-get install -y curl apache2 unzip
LABEL obj=checking_for_ownership
ENV HTML beginner-html-site-styled
WORKDIR /var/www/html/
ADD https://github.com/mdn/$HTML/archive/refs/heads/gh-pages.zip ./mypage.zip
RUN unzip mypage.zip && mv $HTML-gh-pages/* . && echo $HTML > ./env.html
# Add user & Change the file ownership- chown user:group directory -R
RUN useradd $user && chown $user:$user /var/www/html -R
# Switch to the added user
USER $user
# remove file we dont need
RUN rm -rf mypage.zip $HTML-gh-pages/
#RUN chmod +x /var/www/html
USER root
CMD apachectl -DFOREGROUND
```

While building dokcer image: `$ docker build -t apache:v1.0 . --buiild-arg <varName>=<value> .`

CMD
---------------------
CMD command is used to give the default commands when the image is instantiated, it doesn’t execute while build stage. There should be only one CMD per Dockerfile, you can list multiple but the last one will be executed.

Command that runs when container starts; used to give default command to be run when starting the container not during image build like RUN. There can be only one CMD instruction per docker file, if you give more than one then only the last CMD will work. We can check the default CMD of an image using docker inspect

<img width="329" alt="image" src="https://user-images.githubusercontent.com/103237142/191148995-fa22704c-dac5-4b1a-a4be-697851bf20d5.png">

```
# from base image node
FROM node:8.11-slim

# command executable and version
CMD ["node","-v"]
CMD ["node"]
```

* Adding a bach file in Dockerfile and execute it

```
#!/bin/bash

echo "starting httpd"
apachectl -DFOREGROUND


# in script file $? means last process status
FROM ubuntu
ARG user=apiserver
RUN apt-get update && apt-get install -y curl apache2 unzip
LABEL obj=checking_for_ownership
ENV HTML beginner-html-site-styled
WORKDIR /var/www/html/
ADD https://github.com/mdn/$HTML/archive/refs/heads/gh-pages.zip ./mypage.zip
RUN unzip mypage.zip && mv $HTML-gh-pages/* . && echo $HTML > ./env.html
RUN useradd $user && chown $user:$user /var/www/html -R
USER $user
RUN rm -rf mypage.zip $HTML-gh-pages/
USER root
# copy my script to / means root
COPY myscript.sh /myscript.sh
# give executable permission for this script
RUN chmod +x /myscript.sh 
CMD /myscript.sh 

```
<img width="767" alt="image" src="https://user-images.githubusercontent.com/103237142/191153663-56419d22-8537-4920-89de-4da4091112da.png">

<img width="765" alt="image" src="https://user-images.githubusercontent.com/103237142/191153872-24b36de7-eea0-40cd-8801-d0293fe74099.png">

Context means current directory

dockerignore
---------------------------
Used to ignore files (in the current context) in the process of making image.

+ create a file .dockerignore
+ Just paste the directory or file names in the .dockerignore file
+ This is will make docker to ignore these directory/files while building images in current context

```
To avoid pop-ups while creating docker image , add in dockerfile

ARG DEBIAN_FRONTEND=noninteractive
```
Creating SSL certificate for Apache i.e. http to https
--------------------------------------------------------

This involves two steps: generate certificate and configure the server

```
openssl req -new -newkey rsa:2048 -days 365 -nodes -x509 -keyout server.key -out server.crt

here replace <server> with any term, like

openssl req -new -newkey rsa:2048 -days 365 -nodes -x509 -keyout mydocker.key -out mydocker.crt

```
Keep on pressing enter till you see `Common Name`, here you have to give IP or DNS name

<img width="676" alt="image" src="https://user-images.githubusercontent.com/103237142/192076634-7b94090d-9ce4-4ac1-94c2-0cc4a5e80462.png">

<img width="377" alt="image" src="https://user-images.githubusercontent.com/103237142/192076647-1a87447b-5617-4a06-a738-e3834e94f1cd.png">

```
FROM ubuntu
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y \
    curl \ 
    apache2 \
    unzip \
    php \
    libapache2-mod-php \
    php-mysql \
    openssl
COPY htmlcode /var/www/html
RUN echo "<?php phpinfo(); ?>" > /var/www/html/page.php  
COPY mydocker.crt /mydocker.crt 
COPY mydocker.key /mydocker.key
COPY ssl.conf /etc/apache2/sites-available/000-default.conf
RUN chmod -R a+rwx /var/www/html/page.php
RUN chmod -R a+rwx /var/www/html 
CMD apachectl -DFOREGROUND
RUN a2enmod ssl 
```

Overwrite virtual host file (.conf)

```
<VirtualHost *:443>
   ServerName 10.0.0.28
   DocumentRoot "/var/www/html"
   SSLEngine on
   SSLCertificateFile /mydocker.crt
   SSLCertificateKeyFile /mydocker.key
</VirtualHost>
```

<img width="674" alt="image" src="https://user-images.githubusercontent.com/103237142/192077820-bc37d0d7-99ab-4947-869e-a5da7cea236b.png">

Now we can access our conatiner with https

<img width="946" alt="image" src="https://user-images.githubusercontent.com/103237142/192077833-c6b61d52-7714-4007-a5fb-23ce8b719d0d.png">

<img width="946" alt="image" src="https://user-images.githubusercontent.com/103237142/192077841-294d02c5-9aaa-43d0-a2a9-ceefc02f907f.png">

Removing incomplete images (dangling images)

`docker images -f dangling=true`

<img width="433" alt="image" src="https://user-images.githubusercontent.com/103237142/192078224-f4b8be22-4b38-4e90-b170-46ea8028cb49.png">

to remove all in one go: `docker rm -f $(docker images -f dangling=true -q`

<img width="523" alt="image" src="https://user-images.githubusercontent.com/103237142/192078325-53e976ac-9497-4cfa-bcdf-43408d00fcb2.png">

Remove all dead containers in one go: `docker rm $(docker ps -a -q)`

<img width="444" alt="image" src="https://user-images.githubusercontent.com/103237142/192109266-53c2c9f2-ef6a-4301-a937-8f240e690a2b.png">


Nginx with php
-------------------------
```
FROM ubuntu
RUN apt-get update && apt-get install -y \
    nginx \
    curl
# Nginx does come with a default configuration file. However, when we have our own
# Nginx configuration file, it’s much easier to maintain it outside of a Docker container.
#Therefore, we are going to create a default config file for Nginx
COPY nginx /etc/nginx/sites-available/default
# expose port
EXPOSE 80/tcp
# Run nginx
# the -g option specifies a directive to nginx
# the daemon off directive will disable the self-daemonizing behavior of nginx
CMD ["/usr/sbin/nginx", "-g", "daemon off;"]
```

nginx

```
server {
    listen 80 default_server;
    listen [::]:80 default_server;
    
    root /usr/share/nginx/html;
    index index.html index.htm;

    server_name _;
    location / {
        try_files $uri $uri/ =404;
    }
}
```

<img width="841" alt="image" src="https://user-images.githubusercontent.com/103237142/192107494-e3c5d20c-5387-472b-b37c-5a7ca2879b93.png">

**Serving custom content html page**

```
FROM ubuntu 
RUN apt-get update && apt-get install -y \
    nginx \
    curl
# Nginx does come with a default configuration file. However, when we have our own 
# Nginx configuration file, it’s much easier to maintain it outside of a Docker container. 
#Therefore, we are going to create a default config file for Nginx 
COPY nginx /etc/nginx/sites-available/default
# custom
COPY fruit /usr/share/nginx/html/
COPY fruit/index.html /usr/share/nginx/html/index.html
RUN chmod 777 -R /usr/share/nginx/html
# expose port
EXPOSE 80/tcp
# Run nginx
# the -g option specifies a directive to nginx
# the daemon off directive will disable the self-daemonizing behavior of nginx
CMD ["/usr/sbin/nginx", "-g", "daemon off;"]

```

Nginx

```
server {
    listen 80 default_server;
    listen [::]:80 default_server;
    
    root /usr/share/nginx/html;
    index index.html index.htm;

    server_name _;
    location / {
        try_files $uri $uri/ =404;
    }
}
```

<img width="953" alt="image" src="https://user-images.githubusercontent.com/103237142/192108859-36e0c2c3-7de6-4b11-9c56-36c3083ad44d.png">

Multistage dockerfile
------------------------------

Multistage builds make use of one Dockerfile with multiple FROM instructions. Each of these FROM instructions is a new build stage that can **COPY artifacts from the previous stages**. By going and copying the build artifact from the build stage, you eliminate all the intermediate steps such as downloading of code, installing dependencies, and testing. All these steps create additional layers, and you want to eliminate them from the final image.

The build stage is named by appending AS name-of-build to the FROM instruction. The name of the build stage can be used in a subsequent FROM and COPY command by providing a convenient way to identify the source layer for files brought into the image build. The final image is produced from the last stage executed in the Dockerfile.

```
FROM node:12.13.0-alpine as build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=build /app/build /usr/share/nginx/html
```

**Bilding maven java project**

```
FROM maven:3-openjdk-18-slim as builder
COPY mvncode /app 
WORKDIR /app
# maven will check pom and download dependencies and jar will be build
RUN mvn package 
```
<img width="474" alt="image" src="https://user-images.githubusercontent.com/103237142/192112091-cef26a7a-e7c8-4a27-9b4b-15392d9adc39.png">

Now we know the path of jar file, thats what is needed for java application

```
# For java maven app
FROM maven:3-openjdk-18-slim as builder
COPY mvncode /app 
WORKDIR /app
# maven will check pom and download dependencies and jar will be build
RUN mvn package 
# stage-2
FROM openjdk:19-jdk-alpine
COPY --from=builder /app/target/my-app-1.0-SNAPSHOT.jar /app.jar
CMD java -jar /app.jar
```

<img width="508" alt="image" src="https://user-images.githubusercontent.com/103237142/192112286-a8e505b5-100d-40e3-b089-c1bc2656b4d4.png">

<img width="546" alt="image" src="https://user-images.githubusercontent.com/103237142/192112373-4c8b2ffa-0e3a-48fd-b5f9-0b6ca989976a.png">

<img width="654" alt="image" src="https://user-images.githubusercontent.com/103237142/192112450-269756b9-0761-4dd5-a8b9-e05fb039e62f.png">

+ Passing envrionment variable for container outside of docker file

`$ docker run -d --name <contname> -e "varName=value"`

Volume
-----------------
VOLUME is used to create a mount point with the specified name.

```
ARG NODE_VERSION=8.11-slim
FROM node:$NODE_VERSION
LABEL "about"="This file is just am example to demonstarte the LABEL"
ENV workdirectory /home/bhargav
RUN mkdir /dockerexample
VOLUME /dockerexample
COPY package.json .
RUN ls -ll &&\
    npm install
RUN useradd bhargav &&\
    mkdir -p $workdirectory &&\
    chown bhargav $workdirectory    
USER bhargav
WORKDIR $workdirectory
ADD index.js .
RUN ls -l
EXPOSE 3070
# command executable and version
ENTRYPOINT ["node"]
```












