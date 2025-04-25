pipeline {
    agent any

    environment {
        // Append to PATH correctly on Windows
        PATH+EXTRA = "C:\\Program Files\\Apache\\Maven\\bin;C:\\Program Files\\Java\\jdk-17\\bin"
    }

    stages {
        stage('Pull') {
            steps {
                git branch: 'main', url: 'https://github.com/Hanamant001/Amazon-Jenkins.git'
            }
        }

        stage('Compile') {
            steps {
                bat 'mvn compile'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }
    }

    post {
        success {
            echo 'Build success'
        }
        failure {
            echo 'Failure in the build'
        }
    }
}
