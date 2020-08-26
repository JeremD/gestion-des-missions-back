pipeline {
    agent any
    tools {
        maven 'Maven 3.6.3'
    }
    stages {
        stage('compile') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
