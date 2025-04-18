# Jenkins Installation Guide for Ubuntu

## Prerequisites
- Ubuntu 20.04/22.04 LTS
- Java JDK 11 or 17
- Minimum 2GB RAM (4GB recommended)
- 10GB disk space

## Installation Steps

1. Update system packages:
   sudo apt update && sudo apt upgrade -y

2. Install Java (OpenJDK 11):
   sudo apt install openjdk-11-jdk -y

3. Verify Java installation:
   java -version

4. Add Jenkins repository and key:
   curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
     /usr/share/keyrings/jenkins-keyring.asc > /dev/null
   echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
     https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
     /etc/apt/sources.list.d/jenkins.list > /dev/null

5. Install Jenkins:
   sudo apt update
   sudo apt install jenkins -y

6. Start Jenkins service:
   sudo systemctl start jenkins
   sudo systemctl enable jenkins

7. Check Jenkins status:
   sudo systemctl status jenkins

8. Open firewall (if enabled):
   sudo ufw allow 8080
   sudo ufw enable
   sudo ufw status

9. Get initial admin password:
   sudo cat /var/lib/jenkins/secrets/initialAdminPassword

10. Access Jenkins in your browser:
    http://your-server-ip:8080

11. Follow the setup wizard to complete installation:
    - Paste the admin password
    - Install suggested plugins
    - Create admin user
    - Configure instance URL

## Post-Installation Recommendations
- Install recommended plugins like Git, Pipeline, Blue Ocean
- Configure security settings
- Set up backup for Jenkins home directory
- Configure email notifications