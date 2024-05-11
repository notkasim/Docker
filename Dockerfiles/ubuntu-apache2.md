Basic ubuntu image with apache2 and neovim installed

```Dockerfile
FROM ubuntu:24.04
ARG DEDIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get upgrade
RUN apt-get install --no-install-recommends -y apache2
RUN apt-get install --no-install-recommends -y neovim \
&& apt-get clean \
&& rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["apache2ctl", "-D", "FOREGROUND"]
```