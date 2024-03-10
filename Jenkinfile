pipeline {
    agent any
    stages {
        stage('git clone') {
            steps {
                script {
                    echo cloning git repo for app base
                    git clone https://github.com/dhana0803/node.js
                    ls
                    cd node.js
                }
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-hub') {
                        echo builing the dockerfile
                        docker build -d -t nodeapp:latest
                        echo pushing the docker image to docker hub
                        docker push    
                }
            }
        }
    }
}
}
