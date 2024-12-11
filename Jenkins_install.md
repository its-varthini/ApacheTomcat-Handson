## **Ways To Install Jenkins on Windows & Linux**

### **--- INSTALL JENKINS  ON LINUX METHOD -1 ---**

```shell
sudo apt update -y
sudo apt install openjdk-11-jre -y

curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update -y 
sudo apt-get install jenkins -y

sudo systemctl enable jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins

sudo apt-get update -y
sudo apt-get install openjdk-17-jdk -y
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
 sudo apt-get update -y
 sudo apt-get install jenkins -y
 sudo systemctl enable jenkins
 sudo systemctl start jenkins
```
### **--- Change port for JENKINS on ubuntu ---**
```
sudo systemctl stop jenkins
cd /etc/default
vi jenkins # set HTTP_PORT=9090
cd /lib/systemd/system
vi jenkins.service # set PORT = 9090
sudo systemctl daemon-reload
sudo systemctl restart jenkins
sudo systemctl status jenkins
```

### **--- INSTALL JENKINS ON LINUX METHOD -2 ---**

```shell
sudo apt update -y
sudo apt install openjdk-11-jre -y
sudo wget https://updates.jenkins.io/download/war/2.387.3/jenkins.war
java -jar Jenkins.war  --httpPort=8082
```
