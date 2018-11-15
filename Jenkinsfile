/* sintaxis declarativa */
pipeline {
    agent any
    /*checkout scm*/
    stages {
        stage('Build') {
            steps{
                echo 'building.....'
                sh 'mvn package'
                
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
