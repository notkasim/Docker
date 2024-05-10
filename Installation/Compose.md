# Docker Compose
Docker Compose is a tool that helps you define and share multi-container applications. With Compose, you can create a YAML file to define the services and with a single command, you can spin everything up or tear it all down.

The big advantage of using Compose is you can define your application stack in a file, keep it at the root of your project repository (it's now version controlled), and easily enable someone else to contribute to your project. Someone would only need to clone your repository and start the app using Compose. The default path for a Compose file is compose.yaml that is placed in the working directory.

    docker/
    ├── compose.yaml
    ├── Dockerfile
    └── html
        └── index.html*

Compose simplifies the control of your entire application stack, making it easy to manage services, networks, and volumes in a single, comprehensible YAML configuration file. Then, with a single command, you create and start all the services from your configuration file.

*It also has commands for managing the whole lifecycle of your application:*
- Start, stop, and rebuild services
- View the status of running services
- Stream the log output of running services
- Run a one-off command on a service

You  interact with your Compose application through the Compose CLI. Commands such as ```docker compose up``` are used to start the application, while ```docker compose down``` stops and removes the containers.

## Install Docker Compose Standalone
### Linux (Ubuntu 24.04 LTS)
> [!NOTE]
> Here is the official link to the Docker compose standalone installation guide: [Docker Compose](https://docs.docker.com/compose/install/standalone/)

> Note that Compose standalone uses the docker-compose syntax. 

> For example type ```docker-compose up``` when using Compose standalone

1. *To download and install Compose standalone, run:*
```
curl -SL https://github.com/docker/compose/releases/download/v2.27.0/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
```

2. *Apply executable permissions to the standalone binary in the target path for the installation, run:*
```
sudo chmod 755 /usr/local/bin/docker-compose && sudo chmod 755 /usr/local/bin/docker-composecurl
```

3. *Test and execute compose commands using docker-compose.*


### Windows 
Follow these instructions if you are running the Docker daemon and client directly on Microsoft Windows Server and want to install Docker Compose.

1. *Run PowerShell as an administrator. When asked if you want to allow this app to make changes to your device, select Yes in order to proceed with the installation.*

2. *GitHub now requires TLS1.2. In PowerShell, run the following:*
```
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
```

3. *Run the following command to download the latest release of Compose (v2.27.0):*
``` 
Start-BitsTransfer -Source "https://github.com/docker/compose/releases/download/v2.27.0/docker-compose-windows-x86_64.exe" -Destination $Env:ProgramFiles\Docker\docker-compose.exe
```




