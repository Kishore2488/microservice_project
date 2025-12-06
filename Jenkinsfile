pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t kishorevusa/currencyservice:latest .'
            }
        }
        stage("Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker_creds') {
                        sh 'docker push kishorevusa/currencyservice:latest .'
                }
            }
        }
    }
}
