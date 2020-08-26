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
                     discordSend description: "${env.GIT_URL} | ${env.GIT_COMMIT}", footer: "#${env.BUILD_NUMBER} of Jérémy", image: '', link: "${env.BUILD_URL}", result: 'FAILURE', thumbnail: 'https://avatars3.githubusercontent.com/u/22561974?s=60&u=11c8a998e50f2a7961562cdaceda19fca39947a8&v=4', title: "${env.JOB_NAME}, ${env.GIT_BRANCH}", webhookURL: "https://discordapp.com/api/webhooks/747819422705778738/dHWPHidlNLpiiKftWU84__Ss2LAkws77Swfdk5OWs22qla3hlI1B4zywW8ROg4nAwjRM"
                }
                success {
                    discordSend description: "${env.GIT_URL} | ${env.GIT_COMMIT}", footer: "#${env.BUILD_NUMBER} of Jérémy", image: '', link: "${env.BUILD_URL}", result: 'SUCCESS', thumbnail: 'https://avatars3.githubusercontent.com/u/22561974?s=60&u=11c8a998e50f2a7961562cdaceda19fca39947a8&v=4', title: "${env.JOB_NAME}", webhookURL: "https://discordapp.com/api/webhooks/747819422705778738/dHWPHidlNLpiiKftWU84__Ss2LAkws77Swfdk5OWs22qla3hlI1B4zywW8ROg4nAwjRM"
                }
            }
        }
    }
}
