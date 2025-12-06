pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker_creds') {
                        sh 'docker build -t kishorevusa/adservice:latest .'
                    }
                }
            }
        }
        stage("Push") {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker_creds') {
                        sh 'docker push kishorevusa/adservice:latest'
                    }
                }
            }
        }
    }
}
