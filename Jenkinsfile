pipeline {
    agent any

    stages {
        stage('Kubernetes deployment') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: ' EKS-2', contextName: '', credentialsId: 'k8', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://2600B402B15EF89051AABC40807EEC89.yl4.ap-south-1.eks.amazonaws.com') {
    // some block
             
                    sh "kubectl apply -f deployment-service.yml"
                }
            }
        }
        stage('verify deployment') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: ' EKS-2', contextName: '', credentialsId: 'k8', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://2600B402B15EF89051AABC40807EEC89.yl4.ap-south-1.eks.amazonaws.com') {
    // some block
                  sh "kubectl get all -n webapps"
}
            }
        }
    }
}
