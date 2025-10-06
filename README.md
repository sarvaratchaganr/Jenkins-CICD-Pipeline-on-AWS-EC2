# Jenkins-CICD-Pipeline-on-AWS-EC2

## Project Description
Set up Jenkins on EC2 to automate CI/CD for a Python Flask application.

## Features
- Jenkins installed on EC2  
- GitHub integration  
- Pipeline as code using Jenkinsfile  

## Prerequisites
- AWS EC2 instance (Ubuntu 22.04)  
- Git & GitHub account  
- Docker installed (optional)  

## Installation Commands
SSH into EC2:
```ssh -i your-key.pem ubuntu@<EC2_PUBLIC_IP>```

## Install Java & Jenkins:
```
sudo apt update -y
sudo apt install openjdk-11-jdk -y

wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
/usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt update
sudo apt install jenkins -y
sudo systemctl start jenkins
sudo systemctl enable jenkins
```
## Connectivity Commands
- Get initial admin password:
- sudo cat /var/lib/jenkins/secrets/initialAdminPassword

## Access Jenkins:
http://<EC2_PUBLIC_IP>:8080

## How to Run / Access
- Login with admin password

## Create pipeline job using Jenkinsfile
- Pipeline builds Flask app and Docker image

## Next Steps / Improvements
- Deploy Docker image to ECS
- Add unit tests and code coverage
- Add notifications (Slack/Email)
