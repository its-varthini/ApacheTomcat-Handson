pipeline {
    agent any
    
    tools {
        jdk 'jdk17'
        maven 'maven3'
    }
    
    environment {
        SCANNER_HOME=tool 'sonar'
    }
    
    stages {
        stage('Checkout') {
            steps {
                
                git branch: 'main', url: 'https://github.com/its-varthini/Petclinic_devopsShack.git'
            }
        }
        
         stage('compile') {
            steps {
                sh 'mvn clean compile'
            }
        }
         
        stage("Sonarqube Analysis "){
            steps{
                withSonarQubeEnv('sonar') {
                    sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=Petclinic \
                    -Dsonar.java.binaries=. \
                    -Dsonar.projectKey=Petclinic '''
    
                }
            }
        }
        
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

         stage('deploy to nexus') {
            steps {
               
               withMaven(globalMavenSettingsConfig: '17034175-1209-4f5d-a21e-cfc428abf789', jdk: 'jdk17', maven: 'maven3', mavenSettingsConfig: '', traceability: true) {
               sh 'mvn deploy' 
               }
            }
        }
      
       
  }
}
