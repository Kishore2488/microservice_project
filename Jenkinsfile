pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-0', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://98F21B4F861097B6B954AE20B63FBB3D.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-0', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://98F21B4F861097B6B954AE20B63FBB3D.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
