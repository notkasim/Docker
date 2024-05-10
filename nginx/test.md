- [Compose]
    - [] Creates an nginx image
    - [] Port 443:80 exposed
    - [] Creates a volumes that
    - [] Edit the html file and see changes

Dockerfile
-[] Creates an ubuntu container running nginx
    - [] creates test "testfile" in the /root
    - [] delete the default index file and replaces it
    - [] creates a virtualhost named "virtualhost1" in the /etc/nginx/conf.d
    - [] sendes the container to the background
    - [] The webserver can be reaches on port 10.0.0.200:8080


    FROM ubuntu:latest

ARG DEBIAN_FRONTEND=noninteractive

RUN apt update -y \
&& apt upgrade -y \
&& apt install nginx -y \
&& touch /root/workingrun \
&& rm /var/www/html*

COPY /nginx/virtualhost1 /etc/nginx/conf.d/virtualhost1
COPY /nginx/html/index.html /var/www/html/index.html

EXPOSE 8080
ENTRYPOINT [ "nginx" "-g" "daemon off" ]


#WEBSITE1
server {
                listen 80;
                listen [::]:80;
                server_name www.web1.hudds.se;  #Domain name of the website
                root /var/www/websida1/html;
                index index.html;

                location / {
                                try_files $uri $uri/ =404;
                }
}