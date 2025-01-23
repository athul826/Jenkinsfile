pipeline {
    agent {label 'slave-1-node'}
    stages {
        stage ('git checkout') {
            steps {
                echo 'continous downloading'
            }
        }
        stage ('contionus build') {
            steps {
                echo "continous building is happening here"
                sh 'mvn clean package -DskipTests'
            }
        }
        stage ('Test') {
            steps {
                echo "junit test is happening here"
            }
        }
        stage ('application-deploy') {
            steps {
                echo "application deployin on tomcat server"
            }
        }
    }

    post {
        success {
            echo 'pipeline has been successfuly completed!'
        }
        failure {
            echo 'pipleline has been failed.'
        }
    }
}