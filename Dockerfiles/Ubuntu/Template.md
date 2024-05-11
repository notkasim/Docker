# Ubuntu Dockerfile Template
# Just core Stuff 

```Dockerfile
FROM ubuntu:24.04
ARG DEDIAN_FRONTEND=noninteractive
WORKDIR /DIRECTORY-PATH

#RUN commands
RUN apt-get update && apt-get upgrade
RUN apt-get install --no-install-recommends -y \
iputils-ping \
neovim \
PACKAGE-NAME \
PACKAGE-NAME
RUN apt-get clean \
&& rm -rf /var/lib/apt/lists/* 

#COPY commands
COPY SOURCE /DESTINATION
 
ENTRYPOINT ["bash"]

#CMD commands
#CMD [ "executable"]
```