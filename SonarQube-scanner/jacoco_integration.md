**Steps to publish Jacoco code coverage to sonarqube using Jenkins** 

add these below code blocks in the pom.xml file after packaging the application the code coverage report will be published to sonarqube.
```
<properties>
 <!-- JaCoCo Properties -->
    <jacoco.version>0.8.11</jacoco.version>
    <sonar.java.coveragePlugin>jacoco</sonar.java.coveragePlugin>
    <sonar.dynamicAnalysis>reuseReports</sonar.dynamicAnalysis>
    <sonar.jacoco.reportPath>${project.basedir}/../target/jacoco.exec</sonar.jacoco.reportPath>
    <sonar.language>java</sonar.language>
    
  </properties>
```
```
<dependency>
     <groupId>org.jacoco</groupId> 
     <artifactId>jacoco-maven-plugin</artifactId>
     <version>0.8.11</version>
</dependency>
```
```
<plugin>
        <groupId>org.jacoco</groupId>
        <artifactId>jacoco-maven-plugin</artifactId>
        <version>${jacoco.version}</version>
        <executions>
          <execution>
            <goals>
              <goal>prepare-agent</goal>
            </goals>
          </execution>
          <execution>
            <id>report</id>
            <goals>
              <goal>report</goal>
            </goals>
            <phase>prepare-package</phase>
          </execution>
        </executions>
</plugin>
```
![alt text](https://github.com/its-varthini/Installation_Setup_Guide/blob/main/SonarQube-scanner/sonarJacoco.png)
