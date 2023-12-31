Link : https://www.jenkins.io/download/
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

# OR

Connect to instance and execute following commands.
```
# Become a root
sudo su -

# Jenkins repo is added to yum.repos.d
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo

# Import key from Jenkins
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

# Install Java-11
amazon-linux-extras install java-openjdk11 -y

# Install Jenkins
yum install jenkins -y
```

Start Jenkins.
```
# Become a root, no need to execute if you are alread root.
sudo su -

# You can enable the Jenkins service to start at boot with the command:
systemctl enable jenkins

# You can start the Jenkins service with the command:
systemctl start jenkins

# You can check the status of the Jenkins service using the command:
systemctl status jenkins
```
Open Web-Browser and access jenkins on port 8080. `http://<Public-IPv4-address>:8080/`
