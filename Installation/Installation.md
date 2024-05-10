# Docker Installation
> [!NOTE]
> Here is the official link to the Docker installation guide: [Docker installation doc](https://docs.docker.com/engine/install/ubuntu/#uninstall-docker-engine)

> If you use ufw or firewalld to manage firewall settings, be aware that when you expose container ports using Docker, these ports bypass your firewall rules. For more information, refer to [docker and ufw](https://docs.docker.com/network/packet-filtering-firewalls/#docker-and-ufw)

## Linux (Ubuntu 24.04 LTS)
#### Uninstall old verisons

Before you install Docker Engine, you need to uninstall any conflicting packages. Distro maintainers provide unofficial distributions of Docker packages in APT. You must uninstall these packages before you can install the official version of Docker Engine.

The unofficial packages to uninstall are:
- ```docker.io```
- ```docker-compose```
- ```docker-compose-v2```
- ```docker-doc```
- ```podman-docker```

Run the following command to uninstall all conflicting packages:

```apt
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done
```

Images, containers, volumes, and networks stored in ```/var/lib/docker/``` aren't automatically removed when you uninstall Docker. If you want to start with a clean installation, and prefer to clean up any existing data delete the directories ```/var/lib/docker``` ```/var/lib/containerd```


### Install Docker Engine from Docker's apt repository

Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.

1. *Set up Docker's apt repository.*

```apt
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```
___________________________________________________

2. *Install the Docker packages*

To install the latest version, run:
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
___________________________________________________

3. *Verify that the Docker Engine installation is successful by running the hello-world image*

> [!TIP]
> The docker user group exists but contains no users, which is why you’re required to use sudo to run Docker commands.
> Add your user to the docker group inorder to run docker command without sudo.
```sudo usermod -aG docker $USER``` 

```docker run hello-world```

This command downloads a test image and runs it in a container. When the container runs, it prints a confirmation message and exits.

___________________________________________________

#### Upgrade Docker Engine

To upgrade Docker Engine, follow step 2 of the installation instructions, choosing the new version you want to install.
___________________________________________________

#### Uninstall the Docker Engine

```
sudo apt-get purge docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin docker-ce-rootless-extras
```

Images, containers, volumes, or custom configuration files on your host aren't automatically removed. To delete all images, containers, and volumes run:

```
sudo rm -rf /var/lib/docker
sudo rm -rf /var/lib/containerd
```
___________________________________________________
