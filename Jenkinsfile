pipeline {
    agent any
    
    tools {
        maven 'M387'
    }

    stages {
        stage('Echo Maven Version') {
            steps {
                sh 'echo Maven version is:'
                sh 'mvn -version'
            }
        }

        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/sidd-harth/jenkins-hello-world.git'
                sh 'mvn clean package -DskipTests=true'
            }
        }

        stage('Test') {
            steps {
                script {
                    try {
                        sh 'mvn test'
                    } catch (Exception e) {
                        echo 'Test stage failed, but continuing pipeline execution...'
                    }
                }
            }
        }
    }
}
