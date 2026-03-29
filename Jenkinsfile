pipeline {
    agent any
    stages {
        stage('Download') {
            steps {
                echo "Download Code from Github"
                git branch: 'main', url: 'https://github.com/vdgupta324/maven-jenkins10.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                echo "Build the application docker image and push to Docker Hub"
                sh '''docker build -t vinay/java-webapp:v${BUILD_NUMBER} .
                docker tag vinay/java-webapp:v${BUILD_NUMBER} vinay/java-webapp:latest
                docker push vinay/java-webapp:v${BUILD_NUMBER}
                docker push vinay/java-webapp:latest
                '''
            }
        }
    }
}
