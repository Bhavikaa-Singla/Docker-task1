1. Install docker and to verify docker has been installed successfully,use --> docker --version
2. Create Dockerfile --> cd myimages/ \
                         vi Dockerfile 
3. Create a Web Page to Serve on Nginx --> mkdir -p ~/docker-nginx/html \
                                           vi index.html \
                                           edit Dockerfile \
4. Build image using dockerfile --> sudo docker build -t mynginximage1 .
5. Run docker image to create container -->  sudo docker run -p 8080:80 -d mynginximage1 \
( -p is for publishing a host’s port to the container's port , 
  -d is for daemon mode i.e. It is used to run the container in detached mode.So that the container can run in the background.)
6. docker volume create my-vol --> To create volume
7. docker run -d --name=nginxtest -v nginx-vol:/usr/share/nginx/html nginx:latest --> To mount a particular directory in host machine as a volume in nginx container.
8. curl http://localhost:8080/ --> To access the nginx container on console \
   http://instance-ip:8080/ --> To access the nginx container in web browser
9. Other useful commands: \
   sudo docker images  --> To check the images that has been created \
   sudo docker ps -a  --> To check the containers that has been created \
   sudo docker container rm <containerid> --> To remove the unwanted containers \
   sudo docker logs <container name> --> To check logs related to particular container \
   sudo docker exec -it <containerid> /bin/bash --> To go inside the container
