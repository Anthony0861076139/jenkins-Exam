pipeline {
    agent any

    stages {
        stage("Liora Variables") {
            steps {
                script {
                sh '''
                kubectl get namespaces 
                sh "printenv"
                '''
            }
        }
    }
}
