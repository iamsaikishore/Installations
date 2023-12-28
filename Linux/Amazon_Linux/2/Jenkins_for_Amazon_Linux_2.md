### First add the repository
```
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
```
EPEL package is one of the requirement that doesn't unfortunately come with Amazon Linux 2 so we will need to install that by running the command bellow
```
amazon-linux-extras install epel
```
After that, then install Java
```
amazon-linux-extras install java-openjdk11
```
Then proceed finally with Jenkins installation.
```
yum install jenkins
```

