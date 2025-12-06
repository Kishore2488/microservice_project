pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'kishorevusa/productcatalogservice:latest .'
            }
        }
        stage("Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker_creds') {
                        sh 'docker push kishorevusa/productcatalogservice:latest'
                }
            }
        }
    }
}
