# Docker Installation

[Official Installation](https://docs.docker.com/engine/install/rhel/)

## Install using the rpm repository

Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.

## Set up the repository

Install the `yum-utils` package (which provides the `yum-config-manager` utility) and set up the repository.

```
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo
```

## Install Docker Engine

1. Install Docker Engine, containerd, and Docker Compose:

   To install the latest version, run:
   ```
   sudo yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
   ```
   



