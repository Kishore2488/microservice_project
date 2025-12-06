pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script{
                    withDockerRegistry(credentialsId: 'docker_creds') {
                        sh 'docker build -t kishorevusa/recommendationservice:latest .'
                    }
                }
            }
        }
        stage("Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker_creds') {
                        sh 'docker push kishorevusa/recommendationservice:latest'
                    }
                }
            }
        }
    }
}
