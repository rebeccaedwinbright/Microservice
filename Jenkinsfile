pipeline {
    agent any

    stages {
        stage('Deploy to kubernetes') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: ' EKS-1', contextName: '', credentialsId: 'k8', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://6451748EBD03AB2983741EE499E3A2A3.gr7.ap-south-1.eks.amazonaws.com') {
    // some block
                 sh "kubectl apply -f deployment-service.yml"

            }
        }
        
    stage('Verify deployment') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: ' EKS-1', contextName: '', credentialsId: 'k8', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://6451748EBD03AB2983741EE499E3A2A3.gr7.ap-south-1.eks.amazonaws.com') {
    // some block
                 sh "kubectl get all -n webapps"
            }
        }
    }
}
