pipeline {
    agent any
    
    tools {
        maven 'maven3'
     //   jdk 'Java 11'
    }
    
    stages {
        stage('Clone Repository and analysis sonar scanner') {
            steps {
                git branch: 'main', url: 'https://github.com/athul826/spring-petclinic.git'
            }
        }
        
        stage('SonarQube Analysis') {
            steps {
                withCredentials([string(credentialsId: 'sonar-new', variable: 'SONAR_TOKEN')]) {
                    sh '''
                        mvn clean verify sonar:sonar \
                        -Dsonar.projectKey=petclinic \
                        -Dsonar.host.url=http://54.226.254.195:9000 \
                        -Dsonar.login=${SONAR_TOKEN}
                    '''
                }
            }
        }
    }
}