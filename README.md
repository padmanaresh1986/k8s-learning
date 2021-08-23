**Basic Docker Commands**

Login to docker hub  
>docker login  

Check docker version  
>docker --version  
>docker version  

Run docker container  
>docker run image-name  
>docker container run image-name  

Run docker container with port mapping and Name
>docker run --name app1 -p 5000:5000 image-name  

Run docker container in detached mode  
>docker run -p 5000:5000  -d image-name  

Restart container when docker demon restarts   
>dcoker run  image-name --restart=always  

Run docker container with memory and cpu limits with 512 mb and 5% cpu  
>docker run -m 512m --cpu-quota 5000 image_name  

Watch docker logs and tail logs  
>docker logs container_id  
>docker logs container_id -f  

List all running containers  
>docker container ls  
>docker container ls -a  
>docker ps  
>docker ps -a  
>docker ps -a -q  

Pause unpause container  
>docker container pause container_id  
>docker container unpause container_id  

Connect to Container Terminal  
>docker exec -it container-name /bin/sh

To see more details about container  
>docker container inspect container_id  

Gracefull shutdown or stop docker container  
>docker container stop container_id  

Kill docker container  
>docker container kill container_id  

To remove all stopped containers  
>docker container prune 
>docker rm container-name  

See all images available in local  
>docker images  

To tag existing image with new tag  
>docker tag image_name:version image_name:newversion  

To pull image from docker hub but not run  
>docker pull image_name  

To serach for image in docker search  
>docker search image_name  
>docker serach mysql  

To see layered information of docker image  
>docker image history image_name:tag or image_id  

To see detailed information of docker image  
>docker image inspect image_name:tag or image_id  

Remove Image  
>docker images
>docker rmi  image-id

To watch what events docker performing, run below command in separate terminal and watch   
>docker events  

To see all the processes running in specific container  
>docker top container_id  

To see the statistics of all running containers  
>docker stats  

To see docker demon stats  
>docker system df  

**Create a new Docker Image, Run as Container and Push to Docker Hub**  

This example for creating custom nginx image  

>docker run --name mynginxdefault -p 80:80 -d nginx  
>docker ps  
>docker stop mynginxdefault  

Dockerfile  

>FROM nginx
>COPY index.html /usr/share/nginx/html

Build Docker Image & run it  
>docker build -t your-docker-hub-id/mynginx_image1:v1 .  
>docker run --name mynginx1 -p 80:80 -d your-docker-hub-id/mynginx_image1:v1  

Tag & push the Docker image to docker hub  
>docker tag your-docker-hub-id/mynginx_image1:v1 your-docker-hub-id/mynginx_image1:v1-release
>docker push your-docker-hub-id/mynginx_image1:v1-release







