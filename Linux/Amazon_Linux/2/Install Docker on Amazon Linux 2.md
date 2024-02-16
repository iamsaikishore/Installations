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


 
