# Debian/Ubuntu

On Debian and Debian-based distributions like Ubuntu you can install Jenkins through apt.

* With the release of Debian 12, OpenJDK 11 is no longer included. It has been replaced with OpenJDK 17, which is reflected in the instructions below.

## Long Term Support release

A [LTS (Long-Term Support)](https://www.jenkins.io/download/lts/) release is chosen every 12 weeks from the stream of regular releases as the stable release for that time period. It can be installed from the [debian-stable apt repository](https://pkg.jenkins.io/debian-stable/).

```
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

##Weekly release

A new release is produced weekly to deliver bug fixes and features to users and plugin developers. It can be installed from the debian apt repository.

```
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

## Installation of Java

Jenkins requires Java to run, yet not all Linux distributions include Java by default. Additionally, [not all Java versions are compatible](https://www.jenkins.io/doc/book/platform-information/support-policy-java/) with Jenkins.

There are multiple Java implementations which you can use. [OpenJDK](https://openjdk.org/) is the most popular one at the moment, we will use it in this guide.

Update the Debian apt repositories, install OpenJDK 17, and check the installation with the commands:

```
sudo apt update
sudo apt install fontconfig openjdk-17-jre
java -version
openjdk version "17.0.8" 2023-07-18
OpenJDK Runtime Environment (build 17.0.8+7-Debian-1deb12u1)
OpenJDK 64-Bit Server VM (build 17.0.8+7-Debian-1deb12u1, mixed mode, sharing)
```

## Start Jenkins

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
Active: active (running) since Tue 2018-11-13 16:19:01 +03; 4min 57s ago
```

* If you have a firewall installed, you must add Jenkins as an exception. You must change YOURPORT in the script below to the port you want to use. Port 8080 is the most common.
* ```
  YOURPORT=8080
  PERM="--permanent"
  SERV="$PERM --service=jenkins"

  firewall-cmd $PERM --new-service=jenkins
  firewall-cmd $SERV --set-short="Jenkins ports"
  firewall-cmd $SERV --set-description="Jenkins port exceptions"
  firewall-cmd $SERV --add-port=$YOURPORT/tcp
  firewall-cmd $PERM --add-service=jenkins
  firewall-cmd --zone=public --add-service=http --permanent
  firewall-cmd --reload
  ```
