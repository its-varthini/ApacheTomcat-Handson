**Pre-requisite**

Ubuntu machine with Jenkins and Docker installed.


**TO ISNTALL SONARQUBE USING DOCKER RUN BELOW COMMAND**  
```
docker run -d --name sonar -p 9000:9000 sonarqube:lts-community
```
**To configure sonarqube in jenkins follow bellow steps**
1) download all the below plugins in jenkins

   plugin SonarQube Scanner

   Sonar Quality GatesVersion

   Eclipse Temurin installer (jdk17)

   Maven Integration plugin (maven3)

2) Tools configure : jdk , sonarscanner , maven

3)system configuration : Do the SonarQube installations in system configuration section.This need a token generated from sonarQube server for accessing it from jenkins.

