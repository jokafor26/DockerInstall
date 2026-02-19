# DockerInstall

Install Docker on RHEL Linux

In this lab I’m going to install Docker in Redhat Linux. Docker is an open-source tool that allows developers to deploy their applications in a container to run on a host operating system like Linux.

Pre-req Amazon Web Services, Dockerhub 

After downloading doing the docker installation I tested it by running the docker run hello-world command. I get the notification that my installation is working correctly. 
 
![Image](https://github.com/user-attachments/assets/72cb9793-4b48-4139-b090-7898d9da5484)

I then ran the Busybox container by using the docker pull busybox command which would get the image from the docker registry and saves it in my system which I would then see what images are in my system by using the docker images command.  I then used the docker run busybox command but nothing happens because I didn’t provide a utility, so it came out empty. By using the docker run busybox echo “hello from busybox” command I was able to run echo command in the container which shows the image.
 
![Image](https://github.com/user-attachments/assets/9ac579ba-44e7-4133-9420-abd057b4fc6f)

Using the docker ps command I could see what containers are running which is why the docker runs to fast. No containers are running but I could use docker ps -a so I could see the status column and see the container I ran few minutes ago. I could also run the docker run -it busybox sh command to see what I have in my container also.

 ![Image](https://github.com/user-attachments/assets/c6faa9b4-aa1d-47a7-87a7-7d99c7114677)

I could also delete containers by using the docker rm command. I used docker rm 305297d7a235 ff0a5c3750b9 and shows no container. I could also use the docker container prune to achieve the same results.
 
![Image](https://github.com/user-attachments/assets/c3871daa-07c7-44ff-8a03-778fd230838a)

Now I’m going to try to run a static website. First, I would run the docker run –rm -it prakhar1989/static-site command. which shows there isn’t no image found. Then I would use the detached mode by using the docker run -d -P –name static-site prakhar1989/static-site e61d12292d69556eabe2a44c16cbd54486b2527e2ce4f95438e504afb7b02810 command.  -d would do the detachment and p will publish all exposed ports to random ports then the name corresponds to a name I want to give. I could then see the ports by doing the docker port static-site command.

 ![Image](https://github.com/user-attachments/assets/b8da2faa-bb46-4927-a72a-cbf0c4720eb6)

I specified which port to which the client will forward connections to the container by using the docker run -p 8888:80 prakhar1989/static-site command which shows nginx running which is the static site. I then stopped the detatched container by running docker stop static-site command which is the what I used to start the container. 

 ![Image](https://github.com/user-attachments/assets/da408722-9a90-4732-b2d2-cdbd067e0c46)

I tried to make Dockerfile which is a simple text file that contains a list of commands that a docker client calls while making an image, so basically automating the image creation process. I ran into some connection problems error. Also had a syntax error when making sure I had the workdir and python directories. 
 
![Image](https://github.com/user-attachments/assets/c6d014d7-a36c-4e70-ba65-d42085fc8960)
