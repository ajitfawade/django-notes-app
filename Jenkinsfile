pipeline {
    agent any
    
    stages {
        stage("Code") {
            steps{
                echo "Cloning the code"
                git url:"https://github.com/ajitfawade/django-notes-app.git", branch: "main"
            }
        }
        stage("Build") {
            steps{
                echo "Building the code"
                sh "docker build . -t my-notes-app"
            }
        }
        stage("Push to Docker Hub") {
            steps{
                echo "Pushing the image to Docker Hub"
                withCredentials([usernamePassword(credentialsId: "dockerhub", passwordVariable: "dockerHubPass", usernameVariable: "dockerHubUser")]) {
                    sh "docker tag my-notes-app ${env.dockerHubUser}/my-notes-app:latest"
                    sh "docker login -u ${env.dockerHubUser} -p ${dockerHubPass}"
                    sh "docker push ${env.dockerHubUser}/my-notes-app:latest"
                }
            }
        }
        stage("Deploy") {
            steps{
                echo "Deploying the container"
                sh "docker-compose down"
                sh "docker-compose up -d"
            }
        }
        
    }
}
