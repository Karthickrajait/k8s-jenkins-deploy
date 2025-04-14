pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/Karthickrajait/k8s-jenkins-deploy.git'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f nginx-deployment.yaml'
            }
        }

        stage('Verify Deployment') {
            steps {
                sh 'kubectl get all -l app=nginx'
            }
        }
    }
}
