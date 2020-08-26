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

            post {
                    failure {
                        discordSend description: '${env.GIT_COMMIT}', footer: '${env.BUILD_NUMBER}', image: '', link: '${env.GIT_BRANCH}', result: 'FAILURE', thumbnail: '', title: '${env.JOB_NAME}', webhookURL: 'https://discordapp.com/api/webhooks/747819422705778738/dHWPHidlNLpiiKftWU84__Ss2LAkws77Swfdk5OWs22qla3hlI1B4zywW8ROg4nAwjRM'
                    }
                    success {
                        discordSend description: '${env.GIT_COMMIT}', footer: '${env.BUILD_NUMBER}', image: '', link: '${env.GIT_BRANCH}', result: 'SUCCESS', thumbnail: '', title: '${env.JOB_NAME}', webhookURL: 'https://discordapp.com/api/webhooks/747819422705778738/dHWPHidlNLpiiKftWU84__Ss2LAkws77Swfdk5OWs22qla3hlI1B4zywW8ROg4nAwjRM'
                    }
            }
        }
    }
}
