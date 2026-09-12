pipeline {
    agent any

    stages {
        stage("Liora Variables") {
            steps {
                kubectl get namespaces 
                sh "printenv"
            }
        }
    }
}
