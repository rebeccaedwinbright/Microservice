pipeline {
    agent any

    stages {
        stage('deploymet') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-cred', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://F085398B364DDDCA216160575683A8F7.sk1.ap-south-1.eks.amazonaws.com') {
                sh "kubectl apply -f deployment-service.yml"
                }
                   
            }
        }
        stage('run') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-cred', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://F085398B364DDDCA216160575683A8F7.sk1.ap-south-1.eks.amazonaws.com') {
                 sh "kubectl get all -n webapps"
               }
            }
        }
    }
}


