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

