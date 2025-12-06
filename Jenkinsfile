pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t kishorevusa/emailservice:latest .'
            }
        }
        stage("Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker_creds') {
                        sh 'docker build -t kishorevusa/emailservice:latest .'
                }
            }
        }
    }
}
