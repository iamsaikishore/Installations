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


   
