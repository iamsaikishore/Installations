# Jenkins Installation

You can install Jenkins through yum on Red Hat Enterprise Linux.

## Long Term Support release

A LTS (Long-Term Support) release is chosen every 12 weeks from the stream of regular releases as the stable release for that time period. It can be installed from the redhat-stable yum repository.

```
sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
sudo yum upgrade
# Add required dependencies for the jenkins package
sudo yum install fontconfig java-17-openjdk
sudo yum install jenkins
sudo systemctl daemon-reload
```

##  Start Jenkins
You can enable the Jenkins service to start at boot with the command:
```
sudo systemctl enable jenkins
```
You can start the Jenkins service with the command:
```
sudo systemctl start jenkins
```
You can check the status of the Jenkins service using the command:
```
sudo systemctl status jenkins
```
If everything has been set up correctly, you should see an output like this:
```
Loaded: loaded (/lib/systemd/system/jenkins.service; enabled; vendor preset: enabled)
Active: active (running) since Tue 2023-06-22 16:19:01 +03; 4min 57s ago
...
```

> If you have a firewall installed, you must add Jenkins as an exception. You must change YOURPORT in the script below to the port you want to use. Port 8080 is 
  the most common.
>
> YOURPORT=8080
> PERM="--permanent"
> SERV="$PERM --service=jenkins"

> firewall-cmd $PERM --new-service=jenkins
> firewall-cmd $SERV --set-short="Jenkins ports"
> firewall-cmd $SERV --set-description="Jenkins port exceptions"
> firewall-cmd $SERV --add-port=$YOURPORT/tcp
> firewall-cmd $PERM --add-service=jenkins
> firewall-cmd --zone=public --add-service=http --permanent
> firewall-cmd --reload
 
