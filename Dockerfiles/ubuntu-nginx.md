#Basic ubuntu image with nginx and neovim installed

```Dockerfile
FROM ubuntu:24.04
ARG DEDIAN_FRONTEND=noninteractive
WORKDIR /nginx

#RUN commands
RUN apt-get update && apt-get upgrade
RUN apt-get install --no-install-recommends -y \
iputils-ping \
nginx \
noevim
RUN apt-get clean \
&& rm -rf /var/lib/apt/lists/* 
 
ENTRYPOINT ["nginx", "-g", "daemon off;"]

#CMD commands
#CMD [ ""]
```
You can run the image with the command *```docker run -dp 8080:80 IMAGE-NAME```*
The -dp command stand for d=detach meaning run in the background and p stand for port meaning port mapping internal port 8080 mapped to external  port 80.

run the command *```docker exec -it CONTAINER ID bash```* to connect to the containers bash terminal