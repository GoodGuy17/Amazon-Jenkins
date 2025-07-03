pipeline {
    agent any
tools {
    maven 'Apache Maven 3.6.3'
    jdk 'JDK 11'     
}

   

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/GoodGuy17/Amazon-Jenkins.git'

            }
        }

        stage('Clean') {
            steps {
                echo 'Running: mvn clean'
                sh 'mvn clean'
            }
        }

        stage('Compile') {
            steps {
                echo 'Running: mvn compile'
                sh 'mvn compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running: mvn test'
                sh 'mvn test'
            }
        }

        stage('Install') {
            steps {
                echo 'Running: mvn install'
                sh 'mvn install'
            }
        }
    }

    post {
        success {
            echo '✅ Build completed successfully!'
        }
        failure {
            echo '❌ Build failed.'
        }
    }
}
