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
                     discordSend description: "${env.GIT_COMMIT}", footer: "${env.BUILD_NUMBER} of Jérémy", image: '', link: "${env.BUILD_URL}", result: 'FAILURE', thumbnail: '', title: "${env.JOB_NAME}, ${env.GIT_BRANCH}", webhookURL: "https://discordapp.com/api/webhooks/747819422705778738/dHWPHidlNLpiiKftWU84__Ss2LAkws77Swfdk5OWs22qla3hlI1B4zywW8ROg4nAwjRM"
                }
                success {
                    discordSend description: "${env.GIT_COMMIT}", footer: "${env.BUILD_NUMBER} of Jérémy", image: '', link: "${env.BUILD_URL}", result: 'SUCCESS', thumbnail: '', title: "${env.JOB_NAME}, ${env.GIT_BRANCH}", webhookURL: "https://discordapp.com/api/webhooks/747819422705778738/dHWPHidlNLpiiKftWU84__Ss2LAkws77Swfdk5OWs22qla3hlI1B4zywW8ROg4nAwjRM"
                }
            }
        }
    }
}
