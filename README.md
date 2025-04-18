# Jenkins Installation Guide for Ubuntu

## Prerequisites
- Ubuntu 20.04/22.04 LTS
- Java JDK 11 or 17
- Minimum 2GB RAM (4GB recommended)
- 10GB disk space

## Installation Steps

1. Update system packages:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
   
2. Install Java (OpenJDK 11):
 ```bash
   sudo apt install openjdk-11-jdk -y
  ```
3. Verify Java installation:
 ```bash
  java -version
 ```
4. Add Jenkins repository and key:
  ```bash
  curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
     /usr/share/keyrings/jenkins-keyring.asc > /dev/null
  ```
```bash
  echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
     https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
     /etc/apt/sources.list.d/jenkins.list > /dev/null
```
5. Install Jenkins:
 ```bash
   sudo apt update
```
```bash
    sudo apt install jenkins -y
```
6. Start Jenkins service:
 ```bash
  sudo systemctl start jenkins
```
```bash
   sudo systemctl enable jenkins
```
8. Check Jenkins status:
```bash
   sudo systemctl status jenkins
 ```
10. Open firewall (if enabled):
 ```bash
    sudo ufw allow 8080
```
```bash
   sudo ufw enable
```
```bash
   sudo ufw status
```
12. Get initial admin password:
 ```bash
 sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
14. Access Jenkins in your browser:
```bash
     http://your-server-ip:8080
```
16. Follow the setup wizard to complete installation:
    - Paste the admin password
    - Install suggested plugins
    - Create admin user
    - Configure instance URL

## Post-Installation Recommendations
- Install recommended plugins like Git, Pipeline, Blue Ocean
- Configure security settings
- Set up backup for Jenkins home directory
- Configure email notifications
