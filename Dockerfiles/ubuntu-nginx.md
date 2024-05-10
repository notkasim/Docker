#Basic ubuntu image with nginx and neovim installed

```Dockerfile
FROM ubuntu:24.04
ARG DEDIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get upgrade
RUN apt-get install --no-install-recommends -y nginx
RUN apt-get install --no-install-recommends -y neovim \
&& apt-get clean \
&& rm -rf /var/lib/apt/lists/*

ENTRYPOINT [ "nginx", "-g", "daemon off;" ]
```
#FROM ubuntu/bind9