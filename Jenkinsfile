pipeline {
environment {
DOCKER_ID = "anthony086"
MOVIE_IMAGE="app-movie_service"
CAST_IMAGE="app-cast_service"
DOCKER_PASS=credentials("DOCKER_HUB_PASS")


}
    agent any

    stages {
        stage("Docker Build") {
            steps {
                script {
                sh '''
                cd /home/ubuntu/jenkins-Exam/app
                docker compose up -d               
                "printenv"
                '''
                }
            }
        }
        stage("Docker push") {
            steps {
                script {
                sh 
                '''
                docker login -u ${DOCKER_ID} -p ${DOCKER_PASS}
                docker tag ${MOVIE_IMAGE} ${DOCKER_ID}/${MOVIE_IMAGE}
                docker tag ${MOVIE_IMAGE} ${DOCKER_ID}/${MOVIE_IMAGE}
                docker image push ${DOCKER_ID}/${MOVIE_IMAGE}:latest
                docker tag ${CAST_IMAGE} ${DOCKER_ID}/${CAST_IMAGE}
                docker tag ${CAST_IMAGE} ${DOCKER_ID}/${CAST_IMAGE}
                docker image push ${DOCKER_ID}/${CAST_IMAGE}:latest
                '''
                }
            }
        }
    }
}