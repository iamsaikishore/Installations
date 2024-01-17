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

   If prompted to accept the GPG key, verify that the fingerprint matches `060A 61C5 1B55 8A7F 742B 77AA C52F EB6B 621E 9F35`, and if so, accept it.

   This command installs Docker, but it doesn't start Docker. It also creates a `docker` group, however, it doesn't add any users to the group by default.

2. Start Docker.
   ```
   sudo systemctl start docker
   ```

3. Verify that the Docker Engine installation is successful by running the `hello-world` image.

   ```
   sudo docker run hello-world
   ```

   This command downloads a test image and runs it in a container. When the container runs, it prints a confirmation message and exits.

You have now successfully installed and started Docker Engine.
   



