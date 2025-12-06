pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t kishorevusa/service:httpd .'
            }
        }
        stage("Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker_creds') {
                        sh 'docker build -t kishorevusa/service:httpd .'
                }
            }
        }
    }
}
