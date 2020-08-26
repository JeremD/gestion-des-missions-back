pipeline {
    agent any
    tools {
        maven 'Maven 3.6.3'
    }
    stages {
        stage('verify') {
            steps {
                sh 'mvn -v'
            }
        }
        stage('compile') {
            when {
                branch 'master'
            }
            steps {
                sh 'mvn clean package'
            }
            post {
                failure {
                     discordSend description: "${env.GIT_URL} | ${env.GIT_COMMIT}", footer: "#${env.BUILD_NUMBER} - Failure", image: '', link: "${env.BUILD_URL}", result: 'FAILURE', thumbnail: '${AVATAR}', title: "${env.JOB_NAME}, ${env.GIT_BRANCH}", webhookURL: "${WEBHOOK_URL}"
                }
                success {
                    discordSend description: "${env.GIT_URL} | ${env.GIT_COMMIT}", footer: "#${env.BUILD_NUMBER} - Success", image: '', link: "${env.BUILD_URL}", result: 'SUCCESS', thumbnail: '${AVATAR}', title: "${env.JOB_NAME}", webhookURL: "${WEBHOOK_URL}"
                }
            }
        }
    }
}
