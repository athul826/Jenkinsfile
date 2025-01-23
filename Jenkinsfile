pipeline {
    agent {label 'slave-1-node'}
    stages {
        stage ('git checkout') {
            steps {
                echo "continous downloading"
                git 'https://github.com/athul826/Jenkinsfile.git'
            }
        }
    }
}