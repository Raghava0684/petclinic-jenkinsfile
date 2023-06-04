pipeline {
    agent any
    
    tools {
        jdk 'jdk11'
        maven 'maven3'
    }
 
    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Raghava0684/Petclinic-project.git'
            }
        }
        
        stage('Mvn compile') {
            steps {
                sh 'mvn compile'
            }
        }
        
        stage('Mvn package') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Deploy To Tomcat Server') {
            steps {
                sh 'cp target/*.war /opt/apache-tomcat-9.0.65/webapps/'
            }
        }
    }
}
