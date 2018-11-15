/* sintaxis declarativa 
pipeline {
    agent any
    
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
*/
node{
    checkout scm
    tools{
        maven 'Maven Test'
    }
    stage('Build') {
           
                echo 'building...'
                sh 'maven test'
        }
}
