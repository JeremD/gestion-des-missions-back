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
                        discordSend description: '${GIT_COMMIT}', footer: '${BUILD_NUMBER}', image: '', link: '${GIT_BRANCH}', result: 'FAILURE', thumbnail: '', title: '${JOB_NAME}', webhookURL: 'https://discordapp.com/api/webhooks/747819422705778738/dHWPHidlNLpiiKftWU84__Ss2LAkws77Swfdk5OWs22qla3hlI1B4zywW8ROg4nAwjRM'
                    }
                    success {
                        discordSend description: '${GIT_COMMIT}', footer: '${BUILD_NUMBER}', image: '', link: '${GIT_BRANCH}', result: 'SUCCESS', thumbnail: '', title: '${JOB_NAME}', webhookURL: 'https://discordapp.com/api/webhooks/747819422705778738/dHWPHidlNLpiiKftWU84__Ss2LAkws77Swfdk5OWs22qla3hlI1B4zywW8ROg4nAwjRM'
                    }
            }
        }
    }
}
