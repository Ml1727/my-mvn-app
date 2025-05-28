pipeline {
    agent any

    tools {
        maven 'maven3.8.7'   // Must match the Maven name in Jenkins tool config
        jdk 'jdk11'          // Must match the JDK name in Jenkins tool config
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
