pipeline{
    agent any
    
    tools{
        maven 'M387'
    }
    stages{
        stage('echo version'){
            steps{
                sh 'echo maven version is:'
                sh 'mvn -version'
            }
        }
        
        stage('Build'){
            steps{
                git branch: 'main', url: 'https://github.com/sidd-harth/jenkins-hello-world.git'
                sh 'mvn clean package -DskipTests=True' 
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
    }
}