pipeline {
    agent any

    tools {
        maven 'maven-3.9.9'
        jdk 'jdk-11'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Ml1727/my-mvn-app.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo '🎉 Build succeeded!'
        }
        failure {
            echo '❌ Build failed.'
        }
    }
}


  
