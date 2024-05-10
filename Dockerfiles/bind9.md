Basic ubuntu image with apache2 and neovim installed

```Dockerfile
FROM internetsystemsconsortium/bind9:9.18
ARG DEDIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get upgrade
RUN apt-get install --no-install-recommends -y dnsutils 
RUN apt-get install --no-install-recommends -y neovim \
&& apt-get clean \
&& rm -rf /var/lib/apt/lists/*

# Start the Name Service
CMD ["/usr/sbin/named", "-g", "-c", "/etc/bind/named.conf", "-u", "bind"]
```