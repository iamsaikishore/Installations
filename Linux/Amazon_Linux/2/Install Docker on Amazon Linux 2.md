## Installing Docker on Amazon Linux 2

The procedure to install Docker on AMI 2 (Amazon Linux 2) running on either EC2 or Lightsail instance is as follows:

1. Login into remote AWS server using the ssh command:
   ```
   ssh ec2-user@ec2-ip-address-dns-name-here
   ```

2. Apply pending updates using the yum command:
   ```
   sudo yum update
   ```

3. Search for Docker package:
   ```
   sudo yum search docker
   ```

4. Get version information:
   ```
   sudo yum info docker
   ```

![Searching-for-Docker-package-on-Amazon-Linux-2-AM](https://github.com/iamsaikishore/Installations/assets/129657174/87473869-643a-49f4-a5fc-876f0fb0f129)

5. Install docker, run:
   ```
   sudo yum install docker
   ```

![Installing-Docker-on-Amazon-Linux-2-AMI-using-yum-command](https://github.com/iamsaikishore/Installations/assets/129657174/c175760c-aec8-4c38-9af2-d3001d641328)

6. Add group membership for the default ec2-user so you can run all docker commands without using the sudo command:
   ```
   sudo usermod -a -G docker ec2-user
   id ec2-user
   # Reload a Linux user's group assignments to docker w/o logout
   newgrp docker
   ```

7. Need docker-compose too? Try any one of the following command:
   ```
   # 1. Get pip3 
   sudo yum install python3-pip
 
   # 2. Then run any one of the following
   sudo pip3 install docker-compose # with root access
 
   # OR #
 
   pip3 install --user docker-compose # without root access for security reasons
   ```

   OR

   ```
   wget https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) 
   sudo mv docker-compose-$(uname -s)-$(uname -m) /usr/local/bin/docker-compose
   sudo chmod -v +x /usr/local/bin/docker-compose
   ```

