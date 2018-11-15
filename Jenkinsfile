/* sintaxis declarativa */
pipeline {
    agent any 
    tools{
        maven 'Maven Test'
    }
    stages {
        stage('Build') {
            steps{
                echo 'building.....'
                sh 'mvn --version'
                sh 'mvn compile'
                
            }
        }
        stage('Test') {
            steps{
                echo 'testing....'
            }
        }
        stage('Deploy') {
            steps{
                echo 'deploying....'
            }
        }
    }
    
}
