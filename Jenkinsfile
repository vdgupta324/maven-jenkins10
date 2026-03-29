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
                sh '''docker build -t vinaygupta0708/java-webapp:v${BUILD_NUMBER} .
                docker tag vinaygupta0708/java-webapp:v${BUILD_NUMBER} vinaygupta0708/java-webapp:latest
                docker push vinaygupta0708/java-webapp:v${BUILD_NUMBER}
                docker push vinaygupta0708/java-webapp:latest
                '''
            }
        }
    }
}
